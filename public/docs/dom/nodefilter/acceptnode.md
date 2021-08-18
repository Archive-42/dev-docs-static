# NodeFilter.acceptNode()

The `NodeFilter.acceptNode()` method returns an `unsigned short` that will be used to tell if a given [`Node`](../node) must be accepted or not by the [`NodeIterator`](../nodeiterator) or [`TreeWalker`](../treewalker) iteration algorithm. This method is expected to be written by the user of a `NodeFilter`. Possible return values are:

<table><thead><tr class="header"><th>Constant</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NodeFilter.FILTER_ACCEPT</code></td><td>Value returned by the <a href="acceptnode"><code>NodeFilter.acceptNode()</code></a> method when a node should be accepted.</td></tr><tr class="even"><td><code>NodeFilter.FILTER_REJECT</code></td><td>Value to be returned by the <a href="acceptnode"><code>NodeFilter.acceptNode()</code></a> method when a node should be rejected. The children of rejected nodes are not visited by the <a href="../nodeiterator"><code>NodeIterator</code></a> or <a href="../treewalker"><code>TreeWalker</code></a> object; this value is treated as "skip this node and all its children".</td></tr><tr class="odd"><td><code>NodeFilter.FILTER_SKIP</code></td><td>Value to be returned by <a href="acceptnode"><code>NodeFilter.acceptNode()</code></a> for nodes to be skipped by the <a href="../nodeiterator"><code>NodeIterator</code></a> or <a href="../treewalker"><code>TreeWalker</code></a> object. The children of skipped nodes are still considered. This is treated as "skip this node but not its children".</td></tr></tbody></table>

The function should return `NodeFilter.FILTER_ACCEPT`, which causes the TreeWalker to return the node, `NodeFilter.FILTER_REJECT`, which causes the TreeWalker to ignore the entire subtree, or `NodeFilter.FILTER_SKIP`.

The browser doesn't provide any object implementing this method. It is the user who is expected to write an object implementing the [`NodeFilter`](../nodefilter) interface, tailoring the `acceptNode()` method to its needs, and using it with some [`TreeWalker`](../treewalker) or [`NodeIterator`](../nodeiterator) objects.

## Syntax

    result = nodeFilter.acceptNode(node)

### Parameters

_node_  
Is a [`Node`](../node) being the object to check against the filter.

## Example

    var nodeIterator = document.createNodeIterator(
      // Node to use as root
      document.getElementById('someId'),

      // Only consider nodes that are text nodes (nodeType 3)
      NodeFilter.SHOW_TEXT,

      // Object containing the function to use for the acceptNode method
      // of the NodeFilter
        { acceptNode: function(node) {
          // Logic to determine whether to accept, reject or skip node
          // In this case, only accept nodes that have content
          // other than whitespace
          if ( ! /^\s*$/.test(node.data) ) {
            return NodeFilter.FILTER_ACCEPT;
          }
        }
      },
      false
    );

    // Show the content of every non-empty text node that is a child of root
    var node;

    while ((node = iterator.nextNode())) {
      alert(node.data);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodefilter-acceptnode">DOM<br />
<span class="small">The definition of 'NodeFilter.acceptNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeFilter">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeFilter.acceptNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

- The interface it belongs to: [`NodeFilter`](../nodefilter).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter/acceptNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeFilter/acceptNode</a>
