# Client.postMessage()

The `postMessage()` method of the [`Client`](../client) interface allows a service worker to send a message to a client (a [`Window`](../window), [`Worker`](../worker), or [`SharedWorker`](../sharedworker)). The message is received in the "`message`" event on [`navigator.serviceWorker`](../serviceworkercontainer).

## Syntax

    client.postMessage(message[, transfer]);
    client.postMessage(message[, { transfer }]);

### Parameters

`message`  
The message to send to the client. This can be any [structured-clonable type](../web_workers_api/structured_clone_algorithm).

`transfer` <span class="badge inline optional">Optional</span>  
A sequence of objects that are [transferred](../transferable) with the message. The ownership of these objects is given to the destination side and they are no longer usable on the sending side.

### Return value

`undefined`.

## Examples

Sending a message from a service worker to a client:

    addEventListener('fetch', event => {
      event.waitUntil(async function() {
        // Exit early if we don't have access to the client.
        // Eg, if it's cross-origin.
        if (!event.clientId) return;

        // Get the client.
        const client = await clients.get(event.clientId);
        // Exit early if we don't get the client.
        // Eg, if it closed.
        if (!client) return;

        // Send a message to the client.
        client.postMessage({
          msg: "Hey I just got a fetch from you!",
          url: event.request.url
        });

      }());
    });

Receiving that message:

    navigator.serviceWorker.addEventListener('message', event => {
      console.log(event.data.msg, event.data.url);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-client-postmessage-message-options">Service Workers<br />
<span class="small">The definition of 'postMessage()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`postMessage`

45

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

32

11.1

45

45

44

32

11.3

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Client/postMessage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Client/postMessage</a>
