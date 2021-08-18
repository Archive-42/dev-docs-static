A simple RTCDataChannel sample
==============================

The [`RTCDataChannel`](../rtcdatachannel) interface is a feature of the [WebRTC API](../webrtc_api) which lets you open a channel between two peers over which you may send and receive arbitrary data. The API is intentionally similar to the [WebSocket API](../websockets_api), so that the same programming model can be used for each.

In this example, we will open an [`RTCDataChannel`](../rtcdatachannel) connection linking two elements on the same page. While that's obviously a contrived scenario, it's useful for demonstrating the flow of connecting two peers. We'll cover the mechanics of accomplishing the connection and transmitting and receiving data, but we will save the bits about locating and linking to a remote computer for another example.

The HTML
--------

First, let's take a quick look at the [HTML that's needed](https://github.com/mdn/samples-server/tree/master/s/webrtc-simple-datachannel/index.html). There's nothing incredibly complicated here. First, we have a couple of buttons for establishing and closing the connection:

    <button id="connectButton" name="connectButton" class="buttonleft">
      Connect
    </button>
    <button id="disconnectButton" name="disconnectButton" class="buttonright" disabled>
      Disconnect
    </button>

Then there's a box which contains the text input box into which the user can type a message to transmit, with a button to send the entered text. This [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) will be the first peer in the channel.

      <div class="messagebox">
        <label for="message">Enter a message:
          <input type="text" name="message" id="message" placeholder="Message text"
                  inputmode="latin" size=60 maxlength=120 disabled>
        </label>
        <button id="sendButton" name="sendButton" class="buttonright" disabled>
          Send
        </button>
      </div>

Finally, there's the little box into which we'll insert the messages. This [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) block will be the second peer.

    <div class="messagebox" id="receivebox">
      <p>Messages received:</p>
    </div>

The JavaScript code
-------------------

While you can just [look at the code itself on GitHub](https://github.com/mdn/samples-server/tree/master/s/webrtc-simple-datachannel/main.js), below we'll review the parts of the code that do the heavy lifting.

The WebRTC API makes heavy use of [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)s. They make it very easy to chain the steps of the connection process together; if you haven't already read up on this functionality of [ECMAScript 2015](https://developer.mozilla.org/en-US/docs/Archive/Web/JavaScript/New_in_JavaScript/ECMAScript_2015_support_in_Mozilla), you should read up on them. Similarly, this example uses [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) to simplify syntax.

### Starting up

When the script is run, we set up a `load` event listener, so that once the page is fully loaded, our `startup()` function is called.

    function startup() {
      connectButton = document.getElementById('connectButton');
      disconnectButton = document.getElementById('disconnectButton');
      sendButton = document.getElementById('sendButton');
      messageInputBox = document.getElementById('message');
      receiveBox = document.getElementById('receivebox');

      // Set event listeners for user interface widgets

      connectButton.addEventListener('click', connectPeers, false);
      disconnectButton.addEventListener('click', disconnectPeers, false);
      sendButton.addEventListener('click', sendMessage, false);
    }

This is quite straightforward. We grab references to all the page elements we'll need to access, then set [`event listeners`](../eventlistener) on the three buttons.

### Establishing a connection

When the user clicks the "Connect" button, the `connectPeers()` method is called. We're going to break this up and look at it a bit at a time, for clarity.

**Note:** Even though both ends of our connection will be on the same page, we're going to refer to the one that starts the connection as the "local" one, and to the other as the "remote" end.

#### Set up the local peer

    localConnection = new RTCPeerConnection();

    sendChannel = localConnection.createDataChannel("sendChannel");
    sendChannel.onopen = handleSendChannelStatusChange;
    sendChannel.onclose = handleSendChannelStatusChange;

The first step is to create the "local" end of the connection. This is the peer that will send out the connection request. The next step is to create the [`RTCDataChannel`](../rtcdatachannel) by calling [`RTCPeerConnection.createDataChannel()`](../rtcpeerconnection/createdatachannel) and set up event listeners to monitor the channel so that we know when it's opened and closed (that is, when the channel is connected or disconnected within that peer connection).

It's important to keep in mind that each end of the channel has its own [`RTCDataChannel`](../rtcdatachannel) object.

#### Set up the remote peer

    remoteConnection = new RTCPeerConnection();
    remoteConnection.ondatachannel = receiveChannelCallback;

The remote end is set up similarly, except that we don't need to explicitly create an [`RTCDataChannel`](../rtcdatachannel) ourselves, since we're going to be connected through the channel established above. Instead, we set up a `datachannel` event handler; this will be called when the data channel is opened; this handler will receive an `RTCDataChannel` object; you'll see this below.

#### Set up the ICE candidates

The next step is to set up each connection with ICE candidate listeners; these will be called when there's a new ICE candidate to tell the other side about.

**Note:** In a real-world scenario in which the two peers aren't running in the same context, the process is a bit more involved; each side provides, one at a time, a suggested way to connect (for example, UDP, UDP with a relay, TCP, etc.) by calling [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate), and they go back and forth until agreement is reached. But here, we just accept the first offer on each side, since there's no actual networking involved.

        localConnection.onicecandidate = e => !e.candidate
            || remoteConnection.addIceCandidate(e.candidate)
            .catch(handleAddCandidateError);

        remoteConnection.onicecandidate = e => !e.candidate
            || localConnection.addIceCandidate(e.candidate)
            .catch(handleAddCandidateError);

We configure each [`RTCPeerConnection`](../rtcpeerconnection) to have an event handler for the `icecandidate` event.

#### Start the connection attempt

The last thing we need to do in order to begin connecting our peers is to create a connection offer.

        localConnection.createOffer()
        .then(offer => localConnection.setLocalDescription(offer))
        .then(() => remoteConnection.setRemoteDescription(localConnection.localDescription))
        .then(() => remoteConnection.createAnswer())
        .then(answer => remoteConnection.setLocalDescription(answer))
        .then(() => localConnection.setRemoteDescription(remoteConnection.localDescription))
        .catch(handleCreateDescriptionError);

Let's go through this line by line and decipher what it means.

1.  First, we call [`RTCPeerConnection.createOffer()`](../rtcpeerconnection/createoffer) method to create an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) (Session Description Protocol) blob describing the connection we want to make. This method accepts, optionally, an object with constraints to be met for the connection to meet your needs, such as whether the connection should support audio, video, or both. In our simple example, we don't have any constraints.
2.  If the offer is created successfully, we pass the blob along to the local connection's [`RTCPeerConnection.setLocalDescription()`](../rtcpeerconnection/setlocaldescription) method. This configures the local end of the connection.
3.  The next step is to connect the local peer to the remote by telling the remote peer about it. This is done by calling `remoteConnection.`[`RTCPeerConnection.setRemoteDescription()`](../rtcpeerconnection/setremotedescription). Now the `remoteConnection` knows about the connection that's being built. In a real application, this would require a signaling server to exchange the description object.
4.  That means it's time for the remote peer to reply. It does so by calling its [`createAnswer()`](../rtcpeerconnection/createanswer) method. This generates a blob of SDP which describes the connection the remote peer is willing and able to establish. This configuration lies somewhere in the union of options that both peers can support.
5.  Once the answer has been created, it's passed into the remoteConnection by calling [`RTCPeerConnection.setLocalDescription()`](../rtcpeerconnection/setlocaldescription). That establishes the remote's end of the connection (which, to the remote peer, is its local end. This stuff can be confusing, but you get used to it). Again, this would normally be exchanged through a signalling server.
6.  Finally, the local connection's remote description is set to refer to the remote peer by calling localConnection's [`RTCPeerConnection.setRemoteDescription()`](../rtcpeerconnection/setremotedescription).
7.  The `catch()` calls a routine that handles any errors that occur.

**Note:** Once again, this process is not a real-world implementation; in normal usage, there's two chunks of code running on two machines, interacting and negotiating the connection. A side channel, commonly called a “signalling server,” is usually used to exchange the description (which is in **application/sdp** form) between the two peers.

#### Handling successful peer connection

As each side of the peer-to-peer connection is successfully linked up, the corresponding [`RTCPeerConnection`](../rtcpeerconnection)'s `icecandidate` event is fired. These handlers can do whatever's needed, but in this example, all we need to do is update the user interface:

      function handleLocalAddCandidateSuccess() {
        connectButton.disabled = true;
      }

      function handleRemoteAddCandidateSuccess() {
        disconnectButton.disabled = false;
      }

The only thing we do here is disable the "Connect" button when the local peer is connected and enable the "Disconnect" button when the remote peer connects.

#### Connecting the data channel

Once the [`RTCPeerConnection`](../rtcpeerconnection) is open, the `datachannel` event is sent to the remote to complete the process of opening the data channel; this invokes our `receiveChannelCallback()` method, which looks like this:

      function receiveChannelCallback(event) {
        receiveChannel = event.channel;
        receiveChannel.onmessage = handleReceiveMessage;
        receiveChannel.onopen = handleReceiveChannelStatusChange;
        receiveChannel.onclose = handleReceiveChannelStatusChange;
      }

The `datachannel` event includes, in its channel property, a reference to a [`RTCDataChannel`](../rtcdatachannel) representing the remote peer's end of the channel. This is saved, and we set up, on the channel, event listeners for the events we want to handle. Once this is done, our `handleReceiveMessage()` method will be called each time data is received by the remote peer, and the `handleReceiveChannelStatusChange()` method will be called any time the channel's connection state changes, so we can react when the channel is fully opened and when it's closed.

### Handling channel status changes

Both our local and remote peers use a single method to handle events indicating a change in the status of the channel's connection.

When the local peer experiences an open or close event, the `handleSendChannelStatusChange()` method is called:

      function handleSendChannelStatusChange(event) {
        if (sendChannel) {
          var state = sendChannel.readyState;

          if (state === "open") {
            messageInputBox.disabled = false;
            messageInputBox.focus();
            sendButton.disabled = false;
            disconnectButton.disabled = false;
            connectButton.disabled = true;
          } else {
            messageInputBox.disabled = true;
            sendButton.disabled = true;
            connectButton.disabled = false;
            disconnectButton.disabled = true;
          }
        }
      }

If the channel's state has changed to "open", that indicates that we have finished establishing the link between the two peers. The user interface is updated correspondingly by enabling the text input box for the message to send, focusing the input box so that the user can immediately begin to type, enabling the "Send" and "Disconnect" buttons, now that they're usable, and disabling the "Connect" button, since it is not needed when the conneciton is open.

If the state has changed to "closed", the opposite set of actions occurs: the input box and "Send" button are disabled, the "Connect" button is enabled so that the user can open a new connection if they wish to do so, and the "Disconnect" button is disabled, since it's not useful when no connection exists.

Our example's remote peer, on the other hand, ignores the status change events, except for logging the event to the console:

      function handleReceiveChannelStatusChange(event) {
        if (receiveChannel) {
          console.log("Receive channel's status has changed to " +
                      receiveChannel.readyState);
        }
      }

The `handleReceiveChannelStatusChange()` method receives as an input parameter the event which occurred; this will be an [`RTCDataChannelEvent`](../rtcdatachannelevent).

### Sending messages

When the user presses the "Send" button, the sendMessage() method we've established as the handler for the button's `click` event is called. That method is simple enough:

      function sendMessage() {
        var message = messageInputBox.value;
        sendChannel.send(message);

        messageInputBox.value = "";
        messageInputBox.focus();
      }

First, the text of the message is fetched from the input box's [`value`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-value) attribute. This is then sent to the remote peer by calling [`sendChannel.send()`](../rtcdatachannel/send). That's all there is to it! The rest of this method is just some user experience sugar -- the input box is emptied and re-focused so the user can immediately begin typing another message.

### Receiving messages

When a "message" event occurs on the remote channel, our `handleReceiveMessage()` method is called as the event handler.

      function handleReceiveMessage(event) {
        var el = document.createElement("p");
        var txtNode = document.createTextNode(event.data);

        el.appendChild(txtNode);
        receiveBox.appendChild(el);
      }

This method performs some basic [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) injection; it creates a new [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) (paragraph) element, then creates a new [`Text`](../text) node containing the message text, which is received in the event's `data` property. This text node is appended as a child of the new element, which is then inserted into the `receiveBox` block, thereby causing it to draw in the browser window.

### Disconnecting the peers

When the user clicks the "Disconnect" button, the `disconnectPeers()` method previously set as that button's handler is called.

      function disconnectPeers() {

        // Close the RTCDataChannels if they're open.

        sendChannel.close();
        receiveChannel.close();

        // Close the RTCPeerConnections

        localConnection.close();
        remoteConnection.close();

        sendChannel = null;
        receiveChannel = null;
        localConnection = null;
        remoteConnection = null;

        // Update user interface elements

        connectButton.disabled = false;
        disconnectButton.disabled = true;
        sendButton.disabled = true;

        messageInputBox.value = "";
        messageInputBox.disabled = true;
      }

This starts by closing each peer's [`RTCDataChannel`](../rtcdatachannel), then, similarly, each [`RTCPeerConnection`](../rtcpeerconnection). Then all the saved references to these objects are set to `null` to avoid accidental reuse, and the user interface is updated to reflect the fact that the connection has been closed.

Next steps
----------

You should [try out this example](https://mdn-samples.mozilla.org/s/webrtc-simple-datachannel) and take a look at the [webrtc-simple-datachannel](https://github.com/mdn/samples-server/tree/master/s/webrtc-simple-datachannel) source code, available on GitHub.

See also
--------

-   [Signaling and Video Calling](signaling_and_video_calling).
-   The [Perfect Negotiation](perfect_negotiation) pattern.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API/Simple_RTCDataChannel_sample</a>
