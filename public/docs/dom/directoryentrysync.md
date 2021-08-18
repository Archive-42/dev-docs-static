# DirectoryEntrySync

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `DirectoryEntrySync` interface of the [File System API](file_and_directory_entries_api/introduction) represents a directory in a file system. It includes methods for creating, reading, looking up, and recursively removing files in a directory.

This interface has been abandoned: it was on a standard track and it proves not a good idea. Do not use it anymore.

## About this document

This document was last updated on March 2, 2012 and follows the [W3C Specifications (Working Draft)](https://www.w3.org/TR/file-system-api/) drafted on April 19, 2011.

This specification is pretty much abandoned, having failed to reach any substantial traction.

## Basic concepts

If you want to create subdirectories, you have to create each child directory in sequence. If you try to create a directory using a full path that includes parent directories that do not exist yet, you get an error. So create the hierarchy by recursively adding a new path after creating the parent directory.

#### Example

The `getFile()` method returns a `FileEntrySync`, which represents a file in the file system. The following creates an empty file called `seekrits.txt` in the root directory.

    var fileEntry = fs.root.getFile('seekrits.txt', {create: true});

The `getDirectory()` method returns a `DirectoryEntrySync`, which represents a file in the file system. The following creates a new directory called `superseekrit` in the root directory.

    var dirEntry = fs.root.getDirectory('superseekrit', {create: true});

## Method overview

<table><tbody><tr class="odd"><td><code>DirectoryReaderSync createReader () raises (FileException);</code></td></tr><tr class="even"><td><code>FileEntrySync getFile (in DOMString path, in optional Flags options) raises (FileException);</code></td></tr><tr class="odd"><td><code>DirectoryEntrySync getDirectory (in DOMString path, in optional Flags options) raises (FileException);</code></td></tr><tr class="even"><td><code>void removeRecursively () raises (FileException); </code></td></tr></tbody></table>

## Methods

### createReader()

Creates a new `DirectoryReaderSync` to read entries from this directory.

    DirectoryReaderSync createReader (
    ) raises (FileException);

##### Returns

`DirectoryReaderSync`  
Represents a directory in a file system.

##### Parameter

None

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`NOT_FOUND_ERR`

The directory does not exist.

`SECURITY_ERR`

The browser determined that it was not safe to look up the metadata. \[ todo: Explain why \]

### getFile()

Depending on how you've set the `options` parameter, the method either creates a file or looks up an existing file.

    void getFile (
      in DOMString path, in optional Flags options
    ) raises (FileException);

##### Parameter

path  
Either an absolute path or a relative path from the directory to the file to be looked up or created. You cannot create a file whose immediate parent does not exist. Create the parent directory first.

options  
An object literal describing the behavior of the method. If the file does not exist, it is created.

Object literal

Condition

Result

`create: true`  
`exclusive: true`

Path already exists

An error is thrown.

`create: true`  
`exclusive: false`

Path doesn't exist and no other error occurs

A file is created. If a file already exists, no error is thrown.

`create: false`  
(`exclusive` is ignored)

Path exists

The file is returned.

`create: false`  
(`exclusive` is ignored)

Path doesn't exist

An error is thrown.

`create: false`  
(`exclusive` is ignored)

Path exists, but is a directory

An error is thrown.

##### Returns

[`FileEntrySync`](fileentrysync)  
Represents a file in a file system.

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`ENCODING_ERR`

The path supplied is invalid.

`NOT_FOUND_ERR`

The path was structurally correct, but refers to a resource that does not exist.

`NO_MODIFICATION_ALLOWED_ERR`

This is a permission issue. The target directory or file is not writable.

`PATH_EXISTS_ERR`

The file already exists. You cannot create another one with the same path.

`QUOTA_EXCEEDED_ERROR`

The operation would cause the application to exceed its storage quota.

`SECURITY_ERR`

The application does not have permission to access the element referred to by path. \[ todo: Explain why \]

`TYPE_MISMATCH_ERR`

The path supplied exists, but it is not a directory.

### getDirectory()

Creates or looks up a directory. The method is similar to `getFile()` with DirectoryEntrySync being passed.

    void getDirectory (
      in DOMString path, in optional Flags options
    ) raises (FileException);

##### Parameter

path  
Either an absolute path or a relative path from the directory to the file to be looked up or created. You cannot create a file whose immediate parent does not exist. Create the parent directory first.

options  
An object literal describing the behavior of the method if the file does not exist.

Object literal

Condition

Result

`create: true`  
`exclusive: true`

Path already exists

An error is thrown.

`create: true`  
`exclusive: false`

Path doesn't exist and no other error occurs

A directory is created. If a file already exists, no error is thrown.

`create: false`  
(`exclusive` is ignored)

Path exists

The directory is returned.

`create: false`  
(`exclusive` is ignored)

Path doesn't exist

An error is thrown.

`create: false`  
(`exclusive` is ignored)

Path exists, but is a directory

An error is thrown.

##### Returns

[`DirectoryEntrySync`](directoryreadersync)  
Represents a directory in a file system.

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`ENCODING_ERR`

The path supplied is invalid.

`NOT_FOUND_ERR`

The path was structurally correct, but refers to a resource that does not exist.

`NO_MODIFICATION_ALLOWED_ERR`

This is a permission issue. The target directory or file is not writable.

`PATH_EXISTS_ERR`

The file already exists. You cannot create another one with the same path.

`QUOTA_EXCEEDED_ERROR`

The operation would cause the application to exceed its storage quota.

`SECURITY_ERR`

The application does not have permission to access the element referred to by path. \[ todo: Explain why \]

`TYPE_MISMATCH_ERR`

The path supplied exists, but it is not a directory.

### removeRecursively()

Deletes a directory and all of its contents. You cannot delete the root directory of a file system.

If you delete a directory that contains a file that cannot be removed or if an error occurs while the deletion is in progress, some of the contents might not be deleted. Catch these cases with error callbacks and retry the deletion.

    void removeRecursively (
    )  raises (FileException);

##### Parameter

None

##### Returns

`void`

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`NOT_FOUND_ERR`

The target directory does not exist.

`INVALID_STATE_ERR`

This directory is not longer valid for some reason other than being deleted.

\[todo: Explain more \]

`NO_MODIFICATION_ALLOWED_ERR`

One of the following is not writable: the directory, its parent directory, and some of the content in the directory.

`SECURITY_ERR`

The application does not have permission to access the target directory, its parent, or some of its contents.

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

`DirectoryEntrySync`

13

79

No

No

No

No

37

18

No

No

No

1.0

## See also

Specification: [File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DirectoryEntrySync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DirectoryEntrySync</a>
