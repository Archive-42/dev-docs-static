# Node.getUserData()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Node.getUserData()` method returns any user [`DOMUserData`](../domuserdata) set previously on the given node by [`Node.setUserData()`](setuserdata).

The `Node.setUserData` and [`Node.getUserData`](getuserdata) methods are no longer available from Web content. <span class="page-not-created">`Element.dataset`</span> or [`WeakMap`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) can be used instead.

## Syntax

    userData = someNode.getUserData(userKey);

### Parameters

- `userKey` is the key to choose the specific data sought for the given node. More than one key may have been assigned on a given node, containing its own value.

## Example

    var d = document.setUserData('key', 15, null);
    console.log(document.getUserData('key')); // 15

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Node3-getUserData">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.getUserData()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getUserData`

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

- [`Node.setUserData()`](setuserdata)
- [`UserDataHandler`](../userdatahandler)
- [`DOMUserData`](../domuserdata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/getUserData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/getUserData</a>
