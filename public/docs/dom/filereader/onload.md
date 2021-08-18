# FileReader.onload

The `FileReader.onload` property contains an event handler executed when the `load` event is fired, when content read with [readAsArrayBuffer](readasarraybuffer), [readAsBinaryString](readasbinarystring), [readAsDataURL](readasdataurl) or [readAsText](readastext) is available.

## Example

    // Callback from a <input type="file" onchange="onChange(event)">
    function onChange(event) {
      var file = event.target.files[0];
      var reader = new FileReader();
      reader.onload = function(e) {
        // The file's text will be printed here
        console.log(e.target.result)
      };

      reader.readAsText(file);
    }

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

`onload`

7

12

3.6

10

11

6.1

≤37

18

32

11

6.1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileReader/onload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileReader/onload</a>
