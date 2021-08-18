Window.showDirectoryPicker()
============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `showDirectoryPicker()` method of the [`Window`](../window) interface displays a directory picker which allows the user to select a directory.

Syntax
------

    var FileSystemDirectoryHandle = Window.showDirectoryPicker();

### Parameters

None.

### Return value

A [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle).

### Exceptions

`AbortError`  
Thrown if the user dismisses the prompt without making a selection, or if the user agent deems the selected content to be too sensitive or dangerous

Examples
--------

This asynchronous function shows a directory picker and returns a [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) once selected.

    async function getDir() {
      const dirHandle = await window.showDirectoryPicker();

      // run code for dirHandle
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="about:unknown#api-showdirectorypicker">Unknown<br />
<span class="small">The definition of 'showDirectoryPicker' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

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

`showDirectoryPicker`

86

86

No

No

72

No

No

No

No

No

No

No

See also
--------

-   [File System Access API](../file_system_access_api)
-   [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/showDirectoryPicker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/showDirectoryPicker</a>
