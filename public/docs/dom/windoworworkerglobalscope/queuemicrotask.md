WindowOrWorkerGlobalScope.queueMicrotask()
==========================================

The `queueMicrotask()` method, which is exposed on the [`Window`](../window) or [`Worker`](../worker) interface, queues a microtask to be executed at a safe time prior to control returning to the browser's event loop. The microtask is a short function which will run after the current task has completed its work and when there is no other code waiting to be run before control of the execution context is returned to the browser's event loop.

This lets your code run without interfering with any other, potentially higher priority, code that is pending, but before the browser regains control over the execution context, potentially depending on work you need to complete. You can learn more about how to use microtasks and why you might choose to do so in our [microtask guide](../html_dom_api/microtask_guide).

The importance of microtasks comes in its ability to perform tasks asynchronously but in a specific order. See [Using microtasks in JavaScript with queueMicrotask()](../html_dom_api/microtask_guide) for more details.

Microtasks are especially useful for libraries and frameworks that need to perform final cleanup or other just-before-rendering tasks.

`queueMicrotask()` is exposed on the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) mixin.

Syntax
------

    scope.queueMicrotask(function);

### Parameters

`function`  
A [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to be executed when the browser engine determines it is safe to call your code. Enqueued microtasks are executed after all pending tasks have completed but before yielding control to the browser's event loop.

### Return value

`undefined`.

Examples
--------

    self.queueMicrotask(() => {
      // function contents here
    })

Taken from the [queueMicrotask spec](https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#microtask-queuing):

    MyElement.prototype.loadData = function (url) {
      if (this._cache[url]) {
        queueMicrotask(() => {
          this._setData(this._cache[url]);
          this.dispatchEvent(new Event("load"));
        });
      } else {
        fetch(url).then(res => res.arrayBuffer()).then(data => {
          this._cache[url] = data;
          this._setData(data);
          this.dispatchEvent(new Event("load"));
        });
      }
    };

When queueMicrotask() isn't available
-------------------------------------

The code below is basically a monkey-patch for `queueMicrotask()` for modern engines. It creates a microtask by using a promise that resolves immediately.

    if (typeof window.queueMicrotask !== "function") {
      window.queueMicrotask = function (callback) {
        Promise.resolve()
          .then(callback)
          .catch(e => setTimeout(() => { throw e; })); // report exceptions
      };
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#microtask-queuing">HTML Living Standard<br />
<span class="small">The definition of 'self.queueMicrotask()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`queueMicrotask`

71

79

69

No

58

12.1

71

71

No

50

12.2

10.0

See also
--------

-   [Using microtasks in JavaScript with queueMicrotask()](../html_dom_api/microtask_guide)
-   [Asynchronous JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous)
-   [queueMicrotask explainer](https://github.com/fergald/docs/blob/master/explainers/queueMicrotask.md)
-   [Tasks, microtasks, queues and schedules](https://jakearchibald.com/2015/tasks-microtasks-queues-and-schedules/) by Jake Archibald

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask</a>
