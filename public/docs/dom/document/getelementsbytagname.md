# Document.getElementsByTagName()

The `getElementsByTagName` method of [`Document`](../document) interface returns an [`HTMLCollection`](../htmlcollection) of elements with the given tag name. The complete document is searched, including the root node. The returned `HTMLCollection` is live, meaning that it updates itself automatically to stay in sync with the DOM tree without having to call `document.getElementsByTagName()` again.

## Syntax

    var elements = document.getElementsByTagName(name);

- elements is a live [`HTMLCollection`](../htmlcollection) (but see the note below) of found elements in the order they appear in the tree.
- name is a string representing the name of the elements. The special string "\*" represents all elements.

[The latest W3C specification](https://dvcs.w3.org/hg/domcore/raw-file/tip/Overview.html) says elements is an `HTMLCollection`; however, this method returns a [`NodeList`](../nodelist) in WebKit browsers. See [bug 14869](https://bugzilla.mozilla.org/show_bug.cgi?id=14869) for details.

## Example

In the following example, `getElementsByTagName()` starts from a particular parent element and searches top-down recursively through the DOM from that parent element, building a collection of all descendant elements which match the tag `name` parameter. This demonstrates both `document.getElementsByTagName()` and the functionally identical [`Element.getElementsByTagName()`](../element/getelementsbytagname), which starts the search at a specific element within the DOM tree.

Clicking the buttons uses `getElementsByTagName()` to count the descendant paragraph elements of a particular parent (either the document itself or one of two nested [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements).

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <title>getElementsByTagName example</title>
      <script>
        function getAllParaElems() {
          var allParas = document.getElementsByTagName('p');
          var num = allParas.length;
          alert('There are ' + num + ' paragraph in this document');
        }

        function div1ParaElems() {
          var div1 = document.getElementById('div1');
          var div1Paras = div1.getElementsByTagName('p');
          var num = div1Paras.length;
          alert('There are ' + num + ' paragraph in #div1');
        }

        function div2ParaElems() {
          var div2 = document.getElementById('div2');
          var div2Paras = div2.getElementsByTagName('p');
          var num = div2Paras.length;
          alert('There are ' + num + ' paragraph in #div2');
        }
      </script>
    </head>
    <body style="border: solid green 3px">
      <p>Some outer text</p>
      <p>Some outer text</p>

      <div id="div1" style="border: solid blue 3px">
        <p>Some div1 text</p>
        <p>Some div1 text</p>
        <p>Some div1 text</p>

        <div id="div2" style="border: solid red 3px">
          <p>Some div2 text</p>
          <p>Some div2 text</p>
        </div>
      </div>

      <p>Some outer text</p>
      <p>Some outer text</p>

      <button onclick="getAllParaElems();">
        show all p elements in document</button><br />

      <button onclick="div1ParaElems();">
        show all p elements in div1 element</button><br />

      <button onclick="div2ParaElems();">
        show all p elements in div2 element</button>

    </body>
    </html>

## Notes

When called on an HTML document, `getElementsByTagName()` lower-cases its argument before proceeding. This is undesirable when trying to match camelCase SVG elements in a subtree in an HTML document. [`document.getElementsByTagNameNS()`](getelementsbytagnamens) is useful in that case. See also [bug 499656](https://bugzilla.mozilla.org/show_bug.cgi?id=499656).

`document.getElementsByTagName()` is similar to [`Element.getElementsByTagName()`](../element/getelementsbytagname), except that its search encompasses the whole document.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-getelementsbytagname">DOM<br />
<span class="small">The definition of 'document.getElementsByTagName' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getElementsByTagName`

1

12

1

5

5.1

1

1

18

4

10.1

1

1.0

## See also

- [`Element.getElementsByTagName()`](../element/getelementsbytagname)
- [`document.getElementById()`](getelementbyid) to return a reference to an element by its `id`
- [`document.getElementsByName()`](getelementsbyname) to return a reference to an element by its `name`
- [`document.querySelector()`](queryselector) for powerful selectors via queries like `'div.myclass'`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName</a>
