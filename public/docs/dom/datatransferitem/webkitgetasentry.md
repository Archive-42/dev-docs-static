# DataTransferItem.webkitGetAsEntry()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

If the item described by the [`DataTransferItem`](../datatransferitem) is a file, `webkitGetAsEntry()` returns a [`FileSystemFileEntry`](../filesystemfileentry) or [`FileSystemDirectoryEntry`](../filesystemdirectoryentry) representing it. If the item isn't a file, `null` is returned.

This function is implemented as `webkitGetAsEntry()` in non-WebKit browsers including Firefox at this time; it may be renamed to `getAsEntry()` in the future, so you should code defensively, looking for both.

## Syntax

    DataTransferItem.webkitGetAsEntry();

### Parameters

None.

### Return value

A [`FileSystemEntry`](../filesystementry)-based object describing the dropped item. This will be either [`FileSystemFileEntry`](../filesystemfileentry) or [`FileSystemDirectoryEntry`](../filesystemdirectoryentry).

## Example

In this example, a drop zone is created, which responds to the `drop` event by scanning through the dropped files and directories, outputting a hierarchical directory listing.

### HTML content

The HTML establishes the drop zone itself, which is a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element with the ID `"dropzone"`, and an unordered list element with the ID `"listing"`.

    <p>Drag files and/or directories to the box below!</p>

    <div id="dropzone">
      <div id="boxtitle">
        Drop Files Here
      </div>
    </div>

    <h2>Directory tree:</h2>

    <ul id="listing">
    </ul>

### CSS content

The styles used by the example are shown here.

    #dropzone {
      text-align: center;
      width: 300px;
      height: 100px;
      margin: 10px;
      padding: 10px;
      border: 4px dashed red;
      border-radius: 10px;
    }

    #boxtitle {
      display: table-cell;
      vertical-align: middle;
      text-align: center;
      color: black;
      font: bold 2em "Arial", sans-serif;
      width: 300px;
      height: 100px;
    }

    body {
      font: 14px "Arial", sans-serif;
    }

### JavaScript content

First, let's look at the recursive `scanFiles()` function. This function takes as input a [`FileSystemEntry`](../filesystementry) representing an entry in the file system to be scanned and processed (the `item` parameter), and an element into which to insert the list of contents (the `container` parameter).

Note that to read all files in a directory, `readEntries` needs to be called repeatedly until it returns an empty array. In Chromium-based browsers, the following example will only return a max of 100 entries.

    let dropzone = document.getElementById("dropzone");
    let listing = document.getElementById("listing");

    function scanFiles(item, container) {
      let elem = document.createElement("li");
      elem.textContent = item.name;
      container.appendChild(elem);

     if (item.isDirectory) {
        let directoryReader = item.createReader();
        let directoryContainer = document.createElement("ul");
        container.appendChild(directoryContainer);
        directoryReader.readEntries(function(entries) {
            entries.forEach(function(entry) {
              scanFiles(entry, directoryContainer);
          });
        });
      }
    }

`scanFiles()` begins by creating a new [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) element to represent the item being scanned, inserts the name of the item into it as its text content, and then appends it to the container. The container is always a list element in this example, as you'll see shortly.

Once the current item is in the list, the item's [`isDirectory`](../filesystementry/isdirectory) property is checked. If the item is a directory, we need to recurse into that directory. The first step is to create a [`FileSystemDirectoryReader`](../filesystemdirectoryreader) to handle fetching the directory's contents. That's done by calling the item's [`createReader()`](../filesystemdirectoryentry/createreader) method. Then a new [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) is created and appended to the parent list; this will contain the directory's contents in the next level down in the list's hierarchy.

After that, [`directoryReader.readEntries()`](../filesystemdirectoryreader/readentries) is called to read in all the entries in the directory. These are each, in turn, passed into a recursive call to `scanFiles()` to process them. Any of them which are files are inserted into the list; any which are directories are inserted into the list and a new level of the list's hierarchy is added below, and so forth.

Then come the event handlers. First, we prevent the `dragover` event from being handled by the default handler, so that our drop zone can receive the drop:

    dropzone.addEventListener("dragover", function(event) {
        event.preventDefault();
    }, false);

The event handler that kicks everything off, of course, is the handler for the `drop` event:

    dropzone.addEventListener("drop", function(event) {
      let items = event.dataTransfer.items;

      event.preventDefault();
      listing.textContent = "";

      for (let i=0; i<items.length; i++) {
        let item = items[i].webkitGetAsEntry();

        if (item) {
            scanFiles(item, listing);
        }
      }
    }, false);

This fetches the list of [`DataTransferItem`](../datatransferitem) objects representing the items dropped from `event.dataTransfer.items`. Then we call [`Event.preventDefault()`](../event/preventdefault) to prevent the event from being handled further after we're done.

Now it's time to start building the list. First, the list is emptied by setting [`listing.textContent`](../node/textcontent) to be empty. That leaves us with an empty <span class="page-not-created">`ul`</span> to begin inserting directory entries into.

Then we iterate over the items in the list of dropped items. For each one, we call its [`webkitGetAsEntry()`](webkitgetasentry) method to obtain a [`FileSystemEntry`](../filesystementry) representing the file. If that's successful, we call `scanFiles()` to process the item—either by adding it to the list if it's just a file or by adding it and walking down into it if it's a directory.

### Result

You can see how this works by trying it out below. Find some files and directories and drag them in, and take a look at the resulting output.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-datatransferitem-webkitgetasentry">File and Directory Entries API<br />
<span class="small">The definition of 'webkitGetAsEntry()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`DataTransferItem`](../datatransferitem)
- [`FileSystemEntry`](../filesystementry), [`FileSystemFileEntry`](../filesystemfileentry), and [`FileSystemDirectoryEntry`](../filesystemdirectoryentry)
- Events: `dragover` and `drop`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/webkitGetAsEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DataTransferItem/webkitGetAsEntry</a>
