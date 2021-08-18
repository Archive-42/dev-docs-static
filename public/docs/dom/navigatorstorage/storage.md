# NavigatorStorage.storage

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `NavigatorStorage.storage` read-only property returns the singleton [`StorageManager`](../storagemanager) object used to access the overall storage capabilities of the browser for the current site or app. The returned object lets you examine and configure persistence of data stores and learn approximately how much more space your browser has available for local storage use.

## Syntax

    var storageManager = navigator.storage;

### Value

A [`StorageManager`](../storagemanager) object you can use to maintain persistence for stored data, as well as to determine roughly how much room there is for data to be stored.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://storage.spec.whatwg.org/#navigatorstorage">Storage<br />
<span class="small">The definition of 'navigator.storage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`storage`

55

79

57

No

42

No

55

55

57

42

No

6.0

## See also

- [`NavigatorStorage`](../navigatorstorage)
- [`StorageManager`](../storagemanager)
- [`Navigator`](../navigator)
- [`WorkerNavigator`](../workernavigator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage/storage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorStorage/storage</a>
