# AbstractWorker

The `AbstractWorker` interface of the [Web Workers API](web_workers_api) is an abstract interface that defines properties and methods that are common to all types of worker, including not only the basic [`Worker`](worker), but also [`ServiceWorker`](serviceworker) and [`SharedWorker`](sharedworker). As an abstract class, you don't directly interact with `AbstractWorker`.

## Properties

_The `AbstractWorker` interface doesn't inherit any properties._

### Event handlers

[`AbstractWorker.onerror`](abstractworker/onerror)  
An [`EventListener`](eventlistener) which is invoked whenever an [`ErrorEvent`](errorevent) of type `error` bubbles through the worker.

## Methods

_The `AbstractWorker` interface doesn't implement or inherit any methods._

## Example

As an abstract interface, you won't directly use `AbstractWorker` in your code. Instead, you'll interact with either [`Worker`](worker) or [`SharedWorker`](sharedworker), both of which inherit the properties of `AbstractWorker`.

This code snippet demonstrates the creation of a new `Worker` using the [`Worker()`](worker/worker) constructor; it also shows how to then send a message to the worker.

    var myWorker = new Worker('worker.js');

    first.onchange = function() {
      myWorker.postMessage([first.value, second.value]);
      console.log('Message posted to worker');
    }

The worker's code is loaded from the file `"worker.js"`. This code assumes that there's an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element represented by `first`; an event handler for the `change` event is established so that when the user changes the value of `first`, a message is posted to the worker to let it know.

You can find more examples on the MDN Web Docs GitHub repository:

- [Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).
- [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#abstractworker">HTML Living Standard<br />
<span class="small">The definition of 'AbstractWorker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="about:unknown">Unknown</a>.</td></tr></tbody></table>

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

`AbstractWorker`

4

12

3.5

10

10.6

4

4.4

18

4

11

5.1

1.0

`onerror`

4

12

3.5

10

10.6

4

4.4

18

4

11

5.1

1.0

## See also

- The [`Worker`](worker), [`ServiceWorker`](serviceworker), and [`SharedWorker`](sharedworker) interfaces, which are all based upon `AbstractWorker`.
- [Web Workers API](web_workers_api)
- [Using Web Workers](web_workers_api/using_web_workers)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker</a>
