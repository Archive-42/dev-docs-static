WheelEvent.deltaZ
=================

The `WheelEvent.deltaZ` read-only property is a `double` representing the scroll amount along the z-axis, in the [`WheelEvent.deltaMode`](deltamode) unit.

Syntax
------

    var dZ = event.deltaZ;

Example
-------

    var syntheticEvent = new WheelEvent("syntheticWheel", {"deltaZ": 4, "deltaMode": 0});

    console.log(syntheticEvent.deltaZ);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-WheelEvent-deltaZ">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'WheelEvent.deltaZ' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deltaZ`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaZ" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/deltaZ</a>
