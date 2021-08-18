LocalFileSystem
===============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `LocalFileSystem` interface of the [File System API](file_and_directory_entries_api/introduction) gives you access to a sandboxed file system. The methods are implemented by [window](window) and [worker](worker) objects.

Basic concepts
--------------

This section includes a few key concepts for the methods.

### Creating new storage

You request access to a sandboxed file system by calling `window.requestFileSystem().` The argument of a successful callback is the `FileSystem` object, which has two properties: the name and root of the file system.

You can call the method more than once if you want to create two file systems: one that's temporary and one that's persistent. (To learn more about the storage types, see the [Basic Concepts](file_and_directory_entries_api/introduction#the_file_system_api_can_use_different_storage_types) article.) In most cases, you need to create only one file system, but in a few cases, it might be useful to create a second one. For example, if you were to create a mail app, you might create a temporary storage for caching assets (like images and attachments) to speed up performance, while creating persistent storage for unique data—such as drafts of emails that were composed while offline—that should not be lost before they are backed up into the cloud.

### Using persistent storage

The `requestFileSystem()` method lets you ask for [`PERSISTENT` or `TEMPORARY` storage](file_and_directory_entries_api/introduction#the_file_system_api_can_use_different_storage_types). Persistent storage is storage that stays in the browser unless the app or the user removes it, but the user must grant you permission before you can use it. In contrast, temporary storage is automatically granted without any user permission, but it can be expunged by the browser at any time.

To use `PERSISTENT` storage with the File System API, Chrome exposes a requestQuota API. So to request storage, you need to do something like the following:

    var requestedBytes = 1024*1024*10; // 10MB

    navigator.webkitPersistentStorage.requestQuota (
        requestedBytes, function(grantedBytes) {
            window.requestFileSystem(PERSISTENT, grantedBytes, onInitFs, errorHandler);

        }, function(e) { console.log('Error', e); }
    );

Your user must grant your app permission to store data locally before your app can use persistent storage. Once your user grants it, you don't need to call `requestQuota()` again. Subsequent calls are a noop.

Another API, the Quota Management API, lets you query an origin's current quota usage and allocation using `window.webkitPersistentStorage.queryUsageAndQuota()`. To learn more, see this [StackOverflow Answer](https://stackoverflow.com/a/29662985/89484). (An older version of the API is described at [Managing HTML5 Offline Storage](https://developer.chrome.com/apps/offline_storage?csw=1).)

### Working within a single origin

The file system is sandboxed to a single origin. This means that your app cannot read, or write the files of another app's files. Your app cannot access files in an arbitrary folder (such as, My Pictures, My Documents) on the user's hard drive either. For more information about restrictions, see the [Basic Concepts](file_and_directory_entries_api/introduction#restrictions) article.

### Example

The following is a code snippet that shows how you can request a file system storage.

    //Taking care of the browser-specific prefix
    window.requestFileSystem  = window.requestFileSystem || window.webkitRequestFileSystem;

    // The first parameter defines the type of storage: persistent or temporary
    // Next, set the size of space needed (in bytes)
    // initFs is the success callback
    // And the last one is the error callback
    // for denial of access and other errors.

    window.requestFileSystem(window.PERSISTENT, 1024*1024,onInitFs,errorHandler);

Method overview
---------------

<table><tbody><tr class="odd"><td><code>void requestFileSystem (in unsigned short type, in unsigned long long size, in FileSystemCallback successCallback, in optional ErrorCallback errorCallback); </code></td></tr><tr class="even"><td><code>void resolveLocalFileSystemURL (in DOMString url, in EntryCallback successCallback, in optional ErrorCallback errorCallback);</code></td></tr></tbody></table>

Constants
---------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="const_temporary"><code>TEMPORARY</code></span></td><td><code>0</code></td><td><p>Transient storage that can be removed by the browser at its discretion.</p></td></tr><tr class="even"><td><span id="const_persistent"><code>PERSISTENT</code></span></td><td><code>1</code></td><td>Storage that stays in the browser unless the user or the app expunges it. The user must grant permission before the app can use this type of storage.</td></tr></tbody></table>

Methods
-------

### requestFileSystem()

Requests a file system where data should be stored. You access a sandboxed file system by requesting a `LocalFileSystem` object using this global method, `window.requestFileSystem()`.

    void requestFileSystem(
      in unsigned short type,
      in unsigned long long size,
      in FileSystemCallback successCallback,
      in ErrorCallback errorCallback
    );

##### Parameters

type  
The storage type of the file system. The values can be either `TEMPORARY` or `PERSISTENT`.

size  
The storage space—in bytes—that you need for your app.

successCallback  
The success callback that is called when the browser provides a file system. Its argument is the `FileSystem` object with two properties:

-   name - the unique name assigned by the browser to the file system.
-   root - the read-only `DirectoryEntry` object representing the root of the file system.

opt\_errorCallback  
The error callback that is called when errors happen or when the request to obtain the file system is denied. Its argument is the `FileError` object.

##### Returns

`void`

##### Exceptions

This method can raise an [FileError](fileerror) with the following code:

Exception

Description

`SECURITY_ERROR`

The application does not have permission to access the file system interface. For example, you cannot run from `file://`. For more details, see the [article on basic concepts](file_and_directory_entries_api/introduction#you_cannot_run_your_app_from_file:.2f.2f).

### resolveLocalFileSystemURL()

Lets you look up the entry for a file or directory with a local URL.

    void resolveLocalFileSystemURL(
      in DOMString url,
      in EntryCallback successCallback,
      in optional ErrorCallback errorCallback
    );

##### Parameters

url  
The URL of a local file in the file system.

successCallback  
The success callback that is called when the browser provides the file or directory for the supplied URL.

errorCallback  
The error callback that is called when errors happen or when the request to obtain the entry object is denied.

##### Returns

`void`

##### Exceptions

This method can raise an [FileError](fileerror) with the following code:

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

No compatibility data found for `api.LocalFileSystem`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

Specification:[File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LocalFileSystem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LocalFileSystem</a>
