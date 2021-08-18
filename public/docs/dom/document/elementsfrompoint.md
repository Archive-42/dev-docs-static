# Document.elementsFromPoint()

The `elementsFromPoint()` method of the [`Document`](../document) interface returns an array of all elements at the specified coordinates (relative to the viewport).

It operates in a similar way to the [`elementFromPoint()`](elementfrompoint) method.

## Syntax

    elementsFromPoint(x, y);

### Parameters

`x`  
The horizontal coordinate of a point.

`y`  
The vertical coordinate of a point.

### Return value

An array of [`element`](../element) objects.

## Example

### HTML

    <div>
      <p>Some text</p>
    </div>
    <p>Elements at point 30, 20:</p>
    <div id="output"></div>

### JavaScript

    let output = document.getElementById("output");
    if (document.elementsFromPoint) {
      let elements = document.elementsFromPoint(30, 20);
      for (var i = 0; i < elements.length; i++) {
        output.textContent += elements[i].localName;
        if (i < elements.length - 1) {
          output.textContent += " < ";
        }
      }
    } else {
      output.innerHTML = "<span style=\"color: red;\">" +
         "Browser does not support <code>document.elementsFromPoint()</code>" +
         "</span>";
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-document-elementsfrompoint">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'elementsFromPoint()' in that specification.</span></a></td></tr></tbody></table>

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

`elementsFromPoint`

43

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

79

12-79

Returns a `NodeList` instead of an array. See [the MSDN documentation](<https://msdn.microsoft.com/en-us/library/hh772121(v=vs.85).aspx>). Returns `null` when the point provided has no elements beneath it (e.g., when given a point outside the document).

46

10

Returns a `NodeList` instead of an array. See [the MSDN documentation](<https://msdn.microsoft.com/en-us/library/hh772121(v=vs.85).aspx>). Returns `null` when the point provided has no elements beneath it (e.g., when given a point outside the document).

30

11.1

43

Before WebView 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

43

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

46

30

11.3

4.0

Before Samsung Internet 9.0, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

## See also

- [`Document.elementFromPoint()`](elementfrompoint)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/elementsFromPoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/elementsFromPoint</a>
