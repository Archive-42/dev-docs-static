# Metadata.size

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The read-only `size` property of the [`Metadata`](../metadata) interface specifies the size, in bytes, of the referenced file or other file system object on disk.

## Syntax

    var size = Metadata.size;

### Value

A number indicating the size of the file in bytes.

## Example

This example checks the size of a log file and removes it if it's larger than a megabyte.

    workingDirectory.getFile("log/important.log", {}, function(fileEntry) {
      fileEntry.getMetadata(function(metadata) {
        if (metadata.size > 1048576) {
          fileEntry.remove(function() {
            /* log file removed; do something clever here */
          });
        }
      });
    }, handleError);

This API has no official W3C or WHATWG specification.

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

`size`

13

≤79

No

No

No

No

No

Yes

No

No

No

Yes

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`Metadata`](../metadata)
- [`FileSystemEntry.getMetadata()`](../filesystementry/getmetadata)
- [`FileSystemFileEntry`](../filesystemfileentry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Metadata/size" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Metadata/size</a>
