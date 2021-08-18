Web Workers API
===============

**Web Workers** makes it possible to run a script operation in a background thread separate from the main execution thread of a web application. The advantage of this is that laborious processing can be performed in a separate thread, allowing the main (usually the UI) thread to run without being blocked/slowed down.

**Note:** Web Workers can also use the Web Worker API (i.e. workers can spawn workers, provided they are hosted within the same [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) as the parent page).

Web Workers concepts and usage
------------------------------

A worker is an object created using a constructor (e.g. [`Worker()`](worker/worker)) that runs a named JavaScript file — this file contains the code that will run in the worker thread.

In addition to the standard [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) set of functions (such as [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), etc.), you can run almost any code you like inside a worker thread. There are some exceptions: for example, you can't directly manipulate the DOM from inside a worker, or use some default methods and properties of the [`window`](window) object. For information about the code that you *can* run see [worker global context and functions](#worker_global_contexts_and_functions), and [supported web APIs](#supported_web_apis) below.

Data is sent between workers and the main thread via a system of messages — both sides send their messages using the `postMessage()` method, and respond to messages via the `onmessage` event handler (the message is contained within the `Message` event's `data` property). The data is copied rather than shared.

Workers may in turn spawn new workers, as long as those workers are hosted within the same [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) as the parent page. In addition, workers may use <a href="xmlhttprequest" class="internal"><code>XMLHttpRequest</code></a> for network I/O, with the exception that the `responseXML` and `channel` attributes on `XMLHttpRequest` always return `null`.

### Worker types

There are a number of different types of workers:

-   Dedicated workers are workers that are utilized by a single script. This context is represented by either a [`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope) object.
-   [`Shared workers`](sharedworker) are workers that can be utilized by multiple scripts running in different windows, IFrames, etc., as long as they are in the same domain as the worker. They are a little more complex than dedicated workers — scripts must communicate via an active port.
-   [Service Workers](service_worker_api) essentially act as proxy servers that sit between web applications, the browser, and the network (when available). They are intended, among other things, to enable the creation of effective offline experiences, intercept network requests and take appropriate action based on whether the network is available, and update assets residing on the server. They will also allow access to push notifications and background sync APIs.
-   Chrome Workers are a Firefox-only type of worker that you can use if you are developing add-ons and want to use workers in extensions and have access to [js-ctypes](https://developer.mozilla.org/en/js-ctypes) in your worker. See <span class="page-not-created">`ChromeWorker`</span> for more details.

**Note**: As per the [Web workers Spec](https://html.spec.whatwg.org/multipage/workers.html#runtime-script-errors-2), worker error events should not bubble (see [bug 1188141](https://bugzilla.mozilla.org/show_bug.cgi?id=1188141). This has been implemented in Firefox 42.

### Worker global contexts and functions

Workers run in a different global context than the current [`window`](window)! While [`Window`](window) is not directly available to workers, many of the same methods are defined in a shared mixin ([`WindowOrWorkerGlobalScope`](windoworworkerglobalscope)), and made available to workers through their own [`WorkerGlobalScope`](workerglobalscope)-derived contexts:

-   [`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope) for dedicated workers
-   [`SharedWorkerGlobalScope`](sharedworkerglobalscope) for shared workers
-   [`ServiceWorkerGlobalScope`](serviceworkerglobalscope) for [service workers](service_worker_api)

Some of the functions (a subset) that are common to all workers and to the main thread (from [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope)) are: [`atob()`](windoworworkerglobalscope/atob), [`btoa()`](windoworworkerglobalscope/btoa), [`clearInterval()`](windoworworkerglobalscope/clearinterval), [`clearTimeout()`](windoworworkerglobalscope/cleartimeout),[`dump()`](window/dump) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>, [`setInterval()`](windoworworkerglobalscope/setinterval), [`setTimeout()`](windoworworkerglobalscope/settimeout).

The following functions are **only** available to workers:

-   [`WorkerGlobalScope.importScripts()`](workerglobalscope/importscripts) (all workers),
-   [`close()`](workerglobalscope/close) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (dedicated and shared workers only),
-   [`DedicatedWorkerGlobalScope.postMessage`](dedicatedworkerglobalscope/postmessage) (dedicated workers and [chrome workers](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko/Chrome/API/ChromeWorker) only).

### Supported Web APIs

Note that if a listed API is supported by a platform in a particular version, then it can generally be assumed to be available in web workers. You can also test support for a particular object/function using the site: <https://worker-playground.glitch.me/>

The following Web APIs are available to workers: [`Barcode Detection API`](barcode_detection_api), [`Broadcast Channel API`](broadcast_channel_api), [`Cache API`](cache), [`Channel Messaging API`](channel_messaging_api),[`Console API`](console), [Web Crypto API](web_crypto_api) ([`Crypto`](crypto)), [`CustomEvent`](customevent), <span class="page-not-created">`Data Store`</span> (Firefox only), <span class="page-not-created">`DOMRequest`</span> and <span class="page-not-created">`DOMCursor`</span>, [`Encoding API`](encoding_api) ([`TextEncoder`](textencoder), [`TextDecoder`](textdecoder), etc.), [`Fetch API`](fetch_api), [`FileReader`](filereader), [`FileReaderSync`](filereadersync) (only works in workers!), [`FormData`](formdata), [`ImageData`](imagedata), [`IndexedDB`](indexeddb_api), [Network Information API](network_information_api), [`Notifications API`](notifications_api), [`Performance API`](performance_api) (including: [`Performance`](performance), [`PerformanceEntry`](performanceentry), [`PerformanceMeasure`](performancemeasure), [`PerformanceMark`](performancemark), [`PerformanceObserver`](performanceobserver), [`PerformanceResourceTiming`](performanceresourcetiming)), [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), [Server-sent events](server-sent_events), [`ServiceWorkerRegistration`](serviceworkerregistration), [`URL API`](url_api) (e.g. [`URL`](url)), [WebGL](webgl_api) with [`OffscreenCanvas`](offscreencanvas) (enabled behind a feature preference setting `gfx.offscreencanvas.enabled`), [`WebSocket`](websocket), [`XMLHttpRequest`](xmlhttprequest).

Workers can also spawn other workers, so these APIs are also available: [`Worker`](worker), [`WorkerGlobalScope`](workerglobalscope), [`WorkerLocation`](workerlocation), [`WorkerNavigator`](workernavigator).

Web Worker interfaces
---------------------

[`AbstractWorker`](abstractworker)  
Abstracts properties and methods common to all kind of workers (i.e. [`Worker`](worker) or [`SharedWorker`](sharedworker)).

[`Worker`](worker)  
Represents a running worker thread, allowing you to pass messages to the running worker code.

[`WorkerLocation`](workerlocation)  
Defines the absolute location of the script executed by the [`Worker`](worker).

[`SharedWorker`](sharedworker)  
Represents a specific kind of worker that can be *accessed* from several [browsing contexts](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context), being several windows, iframes or even workers.

[`WorkerGlobalScope`](workerglobalscope)  
Represents the generic scope of any worker (doing the same job as [`Window`](window) does for normal web content). Different types of worker have scope objects that inherit from this interface and add more specific features.

[`DedicatedWorkerGlobalScope`](dedicatedworkerglobalscope)  
Represents the scope of a dedicated worker, inheriting from [`WorkerGlobalScope`](workerglobalscope) and adding some dedicated features.

[`SharedWorkerGlobalScope`](sharedworkerglobalscope)  
Represents the scope of a shared worker, inheriting from [`WorkerGlobalScope`](workerglobalscope) and adding some dedicated features.

[`WorkerNavigator`](workernavigator)  
Represents the identity and state of the user agent (the client):

Examples
--------

We have created a couple of simple demos to show basic usage:

-   [Basic dedicated worker example](https://github.com/mdn/simple-web-worker) ([run dedicated worker](https://mdn.github.io/simple-web-worker/)).
-   [Basic shared worker example](https://github.com/mdn/simple-shared-worker) ([run shared worker](https://mdn.github.io/simple-shared-worker/)).

You can find out more information on how these demos work in [Using Web Workers](web_workers_api/using_web_workers).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/workers.html#workers">HTML Living Standard<br />
<span class="small">The definition of 'Web Workers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

See also
--------

-   [Using Web Workers](web_workers_api/using_web_workers)
-   [`Worker`](worker) interface
-   [`SharedWorker`](sharedworker) interface
-   [Service Worker API](service_worker_api)
-   [ChromeWorker](chromeworker): for using workers in privileged/chrome code

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API</a>
