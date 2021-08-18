MutationRecord
==============

A `MutationRecord` represents an individual DOM mutation. It is the object that is passed to [`MutationObserver`](mutationobserver)'s callback.

Properties
----------

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Property</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><span class="page-not-created"><code>MutationRecord.type</code></span></td><td><code>String</code></td><td>Returns <code>"attributes"</code> if the mutation was an attribute mutation,<br />
<code>"characterData"</code> if it was a mutation to a <code>CharacterData</code> node,<br />
and <code>"childList"</code> if it was a mutation to the tree of nodes.</td></tr><tr class="even"><td><span class="page-not-created"><code>MutationRecord.target</code></span></td><td><a href="node"><code>Node</code></a></td><td>Returns the node the mutation affected, depending on the <span class="page-not-created"><code>MutationRecord.type</code></span>.<br />
For <code>attributes</code>, it is the element whose attribute changed.<br />
For <code>characterData</code>, it is the <code>CharacterData</code> node.<br />
For <code>childList</code>, it is the node whose children changed.</td></tr><tr class="odd"><td><span class="page-not-created"><code>MutationRecord.addedNodes</code></span></td><td><a href="nodelist"><code>NodeList</code></a></td><td>Return the nodes added. Will be an empty <a href="nodelist"><code>NodeList</code></a> if no nodes were added.</td></tr><tr class="even"><td><span class="page-not-created"><code>MutationRecord.removedNodes</code></span></td><td><a href="nodelist"><code>NodeList</code></a></td><td>Return the nodes removed. Will be an empty <a href="nodelist"><code>NodeList</code></a> if no nodes were removed.</td></tr><tr class="odd"><td><span class="page-not-created"><code>MutationRecord.previousSibling</code></span></td><td><a href="node"><code>Node</code></a></td><td>Return the previous sibling of the added or removed nodes, or <code>null</code>.</td></tr><tr class="even"><td><span class="page-not-created"><code>MutationRecord.nextSibling</code></span></td><td><a href="node"><code>Node</code></a></td><td>Return the next sibling of the added or removed nodes, or <code>null</code>.</td></tr><tr class="odd"><td><span class="page-not-created"><code>MutationRecord.attributeName</code></span></td><td><code>String</code></td><td>Returns the local name of the changed attribute, or <code>null</code>.</td></tr><tr class="even"><td><span class="page-not-created"><code>MutationRecord.attributeNamespace</code></span></td><td><code>String</code></td><td>Returns the namespace of the changed attribute, or <code>null</code>.</td></tr><tr class="odd"><td><span class="page-not-created"><code>MutationRecord.oldValue</code></span></td><td><code>String</code></td><td><p>The return value depends on the <span class="page-not-created"><code>MutationRecord.type</code></span>.<br />
For <code>attributes</code>, it is the value of the changed attribute before the change.<br />
For <code>characterData</code>, it is the data of the changed node before the change.<br />
For <code>childList</code>, it is <code>null</code>.</p><div class="note notecard"><p>Note that for this to work as expected, <code>attributeOldValue</code> or <code>characterDataOldValue</code> must be set to <code>true</code> in the corresponding <a href="mutationobserverinit">MutationObserverInit</a> parameter of the <code>MutationObserver</code> <a href="mutationobserver/observe">observe</a> method</p></div></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#mutationrecord">DOM<br />
<span class="small">The definition of 'MutationRecord' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MutationRecord`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`addedNodes`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`attributeName`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`attributeNamespace`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`nextSibling`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`oldValue`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`previousSibling`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`removedNodes`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`target`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

`type`

Yes

12

14

11

Yes

6.1

Yes

Yes

14

Yes

7

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationRecord</a>
