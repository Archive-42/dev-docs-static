# FileSystemDirectoryEntry.getFile()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) interface's method ` getFile``() ` returns a [`FileSystemFileEntry`](../filesystemfileentry) object corresponding to a file contained somewhere within the directory subtree rooted at the directory on which it's called.

## Syntax

    FileSystemDirectoryEntry.getFile([path][, options][, successCallback][, errorCallback]);

### Parameters

`path` <span class="badge inline optional">Optional</span>  
A [`USVString`](../usvstring) specifying the path, relative to the directory on which the method is called, describing which file's entry to return.

`options` <span class="badge inline optional">Optional</span>  
An object based on the [`FileSystemFlags`](../filesystemflags) dictionary, which allows you to specify whether or not to create the entry if it's missing and if it's an error if the file already exists. These options are currently not useful in Web contexts.

`successCallback` <span class="badge inline optional">Optional</span>  
A method to be called once the [`FileSystemFileEntry`](../filesystemfileentry) has been created. The method receives a single parameter: the `FileSystemFileEntry` object representing the file in question.

`errorCallback` <span class="badge inline optional">Optional</span>  
A method to be called if an error occurs. Receives as its sole input parameter a [`FileError`](../fileerror) object describing the error which occurred.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Errors

If an error occurs and an `errorCallback` was specified, it gets called with a single parameter: a [`FileError`](../fileerror) object describing the error. The {domxref("FileError.code")}} specifies what type of error occurred, as follows:

`FileError.NOT_FOUND_ERR`  
The `create` option was not specified (or was specified as `false`), and the file doesn't exist.

`FileError.PATH_EXISTS_ERR`  
The `create` and `exclusive` options were both `true`, indicating that the file should be created but must not already exist, but the file does in fact already exist.

`FileError.SECURITY_ERR`  
The request to access the file was denied for security reasons.

`FileError.TYPE_MISMATCH_ERR`  
The path specified is not a file; it's probably a directory, but might be an unsupported file descriptor such as a pipe; this depends on the user agent to some extent.

## FileSystemFlags

The `options` parameter is an object which is based on the [`FileSystemFlags`](../filesystemflags) dictionary; it provides flags which make it possible to adjust the behavior of the `getFile()` method.

[`create`](../filesystemflags/create) <span class="badge inline optional">Optional</span>  
If this property is `true`, and the requested file or directory doesn't exist, the user agent should create it. The default is `false`. The parent directory must already exist.

[`exclusive`](../filesystemflags/exclusive) <span class="badge inline optional">Optional</span>  
If `true`, and the `create` option is also `true`, the file must not exist prior to issuing the call. Instead, it must be possible for it to be created newly at call time. The default is `false`.

### Values and results

The table below describes the result of each possible combination of these flags depending on whether or not the target file or directory path already exists.

Option values

File/directory condition

Result

[`create`](../filesystemflags/create)

[`exclusive`](../filesystemflags/exclusive)

`false`

n/a<sup>\[1\]</sup>

Path exists and matches the desired type (depending on whether the function called is `getFile()` or `getDirectory()`

The `successCallback` is called with a [`FileSystemFileEntry`](../filesystemfileentry) if `getFile()` was called or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) if `getDirectory()` was called.

`false`

n/a<sup>\[1\]</sup>

Path exists but doesn't match the desired type

The `errorCallback` is called with an appropriate error code (if the callback was provided).

`true`

`false`

Path exists

The existing file or directory is removed and replaced with a new one, then the `successCallback` is called with a [`FileSystemFileEntry`](../filesystemfileentry) or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry), as appropriate.

`true`

`false`

Path doesn't exist

The file or directory is created, then a [`FileSystemFileEntry`](../filesystemfileentry) or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) is passed to the `successCallback`, as appropriate.

`true`

`true`

Path exists

The `errorCallback` is called with an appropriate error, such as `FileError.PATH_EXISTS_ERR`.

`true`

`true`

Path doesn't exist

The file or directory is created, then a [`FileSystemFileEntry`](../filesystemfileentry) or a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) is passed to the `successCallback`, as appropriate.

\[1\] When `create` is `false`, the value of `exclusive` is irrelevant and ignored.

## Example

In this example, a function is presented whose job it is to locate within a user's app data directory a JSON file containing a user dictionary for a specified language, then load that dictionary.

    let dictionary = null;

    function loadDictionaryForLanguage(appDataDirEntry, lang) {
      dictionary = null;

      appDataDirEntry.getDirectory("Dictionaries", {}, function(dirEntry) {
        dirEntry.getFile(lang + "-dict.json", {}, function(fileEntry) {
          fileEntry.file(function(dictFile) {
            let reader = new FileReader();

            reader.addEventListener("loadend", function() {
              dictionary = JSON.parse(reader.result);
            });

            reader.readAsText(dictFile);
          });
        });
      });
    }

The `loadDictionaryForLanguage()` function starts by using `getDirectory()` to obtain the [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) object representing a subfolder named "Dictionaries" located inside the specified app data directory. The success callback for this takes the resulting directory entry object and calls [`getFile()`](getfile) to get a [`FileSystemFileEntry`](../filesystemfileentry) object representing the dictionary file; the success callback for this, in turn, creates a new [`FileReader`](../filereader) and uses it to load the contents of the file. When that is loaded successfully (as indicated by the `loadend` event being fired), the loaded text is passed into [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) to be reconstituted into a JavaScript object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystemdirectoryentry-getfile">File and Directory Entries API<br />
<span class="small">The definition of 'getFile()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getFile`

8

79

50

In Firefox, the `errorCallback`'s input parameter is a `DOMException` rather than a `FileError` object.

No

No

11.1

≤37

18

50

In Firefox, the `errorCallback`'s input parameter is a `DOMException` rather than a `FileError` object.

No

11.3

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`FileSystemFileEntry`](../filesystemfileentry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry/getFile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryEntry/getFile</a>
