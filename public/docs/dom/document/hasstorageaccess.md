# Document.hasStorageAccess()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `hasStorageAccess()` method of the [`Document`](../document) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a boolean value indicating whether the document has access to its first-party storage.

See [Storage Access API](../storage_access_api) for more information.

## Syntax

    var promise = document.hasStorageAccess();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a boolean value indicating whether the document has access to its first-party storage.

If the promise gets resolved and a user gesture event was being processed when the function was originally called, the resolve handler will run as if a user gesture was being processed, so it will be able to call APIs that require user activation.

## Examples

    document.hasStorageAccess().then(hasAccess => {
      if (hasAccess) {
        // storage access has been granted already.
      } else {
        // storage access hasn't been granted already;
        // you may want to call requestStorageAccess().
      }
    });

## Specifications

The API is currently only at the proposal stage — the standardization process has yet to begin. You can currently find specification details of the API at Apple's [Introducing Storage Access API](https://webkit.org/blog/8124/introducing-storage-access-api/) blog post, and [WHATWG HTML issue 3338 — Proposal: Storage Access API](https://github.com/whatwg/html/issues/3338).

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

`hasStorageAccess`

78

85

65

No

65

11.1

No

78

65

No

11.3

No

## See also

[Storage Access API](../storage_access_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/hasStorageAccess" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/hasStorageAccess</a>
