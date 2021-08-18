LocalFileSystemSync
===================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `LocalFileSystemSync` interface of the [File System API](file_and_directory_entries_api/introduction) gives you access to a sandboxed file system. It is intended to be used with [WebWorkers](worker). The methods are implemented by [worker](worker) objects.

About this document
-------------------

This document was last updated on March 2, 2012 and follows the [W3C Specifications (Working Draft)](https://www.w3.org/TR/file-system-api/) drafted on April 19, 2011.

This specification is more or less abandoned, failing to get significant traction.

Basic concepts
--------------

You can request access to a sandboxed file system by requesting `LocalFileSystemSync` object from within a web worker. The global methods in the `window` object `requestFileSystemSync()` and `resolveLocalFileSystemSyncURL()` methods are exposed to the Worker's global scope. Calling `window.requestFileSystemSync()` for creates new storage for your web app.

For more concepts, see the counterpart [article for the asynchronous API](localfilesystem#basic_concepts).

### Example

    //Taking care of the browser-specific prefix
    window.requestFileSystemSync  = window.requestFileSystemSync || window.webkitRequestFileSystemSync;

    // The first parameter defines the type of storage: persistent or temporary
    // Next, set the size of space needed (in bytes)
    // initFs is the success callback
    // And the last one is the error callback
    // for denial of access and other errors.

    var fs = requestFileSystemSync(TEMPORARY, 1024*1024 /*1MB*/);

Because you are using a synchronous API, you don't need success and error callbacks.

Method overview
---------------

<table><tbody><tr class="odd"><td><code>FileSystemSync requestFileSystemSync (in unsigned short type, in long long size) raises FileException; </code></td></tr><tr class="even"><td><code>EntrySync resolveLocalFileSystemSyncURL (in DOMString url) raises FileException;</code></td></tr></tbody></table>

Constants
---------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="const_temporary"><code>TEMPORARY</code></span></td><td><code>0</code></td><td><p>Transient storage that can be removed by the browser at its discretion.</p></td></tr><tr class="even"><td><span id="const_persistent"><code>PERSISTENT</code></span></td><td><code>1</code></td><td>Storage that stays in the browser unless the user or the app expunges it.</td></tr></tbody></table>

Methods
-------

### requestFileSystemSync()

Requests a file system where data should be stored. You access a sandboxed file system by requesting a `LocalFileSystemSync` object from within a web worker using this global method, `window.requestFileSystemSync()`. \[ RESEARCH \]

    FileSystemSync requestFileSystemSync(
      in unsigned short type,
      in unsigned long long size
    );

##### Parameters

type  
The storage type of the file system. The values can be either `TEMPORARY` or `PERSISTENT`.

size  
The storage space—in bytes—that you need for your app.

##### Returns

`FileSystemSync`  
An object that represents the file system.

##### Exceptions

This method can raise an [FileException](fileexception) with the following code:

Exception

Description

`SECURITY_ERROR`

The application does not have permission to access the file system interface. For example, you cannot run from `file://`. For more details, see the [article on basic concepts](file_and_directory_entries_api/introduction#you_cannot_run_your_app_from_file:.2f.2f).

### resolveLocalFileSystemSyncURL()

Allows the user to look up the `Entry` for a file or directory referred to by a local URL.

    void resolveLocalFileSystemURL(
      in DOMString url
    );

##### Parameter

url  
The URL of a local file in the file system.

##### Returns

`EntrySync`  
An object that represents entries in the file system.

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`ENCODING_ERR`

The syntax of the URL was invalid.

`NOT_FOUND_ERR`

The URL was structurally correct, but refers to a resource that does not exist.

`SECURITY_ERR`

The application does not have permission to access the file system interface.

Browser compatibility
---------------------

No compatibility data found for `api.LocalFileSystemSync`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

Specification:[File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LocalFileSystemSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LocalFileSystemSync</a>
