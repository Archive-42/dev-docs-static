RTCIceCandidatePairStats.selected
=================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The *non-standard*, Firefox-specific [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) property `selected` indicates whether or not the candidate pair described by the object is the one currently being used to communicate with the remote peer.

Syntax
------

    isSelected = icpStats.selected;

### Value

A Firefox-specific Boolean value which is `true` if the candidate pair described by this object is the one currently in use.

In any other browser, you can determine the selected candidate pair by looking for a stats object of type `transport`, which is an <span class="page-not-created">`RTCTransportStats`</span> object. That object's <span class="page-not-created">`selectedCandidatePairId`</span> property indicates whether or not the specified transport is the one being used.

Example
-------

The function shown in this example identifies the currently-selected candidate pair from a statistics report by first iterating over each report, looking for a `transport` report; when one is found, that transport's <span class="page-not-created">`selectedCandidatePairId`</span> is used to get the [`RTCIceCandidatePair`](../rtcicecandidatepair) describing the connection.

If that fails, then the second section iterates over the reports, looking for a `candidate-pair` record whose Firefox-specific [`selected`](selected) property is `true`. This candidate pair is then returned as the currently-selected one.

    function getCurrentCandidatePair(statsResults) {
      statsResults.forEach(report => {
        if (report.type === "transport") {
          currentPair = statsResults.get(report.selectedCandidatePairId);
        }
      });

      if (!currentPair) {
        statsResults.forEach(report => {
          if (report.type === "candidate-pair" && report.selected) {
            currentPair = report;
          }
        });
      }

      return currentPair;
    }

Specifications
--------------

Not part of any specification. This property is unique to Firefox.

Browser compatibility
---------------------

No compatibility data found for `api.RTCIceCandidatePairStats.selected`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/selected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/selected</a>
