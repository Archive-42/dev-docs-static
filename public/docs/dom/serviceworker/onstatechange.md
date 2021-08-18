ServiceWorker.onstatechange
===========================

An [`EventListener`](../eventlistener) property called whenever an event of type `statechange` is fired; it is basically fired anytime the [`ServiceWorker.state`](state) changes.

Syntax
------

    ServiceWorker.onstatechange = function(statechangeevent) { ... }
    ServiceWorker.addEventListener('statechange', function(statechangeevent) { ... } )

Examples
--------

This code snippet is from the [service worker registration-events sample](https://github.com/GoogleChrome/samples/blob/gh-pages/service-worker/registration-events/index.html) ([live demo](https://googlechrome.github.io/samples/service-worker/registration-events/)). The code listens for any change in the [`ServiceWorker.state`](state) and returns its value.

    var serviceWorker;
    if (registration.installing) {
      serviceWorker = registration.installing;
      document.querySelector('#kind').textContent = 'installing';
    } else if (registration.waiting) {
      serviceWorker = registration.waiting;
      document.querySelector('#kind').textContent = 'waiting';
    } else if (registration.active) {
      serviceWorker = registration.active;
      document.querySelector('#kind').textContent = 'active';
    }

    if (serviceWorker) {
      logState(serviceWorker.state);
      serviceWorker.addEventListener('statechange', function(e) {
      logState(e.target.state);
      });
    }

Note that when `statechange` fires, the service worker's references may have changed. For example:

    navigator.serviceWorker.register(..).then(function(swr) {
      swr.installing.state == "installing"
      swr.installing.onstatechange = function() {
        swr.installing == null;
        // At this point, swr.waiting OR swr.active might be true. This is because the statechange
        // event gets queued, meanwhile the underlying worker may have gone into the waiting
        // state and will be immediately activated if possible.
      }
    })

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworker-onstatechange">Service Workers<br />
<span class="small">The definition of 'ServiceWorker.onstatechange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onstatechange`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/onstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/onstatechange</a>
