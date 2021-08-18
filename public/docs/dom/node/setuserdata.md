# Node.setUserData()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Node.setUserData()` method allows a user to attach (or remove) data to an element, without needing to modify the DOM. Note that such data will not be preserved when imported via <span class="page-not-created">`Node.importNode`</span>, as with [`Node.cloneNode()`](clonenode) and <span class="page-not-created">`Node.renameNode()`</span> operations (though <span class="page-not-created">`Node.adoptNode`</span> does preserve the information), and equality tests in [`Node.isEqualNode()`](isequalnode) do not consider user data in making the assessment.

This method offers the convenience of associating data with specific nodes without needing to alter the structure of a document and in a standard fashion, but it also means that extra steps may need to be taken if one wishes to serialize the information or include the information upon clone, import, or rename operations.

The `Node.getUserData` and [`Node.setUserData`](setuserdata) methods are no longer available from Web content. [`HTMLElement.dataset`](../htmlorforeignelement/dataset) or [`WeakMap`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) can be used instead.

## Syntax

    var prevUserData = someNode.setUserData(userKey, userData, handler);

### Parameters

- `userKey` is used as the key by which one may subsequently obtain the stored data. More than one key can be set for a given node.
- `handler` is a callback which will be called any time the node is being cloned, imported, renamed, as well as if deleted or adopted; a function can be used or an object implementing the `handle` method (part of the [`UserDataHandler`](../userdatahandler) interface). The handler will be passed five arguments: an operation type integer (e.g., 1 to indicate a clone operation), the user key, the data on the node, the source node (`null` if being deleted), the destination node (the newly created node or `null` if none).If no handler is desired, one must specify `null`.
- `userData` is the object to associate to `userKey` on someNode. If `null`, any previously registered object and UserDataHandler associated to `userKey` on this node will be removed.

## Example

    var d = document.implementation.createDocument('', 'test', null);
    d.documentElement.setUserData('key', 15, {handle:function (o, k, d, s, ds) {console.log(o+'::'+k+'::'+d+'::'+s+'::'+ds)}}); // 2::key::15::[object Element]::[object Element]
    console.log(d.documentElement.getUserData('key')); // 15
    var e = document.importNode(d.documentElement, true); // causes handler to be called
    console.log(e.getUserData('key')); // null since user data is not copied

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Node3-setUserData">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.setUserData()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`setUserData`

No

No

1-22

No

No

No

No

No

4-22

No

No

No

## See also

- [`Node.getUserData()`](getuserdata)
- [`UserDataHandler`](../userdatahandler)
- [`DOMUserData`](../domuserdata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/setUserData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/setUserData</a>
