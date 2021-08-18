# IDBFactory.databases

The `databases` method of the [`IDBFactory`](../idbfactory) interface returns a list representing all the available databases, including their names and versions.

**Note:** This feature is available in [Web Workers](../web_workers_api).

**Note**

This method is introduced in a draft of a specifications and browser compatibility is limited.

## Syntax

    const promise = indexedDB.databases()

### Parameters

The method does not take in any parameters.

### Return value

A promise that resolves either to an error or a list of dictionaries, each with two elements, `name` and `version`.

#### `name`

The database name.

#### `version`

The database version.

Exceptions

This method may raise a [`DOMException`](../domexception) of the following types:

Attribute

Description

[`SecurityError`](../domexception#exception-securityerror)

The method is called from an opaque origin.

Other error

Specification does not describe all possible errors.

## Example

    const promise = indexedDB.databases()
    promise.then(databases => {
      console.log(databases)
    })

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/IndexedDB/#dom-idbfactory-databases">Indexed Database API 2.0<br />
<span class="small">The definition of 'databases()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`databases`

71

79

No

See [bug 934640](https://bugzil.la/934640).

No

58

14

71

71

No

See [bug 934640](https://bugzil.la/934640).

Yes

14

10.0

## See also

- [Using IndexedDB](../indexeddb_api/using_indexeddb)
- Starting transactions: [`IDBDatabase`](../idbdatabase)
- Using transactions: [`IDBTransaction`](../idbtransaction)
- Setting a range of keys: [`IDBKeyRange`](../idbkeyrange)
- Retrieving and making changes to your data: [`IDBObjectStore`](../idbobjectstore)
- Using cursors: [`IDBCursor`](../idbcursor)
- Reference example: [To-do Notifications](https://github.com/mdn/to-do-notifications/tree/gh-pages) ([view example live](https://mdn.github.io/to-do-notifications/).)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/databases" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IDBFactory/databases</a>
