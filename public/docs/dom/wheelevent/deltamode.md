WheelEvent.deltaMode
====================

The `WheelEvent.deltaMode` read-only property returns an `unsigned long` representing the unit of the delta values scroll amount. Permitted values are:

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DOM_DELTA_PIXEL</code></td><td><code>0x00</code></td><td>The delta values are specified in pixels.</td></tr><tr class="even"><td><code>DOM_DELTA_LINE</code></td><td><code>0x01</code></td><td>The delta values are specified in lines.</td></tr><tr class="odd"><td><code>DOM_DELTA_PAGE</code></td><td><code>0x02</code></td><td>The delta values are specified in pages.</td></tr></tbody></table>

Syntax
------

    var unit = event.deltaMode;

Example
-------

    var syntheticEvent = new WheelEvent("syntheticWheel", {"deltaX": 4, "deltaMode": 0});

    console.log(syntheticEvent.deltaMode);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-WheelEvent-deltaMode">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'WheelEvent.deltaMode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deltaMode`

31

12

17

9

18

6.1

≤37

Yes

17

Yes

No

Yes

See also
--------

-   `wheel`
-   [`WheelEvent`](../wheelevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaMode</a>
