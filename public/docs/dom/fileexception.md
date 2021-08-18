FileException
=============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

In the [File System API](file_and_directory_entries_api/introduction), a `FileException `object represents error conditions that you might encounter while accessing the file system using the synchronous API. It extends the FileException interface described in [File Writer](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/#bib-FILE-WRITER) and adds several new error codes.

Basic concepts
--------------

Synchronous APIs do not have error callbacks, which makes it difficult to catch errors. The added complexity of using [WebWorkers](worker) with this API makes debugging even more challenging. To simplify things a bit, wrap your worker code in a try/catch. When errors occur, forward them to the main app using `postMessage()` as in the following:

    function onError(e) {
      postMEssage('ERROR:' + e.toString());
    }

    try {
      //Error is thrown if "log.txt" already exists.
    var fileEntry = fs.root.getFile('log.txt', {create: true, exclusive:true}0;
    } catch (e) {
      onErrror(e);
    } 

The sample code was borrowed from [HTML5Rocks](https://www.html5rocks.com/en/tutorials/file/filesystem-sync/)

Attribute
---------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="attr_code"><code>code</code></span></td><td><code>unsigned short</code></td><td>The most appropriate error code for the condition.</td></tr></tbody></table>

Constants
---------

**Note**

Do not rely on the numeric values of the constants, which might change as the specifications continue to change. Use the constant names instead.

Constant

Value

Description

`ENCODING_ERR`

5

The URL is malformed. Make sure that the URL is complete and valid.

`INVALID_MODIFICATION_ERR`

9

The modification requested is not allowed. Examples of invalid modifications include moving a directory into its own child or moving a file into its parent directory without changing its name.

`INVALID_STATE_ERR`

7

The operation cannot be performed on the current state of the interface object. For example, the state that was cached in an interface object has changed since it was last read from disk.

`NO_MODIFICATION_ALLOWED_ERR`

6

The state of the underlying file system prevents any writing to a file or a directory.

`NOT_FOUND_ERR`

1

A required file or directory could not be found at the time an operation was processed. For example, a file did not exist but was being opened.

`NOT_READABLE_ERR`

4

The file or directory cannot be read, typically due to permission problems that occur after a reference to a file has been acquired (for example, the file or directory is concurrently locked by another application).

`PATH_EXISTS_ERR`

12

The file or directory with the same path already exists.

`QUOTA_EXCEEDED_ERR`

10

Either there's not enough remaining storage space or the storage quota was reached and the user declined to give more space to the database.

`SECURITY_ERR`

2

Access to the files were denied for one of the following reasons:

-   The files might be unsafe for access within a Web application.
-   Too many calls are being made on file resources.
-   Other unspecified security error code or situations.

`TYPE_MISMATCH_ERR`

11

The user has attempted to look up a file or directory, but the Entry found is of the wrong type. For example, the app is accessing a DirectoryEntry when the user is requesting a FileEntry.

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

`FileException`

13-29

No

No

No

No

No

No

18-29

No

No

No

1.0-3.0

See also
--------

Specification: [File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileException" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileException</a>
