# NodeFilter

A `NodeFilter` interface represents an object used to filter the nodes in a [`NodeIterator`](nodeiterator) or [`TreeWalker`](treewalker). A `NodeFilter` knows nothing about the document or traversing nodes; it only knows how to evaluate a single node against the provided filter.

**Note:** The browser doesn't provide any object implementing this interface. It is the user who is expected to write one, tailoring the `acceptNode()` method to its needs, and using it with some [`TreeWalker`](treewalker) or [`NodeIterator`](nodeiterator) objects.

## Properties

_This interface neither implements nor inherits any properties._

## Methods

_This interface doesn't inherit any methods._

[`NodeFilter.acceptNode()`](nodefilter/acceptnode)  
Returns an `unsigned short` that will be used to tell if a given [`Node`](node) must be accepted or not by the [`NodeIterator`](nodeiterator) or [`TreeWalker`](treewalker) iteration algorithm.

This method is expected to be written by the user of a `NodeFilter`. Possible return values are:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>FILTER_ACCEPT</code></td><td>Value returned by the <a href="nodefilter/acceptnode"><code>NodeFilter.acceptNode()</code></a> method when a node should be accepted.</td></tr><tr class="even"><td><code>FILTER_REJECT</code></td><td><p>Value to be returned by the <a href="nodefilter/acceptnode"><code>NodeFilter.acceptNode()</code></a> method when a node should be rejected. For <a href="treewalker"><code>TreeWalker</code></a>, child nodes are also rejected.</p><p>For <a href="nodeiterator"><code>NodeIterator</code></a>, this flag is synonymous with <code>FILTER_SKIP</code>.</p></td></tr><tr class="odd"><td><code>FILTER_SKIP</code></td><td><p>Value to be returned by <a href="nodefilter/acceptnode"><code>NodeFilter.acceptNode()</code></a> for nodes to be skipped by the <a href="nodeiterator"><code>NodeIterator</code></a> or <a href="treewalker"><code>TreeWalker</code></a> object.</p><p>The children of skipped nodes are still considered. This is treated as "skip this node but not its children".</p></td></tr></tbody></table>

## Example

    const nodeIterator = document.createNodeIterator(
      // Node to use as root
      document.getElementById('someId'),

      // Only consider nodes that are text nodes (nodeType 3)
      NodeFilter.SHOW_TEXT,

      // Object containing the function to use for the acceptNode method
      // of the NodeFilter
      {
        acceptNode: function(node) {
          // Logic to determine whether to accept, reject or skip node
          // In this case, only accept nodes that have content
          // other than whitespace
          if (/\S/.test(node.data)) {
            return NodeFilter.FILTER_ACCEPT
          }
        }
      },
      false
    );

    // Show the content of every non-empty text node that is a child of root
    let node;

    while ((node = nodeIterator.nextNode())) {
      alert(node.data)
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-nodefilter">DOM<br />
<span class="small">The definition of 'NodeFilter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeFilter">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeFilter' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`NodeFilter`

1

12

2

9

9

3

1

18

4

10.1

3

1.0

`acceptNode`

1

12

2

9

9

3

1

18

4

10.1

3

1.0

## See also

- **Related interfaces**
  - [`TreeWalker`](treewalker)
  - [`NodeIterator`](nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter</a>
