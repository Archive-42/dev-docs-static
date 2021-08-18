TimeRanges
==========

When loading a media resource for use by an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, the `TimeRanges` interface is used for representing the time ranges of the media resource that have been buffered, the time ranges that have been played, and the time ranges that are seekable.

A `TimeRanges` object includes one or more ranges of time, each specified by a starting time offset and an ending time offset. You reference each time range by using the `start()` and `end()` methods, passing the index number of the time range you want to retrieve.

Normalized TimeRanges objects
-----------------------------

Several members of [`HTMLMediaElement`](htmlmediaelement) objects return a **normalized TimeRanges object** — which [the spec describes](https://html.spec.whatwg.org/multipage/media.html#normalised-timeranges-object) as having the following characteristics:

*The ranges in such an object are ordered, don't overlap, and don't touch (adjacent ranges are folded into one bigger range). A range can be empty (referencing just a single moment in time).*

Properties
----------

 [`TimeRanges.length`](timeranges/length) <span class="badge inline readonly">Read only </span>   
Returns an `unsigned long` representing the number of time ranges represented by the time range object.

Methods
-------

[`TimeRanges.start()`](timeranges/start)  
Returns the time for the start of the range with the specified index.

[`TimeRanges.end()`](timeranges/end)  
Returns the time for the end of the specified range.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#time-ranges">HTML Living Standard<br />
<span class="small">The definition of 'TimeRanges' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`TimeRanges`

6

12

4

9

≤12.1

3.1

≤37

18

4

≤12.1

2

1.0

`end`

6

12

4

9

≤12.1

3.1

≤37

18

4

≤12.1

2

1.0

`length`

Yes

12

4

9

Yes

3.1

Yes

Yes

4

Yes

2

Yes

`start`

6

12

4

9

≤12.1

3.1

≤37

18

4

≤12.1

2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges</a>
