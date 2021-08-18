FetchEvent
==========

This is the event type for `fetch` events dispatched on the [service worker global scope](serviceworkerglobalscope). It contains information about the fetch, including the request and how the receiver will treat the response. It provides the [`event.respondWith()`](fetchevent/respondwith) method, which allows us to provide a response to this fetch.

Constructor
-----------

[`FetchEvent()`](fetchevent/fetchevent)  
Creates a new `FetchEvent` object. This constructor is not typically used. The browser creates these objects itself and provides them to `fetch` event callbacks.

Properties
----------

*Inherits properties from its ancestor, [`Event`](event)*.

 [`FetchEvent.clientId`](fetchevent/clientid) <span class="badge inline readonly">Read only </span>   
The [`id`](client/id) of the same-origin [`client`](client) that initiated the fetch.

 [`FetchEvent.preloadResponse`](fetchevent/preloadresponse) <span class="badge inline readonly">Read only </span>   
A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) for a [`Response`](response), or `undefined` if this fetch is not a navigation, or [navigation preload](navigationpreloadmanager) is not enabled.

 [`FetchEvent.replacesClientId`](fetchevent/replacesclientid) <span class="badge inline readonly">Read only </span>   
The [`id`](client/id) of the [`client`](client) that is being replaced during a page navigation.

 [`FetchEvent.resultingClientId`](fetchevent/resultingclientid) <span class="badge inline readonly">Read only </span>   
The [`id`](client/id) of the [`client`](client) that replaces the previous client during a page navigation.

 [`FetchEvent.request`](fetchevent/request) <span class="badge inline readonly">Read only </span>   
The [`Request`](request) the browser intends to make.

Methods
-------

*Inherits methods from its parent, [`ExtendableEvent`](extendableevent)*.

[`FetchEvent.respondWith()`](fetchevent/respondwith)  
Prevent the browser's default fetch handling, and provide (a promise for) a response yourself.

[`ExtendableEvent.waitUntil()`](extendableevent/waituntil)  
Extends the lifetime of the event. Used to notify the browser of tasks that extend beyond the returning of a response, such as streaming and caching.

Examples
--------

This fetch event uses the browser default for non-GET requests. For GET requests it tries to return a match in the cache, and falls back to the network. If it finds a match in the cache, it asynchronously updates the cache for next time.

    self.addEventListener('fetch', event => {
      // Let the browser do its default thing
      // for non-GET requests.
      if (event.request.method != 'GET') return;

      // Prevent the default, and handle the request ourselves.
      event.respondWith(async function() {
        // Try to get the response from a cache.
        const cache = await caches.open('dynamic-v1');
        const cachedResponse = await cache.match(event.request);

        if (cachedResponse) {
          // If we found a match in the cache, return it, but also
          // update the entry in the cache in the background.
          event.waitUntil(cache.add(event.request));
          return cachedResponse;
        }

        // If we didn't find a match in the cache, use the network.
        return fetch(event.request);
      }());
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-fetchevent-fetchevent">Service Workers<br />
<span class="small">The definition of 'FetchEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FetchEvent`

40

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

`FetchEvent`

40

≤18

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

No

40

40

44

27

No

4.0

`client`

42

≤79

44

No

27

No

42

44

No

?

No

4.0

`clientId`

49

≤79

45

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

36

No

49

49

45

36

No

5.0

`isReload`

45

17

44-74

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

32

No

45

45

44

32

No

5.0

`navigationPreload`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

`preloadResponse`

59

18

?

No

46

No

59

59

?

43

No

7.0

`replacesClientId`

No

18-79

65

No

No

No

No

No

65

No

No

No

`request`

Yes

≤79

44

No

Yes

No

Yes

Yes

?

Yes

No

Yes

`respondWith`

42

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

≤79

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

59

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)).

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

29

No

42

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

42

NetworkError thrown if request mode is same-origin and response type is cors (see [bug 1222008](https://bugzil.la/1222008)). This is being worked on - see <https://www.chromestatus.com/feature/5694278818856960>.

?

29

No

4.0

`resultingClientId`

72

18

65

No

60

No

72

72

65

50

No

11.0

`targetClientId`

?

?

?

No

?

No

?

?

?

?

No

?

See also
--------

-   [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
-   [Fetch API](fetch_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FetchEvent</a>
