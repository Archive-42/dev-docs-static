# LocalFileSystemSync.requestFileSystemSync()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Draft**

This page is not complete.

The `requestFileSystemSync` method of the `LocalFileSystemSync` interface of the [File System API](../file_and_directory_entries_api/introduction) creates a new a sandboxed file system. It is intended to be used with [WebWorkers](../worker). The methods are implemented by [worker](../worker) objects.

**Warning:**

This document was last updated on March 2, 2012 and follows the [W3C Specifications (Working Draft)](https://www.w3.org/TR/file-system-api/) drafted on April 19, 2011.

This specification is more or less abandoned, failing to get significant traction.

## Syntax

    LocalFileSystemSync.requestFileSystemSync(
      unsigned short type,
      unsigned long long size
    );

### Parameters

`type`  
The storage type of the file system. The values can be either `TEMPORARY` or `PERSISTENT`.

`size`  
The storage space — in bytes — that you need for your app.

### Returns

[`FileSystemSync`](../filesystemsync)  
An object that represents the file system.

## Exceptions

This method can raise an [FileException](../fileexception) with the following code:

Exception

Description

`SECURITY_ERROR`

The application does not have permission to access the file system interface. For example, you cannot run from `file://`. For more details, see the [article on basic concepts](../file_and_directory_entries_api/introduction#you_cannot_run_your_app_from_file:.2f.2f).

## Examples

    //Taking care of the browser-specific prefix
    window.requestFileSystemSync  = window.requestFileSystemSync || window.webkitRequestFileSystemSync;

    // The first parameter defines the type of storage: persistent or temporary
    // Next, set the size of space needed (in bytes)
    // initFs is the success callback
    // And the last one is the error callback
    // for denial of access and other errors.

    var fs = requestFileSystemSync(TEMPORARY, 1024*1024 /*1MB*/);

Since this interface is synchronous, it doesn't need success and error callbacks.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dev.w3.org/2009/dap/file-system/pub/FileSystem/">File API: Directories and System Specification</a></td><td>Working Draft</td><td>Initial specification, abandoned.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.LocalFileSystemSync.requestFileSystemSync`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- <span class="page-not-created">`LocalFileSystem.requestFileSystem`</span>, asynchronous equivalent of this interface
- [File System API](../file_and_directory_entries_api/introduction)
- [Basic Concepts About the File System API](../file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LocalFileSystemSync/requestFileSystemSync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LocalFileSystemSync/requestFileSystemSync</a>
