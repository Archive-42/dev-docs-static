# FileSystemEntry

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `FileSystemEntry` interface of the File and Directory Entries API represents a single entry in a file system. The entry can be a file or a directory (directories are represented by the [`FileSystemDirectoryEntry`](filesystemdirectoryentry) interface). It includes methods for working with files—including copying, moving, removing, and reading files—as well as information about a file it points to—including the file name and its path from the root to the entry.

Because this is a non-standard API, whose specification is not currently on a standards track, it's important to keep in mind that not all browsers implement it, and those that do may implement only small portions of it. Check the [Browser compatibility](#browser_compatibility) section for details.

## Basic concepts

You don't create `FileSystemEntry` objects directly. Instead, you will receive an object based on this interface through other APIs. This interface serves as a base class for the [`FileSystemFileEntry`](filesystemfileentry) and [`FileSystemDirectoryEntry`](filesystemdirectoryentry) interfaces, which provide features specific to file system entries representing files and directories, respectively.

The `FileSystemEntry` interface includes methods that you would expect for manipulating files and directories, but it also includes a convenient method for obtaining the URL of the entry: `toURL()`. It also introduces a new URL scheme: `filesystem:`.

You can use the `filesystem:` scheme on Google Chrome to see all the files and folders that are stored in the origin of your app. Just use `filesystem:` scheme for the root directory of the origin of the app. For example, if your app is in `http://www.html5rocks.com`, open` filesystem:http://www.html5rocks.com/temporary/` in a tab. Chrome shows a read-only list of all the files and folders stored the origin of your app.

### Example

To see an example of how `toURL()` works, see the [method description](#tourl). The snippet below shows you how you can remove a file by name.

    // Taking care of the browser-specific prefixes.
    window.requestFileSystem  = window.requestFileSystem || window.webkitRequestFileSystem;

    ...

    // Opening a file system with temporary storage
    window.requestFileSystem(TEMPORARY, 1024*1024 /*1MB*/, function(fs) {
      fs.root.getFile('log.txt', {}, function(fileEntry) {

        fileEntry.remove(function() {
          console.log('File removed.');
        }, onError);

      }, onError);
    }, onError);

## Properties

_This interface provides the following properties._

[`filesystem`](filesystementry/filesystem) <span class="badge inline readonly">Read only </span>  
A [`FileSystem`](filesystem) object representing the file system in which the entry is located.

[`fullPath`](filesystementry/fullpath) <span class="badge inline readonly">Read only </span>  
A [`USVString`](usvstring) object which provides the full, absolute path from the file system's root to the entry; it can also be thought of as a path which is relative to the root directory, prepended with a "/" character.

[`isDirectory`](filesystementry/isdirectory) <span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the entry represents a directory; otherwise, it's `false`.

[`isFile`](filesystementry/isfile) <span class="badge inline readonly">Read only </span>  
A Boolean which is `true` if the entry represents a file. If it's not a file, this value is `false`.

[`name`](filesystementry/name) <span class="badge inline readonly">Read only </span>  
A [`USVString`](usvstring) containing the name of the entry (the final part of the path, after the last "/" character).

## Methods

_This interface defines the following methods._

[`copyTo()`](filesystementry/copyto)  
Copies the file or directory to a new location on the file system.

[`getMetadata()`](filesystementry/getmetadata)  
Obtains metadata about the file, such as its modification date and size.

[`getParent()`](filesystementry/getparent)  
Returns a [`FileSystemDirectoryEntry`](filesystemdirectoryentry) representing the entry's parent directory.

[`moveTo()`](filesystementry/moveto)  
Moves the file or directory to a new location on the file system, or renames the file or directory.

[`remove()`](filesystementry/remove)  
Removes the specified file or directory. You can only remove directories which are empty.

[`toURL()`](filesystementry/tourl)  
Creates and returns a URL which identifies the entry. This URL uses the URL scheme `"filesystem:"`.

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

`FileSystemEntry`

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

`copyTo`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

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

`fullPath`

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

`getMetadata`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

`getParent`

8

79

No

No

No

11.1

≤37

18

No

No

11.3

1.0

`isDirectory`

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

`isFile`

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

`moveTo`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

`name`

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

`remove`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

`toURL`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

## See also

- [File and Directory Entries API](file_and_directory_entries_api)
- [Introduction to the File System API](file_and_directory_entries_api/introduction)
- [`FileSystemFileEntry`](filesystemfileentry) and [`FileSystemDirectoryEntry`](filesystemdirectoryentry) are based on `FileSystemEntry`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry</a>
