# FileSystemDirectoryHandle

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `FileSystemDirectoryHandle` interface of the [`File System Access API`](file_system_access_api) provides a handle to a file system directory. The interface is accessed via the [`window.showDirectoryPicker()`](window/showdirectorypicker) method.

## Properties

_Inherits properties from its parent, [`FileSystemHandle`](filesystemhandle)._

## Methods

_Inherits methods from its parent, [`FileSystemHandle`](filesystemhandle)._

[`FileSystemDirectoryHandle.entries()`](filesystemdirectoryhandle/entries)  
Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of a given object's own enumerable property `[key, value]` pairs

[`FileSystemDirectoryHandle.getFileHandle()`](filesystemdirectoryhandle/getfilehandle)  
Returns a [`FileSystemFileHandle`](filesystemfilehandle) for a file with the specified name, within the directory the method is called.

[`FileSystemDirectoryHandle.getDirectoryHandle()`](filesystemdirectoryhandle/getdirectoryhandle)  
Returns a [`FileSystemDirectoryHandle`](filesystemdirectoryhandle) for a subdirectory with the specified name within the directory handle on which the method is called.

[`FileSystemDirectoryHandle.keys()`](filesystemdirectoryhandle/keys)  
Returns a new Array Iterator containing the keys for each item in `FileSystemDirectoryHandle`.

[`FileSystemDirectoryHandle.removeEntry()`](filesystemdirectoryhandle/removeentry)  
Attempts to remove an entry if the directory handle contains a file or directory called the name specified.

[`FileSystemDirectoryHandle.resolve()`](filesystemdirectoryhandle/resolve)  
Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of directory names from the parent handle to the specified child entry, with the name of the child entry as the last array item.

[`FileSystemDirectoryHandle.values()`](filesystemdirectoryhandle/values)  
Returns a new Array Iterator containing the values for each index in the `FileSystemDirectoryHandle` object.

## Examples

The following example returns a directory handle with the specified name, if the directory does not exist it is created.

    const dirName = 'directoryToGetName';

    // assuming we have a directory handle: 'currentDirHandle'
    const subDir = currentDirHandle.getDirectoryHandle(dirName, {create: true});

The following asynchronous function uses `resolve()` to find the path to a chosen file, relative to a specified directory handle.

    async function returnPathDirectories(directoryHandle) {

      // Get a file handle by showing a file picker:
      const handle = await self.showOpenFilePicker();
      if (!handle) {
        // User cancelled, or otherwise failed to open a file.
        return;
      }

      // Check if handle exists inside directory our directory handle
      const relativePaths = await directoryHandle.resolve(handle);

      if (relativePath === null) {
        // Not inside directory handle
      } else {
        // relativePath is an array of names, giving the relative path

        for (const name of relativePaths) {
          // log each entry
          console.log(name);
        }
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#api-filesystemdirectoryhandle">File System Access API<br />
<span class="small">The definition of 'FileSystemDirectoryHandle' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FileSystemDirectoryHandle`

86

86

No

No

72

No

No

86

No

No

No

14.0

`entries`

86

86

No

No

72

No

No

86

No

No

No

14.0

`getDirectoryHandle`

86

86

No

No

72

No

No

86

No

No

No

14.0

`getFileHandle`

86

86

No

No

72

No

No

86

No

No

No

14.0

`keys`

86

86

No

No

72

No

No

86

No

No

No

14.0

`removeEntry`

86

86

No

No

72

No

No

86

No

No

No

14.0

`resolve`

86

86

No

No

72

No

No

86

No

No

No

14.0

`values`

86

86

No

No

72

No

No

86

No

No

No

14.0

## See also

- [File System Access API](file_system_access_api)
- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemDirectoryHandle</a>
