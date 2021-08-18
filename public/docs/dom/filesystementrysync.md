FileSystemEntrySync
===================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `FileSystemEntrySync` interface of the File and Directory Entries API represents an entry in a file system; it can be either a [`FileEntrySync`](fileentrysync) or [`FileSystemDirectoryEntry`](filesystemdirectoryentry). It includes methods for working with files—including copying, moving, removing, and reading files—as well as information about the file it points to—including the file name and its path from the root to the entry.

**Warning:** This API was never accepted and never became standardized. Various browsers implement pieces of the [File and Directory Entries API](file_and_directory_entries_api) (otherwise known as the File System API) but you should try to avoid using it.

Basic concepts
--------------

The `FileSystemEntrySync` interface includes methods that you would expect for manipulating files and directories, but it also include a really handy method for getting a URL of the entry: `toURL()`. It also introduces a new URL scheme: `filesystem:`.

You can use the `filesystem:` scheme on Google Chrome to see all the files and folders that are stored in the origin of your app. Just use `filesystem:` scheme for the root directory of the origin of the app. For example, if your app is in `http://ww.html5rocks.com`, open `filesystem:http://www.html5rocks.com/temporary/` in a tab. Chrome shows a read-only list of all the files and folders stored the origin of your app.

Method overview
---------------

<table><tbody><tr class="odd"><td><code>Metadata getMetadata () raises (FileException);</code></td></tr><tr class="even"><td><code>FileSystemEntrySync moveTo (in DirectoryEntrySync parent, optional DOMString newName) raises (FileException);</code></td></tr><tr class="odd"><td><code>FileSystemEntrySync copyTo(in DirectoryEntrySync parent, optional DOMString newName) raises (FileException);</code></td></tr><tr class="even"><td><code>DOMString toURL();</code></td></tr><tr class="odd"><td><code>void remove() raises (FileException);</code></td></tr><tr class="even"><td><code>DirectoryEntrySync getParent();</code></td></tr></tbody></table>

Attributes
----------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span id="attr_filesystem"><code>filesystem</code></span></td><td><code>readonly FileSystemSync</code></td><td>The file system where the entry resides.</td></tr><tr class="even"><td><span id="attr_fullpath"><code>fullpath</code></span></td><td><code>readonly DOMString</code></td><td><p>The full absolute path from the root to the entry.</p><p>An absolute path is a relative path from the root directory, prepended with a '<code>/</code>'.</p></td></tr><tr class="odd"><td><span id="attr_root"><code>isDirectory</code></span></td><td><code>readonly boolean</code></td><td>True if FileSystemEntrySync is a directory.</td></tr><tr class="even"><td><span id="attr_isfile"><code>isFile</code></span></td><td><code>readonly boolean</code></td><td>True if the FileSystemEntrySync is a file.</td></tr><tr class="odd"><td><span id="attr_name"><code>name</code></span></td><td><code>readonly DOMString</code></td><td>The name of the entry, excluding the path leading to it.</td></tr></tbody></table>

Methods
-------

### getMetadata()

Look up metadata about this entry. \[ todo: specify what kind of metadata \]

    Metadata getMetada ()
      raises (FileException);

##### Parameter

None

##### Returns

`Metadata`

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`NOT_FOUND_ERR`

The entry does not exist.

`INVALID_STATE_ERR`

The FileSystemSync is no longer valid for some reason besides being deleted.

### moveTo()

Move an entry to a different location on the file system. Moving a file over an existing file replaces that existing file. Moving a directory over an existing empty directory replaces that directory. \[todo: What if the directory is not empty? \]

\[todo: Verify \] This is the same method for renaming files. You can keep it in the same location and then define the `newName` parameter.

You cannot do the following:

-   Move a directory inside itself or to any child at any depth
-   Move an entry into its parent if a name different from its current one isn't provided
-   Move a file to a path occupied by a directory or move a directory to a path occupied by a file
-   Move any element to a path occupied by a directory that is not empty.

<!-- -->

    FileSystemEntrySync moveTo (
      in DirectoryEntrySync parent, optional DOMString newName
    ) raises (FileException);

##### Parameters

parent  
The directory to which to move the entry.

