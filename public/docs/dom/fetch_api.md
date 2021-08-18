# Fetch API

The Fetch API provides an interface for fetching resources (including across the network). It will seem familiar to anyone who has used [`XMLHttpRequest`](xmlhttprequest), but the new API provides a more powerful and flexible feature set.

**Note:** This feature is available in [Web Workers](web_workers_api).

## Concepts and usage

Fetch provides a generic definition of [`Request`](request) and [`Response`](response) objects (and other things involved with network requests). This will allow them to be used wherever they are needed in the future, whether it’s for service workers, Cache API, and other similar things that handle or modify requests and responses, or any kind of use case that might require you to generate your responses programmatically (that is, the use of computer program or personal programming instructions).

It also defines related concepts such as CORS and the HTTP Origin header semantics, supplanting their separate definitions elsewhere.

For making a request and fetching a resource, use the [`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch) method. It is implemented in multiple interfaces, specifically [`Window`](window) and [`WorkerGlobalScope`](workerglobalscope). This makes it available in pretty much any context you might want to fetch resources in.

The `fetch()` method takes one mandatory argument, the path to the resource you want to fetch. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to the [`Response`](response) to that request — as soon as the server responds with headers — **even if the server response is an HTTP error status**. You can also optionally pass in an `init` options object as the second argument (see [`Request`](request)).

Once a [`Response`](response) is retrieved, there are a number of methods available to define what the body content is and how it should be handled (see [`Body`](body)).

You can create a request and response directly using the [`Request()`](request/request) and [`Response()`](response/response) constructors, but it's uncommon to do this directly. Instead, these are more likely to be created as results of other API actions (for example, [`FetchEvent.respondWith()`](fetchevent/respondwith) from service workers).

### Differences from jQuery

The `fetch` specification differs from `jQuery.ajax()` in three main ways:

- The Promise returned from `fetch()` **won’t reject on HTTP error status** even if the response is an HTTP `404` or `500`. Instead, it will resolve normally (with `ok` status set to `false`), and it will only reject on network failure or if anything prevented the request from completing.
- `fetch()` **won’t send cross-origin cookies** unless you set the _credentials_ [init option](windoworworkerglobalscope/fetch#parameters) (to `include`).
  - In [April 2018](https://github.com/whatwg/fetch/pull/585), the spec changed the default credentials policy to `'same-origin'`. The following browsers shipped an outdated native fetch, and were updated in these versions: Firefox 61.0b13, Safari 12, Chrome 68.
  - If you are targeting older versions of these browsers, be sure to include `credentials: 'same-origin'` [init option](windoworworkerglobalscope/fetch#parameters) on all api requests that may be affected by cookies/user login state.

**Note**

Find out more about using the Fetch API features in [Using Fetch](fetch_api/using_fetch), and study concepts in [Fetch basic concepts](fetch_api/basic_concepts).

### Aborting a fetch

Browsers have started to add experimental support for the [`AbortController`](abortcontroller) and [`AbortSignal`](abortsignal) interfaces (aka The Abort API), which allow operations like Fetch and XHR to be aborted if they have not already completed. See the interface pages for more details.

## Fetch Interfaces

[`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch)  
The `fetch()` method used to fetch a resource.

[`Headers`](headers)  
Represents response/request headers, allowing you to query them and take different actions depending on the results.

[`Request`](request)  
Represents a resource request.

[`Response`](response)  
Represents the response to a request.

## Fetch mixin

[`Body`](body)  
Provides methods relating to the body of the response/request, allowing you to declare what its content type is and how it should be handled.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/">Fetch</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`Fetch_API`

42

14

39

No

29

10.1

42

42

39

29

10.3

4.0

`blob_data_support`

48

79

?

No

?

?

43

48

?

?

?

5.0

`referrerpolicy`

52

79

52

No

39

11.1

52

52

52

41

No

6.0

`signal`

66

16

57

No

53

11.1

66

66

57

47

11.3

9.0

`streaming_response_body`

43

14

Yes

No

29

10.1

43

43

No

No

10.3

4.0

## See also

- [Using Fetch](fetch_api/using_fetch)
- [ServiceWorker API](service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [Fetch polyfill](https://github.com/github/fetch)
- [Fetch basic concepts](fetch_api/basic_concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API</a>
