StorageManager.estimate()
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `estimate()` method of the [`StorageManager`](../storagemanager) interface asks the Storage Manager for how much storage the current [origin](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy) takes up (`usage`), and how much space is available (`quota`).

This method operates asynchronously, so it returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves once the information is available. The promise's fulfillment handler is called with a [`StorageEstimate`](../storageestimate) containing the usage and quota data.

Syntax
------

    const estimatePromise = StorageManager.estimate();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to an object which conforms to the [`StorageEstimate`](../storageestimate) dictionary. This dictionary contains estimates of how much space is available to the origin in [`StorageEstimate.quota`](../storageestimate/quota), as well as how much is currently used in [`StorageEstimate.usage`](../storageestimate/usage).

**The returned values are not exact;** between compression, deduplication, and obfuscation for security reasons, they will be imprecise.

You may find that the `quota` varies from origin to origin. This variance is based on factors such as:

-   How often the user visits
-   Public site popularity data
-   User engagement signals like bookmarking, adding to homescreen, or accepting push notifications

Example
-------

In this example, we obtain the usage estimates and present the percentage of storage capacity currently used to the user.

### HTML content

    <label>
      You’re currently using about <output id="percent">
      </output>% of your available storage.
    </label>

### JavaScript content

    navigator.storage.estimate().then(function(estimate) {
      document.getElementById("percent").value =
          (estimate.usage / estimate.quota * 100).toFixed(2);
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#dom-storagemanager-estimate">Storage<br />
<span class="small">The definition of 'estimate()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`estimate`

52

≤79

51

No

Yes

No

52

52

51

Yes

No

6.0

See also
--------

-   Storage API
-   [`Storage`](../storage), the object returned by [`Window.localStorage`](../window/localstorage)
-   [`StorageManager`](../storagemanager)
-   [`navigator.storage`](../navigatorstorage/storage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/estimate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageManager/estimate</a>
