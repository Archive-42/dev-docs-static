MessagePort.postMessage()
=========================

The `postMessage()` method of the [`MessagePort`](../messageport) interface sends a message from the port, and optionally, transfers ownership of objects to other browsing contexts.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    port.postMessage(message, transferList);

### Returns

Void.

### Parameters

message  
The message you want to send through the channel. This can be of any basic data type. Multiple data items can be sent as an array.

transferList <span class="badge inline optional">Optional</span>   
[`Transferable`](../transferable) objects to be transferred — these objects have their ownership transferred to the receiving browsing context, so are no longer usable by the sending browsing context.

Example
-------

In the following code block, you can see a new channel being created using the [`MessageChannel.MessageChannel`](../messagechannel) constructor. When the IFrame has loaded, we pass [`MessageChannel.port2`](../messagechannel/port2) to the IFrame using [`window.postMessage`](../window/postmessage) along with a message. The `handleMessage` handler then responds to a message being sent back from the IFrame using `onmessage`, putting it into a paragraph — [`MessageChannel.port1`](../messagechannel/port1) is listened to, to check when the message arrives.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#dom-messageport-postmessage">HTML Living Standard<br />
<span class="small">The definition of 'postMessage()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`postMessage`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/postMessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/postMessage</a>
