# NodeIterator.expandEntityReferences

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `NodeIterator.expandEntityReferences` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating whether or not the children of entity reference nodes are visible to the [`NodeIterator`](../nodeiterator).

If this value is `false`, the children of entity reference nodes (as well as all of their descendants) are rejected. This takes precedence over the value of the [`NodeIterator.whatToShow`](whattoshow) method and the associated filter.

## Syntax

    expand = nodeIterator.expandEntityReferences;

## Example

    var nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    expand = nodeIterator.expandEntityReferences;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeIterator-expandEntityReferences">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator.expandEntityReferences' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`expandEntityReferences`

1-41

12-79

3.5-21

9

9-28

3-10.1

1-41

18-41

4-21

10.1-28

3-10.3

1.0-4.0

## See also

- The interface this property belongs to: [`NodeIterator`](../nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/expandEntityReferences" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/expandEntityReferences</a>
