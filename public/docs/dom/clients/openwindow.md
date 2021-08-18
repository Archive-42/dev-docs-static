# Clients.openWindow()

The `openWindow()` method of the [`Clients`](../clients) interface creates a new top level browsing context and loads a given URL. If the calling script doesn't have permission to show popups, `openWindow()` will throw an `InvalidAccessError`.

In Firefox, the method is allowed to show popups only when called as the result of a notification click event.

In Chrome for Android, the method may instead open the URL in an existing browsing context provided by a [standalone web app](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps) previously added to the user's home screen. As of recently, this also works on Chrome for Windows.

## Syntax

    self.clients.openWindow(url).then(function(windowClient) {
      // Do something with your WindowClient
    });

### Parameters

`url`  
A [`USVString`](../usvstring) representing the URL of the client you want to open in the window. Generally this value must be a URL from the same origin as the calling script.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`WindowClient`](../windowclient) object if the URL is from the same origin as the service worker or a [null value](https://developer.mozilla.org/en-US/docs/Glossary/Null) otherwise.

## Examples

    // Send notification to OS if applicable
    if (self.Notification.permission === 'granted') {
      const notificationObject = {
        body: 'Click here to view your messages.',
        data: { url: self.location.origin + '/some/path' },
        // data: { url: 'http://example.com' },
      };
      self.registration.showNotification('You\'ve got messages!', notificationObject);
    }

    // Notification click event listener
    self.addEventListener('notificationclick', e => {
      // Close the notification popout
      e.notification.close();
      // Get all the Window clients
      e.waitUntil(clients.matchAll({ type: 'window' }).then(clientsArr => {
        // If a Window tab matching the targeted URL already exists, focus that;
        const hadWindowToFocus = clientsArr.some(windowClient => windowClient.url === e.notification.data.url ? (windowClient.focus(), true) : false);
        // Otherwise, open a new tab to the applicable URL and focus it.
        if (!hadWindowToFocus) clients.openWindow(e.notification.data.url).then(windowClient => windowClient ? windowClient.focus() : null);
      }));
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#clients-openwindow">Service Workers<br />
<span class="small">The definition of 'Clients: openWindow' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Clients/openWindow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Clients/openWindow</a>
