WheelEvent.deltaY
=================

The `WheelEvent.deltaY` read-only property is a `double` representing the vertical scroll amount in the [`WheelEvent.deltaMode`](deltamode) unit.

Syntax
------

    var dY = event.deltaY;

Example
-------

    var syntheticEvent = new WheelEvent("syntheticWheel", {"deltaY": 4, "deltaMode": 0});

    console.log(syntheticEvent.deltaY);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-WheelEvent-deltaY">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'WheelEvent.deltaY' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deltaY`

31

12

17

9

IE9 supports an old draft of the spec where this value was a `long` instead of a `double`.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaY</a>
