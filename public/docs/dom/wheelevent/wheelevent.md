WheelEvent()
============

The `WheelEvent()` constructor returns a newly created [`WheelEvent`](../wheelevent) object.

Syntax
------

    var wheelEvent = new WheelEvent(typeArg, wheelEventInit);

### Properties

`typeArg`  
Is a [`DOMString`](../domstring) representing the name of the event.

 `wheelEventInit` <span class="badge inline optional">Optional</span>   
Is a `WheelEventInit` dictionary, having the following fields:

-   `"deltaX"`, optional and defaulting to `0.0`, is a `double` representing the horizontal scroll amount in the `deltaMode` unit.
-   `"deltaY"`, optional and defaulting to `0.0`, is a `double` representing the vertical scroll amount in the `deltaMode` unit.
-   `"deltaZ"`, optional and defaulting to `0.0`, is a `double` representing the scroll amount for the z-axis in the `deltaMode` unit.
-   `"deltaMode"`, optional and defaulting to `0`, is a `unsigned long` representing the unit of the delta values scroll amount. Permitted values are:
    <table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>DOM_DELTA_PIXEL</code></td><td><code>0x00</code></td><td>The delta values are specified in pixels.</td></tr><tr class="even"><td><code>DOM_DELTA_LINE</code></td><td><code>0x01</code></td><td>The delta values are specified in lines.</td></tr><tr class="odd"><td><code>DOM_DELTA_PAGE</code></td><td><code>0x02</code></td><td>The delta values are specified in pages.</td></tr></tbody></table>

The `WheelEventInit` dictionary also accepts fields from the [`MouseEventInit`](../mouseevent/mouseevent), [`UIEventInit`](../uievent/uievent) and [`EventInit`](../event/event) dictionaries.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-WheelEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'WheelEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`WheelEvent`

Yes

≤18

17

No

Yes

6.1

Yes

Yes

17

Yes

No

Yes

See also
--------

-   The [`WheelEvent`](../wheelevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/WheelEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WheelEvent/WheelEvent</a>
