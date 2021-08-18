MessageChannel.port1
====================

The `port1` read-only property of the [`MessageChannel`](../messagechannel) interface returns the first port of the message channel — the port attached to the context that originated the channel.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    channel.port1;

### Value

A [`MessagePort`](../messageport) object, the first port of the channel, that is the port attached to the context that originated the channel.

Example
-------

In the following code block, you can see a new channel being created using the [`MessageChannel()`](messagechannel) constructor. When the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) has loaded, we pass [`MessageChannel.port2`](port2) to the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) using [`MessagePort.postMessage`](../messageport/postmessage) along with a message. The `handleMessage` handler then responds to a message being sent back from the `<iframe>` (using [`MessagePort.onmessage`](../messageport/onmessage)), putting it into a paragraph. The `handleMessage` method is associated to the `port1` to listen when the message arrives.

    var channel = new MessageChannel();
    var para = document.querySelector('p');

    var ifr = document.querySelector('iframe');
    var otherWindow = ifr.contentWindow;

    ifr.addEventListener("load", iframeLoaded, false);

    function iframeLoaded() {
      otherWindow.postMessage('Hello from the main page!', '*', [channel.port2]);
    }

    channel.port1.onmessage = handleMessage;
    function handleMessage(e) {
      para.innerHTML = e.data;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#dom-messagechannel-port1">HTML Living Standard<br />
<span class="small">The definition of 'port1' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`port1`

4

12

41

10

10.6

5

4.4

18

41

11

5.1

1.0

See also
--------

-   [Using channel messaging](../channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel/port1" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel/port1</a>
