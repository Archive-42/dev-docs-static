MessageChannel()
================

The `MessageChannel()` constructor of the [`MessageChannel`](../messagechannel) interface returns a new [`MessageChannel`](../messagechannel) object with two new [`MessagePort`](../messageport) objects.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    var channel = new MessageChannel();

### Returns

A newly created [`MessageChannel`](../messagechannel) object.

Example
-------

In the following code block, you can see a new channel being created using the [`MessageChannel.MessageChannel`](../messagechannel) constructor. When the IFrame has loaded, we pass `port2` to the IFrame using [`MessagePort.postMessage`](../messageport/postmessage) along with a message. The `handleMessage` handler then responds to a message being sent back from the IFrame (using [`MessagePort.onmessage`](../messageport/onmessage)), putting it into a paragraph. [`MessageChannel.port1`](port1) is listened to, to check when the message arrives.

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

For a full working example, see our [channel messaging basic demo](https://github.com/mdn/dom-examples/tree/master/channel-messaging-basic) on Github ([run it live too](https://mdn.github.io/dom-examples/channel-messaging-basic/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#dom-messagechannel">HTML Living Standard<br />
<span class="small">The definition of 'MessageChannel()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MessageChannel`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel/MessageChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel/MessageChannel</a>
