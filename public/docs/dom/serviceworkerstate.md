ServiceWorkerState
==================

The `ServiceWorkerState` is associated with its [`ServiceWorker`](serviceworker)'s state.

Values
------

`installing`  
The service worker in this state is considered an installing worker. During this state, [`ExtendableEvent.waitUntil()`](extendableevent/waituntil) can be called inside the `install` event handler to extend the life of the installing worker until the passed promise resolves successfully. This is primarily used to ensure that the service worker is not active until all of the core caches are populated.

`installed`  
The service worker in this state is considered a waiting worker.

`activating`  
The service worker in this state is considered an active worker. During this state, [`ExtendableEvent.waitUntil()`](extendableevent/waituntil) can be called inside the `onactivate` event handler to extend the life of the active worker until the passed promise resolves successfully. No functional events are dispatched until the state becomes activated.

`activated`  
The service worker in this state is considered an active worker ready to handle functional events.

`redundant`  
A new service worker is replacing the current service worker, or the current service worker is being discarded due to an install failure.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#service-worker-state-enum">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerState' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

See also
--------

-   [`ServiceWorker.state`](serviceworker/state)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerState</a>
