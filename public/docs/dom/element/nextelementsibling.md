Element.nextElementSibling
==========================

The `Element.nextElementSibling` read-only property returns the element immediately following the specified one in its parent's children list, or `null` if the specified element is the last one in the list.

Syntax
------

    // Getter
    element = el.nextElementSibling;

    // No setter; read-only property

Example
-------

    <div id="div-01">Here is div-01</div>
    <div id="div-02">Here is div-02</div>

    <script type="text/javascript">
      let el = document.getElementById('div-01').nextElementSibling;
      console.log('Siblings of div-01:');
      while (el) {
        console.log(el.nodeName);
        el = el.nextElementSibling;
      }
    </script>

This example outputs the following into the console when it loads:

    Siblings of div-01:
    DIV
    SCRIPT

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nondocumenttypechildnode-nextelementsibling">DOM<br />
<span class="small">The definition of 'NonDocumentTypeChildNode.nextElementSibling' in that specification.</span></a></td></tr></tbody></table>

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

`nextElementSibling`

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

See also
--------

-   [`Element.previousElementSibling`](previouselementsibling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/nextElementSibling" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/nextElementSibling</a>
