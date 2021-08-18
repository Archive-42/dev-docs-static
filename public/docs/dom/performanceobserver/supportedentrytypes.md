# PerformanceObserver.supportedEntryTypes

The `supportedEntryTypes` read-only property of the [`PerformanceObserver`](../performanceobserver) interface returns an array of the [`entryType`](../performanceentry/entrytype) values supported by the user agent.

As the list of supported entries varies per browser and is evolving, this property allows web developers to check which are available.

## Syntax

    var supportedEntryTypes = PerformanceObserver.supportedEntryTypes;

### Return value

An array of [`PerformanceEntry.entryType`](../performanceentry/entrytype) values.

## Example

### Using the console to check supported types

To find out which [`entryType`](../performanceentry/entrytype) values a browser supports enter PerformanceObserver.supportedEntryTypes into the console. This will return an array of `EntryType` values.

    PerformanceObserver.supportedEntryTypes

    // returns ["element", "event", "first-input", "largest-contentful-paint", "layout-shift", "longtask", "mark", "measure", "navigation", "paint", "resource"] in Chrome 89

### Checking for unsupported types

The following function checks for support of an array of possible entry types. The unsupported types are logged to the console, however this information could be logged to client-side analytics to indicate that the particular type could not be observed.

    function detectSupport(entryTypes) {
      for (const entryType of entryTypes) {
        if (!PerformanceObserver.supportedEntryTypes.includes(entryType)) {
          console.log(entryType);
        }
      }
    }

    detectSupport(["resource", "mark", "frame"]);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#supportedentrytypes-attribute">Performance Timeline Level 2<br />
<span class="small">The definition of 'PerformanceObserver.supportedEntryTypes' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>PerformanceObserver</code> interface.</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`supportedEntryTypes`

73

≤79

68

No

Yes

12.1

73

73

68

Yes

12.2

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/supportedEntryTypes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/supportedEntryTypes</a>
