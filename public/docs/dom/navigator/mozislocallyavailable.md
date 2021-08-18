Navigator.mozIsLocallyAvailable()
=================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Navigator.mozIsLocallyAvailable()` method allows add-ons to determine whether or not a given resource is available.

**Note**

Security exceptions can occur if the requested URI is not from the same origin.

Syntax
------

    navigator.mozIsLocallyAvailable(uri, ifOffline);

### Parameters

`uri`  
The URI of the resource whose availability is to be checked, as a string.

`ifOffline`  
Allows you to specify whether or not the offline resources cache should be checked; specify `true` to consider the offline resources cache.

Example
-------

    var available = navigator.mozIsLocallyAvailable("my-image-file.png", true);
    if (available) {
      /* the offline resource is present */
    } else {
      console.log("Certain needed resources are not available offline");
    }

Specifications
--------------

Not part of any specifications.

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

`mozIsLocallyAvailable`

No

No

3-35

No

No

No

No

No

4-35

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mozIsLocallyAvailable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mozIsLocallyAvailable</a>
