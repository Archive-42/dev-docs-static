Storage.key()
=============

The `key()` method of the [`Storage`](../storage) interface, when passed a number n, returns the name of the nth key in a given `Storage` object. The order of keys is user-agent defined, so you should not rely on it.

Syntax
------

    var aKeyName = storage.key(index);

### Parameters

`index`  
An integer representing the number of the key you want to get the name of. This is a zero-based index.

### Return value

A [`DOMString`](../domstring) containing the name of the key. If the index does not exist, `null` is returned.

Examples
--------

The following function iterates over the local storage keys:

    function forEachKey(callback) {
      for (var i = 0; i < localStorage.length; i++) {
        callback(localStorage.key(i));
      }
    }

The following function iterates over the local storage keys and gets the value set for each key:

    for(var i =0; i < localStorage.length; i++){
      console.log(localStorage.getItem(localStorage.key(i)));
    }

**Note**: For a real world example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-storage-key">HTML Living Standard<br />
<span class="small">The definition of 'Storage.key' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`key`

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

-   [Using the Web Storage API](../web_storage_api/using_the_web_storage_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage/key" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage/key</a>
