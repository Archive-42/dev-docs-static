Storage.length
==============

The `length` read-only property of the [`Storage`](../storage) interface returns the number of data items stored in a given `Storage` object.

Syntax
------

    length = storage.length;

### Return value

The number of items stored in the `Storage` object.

Example
-------

The following function adds three data items to the local storage for the current domain, then returns the number of items in the storage:

    function populateStorage() {
      localStorage.setItem('bgcolor', 'yellow');
      localStorage.setItem('font', 'Helvetica');
      localStorage.setItem('image', 'cats.png');

      return localStorage.length; // Should return 3
    }

**Note**: For a real world example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-storage-length">HTML Living Standard<br />
<span class="small">The definition of 'Storage.length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`length`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage/length</a>
