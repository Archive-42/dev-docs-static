FileList
========

An object of this type is returned by the `files` property of the HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element; this lets you access the list of files selected with the `<input type="file">` element. It's also used for a list of files dropped into web content when using the drag and drop API; see the [`DataTransfer`](datatransfer) object for details on this usage.

**Note:** Prior to Gecko 1.9.2, the input element only supported a single file being selected at a time, meaning that the FileList would contain only one file. Starting with Gecko 1.9.2, if the input element's multiple attribute is true, the FileList may contain multiple files.

Using the file list
-------------------

All `<input>` element nodes have a `files` attribute of type `FileList` on them which allows access to the items in this list. For example, if the HTML includes the following file input:

    <input id="fileItem" type="file">

The following line of code fetches the first file in the node's file list as a [`File`](file) object:

    var file = document.getElementById('fileItem').files[0];

Method overview
---------------

<table><tbody><tr class="odd"><td><code>File item(index);</code></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Attribute</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>length</code></td><td><code>integer</code></td><td>A read-only value indicating the number of files in the list.</td></tr></tbody></table>

Methods
-------

### item()

Returns a [`File`](file) object representing the file at the specified index in the file list.

     File item(
       index
     );

###### Parameters

`index`  
The zero-based index of the file to retrieve from the list.

###### Return value

The [`File`](file) representing the requested file.

Example
-------

This example iterates over all the files selected by the user using an `input` element:

    // fileInput is an HTML input element: <input type="file" id="myfileinput" multiple>
    var fileInput = document.getElementById("myfileinput");

    // files is a FileList object (similar to NodeList)
    var files = fileInput.files;
    var file;

    // loop through files
    for (var i = 0; i < files.length; i++) {

        // get item
        file = files.item(i);
        //or
        file = files[i];

        alert(file.name);
    }

Here is a complete example.

    <!DOCTYPE HTML>
    <html>
    <head>
    </head>
    <body>
    <!--multiple is set to allow multiple files to be selected-->

    <input id="myfiles" multiple type="file">

    </body>

    <script>

    var pullfiles=function(){
        // love the query selector
        var fileInput = document.querySelector("#myfiles");
        var files = fileInput.files;
        // cache files.length
        var fl = files.length;
        var i = 0;

        while ( i < fl) {
            // localize file var in the loop
            var file = files[i];
            alert(file.name);
            i++;
        }
    }

    // set the input element onchange to call pullfiles
    document.querySelector("#myfiles").onchange=pullfiles;

    //a.t
    </script>

    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#filelist-section">File API<br />
<span class="small">The definition of 'FileList' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#concept-input-type-file-selected">HTML Living Standard<br />
<span class="small">The definition of 'selected files' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`FileList`

1

12

3

10

11.1

4

1

18

4

11.1

3.2

1.0

`item`

1

12

3

10

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`length`

Yes

12

3

10

Yes

10

Yes

Yes

4

Yes

10

Yes

See also
--------

-   [Using files from web applications](file/using_files_from_web_applications)
-   `File`
-   `FileReader`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileList</a>
