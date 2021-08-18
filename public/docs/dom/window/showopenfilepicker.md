Window.showOpenFilePicker()
===========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `showOpenFilePicker()` method of the [`Window`](../window) interface shows a file picker that allows a user to select a file or multiple files and returns a handle for the file(s).

Syntax
------

    var FileSystemHandles = Window.showOpenFilePicker();

### Parameters

 *options* <span class="badge inline optional">Optional</span>   
An optional object containing options, which are as follows:

-   `multiple`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Default `false`. When set to `true` multiple files may be selected.
-   `excludeAcceptAllOption`:A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Default `false`. By default the picker should include an option to not apply any file type filters (instigated with the type option below). Setting this option to `true` means that option is *not* available.
-   `types`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of allowed file types to pick. Each item is an object with the following options:
    -   `description`: An optional description of the category of files types allowed.
    -   `accept`: An [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) with the keys set to the [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types) and the values an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of file extensions (see below for an example).

### Return value

A [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`FileSystemFileHandle`](../filesystemfilehandle) objects.

### Exceptions

`AbortError`  
An AbortError is thrown if a user dismisses the prompt without making a selection or if a file selected is deemed too sensitive or dangerous to be exposed to the website.

Examples
--------

Here we set the options object for passing into the method. We'll allow a selection of image file types, with no option to allow for all files types, or multiple file selection.

    const pickerOpts = {
      types: [
        {
          description: 'Images',
          accept: {
            'image/*': ['.png', '.gif', '.jpeg', '.jpg']
          }
        },
      ],
      excludeAcceptAllOption: true,
      multiple: false
    };

Next we can create an asynchronous function which show the file picker and return the selected file.

    // create a reference for our file handle
    let fileHandle;

    async function getFile() {
      // open file picker, destructure the one element returned array
      [fileHandle] = await window.showOpenFilePicker(pickerOpts);

      // run code with our fileHandle
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-showopenfilepicker">File System Access API<br />
<span class="small">The definition of 'showOpenFilePicker' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`showOpenFilePicker`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/showOpenFilePicker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/showOpenFilePicker</a>
