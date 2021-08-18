# IDBVersionChangeEvent()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `IDBVersionChangeEvent()` constructor creates a new [`IDBVersionChangeEvent`](../idbversionchangeevent) object, which is used to represent when a version of the database has changed, as a result of the [`IDBOpenDBRequest.onupgradeneeded`](../idbopendbrequest/onupgradeneeded) event handler.

## Syntax

    var idbVersionChangeEvent = new IDBVersionChangeEvent();

### Parameters

`type`  
A [`DOMString`](../domstring) indicating the event which occurred. For `IDBVersionChangeEvent` this is `versionchange`.

`eventInitDict`  
An optional dictionary of initial values for the event's properties. These are as follows:

- `oldVersion`: An unsigned long representing the previous version of the database. Default is `0`.
- `newVersion`: An unsigned long representing the new version of the database, or `null` if the database is being deleted. Default is `null`.

## Examples

For a full working example, see our [To-do Notifications](https://github.com/mdn/to-do-notifications/) app ([view example live](https://mdn.github.io/to-do-notifications/).)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#idbversionchangeevent">Indexed Database API 2.0<br />
<span class="small">The definition of 'IDBVersionChangeEvent' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.IDBVersionChangeEvent.IDBVersionChangeEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/IDBVersionChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBVersionChangeEvent/IDBVersionChangeEvent</a>
