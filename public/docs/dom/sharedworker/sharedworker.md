SharedWorker()
==============

The `SharedWorker()` constructor creates a [`SharedWorker`](../sharedworker) object that executes the script at the specified URL. This script must obey the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).

**Note**: there is disagreement among browser manufacturers about whether a data URI is of the same origin or not. Although Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7) and later accept data URIs, that's not the case in all other browsers.

Syntax
------

    var myWorker = new SharedWorker(aURL, name);
    var myWorker = new SharedWorker(aURL, options);

### Parameters

*aURL*  
A [`DOMString`](../domstring) representing the URL of the script the worker will execute. It must obey the same-origin policy.

name <span class="badge inline optional">Optional</span>   
A [`DOMString`](../domstring) specifying an identifying name for the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) representing the scope of the worker, which is mainly useful for debugging purposes.

 *options* <span class="badge inline optional">Optional</span>   
An object containing option properties that can set when creating the object instance. Available properties are as follows:

-   `type`: A [`DOMString`](../domstring) specifying the type of worker to create. The value can be `classic` or `module`. If not specified, the default used is `classic`.
-   `credentials`: A [`DOMString`](../domstring) specifying the type of credentials to use for the worker. The value can be `omit`, `same-origin`, or `include`. If not specified, or if type is `classic`, the default used is `omit` (no credentials required).
-   `name`: A [`DOMString`](../domstring) specifying an identifying name for the [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) representing the scope of the worker, which is mainly useful for debugging purposes.

### Return value

The created worker.

### Exceptions

-   A `SecurityError` is raised if the document is not allowed to start workers, for example if the URL has an invalid syntax or if the same-origin policy is violated.
-   A `NetworkError` is raised if the MIME type of the worker script is incorrect. It should *always* be `text/javascript` (for historical reasons [other JavaScript MIME types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#javascript_types) may be accepted).
-   A `SyntaxError` is raised if *aURL* cannot be parsed.

Examples
--------

The following code snippet shows creation of a [`SharedWorker`](../sharedworker) object using the `SharedWorker()` constructor and subsequent usage of the object:

    var myWorker = new SharedWorker('worker.js');

    myWorker.port.start();

    first.onchange = function() {
      myWorker.port.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    second.onchange = function() {
      myWorker.port.postMessage([first.value,second.value]);
      console.log('Message posted to worker');
    }

    myWorker.port.onmessage = function(e) {
      result1.textContent = e.data;
      console.log('Message received from worker');
    }

For a full example, see our [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/).)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-sharedworker">HTML Living Standard<br />
<span class="small">The definition of 'SharedWorker()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`SharedWorker`

4

79

29

No

10.6

5-6.1

No

No

33

11-14

5.1-7

4.0-5.0

`mime_checks`

?

?

81

No

?

No

No

No

81

No

No

No

`name_option`

Yes

79

55

No

?

No

No

No

55

No

No

4.0-5.0

See also
--------

-   The [`SharedWorker`](../sharedworker) interface it belongs to.
-   [another multiply demo](https://anlexn.github.io/shared-worker-mdn/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker/SharedWorker</a>
