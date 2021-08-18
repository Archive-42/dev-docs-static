Storage.setItem()
=================

The `setItem()` method of the [`Storage`](../storage) interface, when passed a key name and value, will add that key to the given `Storage` object, or update that key's value if it already exists.

Syntax
------

    storage.setItem(keyName, keyValue);

### Parameters

`keyName`  
A [`DOMString`](../domstring) containing the name of the key you want to create/update.

`keyValue`  
A [`DOMString`](../domstring) containing the value you want to give the key you are creating/updating.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`setItem()` may throw an exception if the storage is full. Particularly, in Mobile Safari (since iOS 5) it always throws when the user enters private mode. (Safari sets the quota to 0 bytes in private mode, unlike other browsers, which allow storage in private mode using separate data containers.) Hence developers should make sure to `setItem()`.

Example
-------

The following function creates three data items inside local storage.

    function populateStorage() {
      localStorage.setItem('bgcolor', 'red');
      localStorage.setItem('font', 'Helvetica');
      localStorage.setItem('image', 'myCat.png');
    }

**Note**: To see this used within a real world example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-storage-setitem">HTML Living Standard<br />
<span class="small">The definition of 'Storage.setItem' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setItem`

4

12

3.5

8

10.5

4

≤37

18

6

11

3.2

1.0

See also
--------

-   [Storage.getItem()](getitem)
-   [Storage.removeItem()](removeitem)
-   [Using the Web Storage API](../web_storage_api/using_the_web_storage_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage/setItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage/setItem</a>
