MessagePort.start()
===================

The `start()` method of the [`MessagePort`](../messageport) interface starts the sending of messages queued on the port. This method is only needed when using [`EventTarget.addEventListener`](../eventtarget/addeventlistener); it is implied when using <span class="page-not-created">`MessageChannel.onmessage`</span>.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    port.start()

### Returns

Void.

### Parameters

None.

Example
-------

In the following code block, you can see a `handleMessage` handler function, run when a message is sent back to this document using `onmessage`:

    channel.port1.onmessage = handleMessage;
    function handleMessage(e) {
      para.innerHTML = e.data;
    }   

Another option would be to do this using [`EventTarget.addEventListener`](../eventtarget/addeventlistener), however, when this method is used, you need to explicitly call `start()` to begin the flow of messages to this document:

    channel.port1.addEventListener('message', handleMessage, false);
    function handleMessage(e) {
      para.innerHTML = e.data;
      textInput.value = '';
    }

    channel.port1.start();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#dom-messageport-start">HTML Living Standard<br />
<span class="small">The definition of 'start()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`start`

4

12

41

10

10.6

5

≤37

18

41

11

5.1

1.0

See also
--------

-   [Using channel messaging](../channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/start</a>
