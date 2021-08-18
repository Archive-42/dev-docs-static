Window.showSaveFilePicker()
===========================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `showSaveFilePicker()` method of the [`Window`](../window) interface shows a file picker that allows a user to save a file. Either by selecting an existing file, or entering a name for a new file.

Syntax
------

    var FileSystemFileHandle = Window.showSaveFilePicker();

### Parameters

 *options* <span class="badge inline optional">Optional</span>   
An optional object containing options, which are as follows:

-   `excludeAcceptAllOption`:A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Default `false`. By default the picker should include an option to not apply any file type filters (instigated with the type option below). Setting this option to `true` means that option is *not* available.
-   `types`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of allowed file types to save. Each item is an object with the following options:
    -   `description`: An optional description of the category of files types allowed.
    -   `accept`: An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) with the keys set to the [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types) and the values an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of file extensions (see below for an example).

### Return value

A [`FileSystemFileHandle`](../filesystemfilehandle).

### Exceptions

`AbortError`  
Thrown if the user dismisses the file picker without selecting or inputting a file, or if the user agent deems any selected files too sensitive or dangerous.

Examples
--------

The following function shows a file picker, with text files highlighted for selection.

    function getNewFileHandle() {
      const opts = {
        types: [{
          description: 'Text file',
          accept: {'text/plain': ['.txt']},
        }],
      };
      return window.showSaveFilePicker(opts);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="about:unknown#api-showsavefilepicker">Unknown<br />
<span class="small">The definition of 'showSaveFilePicker' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

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

`showSaveFilePicker`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/showSaveFilePicker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/showSaveFilePicker</a>
