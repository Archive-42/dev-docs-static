# FileSystem

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The File and Directory Entries API interface `FileSystem` is used to represent a file system. These objects can be obtained from the [`filesystem`](filesystementry/filesystem) property on any file system entry. Some browsers offer additional APIs to create and manage file systems, such as Chrome's [`requestFileSystem()`](window/requestfilesystem) method.

This interface will not grant you access to the users filesystem. Instead you will have a "virtual drive" within the browser sandbox. If you want to gain access to the users filesystem you need to invoke the user by eg. installing a Chrome extension. The relevant Chrome API can be found [here](https://developer.chrome.com/apps/fileSystem).

## Basic concepts

There are two ways to get access to a `FileSystem` object:

1.  You can directly ask for one representing a sandboxed file system created just for your web app directly by calling `window.requestFileSystem()`. If that call is successful, it executes a callback handler, which receives as a parameter a `FileSystem` object describing the file system.
2.  You can get it from a file system entry object, through its [`filesystem`](filesystementry/filesystem) property.

## Properties

[`FileSystem.name`](filesystem/name) <span class="badge inline readonly">Read only </span>  
A [`USVString`](usvstring) representing the file system's name. This name is unique among the entire list of exposed file systems.

[`FileSystem.root`](filesystem/root) <span class="badge inline readonly">Read only </span>  
A [`FileSystemDirectoryEntry`](filesystemdirectoryentry) object which represents the file system's root directory. Through this object, you can gain access to all files and directories in the file system.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#api-domfilesystem">File and Directory Entries API<br />
<span class="small">The definition of 'FileSystem' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`FileSystem`

7

≤18

Edge only supports this API in drag-and-drop scenarios using the the `DataTransferItem.webkitGetAsEntry()` method. It's not available for use in file or folder picker panels (such as when you use an `<input>` element with the `HTMLInputElement.webkitdirectory` attribute.

50

No

15

11.1

≤37

18

50

14

11.3

1.0

`name`

7

≤18

50

No

15

11.1

≤37

18

50

14

11.3

1.0

`root`

7

≤18

50

No

15

11.1

≤37

18

50

14

11.3

1.0

## See also

- [File and Directory Entries API](file_and_directory_entries_api)
- [Introduction to the File System API](file_and_directory_entries_api/introduction)
- [`FileSystemEntry`](filesystementry), [`FileSystemFileEntry`](filesystemfileentry), and [`FileSystemDirectoryEntry`](filesystemdirectoryentry)
- MSDN article: [WebKitFileSystem object](https://msdn.microsoft.com/library/mt732564)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystem</a>
