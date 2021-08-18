# DOMException

The `DOMException` interface represents an abnormal event (called an **exception**) that occurs as a result of calling a method or accessing a property of a web API. This is basically how error conditions are described in web APIs.

Each exception has a **name**, which is a short "PascalCase"-style string identifying the error or abnormal condition.

## Constructor

[`DOMException()`](domexception/domexception) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a `DOMException` object with a specified message and name.

## Properties

[`DOMException.code`](domexception/code) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>  
Returns a `short` that contains one of the error code constants, or `0` if none match. This field is used for historical reasons. New DOM exceptions don't use this anymore: they put this info in the [`DOMException.name`](domexception/name) attribute.

[`DOMException.message`](domexception/message) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) representing a message or description associated with the given [error name](#error_names).

[`DOMException.name`](domexception/name) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) that contains one of the strings associated with an [error name](#error_names).

## Error names

Common error names are listed here. Some APIs define their own sets of names, so this is not necessarily a complete list.

**Note**: Because historically the errors were identified by a numeric value that corresponded with a named variable defined to have that value, some of the entries below indicate the legacy code value and constant name that were used in the past.

`IndexSizeError`  
The index is not in the allowed range. For example, this can be thrown by the [`Range`](range) object. (Legacy code value: `1` and legacy constant name: `INDEX_SIZE_ERR`)

`HierarchyRequestError`  
The node tree hierarchy is not correct. (Legacy code value: `3` and legacy constant name: `HIERARCHY_REQUEST_ERR`)

`WrongDocumentError`  
The object is in the wrong [`Document`](document). (Legacy code value: `4` and legacy constant name: `WRONG_DOCUMENT_ERR`)

`InvalidCharacterError`  
The string contains invalid characters. (Legacy code value: `5` and legacy constant name: `INVALID_CHARACTER_ERR`)

`NoModificationAllowedError`  
The object cannot be modified. (Legacy code value: `7` and legacy constant name: `NO_MODIFICATION_ALLOWED_ERR`)

`NotFoundError`  
The object cannot be found here. (Legacy code value: `8` and legacy constant name: `NOT_FOUND_ERR`)

`NotSupportedError`  
The operation is not supported. (Legacy code value: `9` and legacy constant name: `NOT_SUPPORTED_ERR`)

`InvalidStateError`  
The object is in an invalid state. (Legacy code value: `11` and legacy constant name: `INVALID_STATE_ERR`)

`SyntaxError`  
The string did not match the expected pattern. (Legacy code value: `12` and legacy constant name: `SYNTAX_ERR`)

`InvalidModificationError`  
The object cannot be modified in this way. (Legacy code value: `13` and legacy constant name: `INVALID_MODIFICATION_ERR`)

`NamespaceError`  
The operation is not allowed by Namespaces in XML. (Legacy code value: `14` and legacy constant name: `NAMESPACE_ERR`)

`InvalidAccessError`  
The object does not support the operation or argument. (Legacy code value: `15` and legacy constant name: `INVALID_ACCESS_ERR`)

`TypeMismatchError` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
The type of the object does not match the expected type. (Legacy code value: `17` and legacy constant name: `TYPE_MISMATCH_ERR`) This value is deprecated; the JavaScript [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) exception is now raised instead of a `DOMException` with this value.

`SecurityError`  
The operation is insecure. (Legacy code value: `18` and legacy constant name: `SECURITY_ERR`)

`NetworkError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A network error occurred. (Legacy code value: `19` and legacy constant name: `NETWORK_ERR`)

`AbortError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The operation was aborted. (Legacy code value: `20` and legacy constant name: `ABORT_ERR`)

`URLMismatchError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The given URL does not match another URL. (Legacy code value: `21` and legacy constant name: `URL_MISMATCH_ERR`)

`QuotaExceededError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The quota has been exceeded. (Legacy code value: `22` and legacy constant name: `QUOTA_EXCEEDED_ERR`)

`TimeoutError`  
The operation timed out. (Legacy code value: `23` and legacy constant name: `TIMEOUT_ERR`)

`InvalidNodeTypeError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The node is incorrect or has an incorrect ancestor for this operation. (Legacy code value: `24` and legacy constant name: `INVALID_NODE_TYPE_ERR`)

`DataCloneError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The object can not be cloned. (Legacy code value: `25` and legacy constant name: `DATA_CLONE_ERR`)

`EncodingError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The encoding or decoding operation failed (No legacy code value and constant name).

`NotReadableError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The input/output read operation failed (No legacy code value and constant name).

`UnknownError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The operation failed for an unknown transient reason (e.g. out of memory) (No legacy code value and constant name).

`ConstraintError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A mutation operation in a transaction failed because a constraint was not satisfied (No legacy code value and constant name).

`DataError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Provided data is inadequate (No legacy code value and constant name).

`TransactionInactiveError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A request was placed against a transaction that is currently not active or is finished (No legacy code value and constant name).

`ReadOnlyError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The mutating operation was attempted in a "readonly" transaction (No legacy code value and constant name).

`VersionError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
An attempt was made to open a database using a lower version than the existing version (No legacy code value and constant name).

`OperationError` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The operation failed for an operation-specific reason (No legacy code value and constant name).

`NotAllowedError`  
The request is not allowed by the user agent or the platform in the current context, possibly because the user denied permission (No legacy code value and constant name).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#idl-DOMException">Web IDL<br />
<span class="small">The definition of 'constructor' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the constructor for the <code>DOMException</code> class. Adds the <code>NotReadableError</code>, <code>UnknownError</code>, <code>ConstraintError</code>, <code>DataError</code>, <code>TransactionInactiveError</code>, <code>ReadOnlyError</code>, <code>VersionError</code>, <code>OperationError</code>, and <code>NotAllowedError</code> values.</td></tr></tbody></table>

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

`DOMException`

1

12

1

10

≤15

1

1

18

4

≤14

1

1.0

`DOMException`

46

79

37

No

33

10.1

46

46

37

33

10.3

5.0

`code`

1

12

1

10

≤15

1

1

18

4

≤14

1

1.0

`message`

1

12

1

10

≤15

1

1

18

4

≤14

1

1.0

`name`

1

12

1

10

≤15

1

1

18

4

≤14

1

1.0

## See also

- [`DOMError`](domerror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMException" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMException</a>
