# FileSystemFileEntry.file()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`FileSystemFileEntry`](../filesystemfileentry) interface's method ` file``() ` returns a [`File`](../file) object which can be used to read data from the file represented by the directory entry.

## Syntax

    FileSystemFileEntry.file(successCallback[, errorCallback]);

### Parameters

`successCallback`  
A callback function which is called when the [`File`](../file) has been created successfully; the `File` is passed into the callback as the only parameter.

`errorCallback` <span class="badge inline optional">Optional</span>  
If provided, this must be a method which is called when an error occurs while trying to create the [`File`](../file). This callback receives as input a [`FileError`](../fileerror) object describing the error.

Editor's note: We need to find out what kinds of errors can occur and document them.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Example

This example establishes a method, `readFile()`, reads a text file and calls a specified callback function with the received text (in a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object) once the read is completed. If an error occurs, a specified (optional) error callback is called.

    function readFile(entry, successCallback, errorCallback) {
      entry.file(function(file) {
        let reader = new FileReader();

        reader.onload = function() {
          successCallback(reader.result);
        };

        reader.onerror = function() {
          errorCallback(reader.error);
        }

        reader.readAsText(file);
      }, errorCallback);
    }

This function calls `file()`, specifying as its success callback a method which proceeds to use a [`FileReader`](../filereader) to read the file as text. The FileReader's `load` event handler is set up to deliver the loaded string to the `successCallback` specified when the `readFile()` method was called; similarly, its `error` handler is set up to call the `errorCallback` specified.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystemfileentry-file">File and Directory Entries API<br />
<span class="small">The definition of 'file()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`file`

8

79

50

No

No

11.1

≤37

18

50

No

11.3

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileEntry/file" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFileEntry/file</a>
