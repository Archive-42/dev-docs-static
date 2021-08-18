# DataTransferItem

The `DataTransferItem` object represents one drag data item. During a _drag operation_, each [`drag event`](dragevent) has a [`dataTransfer`](dragevent/datatransfer) property which contains a [`list`](datatransferitemlist) of drag data items. Each item in the list is a `DataTransferItem` object.

This interface has no constructor.

## Properties

[`DataTransferItem.kind`](datatransferitem/kind) <span class="badge inline readonly">Read only </span>  
The _kind_ of drag data item, `string` or `file`.

[`DataTransferItem.type`](datatransferitem/type) <span class="badge inline readonly">Read only </span>  
The drag data item's type, typically a MIME type.

## Methods

[`DataTransferItem.getAsFile()`](datatransferitem/getasfile)  
Returns the [`File`](file) object associated with the drag data item (or null if the drag item is not a file).

[`DataTransferItem.getAsFileSystemHandle()`](datatransferitem/getasfilesystemhandle)  
Returns a [`FileSystemFileHandle`](filesystemfilehandle) if the dragged item is a file, or a [`FileSystemDirectoryHandle`](filesystemdirectoryhandle) if the dragged item is a directory.

[`DataTransferItem.getAsString()`](datatransferitem/getasstring)  
Invokes the specified callback with the drag data item string as its argument.

[`DataTransferItem.webkitGetAsEntry()`](datatransferitem/webkitgetasentry) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Returns an object based on [`FileSystemEntry`](filesystementry) representing the selected file's entry in its file system. This will generally be either a [`FileSystemFileEntry`](filesystemfileentry) or [`FileSystemDirectoryEntry`](filesystemdirectoryentry) object.

## Example

All of this interface's methods and properties have their own reference page, and each reference page has an example of its usage.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interaction.html#datatransferitem">HTML Living Standard<br />
<span class="small">The definition of 'DataTransferItem' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/editing.html#datatransferitem">HTML 5.1<br />
<span class="small">The definition of 'DataTransferItem' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>W3C snapshot of WHATWG</td></tr><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-datatransferitem-webkitgetasentry">File and Directory Entries API<br />
<span class="small">The definition of 'DataTransferItem.webkitGetAsEntry()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Definition of <code>webkitGetAsEntry()</code> as part of the <a href="file_and_directory_entries_api">File and Directory Entries API</a>.</td></tr></tbody></table>

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

`DataTransferItem`

11

12

50

No

12

5.1

4

18

50

No

5

1.0

`getAsFile`

11

12

50

No

12

5.1

4

18

50

No

5

1.0

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

`getAsString`

11

12

50

No

12

5.1

4

18

50

No

5

1.0

`kind`

11

12

50

No

12

5.1

4

18

50

No

5

1.0

`type`

11

12

50

No

12

5.1

4

18

50

No

5

1.0

`webkitGetAsEntry`

13

14

50

No

No

11.1

No

Yes

50

No

11.3

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem</a>
