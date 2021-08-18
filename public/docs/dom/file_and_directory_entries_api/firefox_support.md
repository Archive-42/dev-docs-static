# File and Directory Entries API support in Firefox

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The original File System API was created to let browsers implement support for accessing a sandboxed virtual file system on the user's storage device. Work to standardize the specification was abandoned back in 2012, but by that point, Google Chrome included its own implementation of the API. Over time, a number of popular sites and Web applications came to use it, often without providing any means of falling back to standard APIs or even checking to be sure the API is available before using it. Mozilla instead opted to implement other APIs which can be used to solve many of the same problems, such as [IndexedDB](../indexeddb_api); see the blog post [Why no FileSystem API in Firefox?](https://hacks.mozilla.org/2012/07/why-no-filesystem-api-in-firefox/) for more insights.

This has caused a number of popular web sites not to work properly on browsers other than Chrome. Because of that, an attempt was made to create a spec offering the features of Google's API which consensus could be reached on. The result was the [File and Directory Entries API](../file_and_directory_entries_api). This subset of the API provided by Chrome is still not fully specified; however, for web compatibility reasons, it was decided to implement a subset of the API in Firefox; this was introduced in Firefox 50.

This article describes how the Firefox implementation of the File and Directory Entries API differs from other implementations and/or the specification.

## Chrome deviations from the specification

The largest compatibility issue still remaining is that Chrome is still using older names for many of the interfaces in the API, since they implemented a related but different specification:

<table><thead><tr class="header"><th>Name in specification</th><th>Name in Google Chrome</th></tr></thead><tbody><tr class="odd"><td><code>FileSystemDirectoryEntry</code></td><td><code>DirectoryEntry</code></td></tr><tr class="even"><td><code>FileSystemDirectoryEntrySync</code></td><td><code>DirectoryEntrySync</code></td></tr><tr class="odd"><td><code>FileSystemDirectoryReader</code></td><td><code>DirectoryReader</code></td></tr><tr class="even"><td><code>FileSystemDirectoryReaderSync</code></td><td><code>DirectoryReaderSync</code></td></tr><tr class="odd"><td><code>FileSystemEntry</code></td><td><code>Entry</code></td></tr><tr class="even"><td><code>FileSystemEntrySync</code></td><td><code>EntrySync</code></td></tr><tr class="odd"><td><code>FileSystemFileEntry</code></td><td><code>FileEntry</code></td></tr><tr class="even"><td><code>FileSystemFileEntrySync</code></td><td><code>FileEntrySync</code></td></tr></tbody></table>

Be sure to account for this in your code by allowing for both names. Hopefully Chrome will be updated soon to use the newer names!

To ensure your code will work in both Chrome and other browsers, you can include code similar to the following:

    var FileSystemDirectoryEntry = window.FileSystemDirectoryEntry || window.DirectoryEntry;
    var FileSystemEntry = window.FileSystemEntry || window.Entry;

## Limitations in Firefox

Next, let's look at limitations of the Firefox implementation of the API. In broad strokes, those limitations can be summarized as follows:

- Content scripts can't create file systems or initiate access to a file system. There are only two ways to get access to file system entries at this time:
  - The [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element, using the [`HTMLInputElement.webkitEntries`](../htmlinputelement/webkitentries) property to access an array of [`FileSystemEntry`](../filesystementry) objects describing file system entries you can then read.
  - Using drag and drop by calling the [`DataTransferItem.getAsEntry()`](../datatransferitem/webkitgetasentry) method, which lets you get a [`FileSystemFileEntry`](../filesystemfileentry) or [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) for files dropped on a drop zone.
- You can't use the `LocalFileSystem.requestFileSystem()` method to get access to a specified local file system.
- The `LocalFileSystem.resolveLocalFileSystemURL()` method isn't implemented.
- Only the asynchronous versions of the interfaces are implemented. Any interfaces with names that end in "`Sync"` aren't available.
- Firefox only supports reading from files in the file system. You can't write to them. In particular, the [`FileSystemFileEntry.createWriter()`](../filesystemfileentry/createwriter) method, used to create a <span class="page-not-created">`FileWriter`</span> to handle writing to a file, is not implemented and will just return an error.
- Firefox doesn't support the `"filesystem:"` URL scheme.

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File and Directory Entries API](introduction)
- Latest but still early specification for the [File and Directory Entries API](https://wicg.github.io/entries-api/).
- Original specification for the [File API: Directories and System](https://dev.w3.org/2009/dap/file-system/file-dir-sys.html) (often called the "FileSystem API"); Google Chrome was the only browser to implement this **abandoned** API.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API/Firefox_support" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File_and_Directory_Entries_API/Firefox_support</a>
