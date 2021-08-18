# Metadata

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Metadata` interface is used by the File and Directory Entries API to contain information about a file system entry. This metadata includes the file's size and modification date and time.

This interface isn't available through the global scope; instead, you obtain a `Metadata` object describing a [`FileSystemEntry`](filesystementry) using the method [`FileSystemEntry.getMetadata()`](filesystementry/getmetadata).

## Properties

[`modificationTime`](metadata/modificationtime) <span class="badge inline readonly">Read only </span>  
A [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) object indicating the date and time the entry was modified.

[`size`](metadata/size) <span class="badge inline readonly">Read only </span>  
A 64-bit unsigned integer indicating the size of the entry in bytes.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/">File and Directory Entries API</a></td><td><span class="spec-draft">Draft</span></td><td>Draft of proposed API</td></tr></tbody></table>

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

`Metadata`

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

- [File and Directory Entries API](file_and_directory_entries_api)
- [Introduction to the File System API](file_and_directory_entries_api/introduction)
- [`FileSystemEntry`](filesystementry)
- [`FileSystemFileEntry`](filesystemfileentry) and [`FileSystemDirectoryEntry`](filesystemdirectoryentry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Metadata" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Metadata</a>
