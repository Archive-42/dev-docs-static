MessagePort.close()
===================

The `close()` method of the [`MessagePort`](../messageport) interface disconnects the port, so it is no longer active. This stops the flow of messages to that port.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    port.close()

### Returns

Void.

### Parameters

None.

Example
-------

In the following code block, you can see a `handleMessage` handler function, run when a message is sent back to this document using [`EventTarget.addEventListener`](../eventtarget/addeventlistener).

    channel.port1.addEventListener('message', handleMessage, false);
    function handleMessage(e) {
      para.innerHTML = e.data;
      textInput.value = '';
    }

    channel.port1.start();

You could stop messages being sent at any time using

    channel.port1.close();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#dom-messageport-close">HTML Living Standard<br />
<span class="small">The definition of 'close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`close`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/close</a>
