UIEvent()
=========

The `UIEvent()` constructor creates a new [`UIEvent`](../uievent).

Syntax
------

    event = new UIEvent(typeArg [, UIEventInit])

### Values

`typeArg`  
Is a [`DOMString`](../domstring) representing the name of the event.

 `UIEventInit` <span class="badge inline optional">Optional</span>   
Is a `UIEventInit` dictionary, having the following fields:

-   `detail`: optional and defaulting to `0`, of type `long`, that is a event-dependant value associated with the event. [`UIEvent.detail`](detail) lists the semantic for standard events.
-   `view`: optional and defaulting to `null`, of type <span class="page-not-created">`WindowProxy`</span>, that is the [`Window`](../window) associated with the event .
-   `sourceCapabilities`: <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> An instance of the [`InputDeviceCapabilities`](../inputdevicecapabilities) interface which provides information about the physical device responsible for generating a touch event.

The `UIEventInit` dictionary also accepts fields from the [`EventInit`](../event/event) dictionary.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/InputDeviceCapabilities/">InputDeviceCapabilities</a></td><td><span class="spec-draft">Draft</span></td><td>Added <code>sourceCapabilities</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-UIEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'UIEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`UIEvent`

Yes

≤18

11

?

Yes

Yes

Yes

Yes

14

Yes

Yes

Yes

See also
--------

-   [`UIEvent`](../uievent), the interface of the objects it constructs.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/UIEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/UIEvent</a>
