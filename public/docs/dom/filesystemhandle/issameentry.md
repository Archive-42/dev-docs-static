# FileSystemHandle.isSameEntry()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `isSameEntry()` method of the [`FileSystemHandle`](../filesystemhandle) interface compares two [`handles`](../filesystemhandle) to see if the associated entries (either a file or directory) match.

## Syntax

    var Boolean = FileSystemHandle1.isSameEntry(FileSystemHandle2);

### Parameters

[`FileSystemHandle`](../filesystemhandle)  
The `FileSystemHandle` to match against the handle on which the method is invoked.

### Return value

Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` is the entries match.

### Exceptions

No exceptions are thrown.

## Examples

The following function compares a single entry with an array of entries, and returns a new array with any matching entries removed.

    function removeMatches(fileEntry, entriesArr) {

      let newArr = entriesArr.filter( entry => !fileEntry.isSameEntry(entry) )

      return newArr;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#dom-filesystemhandle-issameentry">File System Access API<br />
<span class="small">The definition of 'isSameEntry' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isSameEntry`

86

86

No

No

72

No

No

86

No

No

No

14.0

## See also

- [File System Access API](../file_system_access_api)
- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/isSameEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/isSameEntry</a>
