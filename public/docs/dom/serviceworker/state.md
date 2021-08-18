ServiceWorker.state
===================

The `state` read-only property of the [`ServiceWorker`](../serviceworker) interface returns a string representing the current state of the service worker. It can be one of the following values: `installing`, `installed,` `activating`, `activated`, or `redundant`.

Syntax
------

    someURL = ServiceWorker.state

### Value

A [`ServiceWorkerState`](../serviceworkerstate) definition ([see the spec](https://slightlyoff.github.io/ServiceWorker/spec/service_worker/#service-worker-state-enum).)

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-state">Service Workers<br />
<span class="small">The definition of 'state' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`state`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker/state</a>
