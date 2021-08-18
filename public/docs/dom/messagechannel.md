MessageChannel
==============

The `MessageChannel` interface of the [Channel Messaging API](channel_messaging_api) allows us to create a new message channel and send data through it via its two [`MessagePort`](messageport) properties.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

 [`MessageChannel.port1`](messagechannel/port1) <span class="badge inline readonly">Read only </span>   
Returns port1 of the channel.

 [`MessageChannel.port2`](messagechannel/port2) <span class="badge inline readonly">Read only </span>   
Returns port2 of the channel.

Constructor
-----------

[`MessageChannel()`](messagechannel/messagechannel)  
Returns a new `MessageChannel` object with two new [`MessagePort`](messageport) objects.

Example
-------

In the following example, you can see a new channel being created using the [`MessageChannel.MessageChannel`](messagechannel) constructor.

When the IFrame has loaded, we register an `onmessage` handler for [`MessageChannel.port1`](messagechannel/port1) and transfer [`MessageChannel.port2`](messagechannel/port2) to the IFrame using the [`window.postMessage`](window/postmessage) method along with a message.

When a message is received back from the IFrame, the `onMessage` function outputs the message to a paragraph.

    var channel = new MessageChannel();
    var output = document.querySelector('.output');
    var iframe = document.querySelector('iframe');

    // Wait for the iframe to load
    iframe.addEventListener("load", onLoad);

    function onLoad() {
      // Listen for messages on port1
      channel.port1.onmessage = onMessage;

      // Transfer port2 to the iframe
      iframe.contentWindow.postMessage('Hello from the main page!', '*', [channel.port2]);
    }

    // Handle messages received on port1
    function onMessage(e) {
      output.innerHTML = e.data;
    }

For a full working example, see our [channel messaging basic demo](https://github.com/mdn/dom-examples/tree/master/channel-messaging-basic) on Github ([run it live too](https://mdn.github.io/dom-examples/channel-messaging-basic/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#message-channels">HTML Living Standard<br />
<span class="small">The definition of 'Message channels' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`port2`

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

-   [Using channel messaging](channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageChannel</a>
