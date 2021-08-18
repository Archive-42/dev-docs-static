Range.extractContents()
=======================

The `Range.extractContents()` method moves contents of the [`Range`](../range) from the document tree into a [`DocumentFragment`](../documentfragment).

Event listeners added using DOM Events are not retained during extraction. HTML attribute events are retained or duplicated as they are for the [`Node.cloneNode()`](../node/clonenode) method. HTML `id` attributes are also cloned, which can lead to an invalid document if a partially-selected node is extracted and appended to the document.

Partially selected nodes are cloned to include the parent tags necessary to make the document fragment valid.

Syntax
------

    documentFragment = range.extractContents();

Example
-------

### Basic example

    var range = document.createRange();
    range.selectNode(document.getElementsByTagName("div").item(0));
    var documentFragment = range.extractContents();
    document.body.appendChild(documentFragment);

### Moving items between containers

This example lets you move items between two containers. Select one or more item, and then click "swap" to move them to the opposite container.

#### HTML

    <p id="list1">123456</p>
    <button id="swap">Swap selected item(s)</button>
    <p id="list2">abcdef</p>

#### CSS

    body {
      pointer-events: none;
    }

    p {
      border: 1px solid;
      font-size: 2em;
      padding: .3em;
    }

    button {
      font-size: 1.2em;
      padding: .5em;
      pointer-events: auto;
    }

#### JavaScript

    const list1 = document.getElementById('list1');
    const list2 = document.getElementById('list2');
    const button = document.getElementById('swap');

    button.addEventListener('click', e => {
      selection = window.getSelection();

      for (let i = 0; i < selection.rangeCount; i++) {
        const range = selection.getRangeAt(i);

        if (range.commonAncestorContainer === list1 ||
            range.commonAncestorContainer.parentNode === list1) {
          const documentFragment = range.extractContents();
          list2.appendChild(documentFragment);
        } else if (range.commonAncestorContainer === list2 ||
            range.commonAncestorContainer.parentNode === list2) {
          const documentFragment = range.extractContents();
          list1.appendChild(documentFragment);
        }
      }
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-extractcontents">DOM<br />
<span class="small">The definition of 'Range.extractContents()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-extractContents">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.extractContents()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`extractContents`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/extractContents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/extractContents</a>
