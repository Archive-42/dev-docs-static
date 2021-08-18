# FileError

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Represents an error that occurs while using the [`FileReader`](filereader) interface.

**Note**

This interface is obsolete per the latest specification. Use the new DOM4 [`DOMError`](domerror) interface instead.

In the [File System API](file_and_directory_entries_api/introduction), a `FileError` represents error conditions that you might encounter while accessing the file system using the asynchronous API. It extends the `FileError` interface described in [File Writer](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/#bib-FILE-WRITER) and adds several new error codes.

`FileError` objects are passed to error callbacks. The objects have a code that shows the type of error that occurred.

## Best practices

Most people don't read the page on errors and exceptions unless they're stumped. So the following are a few tips that could help you avoid some pitfalls.

### Error callbacks are not optional for your sanity

Although error callbacks are optional, you should include them in the arguments of the methods for the sake of the sanity of your users. A web app could fail for various reasons, so you don't want to spend the rest of your day guessing what's going on and going through maddening troubleshooting.

### Don't run your app from file://

For security reasons, browsers do not allow you to run your app from `file://`. In fact, many of the powerful storage APIs (such as File System, BlobBuilder, and FileReader) throw errors if you run the app locally from `file://`. When you're just testing your app, and you don't want to set up a web server, you can bypass the security restriction on Chrome. Just start Chrome with the `--allow-file-access-from-files` flag. Use the flag only for testing purposes.

## Attribute

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span><code>code</code></span></td><td><code>unsigned short</code></td><td>The most appropriate error code for the condition. See <a href="#error_codes">Error codes</a> for possible values.</td></tr></tbody></table>

## Error codes

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

The modification requested is not allowed. For example, the app might be trying to move a directory into its own child or moving a file into its parent directory without changing its name.

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

Either there's not enough remaining storage space or the storage quota was reached and the user declined to give more space to the database. To ask for more storage, see [Managing HTML5 Offline Storage](https://code.google.com/chrome/whitepapers/storage.html).

`SECURITY_ERR`

2

Access to the files were denied for one of the following reasons:

- The files might be unsafe for access within a Web application.
- Too many calls are being made on file resources.
- Other unspecified security error code or situations.

`TYPE_MISMATCH_ERR`

11

The app looked up an entry, but the entry found is of the wrong type. For example, the app is asking for a directory, when the entry is really a file.

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

`FileError`

13-53

No

Yes-13

The `FileError` interface has been removed starting with Firefox 13.0. Instead the more general [`DOMError`](https://developer.mozilla.org/docs/Web/API/DOMError) interface is used and returned by [`FileReader.error`](https://developer.mozilla.org/docs/Web/API/FileReader).

No

Yes-40

No

≤37-53

18-53

Yes-14

The `FileError` interface has been removed starting with Firefox 13.0. Instead the more general [`DOMError`](https://developer.mozilla.org/docs/Web/API/DOMError) interface is used and returned by [`FileReader.error`](https://developer.mozilla.org/docs/Web/API/FileReader).

Yes-41

No

1.0-6.0

## See also

- [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)
- [`FileReader`](filereader)
- [`File`](file)
- [`Blob`](blob)
- [Specification: FileAPI Errors and exceptions](https://www.w3.org/TR/file-system-api/#errors-and-exceptions)WD

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileError</a>
