# ElementTraversal

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `ElementTraversal` interface used to define methods that allowed access from one [`Node`](node) to another in the document tree.

It proved useless, as very few types of [`Node`](node) were able to implement all its methods and properties. It has been split into two interfaces, containing the useful methods and properties for each kind of nodes:

- [`ChildNode`](childnode)
- [`ParentNode`](parentnode)

As it was a pure interface, with no object of this type, this change has no effect on the Web.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-childnode">DOM<br />
<span class="small">The definition of 'ChildNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Splitted the <code>ElementTraversal</code> interface in <a href="parentnode"><code>ParentNode</code></a> and <a href="childnode"><code>ChildNode</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/ElementTraversal/#interface-elementTraversal">Element Traversal Specification<br />
<span class="small">The definition of 'ElementTraversal' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ElementTraversal</a>
