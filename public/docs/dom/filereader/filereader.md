FileReader()
============

The `FileReader()` constructor creates a new FileReader.

For details about how to use `FileReader`, see [Using files from web applications](../file/using_files_from_web_applications).

Syntax
------

    const reader = new FileReader();

### Parameters

None.

Example
-------

The following code snippet shows creation of a `FileReader` object using the `FileReader()` constructor and subsequent usage of the object:

    function printFile(file) {
      const reader = new FileReader();
      reader.onload = function(evt) {
        console.log(evt.target.result);
      };
      reader.readAsText(file);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/FileAPI/">File API</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

See also
--------

-   [Using files from web applications](../file/using_files_from_web_applications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/FileReader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/FileReader</a>
