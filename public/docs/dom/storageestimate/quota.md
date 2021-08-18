StorageEstimate.quota
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`StorageEstimate`](../storageestimate) dictionary's `quota` property is a conservative approximation of how much storage is allotted to the origin or Web app that called [`StorageManager.estimate()`](../storagemanager/estimate); there may be more space available, but there will not be less. This value is an estimate to help prevent its use for fingerprinting—that is, identifying a device using an amalgamation of the values of seemingly innocuous properties.

Syntax
------

    quota = StorageEstimate.quota;

### Value

A numeric value specifying an approximation of the total amount of storage space available for use by the application.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#dom-storageestimate-quota">Storage<br />
<span class="small">The definition of 'quota' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`quota`

52

≤79

51

No

42

No

52

52

51

42

No

6.0

See also
--------

-   [Storage API](../storage_api)
-   [`Navigator`](../navigator)
-   [`StorageManager`](../storagemanager)
-   [`StorageEstimate`](../storageestimate)
-   [`StorageEstimate.usage`](usage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StorageEstimate/quota" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StorageEstimate/quota</a>
