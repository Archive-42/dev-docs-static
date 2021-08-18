# Clients

The `Clients` interface provides access to [`Client`](client) objects. Access it via `self`.clients within a [service worker](service_worker_api).

## Methods

[`Clients.get()`](clients/get)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a [`Client`](client) matching a given [`id`](client/id).

[`Clients.matchAll()`](clients/matchall)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for an array of [`Client`](client) objects. An options argument allows you to control the types of clients returned.

[`Clients.openWindow()`](clients/openwindow)  
Opens a new browser window for a given url and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for the new [`WindowClient`](windowclient).

[`Clients.claim()`](clients/claim)  
Allows an active service worker to set itself as the [`controller`](serviceworkercontainer/controller) for all clients within its [`scope`](serviceworkerregistration/scope).

## Examples

The following example shows an existing chat window or creates a new one when the user clicks a notification.

    addEventListener('notificationclick', event => {
      event.waitUntil(async function() {
        const allClients = await clients.matchAll({
          includeUncontrolled: true
        });

        let chatClient;

        // Let's see if we already have a chat window open:
        for (const client of allClients) {
          const url = new URL(client.url);

          if (url.pathname == '/chat/') {
            // Excellent, let's use it!
            client.focus();
            chatClient = client;
            break;
          }
        }

        // If we didn't find an existing chat window,
        // open a new one:
        if (!chatClient) {
          chatClient = await clients.openWindow('/chat/');
        }

        // Message the client:
        chatClient.postMessage("New chat messages!");
      }());
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#clients">Service Workers<br />
<span class="small">The definition of 'Clients' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Clients`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

`claim`

42

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

11.1

42

42

44

29

11.3

4.0

`get`

51

17

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

38

11.1

No

51

45

41

11.3

5.0

`matchAll`

47

`Client` objects returned in most recent focus order.

17

`Client` objects returned in most recent focus order.

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

54

`Client` objects returned in most recent focus order.

No

32

11.1

47

`Client` objects returned in most recent focus order.

47

`Client` objects returned in most recent focus order.

44

54

`Client` objects returned in most recent focus order.

32

11.3

4.0

`Client` objects returned in most recent focus order.

`openWindow`

40

42

Can only open URLs on the same origin.

43

Can open any URL.

51

URLs may open inside an existing browsing context provided by a standalone web app

17

79

URLs may open inside an existing browsing context provided by a standalone web app

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

38

11.1

40

42

Can only open URLs on the same origin.

43

Can open any URL.

51

URLs may open inside an existing browsing context provided by a standalone web app

40

42

Can only open URLs on the same origin.

43

Can open any URL.

51

URLs may open inside an existing browsing context provided by a standalone web app

45

41

11.3

4.0

5.0

URLs may open inside an existing browsing context provided by a standalone web app

## See also

- [Using Service Workers](service_worker_api/using_service_workers)
- [Is ServiceWorker ready?](https://jakearchibald.github.io/isserviceworkerready/)
- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clients" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clients</a>
