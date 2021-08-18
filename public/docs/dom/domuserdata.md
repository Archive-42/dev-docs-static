# DOMUserData

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`DOMUserData` refers to application data. In JavaScript, it maps directly to `Object`. It is returned or used as an argument by `Node.setUserData()`, `Node.getUserData()`, used as the third argument to `handle()` on <a href="userdatahandler" class="internal"><code>UserDataHandler</code></a>, and is used or returned by various <a href="https://developer.mozilla.org/en-US/docs/DOM/DOMConfiguration" class="internal"><code>DOMConfiguration</code></a> methods.

Note that although it can be an object, in Mozilla, it may be returned as a string or other type, if it was set as such a type (e.g., `Node.setUserData()` and `Node.getUserData()`).

`DOMUserData` is not persisted nor serialized and will not be present after the application has restarted or after a crash. If you are interested in persisting data you might rather need to use <span class="page-not-created">`nsISessionStore`</span>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#DOMUserData">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DOMUserData' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification</td></tr></tbody></table>

## See also

- Other obsolete APIs for userData: [`UserDataHandler`](userdatahandler), [`node.getUserData`](node/getuserdata), [`node.setUserData`](node/setuserdata)
- [Using data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) is the modern alternative (see [`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-data-*) attributes, [`HTMLOrForeignElement.dataset`](htmlorforeignelement/dataset))
- <span class="page-not-created">`nsISessionStore`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMUserData</a>
