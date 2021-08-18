ServiceWorkerContainer.register()
=================================

The `register()` method of the [`ServiceWorkerContainer`](../serviceworkercontainer) interface creates or updates a [`ServiceWorkerRegistration`](../serviceworkerregistration) for the given `scriptURL`.

If successful, a service worker registration ties the provided script URL to a *scope*, which is subsequently used for navigation matching. You can call this method unconditionally from the controlled page. I.e., you don't need to first check whether there's an active registration.

There is frequent confusion surrounding the meaning and use of *scope*. Since a service worker can't have a scope broader than its own location, only use the `scope` option when you need a scope that is narrower than the default.

Syntax
------

    serviceWorkerContainer.register(scriptURL, options)
      .then(function(serviceWorkerRegistration) { ... });

### Parameters

`scriptURL`  
The URL of the service worker script. The registered service worker file needs to have a valid [JavaScript MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#javascript_types).

 `options` <span class="badge inline optional">Optional</span>   
An object containing registration options. Currently available options are:

-   `scope`: A [`USVString`](../usvstring) representing a URL that defines a service worker's registration scope; that is, what range of URLs a service worker can control. This is usually a relative URL. It is relative to the base URL of the application. By default, the `scope` value for a service worker registration is set to the directory where the service worker script is located. See the [Examples](#examples) section for more information on how it works.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`ServiceWorkerRegistration`](../serviceworkerregistration) object.

Examples
--------

The examples described here should be taken together to get a better understanding of how service workers scope applies to a page.

The following example uses the default value of `scope` (by omitting it). The service worker code in this case, if included in `example.com/index.html`, will control `example.com/index.html`, as well as pages underneath it, like `example.com/product/description.html`.

    if ('serviceWorker' in navigator) {
      // Register a service worker hosted at the root of the
      // site using the default scope.
      navigator.serviceWorker.register('/sw.js').then(function(registration) {
        console.log('Service worker registration succeeded:', registration);
      }, /*catch*/ function(error) {
        console.log('Service worker registration failed:', error);
      });
    } else {
      console.log('Service workers are not supported.');
    }

The following code, if included in `example.com/index.html`, at the root of a site, would apply to exactly the same pages as the example above. Remember the scope, when included, uses the page's location as its base.

Alternatively, if this code were included in a page at `example.com/product/description.html`, with the Javascript file residing at `example.com/product/sw.js`, then the service worker would only apply to resources under `example.com/product`.

    if ('serviceWorker' in navigator) {
      // declaring scope manually
      navigator.serviceWorker.register('/sw.js', {scope: './'}).then(function(registration) {
        console.log('Service worker registration succeeded:', registration);
      }, /*catch*/ function(error) {
        console.log('Service worker registration failed:', error);
      });
    } else {
      console.log('Service workers are not supported.');
    }

There is frequent confusion surrounding the meaning and use of *scope*. Since a service worker can't have a scope broader than its own location, only use the `scope` option when you need a scope that is narrower than the default.

The following code, if included in `example.com/index.html`, at the root of a site, would only apply to resources under `example.com/product`.

    if ('serviceWorker' in navigator) {
      // declaring scope manually
      navigator.serviceWorker.register('/sw.js', {scope: '/product/'}).then(function(registration) {
        console.log('Service worker registration succeeded:', registration);
      }, /*catch*/ function(error) {
        console.log('Service worker registration failed:', error);
      });
    } else {
      console.log('Service workers are not supported.');
    }

However, Servers can remove this restriction by setting a <a href="https://w3c.github.io/ServiceWorker/#service-worker-allowed" id="ref-for-service-worker-allowed">Service-Worker-Allowed</a> header on the service worker script, and then you can specify a max scope for that service worker above the service worker's location.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#dom-serviceworkercontainer-register">Service Workers<br />
<span class="small">The definition of 'ServiceWorkerContainer: register' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`register`

40

17

44

[Extended Support Releases (ESR)](https://www.mozilla.org/en-US/firefox/organizations/) before Firefox 78 ESR do not support service workers and the Push API.

No

27

11.1

40

40

44

27

11.3

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/register" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorkerContainer/register</a>
