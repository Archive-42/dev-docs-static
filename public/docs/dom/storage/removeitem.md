Storage.removeItem()
====================

The `removeItem()` method of the [`Storage`](../storage) interface, when passed a key name, will remove that key from the given `Storage` object if it exists. The `Storage` interface of the [Web Storage API](../web_storage_api) provides access to a particular domain's session or local storage.

If there is no item associated with the given key, this method will do nothing.

Syntax
------

    storage.removeItem(keyName);

### Parameters

`keyName`  
A [`DOMString`](../domstring) containing the name of the key you want to remove.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Example
-------

The following function creates three data items inside local storage, then removes the `image` data item.

    function populateStorage() {
      localStorage.setItem('bgcolor', 'red');
      localStorage.setItem('font', 'Helvetica');
      localStorage.setItem('image', 'myCat.png');

      localStorage.removeItem('image');
    }

We can do the same for the session storage.

    function populateStorage() {
      sessionStorage.setItem('bgcolor', 'red');
      sessionStorage.setItem('font', 'Helvetica');
      sessionStorage.setItem('image', 'myCat.png');

      sessionStorage.removeItem('image');
    }

**Note**: To see this used within a real world example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-storage-removeitem">HTML Living Standard<br />
<span class="small">The definition of 'Storage.removeItem' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`removeItem`

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

[Using the Web Storage API](../web_storage_api/using_the_web_storage_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage/removeItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage/removeItem</a>
