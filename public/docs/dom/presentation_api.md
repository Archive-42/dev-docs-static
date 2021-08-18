# Presentation API

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Presentation API lets a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) (such as a Web browser) effectively display web content through large presentation devices such as projectors and network-connected televisions. Supported types of multimedia devices include both displays which are wired using HDMI, DVI, or the like, or wireless, using [DLNA](https://www.dlna.org/), [Chromecast](https://developers.google.com/cast/), [AirPlay](https://developer.apple.com/airplay/), or [Miracast](https://www.wi-fi.org/discover-wi-fi/miracast).

<img src="data:image/png;base64,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" width="945" height="382" />

In general, a web page uses the Presentation Controller API to specify the web content to be rendered on presentation device and initiate the presentation session. With Presentation Receiver API, the presenting web content obtains the session status. With providing both the controller page and the receiver one with a messaged-based channel, a Web developer can implement the interaction between these two pages.

Depending on the connection mechanism provided by the presentation device, any controller- and receiver page can be rendered by the same user agent, or by separated user agents.

- For 1-UA mode devices, both pages are loaded by the same user agent. However, rendering result of the receiver page will be sent to the presentation device via supported remote rendering protocol.
- For 2-UAs mode device, the receiver page is loaded directly on the presentation device. Controlling user agent communicates with presentation device via supported presentation control protocol, to control the presentation session and to transmit the message between two pages.

## Interfaces

[`Presentation`](presentation)  
In controlling browsing context, the `Presentation` interface provides a mechanism to override the browser default behavior of launching presentation to external screen. In receiving browsing context, `Presentation` interface provides the access to the available presentation connections.

[`PresentationRequest`](presentationrequest)  
Initiates or reconnects to a presentation made by a controlling browsing context.

[`PresentationAvailability`](presentationavailability)  
A [PresentationAvailability](presentationavailability) object is associated with available presentation displays and represents the presentation display availability for a presentation request.

[`PresentationConnectionAvailableEvent`](presentationconnectionavailableevent)  
The `PresentationConnectionAvailableEvent` is fired on a [`PresentationRequest`](presentationrequest) when a connection associated with the object is created.

[`PresentationConnection`](presentationconnection)  
Each presentation connection is represented by a [PresentationConnection](presentationconnection) object.

[`PresentationConnectionCloseEvent`](presentationconnectioncloseevent)  
A `PresentationConnectionCloseEvent` is fired when a presentation connection enters a `closed` state.

[`PresentationReceiver`](presentationreceiver)  
The [PresentationReceiver](presentationreceiver) allows a receiving browsing context to access the controlling browsing contexts and communicate with them.

[`PresentationConnectionList`](presentationconnectionlist)  
`PresentationConnectionList` represents the collection of non-terminated presentation connections. It is also a monitor for the event of new available presentation connection.

## Example

Example codes below highlight the usage of main features of the Presentation API: `controller.html` implements the controller and `presentation.html` implements the presentation. Both pages are served from the domain `http://example.org` (`http://example.org/controller.html` and `http://example.org/presentation.html`). These examples assume that the controlling page is managing one presentation at a time. Please refer to the comments in the code examples for further details.

### Monitor availability of presentation displays

    <!-- controller.html -->
    <button id="presentBtn" style="display: none;">Present</button>
    <script>
      // The Present button is visible if at least one presentation display is available
      var presentBtn = document.getElementById("presentBtn");
      // It is also possible to use relative presentation URL e.g. "presentation.html"
      var presUrls = ["http://example.com/presentation.html",
                      "http://example.net/alternate.html"];
      // show or hide present button depending on display availability
      var handleAvailabilityChange = function(available) {
        presentBtn.style.display = available ? "inline" : "none";
      };
      // Promise is resolved as soon as the presentation display availability is
      // known.
      var request = new PresentationRequest(presUrls);
      request.getAvailability().then(function(availability) {
        // availability.value may be kept up-to-date by the controlling UA as long
        // as the availability object is alive. It is advised for the web developers
        // to discard the object as soon as it's not needed.
        handleAvailabilityChange(availability.value);
        availability.onchange = function() { handleAvailabilityChange(this.value); };
      }).catch(function() {
        // Availability monitoring is not supported by the platform, so discovery of
        // presentation displays will happen only after request.start() is called.
        // Pretend the devices are available for simplicity; or, one could implement
        // a third state for the button.
        handleAvailabilityChange(true);
      });
    </script>

### Starting a new presentation

    <!-- controller.html -->
    <script>
      presentBtn.onclick = function () {
        // Start new presentation.
        request.start()
          // The connection to the presentation will be passed to setConnection on
          // success.
          .then(setConnection);
          // Otherwise, the user canceled the selection dialog or no screens were
          // found.
      };
    </script>

### Reconnect to a presentation

    <!-- controller.html -->
    <button id="reconnectBtn" style="display: none;">Reconnect</button>
    <script>
      var reconnect = function () {
        // read presId from localStorage if exists
        var presId = localStorage["presId"];
        // presId is mandatory when reconnecting to a presentation.
        if (!!presId) {
          request.reconnect(presId)
            // The new connection to the presentation will be passed to
            // setConnection on success.
            .then(setConnection);
            // No connection found for presUrl and presId, or an error occurred.
        }
      };
      // On navigation of the controller, reconnect automatically.
      document.addEventListener("DOMContentLoaded", reconnect);
      // Or allow manual reconnection.
      reconnectBtn.onclick = reconnect;
    </script>

### Presentation initiation by the controlling UA

    <!-- controller.html -->
    <!-- Setting presentation.defaultRequest allows the page to specify the
         PresentationRequest to use when the controlling UA initiates a
         presentation. -->
    <script>
      navigator.presentation.defaultRequest = new PresentationRequest(presUrls);
      navigator.presentation.defaultRequest.onconnectionavailable = function(evt) {
        setConnection(evt.connection);
      };
    </script>

### Monitor connection's state and exchange data

    <!-- controller.html -->
    <button id="disconnectBtn" style="display: none;">Disconnect</button>
    <button id="stopBtn" style="display: none;">Stop</button>
    <button id="reconnectBtn" style="display: none;">Reconnect</button>
    <script>
      let connection;

      // The Disconnect and Stop buttons are visible if there is a connected presentation
      const stopBtn = document.querySelector("#stopBtn");
      const reconnectBtn = document.querySelector("#reconnectBtn");
      const disconnectBtn = document.querySelector("#disconnectBtn");

      stopBtn.onclick = _ => {
        connection && connection.terminate();
      };

      disconnectBtn.onclick = _ => {
        connection && connection.close();
      };

      function setConnection(newConnection) {
        // Disconnect from existing presentation, if not attempting to reconnect
        if (connection && connection != newConnection && connection.state != 'closed') {
          connection.onclosed = undefined;
          connection.close();
        }

        // Set the new connection and save the presentation ID
        connection = newConnection;
        localStorage["presId"] = connection.id;

        function showConnectedUI() {
          // Allow the user to disconnect from or terminate the presentation
          stopBtn.style.display = "inline";
          disconnectBtn.style.display = "inline";
          reconnectBtn.style.display = "none";
        }

        function showDisconnectedUI() {
          disconnectBtn.style.display = "none";
          stopBtn.style.display = "none";
          reconnectBtn.style.display = localStorage["presId"] ? "inline" : "none";
        }

        // Monitor the connection state
        connection.onconnect = _ => {
          showConnectedUI();

          // Register message handler
          connection.onmessage = message => {
            console.log(`Received message: ${message.data}`);
          };

          // Send initial message to presentation page
          connection.send("Say hello");
        };

        connection.onclose = _ => {
          connection = null;
          showDisconnectedUI();
        };

        connection.onterminate = _ => {
          // Remove presId from localStorage if exists
          delete localStorage["presId"];
          connection = null;
          showDisconnectedUI();
        };
      };
    </script>

### Monitor available connection(s) and say hello

    <!-- presentation.html -->
    <script>
      var addConnection = function(connection) {
        this.onmessage = function (message) {
          if (message.data == "say hello")
            this.send("hello");
        };
      };

      navigator.presentation.receiver.connectionList.then(function (list) {
        list.connections.map(function (connection) {
          addConnection(connection);
        });
        list.onconnectionavailable = function (evt) {
          addConnection(evt.connection);
        };
      });
    </script>

### Passing locale information with a message

    <!-- controller.html -->
    <script>
      connection.send("{string: '你好，世界!', lang: 'zh-CN'}");
      connection.send("{string: 'こんにちは、世界!', lang: 'ja'}");
      connection.send("{string: '안녕하세요, 세계!', lang: 'ko'}");
      connection.send("{string: 'Hello, world!', lang: 'en-US'}");
    </script>

    <!-- presentation.html -->
    <script>
      connection.onmessage = function (message) {
        var messageObj = JSON.parse(message.data);
        var spanElt = document.createElement("SPAN");
        spanElt.lang = messageObj.lang;
        spanElt.textContent = messageObj.string;
        document.appendChild(spanElt);
      };
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/">Presentation API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Presentation_API`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`defaultRequest`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`receiver`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

BCD tables only load in the browser

## See also

[Presentation API polyfill](https://mediascape.github.io/presentation-api-polyfill/) contains a JavaScript polyfill of the [Presentation API](https://w3c.github.io/presentation-api/) specification under standardisation within the [Second Screen Working Group](https://www.w3.org/2014/secondscreen/) at W3C. The polyfill is mostly intended for exploring how the Presentation API may be implemented on top of different presentation mechanisms.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Presentation_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Presentation_API</a>
