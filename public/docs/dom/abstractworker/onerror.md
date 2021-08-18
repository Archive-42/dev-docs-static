# AbstractWorker.onerror

The ` AbstractWorker``.onerror ` property of the [`AbstractWorker`](../abstractworker) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers), that is a function to be called when the `error` event occurs and bubbles through the [`Worker`](../worker).

## Syntax

    myWorker.onerror = function() { ... };

## Example

The following code snippet shows creation of a [`Worker`](../worker) object using the [`Worker()`](../worker/worker) constructor and setting up of an `onerror` handler on the resulting object:

    var myWorker = new Worker('worker.js');

    myWorker.onerror = function() {
      console.log('There is an error with your worker!');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-abstractworker-onerror">HTML Living Standard<br />
<span class="small">The definition of 'AbstractWorker.onerror' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

### Cross-origin worker error behavior

In earlier browser versions, trying to load a cross-origin worker script threw a `SecurityError`; in newer browsers an `error` event is thrown instead due to a spec change. Find out more information on how to deal with this in [Loading cross-origin worker now fires error event instead of throwing; worker in sandboxed iframe no longer allowed](https://github.com/mdn/kuma/issues/7647).

## See also

- The [`AbstractWorker`](../abstractworker) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AbstractWorker/onerror</a>
