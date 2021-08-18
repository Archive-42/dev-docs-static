# FileEntrySync

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `FileEntrySync` interface of the [File System API](file_and_directory_entries_api/introduction) represents a file in a file system. It lets you write content to a file.

Inherits from: [EntrySync](filesystementrysync)

## About this document

This document was last updated on March 2, 2012 and follows the [W3C Specifications (Working Draft)](https://www.w3.org/TR/file-system-api/) drafted on April 19, 2011.

This specification is more or less abandoned as it didn't get significant traction among browser makers.

## Basic concepts

To write content to file, create a FileWriter object by calling [`createWriter()`](#createwriter).

## Method overview

<table><tbody><tr class="odd"><td><code>FileWriterSync createWriter () raises (FileException);</code></td></tr><tr class="even"><td><code>File file () raises (FileException);</code></td></tr></tbody></table>

## Methods

### createWriter()

Creates a new `FileWriter` associated with the file that the `FileEntry` represents.

    void createWriter (
    ) raises (FileException);

##### Parameter

None.

##### Returns

`FileWriterSync`

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`NOT_FOUND_ERR`

The file does not exist.

`INVALID_STATE_ERR`

The file is no longer valid for some reason other than it having been deleted.

### file()

Returns a File that represents the current state of the file that this `FileEntry` represents.

    void file (
    ) raises (FileException);

##### Parameter

None.

##### Returns

`File`

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`NOT_FOUND_ERR`

The file does not exist.

`INVALID_STATE_ERR`

The file is no longer valid for some reason other than it having been deleted.

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

`FileEntrySync`

13

≤79

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

Specification:[File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileEntrySync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileEntrySync</a>
