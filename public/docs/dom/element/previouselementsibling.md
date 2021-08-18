# Element.previousElementSibling

The `Element.previousElementSibling` read-only property returns the [`Element`](../element) immediately prior to the specified one in its parent's children list, or `null` if the specified element is the first one in the list.

## Syntax

    // Getter
    element = el.previousElementSibling;

    // No setter; read-only property

## Example

    <div id="div-01">Here is div-01</div>
    <div id="div-02">Here is div-02</div>
    <li>This is a list item</li>
    <li>This is another list item</li>
    <div id="div-03">Here is div-03</div>

    <script>
      let el = document.getElementById('div-03').previousElementSibling;
      document.write('<p>Siblings of div-03</p><ol>');
      while (el) {
        document.write('<li>' + el.nodeName + '</li>');
        el = el.previousElementSibling;
      }
      document.write('</ol>');
    </script>

This example outputs the following into the page when it loads:

    Siblings of div-03

       1. LI
       2. LI
       3. DIV
       4. DIV

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nondocumenttypechildnode-previouselementsibling">DOM<br />
<span class="small">The definition of 'NonDocumentTypeChildNode.previousElementSibling' in that specification.</span></a></td></tr></tbody></table>

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

`previousElementSibling`

1

12

3.5

9

10

4

≤37

18

4

10.1

3

1.0

## See also

- [`Element.nextElementSibling`](nextelementsibling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/previousElementSibling" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/previousElementSibling</a>
