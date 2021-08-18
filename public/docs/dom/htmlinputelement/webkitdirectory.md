# HTMLInputElement.webkitdirectory

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `HTMLInputElement.webkitdirectory` is a property that reflects the [`webkitdirectory`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-webkitdirectory) HTML attribute and indicates that the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element should let the user select directories instead of files. When a directory is selected, the directory and its entire hierarchy of contents are included in the set of selected items. The selected file system entries can be obtained using the [`webkitEntries`](webkitentries) property.

## Syntax

     HTMLInputElement.webkitdirectory = boolValue

### Value

A Boolean; `true` if the [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element should allow picking only directories or `false` if only files should be selectable.

## Understanding the results

After the user makes a selection, each [`File`](../file) object in `files` has its [`File.webkitRelativePath`](../file/webkitrelativepath) property set to the relative path within the selected directory at which the file is located. For example, consider this file system:

- PhotoAlbums
  - Birthdays
    - Jamie's 1st birthday
      - PIC1000.jpg
      - PIC1004.jpg
      - PIC1044.jpg
    - Don's 40th birthday
      - PIC2343.jpg
      - PIC2344.jpg
      - PIC2355.jpg
      - PIC2356.jpg
  - Vacations
    - Mars
      - PIC5533.jpg
      - PIC5534.jpg
      - PIC5556.jpg
      - PIC5684.jpg
      - PIC5712.jpg

If the user chooses `PhotoAlbums`, then the list reported by files will contain [`File`](../file) objects for every file listed above—but not the directories. The entry for `PIC2343.jpg` will have a `webkitRelativePath` of `PhotoAlbums/Birthdays/Don's 40th birthday/PIC2343.jpg`. This makes it possible to know the hierarchy even though the [`FileList`](../filelist) is flat.

**Note:** The behavior of `webkitRelativePath` is different in _Chromium &lt; 72_. See [this bug](https://bugs.chromium.org/p/chromium/issues/detail?id=124187) for further details.

## Example

In this example, a directory picker is presented which lets the user choose one or more directories. When the `change` event occurs, a list of all files contained within the selected directory hierarchies is generated and displayed.

### HTML content

    <input type="file" id="filepicker" name="fileList" webkitdirectory multiple />
    <ul id="listing"></ul>

### JavaScript content

    document.getElementById("filepicker").addEventListener("change", function(event) {
      let output = document.getElementById("listing");
      let files = event.target.files;

      for (let i=0; i<files.length; i++) {
        let item = document.createElement("li");
        item.innerHTML = files[i].webkitRelativePath;
        output.appendChild(item);
      };
    }, false);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-htmlinputelement-webkitdirectory">File and Directory Entries API<br />
<span class="small">The definition of 'webkitdirectory' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`webkitdirectory`

6

13

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

- [File and Directory Entries API](../file_and_directory_entries_api)
- [`HTMLInputElement.webkitEntries`](webkitentries)
- [`File.webkitRelativePath`](../file/webkitrelativepath)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/webkitdirectory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/webkitdirectory</a>
