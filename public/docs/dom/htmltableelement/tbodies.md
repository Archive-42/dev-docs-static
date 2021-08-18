HTMLTableElement.tBodies
========================

The `HTMLTableElement.tBodies` read-only property returns a live [`HTMLCollection`](../htmlcollection) of the bodies in a [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

Although the property is read-only, the returned object is live and allows the modification of its content.

The collection returned includes implicit [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) elements. For example:

    <table>
      <tr>
        <td>cell one</td>
      </tr>
    </table>

The HTML DOM generated from the above HTML will have a [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) element even though the tags are not included in the source HTML.

Syntax
------

    HTMLCollectionObject = table.tBodies

Example
-------

This snippet gets the number of bodies in a table.

    mytable.tBodies.length;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-tbodies">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: tBodies' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`tBodies`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`HTMLCollection`](../htmlcollection)
-   [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/tBodies" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/tBodies</a>
