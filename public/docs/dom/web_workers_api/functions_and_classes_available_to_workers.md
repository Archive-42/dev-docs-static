Functions and classes available to Web Workers
==============================================

In addition to the standard [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) set of functions (such as [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), etc), there are a variety of functions available from the DOM to workers. This article provides a list of those.

Worker Contexts & Functions
---------------------------

**Workers run in a different global context than the current window!** While [`Window`](../window) is not directly available to workers, many of the same methods are defined in a shared mixin ([`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope)), and made available to workers through their own [`WorkerGlobalScope`](../workerglobalscope)-derived contexts:

-   [`DedicatedWorkerGlobalScope`](../dedicatedworkerglobalscope) for dedicated workers
-   [`SharedWorkerGlobalScope`](../sharedworkerglobalscope) for shared workers
-   [`ServiceWorkerGlobalScope`](../serviceworkerglobalscope) for [service workers](../service_worker_api)

Some of the functions that are common to all workers and to the main thread (from [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope)) are: [`atob()`](../windoworworkerglobalscope/atob), [`btoa()`](../windoworworkerglobalscope/btoa), [`clearInterval()`](../windoworworkerglobalscope/clearinterval), [`clearTimeout()`](../windoworworkerglobalscope/cleartimeout),[`dump()`](../window/dump) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>, [`setInterval()`](../windoworworkerglobalscope/setinterval), [`setTimeout()`](../windoworworkerglobalscope/settimeout).

The following functions are **only** available to workers:

-   [`WorkerGlobalScope.importScripts()`](../workerglobalscope/importscripts) (all workers),
-   [`close()`](../workerglobalscope/close) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> (dedicated and shared workers only),
-   [`DedicatedWorkerGlobalScope.postMessage`](../dedicatedworkerglobalscope/postmessage) (dedicated workers and [chrome workers](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko/Chrome/API/ChromeWorker) only).

Web APIs available in workers
-----------------------------

Note that if a listed API is supported by a platform in a particular version, then it can generally be assumed to work in web workers.

The following Web APIs are available to workers: [`Broadcast Channel API`](../broadcast_channel_api), [`Cache API`](../cache),[`Channel Messaging API`](../channel_messaging_api),[`Console API`](../console), [`Crypto`](../crypto), [`CustomEvent`](../customevent), <span class="page-not-created">`Data Store`</span> (Firefox only), <span class="page-not-created">`DOMRequest`</span> and <span class="page-not-created">`DOMCursor`</span>, [`Fetch`](../fetch_api), [`FileReader`](../filereader), [`FileReaderSync`](../filereadersync) (only works in workers!), [`FormData`](../formdata), [`ImageData`](../imagedata), [`IndexedDB`](../indexeddb_api), [Network Information API](../network_information_api), [`Notifications`](../notifications_api), [`Performance`](../performance), [`PerformanceEntry`](../performanceentry), [`PerformanceMeasure`](../performancemeasure), [`PerformanceMark`](../performancemark), [`PerformanceObserver`](../performanceobserver), [`PerformanceResourceTiming`](../performanceresourcetiming), [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), [Server-sent events](../server-sent_events), [`ServiceWorkerRegistration`](../serviceworkerregistration), [`TextEncoder`](../textencoder) and [`TextDecoder`](../textdecoder), [`URL`](../url), [WebGL](../webgl_api) with [`OffscreenCanvas`](../offscreencanvas) (enabled behind a feature preference setting `gfx.offscreencanvas.enabled`), [`WebSocket`](../websocket), [`XMLHttpRequest`](../xmlhttprequest).

Workers can also spawn other workers, so these APIs are also available: [`Worker`](../worker), [`WorkerGlobalScope`](../workerglobalscope), [`WorkerLocation`](../workerlocation), [`WorkerNavigator`](../workernavigator).

See also
--------

-   [Using web workers](using_web_workers)
-   [`Worker`](../worker)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers</a>
