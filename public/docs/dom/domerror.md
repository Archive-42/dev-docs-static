# DOMError

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `DOMError` interface describes an error object that contains an error name.

## Properties

<span class="page-not-created">`DOMError.name`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) representing one of the error type names (see below).

<span class="page-not-created">`DOMError.message`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) representing a message or description associated with the given error type name.

## Error types

<table><thead><tr class="header"><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>IndexSizeError</code></td><td>The index is not in the allowed range (e.g. thrown in a <a href="range"><code>range</code></a> object).</td></tr><tr class="even"><td><code>HierarchyRequestError</code></td><td>The node tree hierarchy is not correct.</td></tr><tr class="odd"><td><code>WrongDocumentError</code></td><td>The object is in the wrong <a href="document"><code>document</code></a>.</td></tr><tr class="even"><td><code>InvalidCharacterError</code></td><td>The string contains invalid characters.</td></tr><tr class="odd"><td><code>NoModificationAllowedError</code></td><td>The object can not be modified.</td></tr><tr class="even"><td><code>NotFoundError</code></td><td>The object can not be found here.</td></tr><tr class="odd"><td><code>NotSupportedError</code></td><td>The operation is not supported</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td>The object is in an invalid state.</td></tr><tr class="odd"><td><code>SyntaxError</code></td><td>The string did not match the expected pattern.</td></tr><tr class="even"><td><code>InvalidModificationError</code></td><td>The object can not be modified in this way.</td></tr><tr class="odd"><td><code>NamespaceError</code></td><td>The operation is not allowed by Namespaces in XML</td></tr><tr class="even"><td><code>InvalidAccessError</code></td><td>The object does not support the operation or argument.</td></tr><tr class="odd"><td><code>TypeMismatchError</code></td><td>The type of the object does not match the expected type.</td></tr><tr class="even"><td><code>SecurityError</code></td><td>The operation is insecure.</td></tr><tr class="odd"><td><code>NetworkError</code></td><td>A network error occurred.</td></tr><tr class="even"><td><code>AbortError</code></td><td>The operation was aborted.</td></tr><tr class="odd"><td><code>URLMismatchError</code></td><td>The given URL does not match another URL.</td></tr><tr class="even"><td><code>QuotaExceededError</code></td><td>The quota has been exceeded.</td></tr><tr class="odd"><td><code>TimeoutError</code></td><td>The operation timed out.</td></tr><tr class="even"><td><code>InvalidNodeTypeError</code></td><td>The node is incorrect or has an incorrect ancestor for this operation.</td></tr><tr class="odd"><td><code>DataCloneError</code></td><td>The object can not be cloned.</td></tr></tbody></table>

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

`DOMError`

36

12

12-69

10

23

≤12.1-15

No

37

36

14-79

24

≤12.1-14

No

3.0

`message`

36

12

12-69

10

23

No

37

36

14-79

24

No

3.0

`name`

36

12

12-69

10

23

No

37

36

14-79

24

No

3.0

## See also

- [`DOMException`](domexception)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMError</a>
