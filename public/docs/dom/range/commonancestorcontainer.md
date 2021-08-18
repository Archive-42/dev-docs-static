Range.commonAncestorContainer
=============================

The `Range.commonAncestorContainer` read-only property returns the deepest — or furthest down the document tree — [`Node`](../node) that contains both [boundary points](https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level-2-Range-Position-h3) of the [`Range`](../range). This means that if [`Range.startContainer`](startcontainer) and [`Range.endContainer`](endcontainer) both refer to the same node, this node is the **common ancestor container**.

Since a `Range` need not be continuous, and may also partially select nodes, this is a convenient way to find a `Node` which encloses a `Range`.

This property is read-only. To change the ancestor container of a `Node`, consider using the various methods available to set the start and end positions of the `Range`, such as [`Range.setStart()`](setstart) and [`Range.setEnd()`](setend).

Syntax
------

    rangeAncestor = range.commonAncestorContainer;

Example
-------

In this example, we create an event listener to handle `pointerup` events on a list. The listener gets the common ancestors of each piece of selected text, and triggers an animation to highlight them.

### HTML

    <ul>
      <li>Strings
        <ul>
          <li>Cello</li>
          <li>Violin
            <ul>
              <li>First Chair</li>
              <li>Second Chair</li>
            </ul>
          </li>
        </ul>
      </li>
      <li>Woodwinds
        <ul>
          <li>Clarinet</li>
          <li>Oboe</li>
        </ul>
      </li>
    </ul>

### CSS

The `.highlight` class created below uses a set of CSS [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) to animate a fading outline.

    .highlight {
      animation: highlight linear 1s;
    }

    @keyframes highlight {
      from { outline: 1px solid #f00f; }
      to   { outline: 1px solid #f000; }
    }

### JavaScript

    document.addEventListener('pointerup', e => {
      const selection = window.getSelection();

      if (selection.type === 'Range') {
        for (let i = 0; i < selection.rangeCount; i++) {
          const range = selection.getRangeAt(i);
          playAnimation(range.commonAncestorContainer);
        }
      }
    });

    function playAnimation(el) {
      if (el.nodeType === Node.TEXT_NODE) {
        el = el.parentNode;
      }

      el.classList.remove('highlight');
      setTimeout(() => {
        el.classList.add('highlight');
      }, 0);
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-commonancestorcontainer">DOM<br />
<span class="small">The definition of 'Range.commonAncestorContainer' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level-2-Range-attr-commonParent">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.commonAncestorContainer' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`commonAncestorContainer`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/commonAncestorContainer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/commonAncestorContainer</a>
