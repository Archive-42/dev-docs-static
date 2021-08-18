# MessagePort

The `MessagePort` interface of the [Channel Messaging API](channel_messaging_api) represents one of the two ports of a [`MessageChannel`](messagechannel), allowing messages to be sent from one port and listening out for them arriving at the other.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Methods

_Inherits methods from its parent, [`EventTarget`](eventtarget)_

[`postMessage()`](messageport/postmessage)  
Sends a message from the port, and optionally, transfers ownership of objects to other browsing contexts.

[`start()`](messageport/start)  
Starts the sending of messages queued on the port (only needed when using [`EventTarget.addEventListener`](eventtarget/addeventlistener); it is implied when using [`MessagePort.onmessage`](messageport/onmessage).)

[`close()`](messageport/close)  
Disconnects the port, so it is no longer active.

## Event handlers

_Inherits event handlers from its parent, [`EventTarget`](eventtarget)_

[`onmessage`](messageport/onmessage)  
An [`EventListener`](eventlistener) called when [`MessageEvent`](messageevent) of type `message` is fired on the port—that is, when the port receives a message.

[`onmessageerror`](messageport/onmessageerror)  
An [`EventListener`](eventlistener) called when a [`MessageEvent`](messageevent) of type <span class="page-not-created">`MessageError`</span> is fired—that is, when it receives a message that cannot be deserialized.

## Events

[`message`](messageport/message_event)  
Fired when a `MessagePort` object receives a message.  
Also available via the [`onmessage`](messageport/onmessage) property.

[`messageerror`](messageport/messageerror_event)  
Fired when a `MessagePort` object receives a message that can't be deserialized.  
Also available via the [`onmessageerror`](messageport/onmessageerror) property.

## Example

In the following example, you can see a new channel being created using the [`MessageChannel()`](messagechannel/messagechannel) constructor.

When the IFrame has loaded, we register an [`onmessage`](messageport/onmessage) handler for [`MessageChannel.port1`](messagechannel/port1) and transfer [`MessageChannel.port2`](messagechannel/port2) to the IFrame using the [`window.postMessage`](window/postmessage) method along with a message.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#message-ports">HTML Living Standard<br />
<span class="small">The definition of 'Message ports' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`MessagePort`

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

`message_event`

4

12

Yes

10

10.6

5

≤37

18

No

11.5

5.1

1.0

`messageerror_event`

60

18

57

?

47

?

60

60

57

47

?

8.0

`onmessage`

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

`onmessageerror`

60

18

57

No

47

No

60

60

57

44

No

8.0

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

`worker_support`

Yes

12

41

Yes

Yes

Yes

Yes

Yes

41

Yes

Yes

Yes

## See also

- [Using channel messaging](channel_messaging_api/using_channel_messaging)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessagePort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessagePort</a>
