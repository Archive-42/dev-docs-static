# FileSystemFlags

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FileSystemFlags` dictionary defines a set of values which are used when specifying option flags when calling certain methods in the [File and Directory Entries API](file_and_directory_entries_api). Methods which accept an options parameter of this type may specify zero or more of these flags as fields in an object, like this:

    dataDirectoryEntry.getDirectory("Workspace", { create: true }, function(entry) {
    });

Here, we see that the `create` property is provided, with a value of `true`, indicating that the directory should be created if it's not already there.

Note that these option flags currently don't have any useful meaning when used in the scope of Web content, where security precautions prevent the creation of new files or the replacement of existing ones.

## Properties

[`create`](filesystemflags/create) <span class="badge inline optional">Optional</span>  
If this property is `true`, and the requested file or directory doesn't exist, the user agent should create it. The default is `false`. The parent directory must already exist.

[`exclusive`](filesystemflags/exclusive) <span class="badge inline optional">Optional</span>  
If `true`, and the `create` option is also `true`, the file must not exist prior to issuing the call. Instead, it must be possible for it to be created newly at call time. The default is `false`.

### Values and results

The table below describes the result of each possible combination of these flags depending on whether or not the target file or directory path already exists.

Option values

File/directory condition

Result

[`create`](filesystemflags/create)

[`exclusive`](filesystemflags/exclusive)

`false`

n/a<sup>\[1\]</sup>

Path exists and matches the desired type (depending on whether the function called is `getFile()` or `getDirectory()`

The `successCallback` is called with a [`FileSystemFileEntry`](filesystemfileentry) if `getFile()` was called or a [`FileSystemDirectoryEntry`](filesystemdirectoryentry) if `getDirectory()` was called.

`false`

n/a<sup>\[1\]</sup>

Path exists but doesn't match the desired type

The `errorCallback` is called with an appropriate error code (if the callback was provided).

`true`

`false`

Path exists

The existing file or directory is removed and replaced with a new one, then the `successCallback` is called with a [`FileSystemFileEntry`](filesystemfileentry) or a [`FileSystemDirectoryEntry`](filesystemdirectoryentry), as appropriate.

`true`

`false`

Path doesn't exist

The file or directory is created, then a [`FileSystemFileEntry`](filesystemfileentry) or a [`FileSystemDirectoryEntry`](filesystemdirectoryentry) is passed to the `successCallback`, as appropriate.

`true`

`true`

Path exists

The `errorCallback` is called with an appropriate error, such as `FileError.PATH_EXISTS_ERR`.

`true`

`true`

Path doesn't exist

The file or directory is created, then a [`FileSystemFileEntry`](filesystemfileentry) or a [`FileSystemDirectoryEntry`](filesystemdirectoryentry) is passed to the `successCallback`, as appropriate.

\[1\] When `create` is `false`, the value of `exclusive` is irrelevant and ignored.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dictdef-filesystemflags">File and Directory Entries API<br />
<span class="small">The definition of 'FileSystemFlags' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`FileSystemFlags`

13

≤79

50

No

No

No

≤37

Yes

50

No

No

Yes

`create`

13

≤79

50

For security reasons, Firefox does not support creating files. This option has no effect.

No

No

No

≤37

Yes

50

For security reasons, Firefox does not support creating files. This option has no effect.

No

No

Yes

`exclusive`

13

≤79

50

For security reasons, Firefox does not support creating files. This option has no effect.

No

No

No

≤37

Yes

50

For security reasons, Firefox does not support creating files. This option has no effect.

No

No

Yes

## See also

- [File and Directory Entries API](file_and_directory_entries_api)
- [Introduction to the File System API](file_and_directory_entries_api/introduction)
- [`FileSystemDirectoryEntry`](filesystemdirectoryentry)
- [`FileSystemFileEntry`](filesystemfileentry)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFlags" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemFlags</a>