newName  
The new name of the entry. If you do not specify a name, the browser preserves the entry's current name.

##### Returns

`FileSystemEntrySync`  
An object that represents an entry in the file system.

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`ENCODING_ERR`

The name supplied is invalid, because at least one of the characters is reserved or illegal. Examples include a backslash (\\), dot (.), and two dots (..).

`NOT_FOUND_ERR`

The target directory does not exist.

`INVALID_MODIFICATION_ERR`

You tried one of the following disallowed operations:

-   Moving an entry into its parent without changing its name
-   Moving a parent directory into one of its child directories. \[todo: verify \]

`NO_MODIFICATION_ALLOWED_ERR`

One of the following is not writable: the source entry, its parent directory, and the target directory.

### copyTo()

Copy an entry to a different location on the file system. You cannot copy an entry inside itself if it is a directory, nor can you copy it into its parent without providing a new name. Directory copies are always recursive—that is, all contents of the directory are copied. You cannot change this behavior. Files are duplicated.

    void copyTo (
      in DirectoryEntrySync parent, optional DOMString newName
    ) raises (FileException);

##### Parameters

parent  
The directory where you want the entry to move to.

newName  
The new name of the entry. If you do not specify a name, the browser preserves the FileSystemEntrySync's current name.

##### Returns

`FileSystemEntrySync`  
An object that represents an entry in the file system.

##### Exceptions

This method can raise a [FileException](fileexception) with the following codes:

Exception

Description

`ENCODING_ERR`

The name supplied is invalid, because at least one of the characters is reserved or illegal. Examples include a backslash (\\), dot (.), and two dots (..).

`NOT_FOUND_ERR`

The target directory does not exist.

`INVALID_MODIFICATION_ERR`

You tried one of the following disallowed operations:

-   Moving an entry into its parent without changing its name
-   Moving a parent directory into one of its child directories.

`NO_MODIFICATION_ALLOWED_ERR`

One of the following is not writable: the source entry, its parent directory, and the target directory.

`QUOTA_EXCEEDED_ERR`

The operation would cause the application to exceed its storage quota. You can ask for a larger persistent storage, which your user must explicitly grant. For more information, see the article on [basic concepts](file_and_directory_entries_api/introduction).

### toURL()

Returns a URL that can be used to identify this entry. It exposes a new URL scheme—`filesystem:`—that you can use to fill `src` or `href `attributes. For example, if you wanted to display an image and have its [fileEntry](filesystemfileentry), calling `toURL()` gives you the image file's file system URL. You get something like: `filesystem:http://example.com/temporary/lolcat.png.`

The file system URL does not expire. Because the method describes a location on disk, the URL is valid for as long as that location exists. You can delete the file and recreate it, and it's all good.

You can supply the `mimeType` to simulate the optional MIME type header associated with HTTP downloads.

    DOMString toURL ();

##### Parameter

None.

##### Returns

`DOMString`

##### Exceptions

None

### remove()

Deletes a file or directory. You cannot delete an empty directory or the root directory of a file system. If you want to remove an empty directory, use [`removeRecursively()`](directoryentrysync#removerecursively()) instead.

    void remove (
    ) raises (FileException);

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

`INVALID_MODIFICATION_ERR`

You tried to remove a directory that is not empty. If you want to remove an empty directory, use [`removeRecursively()`](directoryentrysync#removerecursively()) instead.

`NO_MODIFICATION_ALLOWED_ERR`

One of the following is not writable: the source entry, its parent directory, and the target directory.

### getParent()

Look up the parent [`DirectoryEntrySync`](directoryentrysync) containing the entry. If this entry is the root of its file system, then the parent is itself.

    void getParent ();

##### Parameter

None

##### Returns

`DirectoryEntrySync`  
An object that represents a directory in the file system.

##### Exceptions

None.

Browser compatibility
---------------------

No compatibility data found for `api.FileSystemEntrySync`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

Specification:[File API: Directories and System Specification](https://dev.w3.org/2009/dap/file-system/pub/FileSystem/)WD

Reference: [File System API](file_and_directory_entries_api/introduction)

Introduction: [Basic Concepts About the File System API](file_and_directory_entries_api/introduction)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntrySync" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntrySync</a>
