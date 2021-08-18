File.name
=========

Returns the name of the file represented by a [`File`](../file) object. For security reasons, the path is excluded from this property.

Syntax
------

    var name = file.name;

Value
-----

A string, containing the name of the file without path, such as "My Resume.rtf".

Example
-------

    <input type="file" multiple onchange="processSelectedFiles(this)">

    function processSelectedFiles(fileInput) {
      var files = fileInput.files;

      for (var i = 0; i < files.length; i++) {
        alert("Filename " + files[i].name);
      }
    }

Try the results out below:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/#file-attrs">File API<br />
<span class="small">The definition of 'name' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`name`

13

12

3.6

10

16

6.1

≤37

Yes

4

No

7

Yes

See also
--------

-   [Using files from web applications](using_files_from_web_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/File/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/File/name</a>
