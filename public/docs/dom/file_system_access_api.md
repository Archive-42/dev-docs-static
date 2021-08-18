# File System Access API

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The File System Access API allows read, write and file management capabilities.

## Concepts and Usage

This API allows interaction with files on a user's local device, or on a user-accessible network file system. Core functionality of this API includes reading files, writing or saving files, and access to directory structure.

Most of the interaction with files and directories is accomplished through handles. A parent [`FileSystemHandle`](filesystemhandle) class helps define two child classes: [`FileSystemFileHandle`](filesystemfilehandle) and [`FileSystemDirectoryHandle`](filesystemdirectoryhandle), for files and directories respectively.

These handles represent the file or directory on the user's system. You must first gain access to them by showing the user a file or directory picker. The methods which allow this are [`window.showOpenFilePicker`](window/showopenfilepicker) and [`window.showDirectoryPicker`](window/showdirectorypicker). Once these are called, the file picker presents itself and the user selects either a file or directory. Once this happens successfully, a handle is returned. You can also gain access to file handles via the [`DataTransferItem.getAsFileSystemHandle()`](datatransferitem/getasfilesystemhandle) method of the [`HTML Drag and Drop API`](html_drag_and_drop_api).

The handle provides its own functionality and there are a few differences depending on whether a file or directory was selected (see the [interfaces](#interfaces) section for specific details). You then can access file data, or information (including children) of the directory selected.

There is also “save” functionality, using the [`FilesystemWritableFileStream`](filesystemwritablefilestream) interface. Once the data you'd like to save is in a format of [`Blob`](blob), [`USVString`](usvstring) or [`buffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), you can open a stream and save the data to a file. This can be the existing file or a new file.

This API opens up potential functionality the web has been lacking. Still, security has been of utmost concern when designing the API, and access to file/directory data is disallowed unless the user specifically permits it.

## Interfaces

[`FileSystemHandle`](filesystemhandle)  
The `FileSystemHandle` interface is an object which represents an entry. Multiple handles can represent the same entry. For the most part you do not work with `FileSystemEntry` directly but rather it's child interfaces [`FileSystemFileEntry`](filesystemfileentry) and [`FileSystemDirectoryEntry`](filesystemdirectoryentry).

[`FileSystemFileHandle`](filesystemfilehandle)  
Provides a handle to a file system entry.

[`FileSystemDirectoryHandle`](filesystemdirectoryhandle)  
provides a handle to a file system directory.

[`FileSystemWritableFileStream`](filesystemwritablefilestream)  
is a [`WritableStream`](writablestream) object with additional convenience methods, which operates on a single file on disk.

## Examples

### Accessing files

The below code allows the user to choose a file from the file picker and then tests to see whether the handle returned is a file or directory

    // store a reference to our file handle
    let fileHandle;

    async function getFile() {
      // open file picker
      [fileHandle] = await window.showOpenFilePicker();

      if (fileHandle.kind === 'file') {
        // run file code
      } else if (fileHandle.kind === 'directory') {
        // run directory code
      }

    }

The following asynchronous function presents a file picker and once a file is chosen, uses the `getFile()` method to retrieve the contents.

    const pickerOpts = {
      types: [
        {
          description: 'Images',
          accept: {
            'image/*': ['.png', '.gif', '.jpeg', '.jpg']
          }
        },
      ],
      excludeAcceptAllOption: true,
      multiple: false
    };

    async function getTheFile() {
      // open file picker
      [fileHandle] = await window.showOpenFilePicker(pickerOpts);

      // get file contents
      const fileData = await fileHandle.getFile();
    }

### Accessing directories

The following example returns a directory handle with the specified name. If the directory does not exist, it is created.

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

### Writing to files

The following asynchronous function opens the save file picker, which returns a [`FileSystemFileHandle`](filesystemfilehandle) once a file is selected. A writable stream is then created using the [`FileSystemFileHandle.createWritable()`](filesystemfilehandle/createwritable) method.

A user defined [`Blob`](blob) is then written to the stream which is subsequently closed.

    async function saveFile() {

      // create a new handle
      const newHandle = await window.showSaveFilePicker();

      // create a FileSystemWritableFileStream to write to
      const writableStream = await newHandle.createWritable();

      // write our file
      await writableStream.write(imgBlob);

      // close the file and write the contents to disk.
      await writableStream.close();
    }

The following show different examples of options that can be passed into the `write()` method.

    // just pass in the data (no options)
    writableStream.write(data)

    // writes the data to the stream from the determined position
    writableStream.write({ type: "write", position: position, data: data })

    // updates the current file cursor offset to the position specified
    writableStream.write({ type: "seek", position: position })

    // resizes the file to be size bytes long
    writableStream.write({ type: "truncate", size: size })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/file-system-access/">File System Access API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.FileSystemAccess`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [The File System Access API: simplifying access to local files](https://web.dev/file-system-access/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API</a>
