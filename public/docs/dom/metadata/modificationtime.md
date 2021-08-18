# Metadata.modificationTime

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The read-only `modificationTime` property of the [`Metadata`](../metadata) interface is a [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) object which specifies the date and time the file system entry (or the data referenced by the entry) was last modified.A file system entry is considered to have been modified if the metadata or the contents of the referenced file (or directory, or whatever other kind of file system entry might exist on the platform in use) has changed.

## Syntax

    var modificationTime = Metadata.modificationTime;

### Value

A [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) timestamp indicating when the file system entry was last changed.

## Example

This example tries to get a particular working file at `tmp/workfile.json`. Once that file has been found, its metadata is obtained and the file's modification timestamp year is compared to the current year. If it was last modified in a year at least five prior to the current year, the file is removed and a new one is created.

    workingDirectory.getFile("tmp/workfile.json", { create: true }, function(fileEntry) {
      fileEntry.getMetadata(function(metadata) {
        if ((new Date().getFullYear() - metadata.modificationTime.getFullYear()) >= 5) {
          fileEntry.remove(function() {
            workingDirectory.getFile("tmp/workfile.json", { create: true }, function(newEntry) {
              fileEntry = newEntry;
            });
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

`modificationTime`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Metadata/modificationTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Metadata/modificationTime</a>
