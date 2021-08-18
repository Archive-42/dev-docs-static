# FileSystemEntry.filesystem

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only `filesystem` property of the [`FileSystemEntry`](../filesystementry) interface contains a [`FileSystem`](../filesystem) object that represents the file system on which the entry resides.

## Syntax

    var filesystem = FileSystemEntry.filesystem;

### Value

A [`FileSystem`](../filesystem) representing the file system on which the file or directory described by the `FileSystemEntry` is located..

## Example

This example obtains a [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) for the root directory of the file system containing a file.

    let rootDirEntry = fileEntry.filesystem.root;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-filesystementry-filesystem">File and Directory Entries API<br />
<span class="small">The definition of 'filesystem' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`filesystem`

8

79

50

No

No

11.1

≤37

18

50

No

11.3

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`FileSystemEntry`](../filesystementry)
- [`FileSystem`](../filesystem)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/filesystem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/filesystem</a>
