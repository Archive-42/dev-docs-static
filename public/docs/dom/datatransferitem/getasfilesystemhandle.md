# DataTransferItem.getAsFileSystemHandle()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getAsFileSystemHandle()` method of the [`DataTransferItem`](../datatransferitem) interface returns a [`FileSystemFileHandle`](../filesystemfilehandle) if the dragged item is a file, or a [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle) if the dragged item is a directory.

## Syntax

    var handle = DataTransferItem.getAsFileSystemHandle();

### Parameters

None.

### Return value

A [`FileSystemFileHandle`](../filesystemfilehandle) or [`FileSystemDirectoryHandle`](../filesystemdirectoryhandle).

### Exceptions

None.

## Examples

This example uses the `getAsFileSystemHandle` method to return [`file handles`](../filesystemhandle) for dropped items.

    elem.addEventListener('dragover', (e) => {
      // Prevent navigation.
      e.preventDefault();
    });
    elem.addEventListener('drop', async (e) => {
      // Prevent navigation.
      e.preventDefault();

      // Process all of the items.
      for (const item of e.dataTransfer.items) {
        // kind will be 'file' for file/directory entries.
        if (item.kind === 'file') {
        const entry = await item.getAsFileSystemHandle();
          if (entry.kind === 'file') {
            // run code for if entry is a file
          } else if (entry.kind === 'directory') {
            // run code for is entry is a directory
          }
        }
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="about:unknown#drag-and-drop">Unknown<br />
<span class="small">The definition of 'getAsFileSystemHandle' in that specification.</span></a></td><td><span class="spec-">Unknown</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAsFileSystemHandle`

86

86

No

No

72

No

No

No

No

No

No

No

## See also

- [File System Access API](../file_system_access_api)
- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/getAsFileSystemHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/getAsFileSystemHandle</a>
