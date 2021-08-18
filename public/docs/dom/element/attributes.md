# Element.attributes

The `Element.attributes` property returns a live collection of all attribute nodes registered to the specified node. It is a [`NamedNodeMap`](../namednodemap), not an `Array`, so it has no [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) methods and the [`Attr`](../attr) nodes' indexes may differ among browsers. To be more specific, `attributes` is a key/value pair of strings that represents any information regarding that attribute.

## Syntax

    var attr = element.attributes;

## Example

### Basic examples

    // Get the first <p> element in the document
    var para = document.getElementsByTagName("p")[0];
    var atts = para.attributes;

### Enumerating elements attributes

Numerical indexing is useful for going through all of an element's attributes.  
The following example runs through the attribute nodes for the element in the document with id "paragraph", and prints each attribute's value.

    <!DOCTYPE html>

    <html>

     <head>
      <title>Attributes example</title>
      <script type="text/javascript">
       function listAttributes() {
         var paragraph = document.getElementById("paragraph");
         var result = document.getElementById("result");

         // First, let's verify that the paragraph has some attributes
         if (paragraph.hasAttributes()) {
           var attrs = paragraph.attributes;
           var output = "";
           for(var i = attrs.length - 1; i >= 0; i--) {
             output += attrs[i].name + "->" + attrs[i].value;
           }
           result.value = output;
         } else {
           result.value = "No attributes to show";
         }
       }
      </script>
     </head>

    <body>
     <p id="paragraph" style="color: green;">Sample Paragraph</p>
     <form action="">
      <p>
        <input type="button" value="Show first attribute name and value"
          onclick="listAttributes();">
        <input id="result" type="text" value="">
      </p>
     </form>
    </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-attributes">DOM<br />
<span class="small">The definition of 'Element.attributes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-3-Core/">Document Object Model (DOM) Level 3 Core Specification</a>, moved from <a href="../node"><code>Node</code></a> to <a href="../element"><code>Element</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-84CF096">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element.attributes' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-84CF096">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element.attributes' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-84CF096">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Element.attributes' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`attributes`

1

12

1

5.5

8

1

1

18

4

10.1

1

1.0

## See also

- [`NamedNodeMap`](../namednodemap), the interface of the returned object
- Cross-browser compatibility considerations: on [quirksmode](https://www.quirksmode.org/dom/w3c_core.html#attributes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/attributes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/attributes</a>
