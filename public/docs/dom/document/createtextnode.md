# Document.createTextNode()

Creates a new [`Text`](../text) node. This method can be used to escape HTML characters.

## Syntax

    var text = document.createTextNode(data);

- text is a [`Text`](../text) node.
- data is a [string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the data to be put in the text node.

## Example

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <title>createTextNode example</title>
    <script>
    function addTextNode(text) {
      var newtext = document.createTextNode(text),
          p1 = document.getElementById("p1");

      p1.appendChild(newtext);
    }
    </script>
    </head>

    <body>
      <button onclick="addTextNode('YES! ');">YES!</button>
      <button onclick="addTextNode('NO! ');">NO!</button>
      <button onclick="addTextNode('WE CAN! ');">WE CAN!</button>

      <hr />

      <p id="p1">First line of paragraph.</p>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createtextnode">DOM<br />
<span class="small">The definition of 'Document: createTextNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createTextNode`

1

12

1

5

7

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode</a>
