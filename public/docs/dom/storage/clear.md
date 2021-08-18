Storage.clear()
===============

The `clear()` method of the [`Storage`](../storage) interface clears all keys stored in a given `Storage` object.

Syntax
------

    storage.clear();

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Examples
--------

The following function creates three data entries in local storage, and then deletes them by using `clear()`.

    function populateStorage() {
      localStorage.setItem('bgcolor', 'red');
      localStorage.setItem('font', 'Helvetica');
      localStorage.setItem('image', 'miGato.png');

      localStorage.clear();
    }

**Note**: For a real world example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-storage-clear">HTML Living Standard<br />
<span class="small">The definition of 'Storage.clear' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`clear`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage/clear" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage/clear</a>
