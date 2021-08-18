FileReader.onerror
==================

The [FileReader](../filereader) onerror handler receives an Event object, not an Error object, as a parameter, but an error can be accessed from the FileReader object, as `instanceOfFileReader.error`

    // Callback from a <input type="file" onchange="onChange(event)">
    function onChange(event) {
      var file = event.target.files[0];
      var reader = new FileReader();
      reader.onerror = function(event) {
        alert("Failed to read file!\n\n" + reader.error);
        reader.abort(); // (...does this do anything useful in an onerror handler?)
      };

      reader.readAsText(file);
    }

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

`onerror`

7

12

3.6

10

11

6.1

≤37

Yes

32

11

6.1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/onerror</a>
