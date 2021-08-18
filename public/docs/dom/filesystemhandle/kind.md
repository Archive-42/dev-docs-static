# FileSystemHandle.kind

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `kind` read-only property of the [`FileSystemHandle`](../filesystemhandle) interface returns the type of entry. This is `'file'` if the associated entry is a file or `'directory'`. It is used to distinguish files from directories when iterating over the contents of a directory.

## Syntax

    var FileSystemHandleKind = FileSystemHandle.kind;

### Value

_FileSystemHandleKind_  
Can be either:

- `'file'`: If handle is a [`FileSystemFileHandle`](../filesystemfilehandle).
- `'directory'`: If handle is a [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle).

## Examples

The following function allows the user to choose a file from the file picker and then tests to see whether the handle returned is a file or directory

    // store a reference to our file handle
    let fileHandle;

    async function getFile() {
      // open file picker
      [fileHandle] = await window.showOpenFilePicker();

      if (fileHandle.kind === 'file') {
        // run file code
      } else if (fileHandle.kind === 'directory')
        // run directory code
      }

    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/#dom-filesystemhandle-kind">File System Access API<br />
<span class="small">The definition of 'kind' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`kind`

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

- [File System Access API](../file_system_access_api)
- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/kind" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemHandle/kind</a>
