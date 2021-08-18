File.webkitRelativePath
=======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `File.webkitRelativePath` is a read-only property that contains a [`USVString`](../usvstring) which specifies the file's path relative to the directory selected by the user in an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with its [`webkitdirectory`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-webkitdirectory) attribute set.

Syntax
------

     relativePath = File.webkitRelativePath

### Value

A [`USVString`](../usvstring) containing the path of the file relative to the ancestor directory the user selected.

Example
-------

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/#dom-file-webkitrelativepath">File and Directory Entries API<br />
<span class="small">The definition of 'webkitRelativePath' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

This API has no official W3C or WHATWG specification.

Browser compatibility
---------------------

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

`webkitRelativePath`

13

13

49

No

No

11.1

≤37

18

49

No

11.3

1.0

See also
--------

-   [File and Directory Entries API](../file_and_directory_entries_api)
-   [`HTMLInputElement.webkitEntries`](../htmlinputelement/webkitentries)
-   [`HTMLInputElement.webkitdirectory`](../htmlinputelement/webkitdirectory)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/webkitRelativePath" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/webkitRelativePath</a>
