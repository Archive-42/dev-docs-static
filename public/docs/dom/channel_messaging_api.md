# Channel Messaging API

The **Channel Messaging API** allows two separate scripts running in different browsing contexts attached to the same document (e.g., two IFrames, or the main document and an IFrame, two documents via a [`SharedWorker`](sharedworker), or two workers) to communicate directly, passing messages between one another through two-way channels (or pipes) with a port at each end.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Channel messaging concepts and usage

A message channel is created using the [`MessageChannel()`](messagechannel/messagechannel) constructor. Once created, the two ports of the channel can be accessed through the [`MessageChannel.port1`](messagechannel/port1) and [`MessageChannel.port2`](messagechannel/port2) properties (which both return [`MessagePort`](messageport) objects.) The app that created the channel uses `port1`, and the app at the other end of the port uses `port2` — you send a message to `port2`, and transfer the port over to the other browsing context using [`window.postMessage`](window/postmessage) along with two arguments (the message to send, and the object to transfer ownership of, in this case the port itself.)

When these transferable objects are transferred, they are no longer usable on the context they previously belonged to. A port, after it is sent, can no longer be used by the original context.

The other browsing context can listen for the message using [`MessagePort.onmessage`](messageport/onmessage), and grab the contents of the message using the event's `data` attribute. You could then respond by sending a message back to the original document using [`MessagePort.postMessage`](messageport/postmessage).

When you want to stop sending messages down the channel, you can invoke [`MessagePort.close`](messageport/close) to close the ports.

Find out more about how to use this API in [Using channel messaging](channel_messaging_api/using_channel_messaging).

## Channel messaging interfaces

[`MessageChannel`](messagechannel)  
Creates a new message channel to send messages across.

[`MessagePort`](messageport)  
Controls the ports on the message channel, allowing sending of messages from one port and listening out for them arriving at the other.

<span class="page-not-created">`PortCollection`</span>  
An array of `MessagePort`s; an experimental solution to allow broadcasting of a message to multiple ports simultaneously.

## Examples

- We have published a [channel messaging basic demo](https://github.com/mdn/dom-examples/tree/master/channel-messaging-basic) on Github ([run it live too](https://mdn.github.io/dom-examples/channel-messaging-basic/)), which shows a really simple single message transfer between a page and an embedded [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).
- You can also see a [multimessaging demo](https://github.com/mdn/dom-examples/tree/master/channel-messaging-multimessage) ([run this live](https://mdn.github.io/dom-examples/channel-messaging-multimessage/)), which shows a slightly more complex setup that can send multiple messages between main page and IFrame.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/web-messaging.html#channel-messaging">HTML Living Standard<br />
<span class="small">The definition of 'Channel messaging' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Channel_Messaging_API`

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

`Channel_Messaging_API`

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

BCD tables only load in the browser

### MessagePort

BCD tables only load in the browser

## See also

- [Using channel messaging](channel_messaging_api/using_channel_messaging)
- [Web Workers API](web_workers_api)
- [Broadcast Channel API](broadcast_channel_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API</a>
