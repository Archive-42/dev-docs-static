MessageEvent.MessageEvent()
===========================

**Draft**

This page is not complete.

The `MessageEvent()` constructor creates a new [`MessageEvent`](../messageevent) object instance.

Syntax
------

    var messageEvent = new MessageEvent(type, init);

### Parameters

`type`

The type of `MessageEvent` that will be created. This can be one of XXX

`init`<span class="badge inline optional">Optional</span>

A dictionary object that can contain the following properties:

-   `data`: The data you want contained in the MessageEvent. This can be of any data type, and will default to `null` if not specified.
-   `origin`: A [`USVString`](../usvstring) representing the origin of the message emitter. This defaults to an empty string ("") if not specified.
-   `lastEventId`: A [`DOMString`](../domstring) representing a unique ID for the event. This defaults to an empty string ("") if not specified.
-   `source`: An `MessageEventSource` (which can be a <span class="page-not-created">`WindowProxy`</span>, [`MessagePort`](../messageport), or [`ServiceWorker`](../serviceworker) object) representing the message emitter. This defaults to `null` if not set.
-   `ports`: An array of [`MessagePort`](../messageport) objects representing the ports associated with the channel the message is being sent through (where appropriate, e.g. in channel messaging or when sending a message to a shared worker). This defaults to an empty array (`[]`) if not specified.

Example
-------

    var myMessage = new MessageEvent('worker', {
      data : 'hello'
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-event-constructor">HTML Living Standard<br />
<span class="small">The definition of 'MessageEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MessageEvent`

1

12

4

9

?

4

37

18

?

?

3

1.0

See also
--------

-   [`ExtendableMessageEvent`](../extendablemessageevent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/MessageEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/MessageEvent</a>
