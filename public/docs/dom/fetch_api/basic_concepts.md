# Fetch basic concepts

**Draft**

This page is not complete.

The [Fetch API](../fetch_api) provides an interface for fetching resources (including across the network). It will seem familiar to anyone who has used [`XMLHttpRequest`](../xmlhttprequest), but it provides a more powerful and flexible feature set. This article explains some of the basic concepts of the Fetch API.

**Note:** This article will be added to over time. If you find a Fetch concept that you feel needs explaining better, let someone know on the [MDN discussion forum](https://discourse.mozilla-community.org/c/mdn), or [MDN Web Docs room](#) on [Matrix](https://wiki.mozilla.org/Matrix).

## In a nutshell

At the heart of Fetch are the Interface abstractions of HTTP [`Request`](../request)s, [`Response`](../response)s, [`Headers`](../headers), and [`Body`](../body) payloads, along with a [`global fetch`](../windoworworkerglobalscope/fetch) method for initiating asynchronous resource requests. Because the main components of HTTP are abstracted as JavaScript objects, it is easy for other APIs to make use of such functionality.

[Service Workers](../service_worker_api) is an example of an API that makes heavy use of Fetch.

Fetch takes the asynchronous nature of such requests one step further. The API is completely [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-based.

## Guard

Guard is a feature of [`Headers`](../headers) objects, with possible values of `immutable`, `request`, `request-no-cors`, `response`, or `none`, depending on where the header is used.

When a new [`Headers`](../headers) object is created using the [`Headers()`](../headers/headers) [constructor](https://developer.mozilla.org/en-US/docs/Glossary/Constructor), its guard is set to `none` (the default). When a [`Request`](../request) or [`Response`](../response) object is created, it has an associated [`Headers`](../headers) object whose guard is set as summarized below:

new object's type

creating constructor

guard setting of associated [`Headers`](../headers) object

[`Request`](../request)

[`Request()`](../request/request)

`request`

[`Request()`](../request/request) with [`mode`](../request/mode) of `no-cors`

`request-no-cors`

[`Response`](../response)

[`Response()`](../response/response)

`response`

[`error()`](../response/error) or [`redirect()`](../response/redirect) methods

`immutable`

A header's guard affects the [`set()`](../headers/set), [`delete()`](../headers/delete), and [`append()`](../headers/append) methods which change the header's contents. A `TypeError` is thrown if you try to modify a [`Headers`](../headers) object whose guard is `immutable`. However, the operation will work if

- guard is `request` and the header name isn't a [forbidden header name](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name) .
- guard is `request-no-cors` and the header name/value is a [simple header](https://developer.mozilla.org/en-US/docs/Glossary/Simple_header) .
- guard is `response` and the header name isn't a [forbidden response header name](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_response_header_name) .

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Basic_concepts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Basic_concepts</a>
