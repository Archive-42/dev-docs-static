Storage.getItem()
=================

The `getItem()` method of the [`Storage`](../storage) interface, when passed a key name, will return that key's value, or `null` if the key does not exist, in the given `Storage` object.

Syntax
------

    var aValue = storage.getItem(keyName);

### Parameters

`keyName`  
A [`DOMString`](../domstring) containing the name of the key you want to retrieve the value of.

### Return value

A [`DOMString`](../domstring) containing the value of the key. If the key does not exist, `null` is returned.

Example
-------

The following function retrieves three data items from local storage, then uses them to set custom styles on a page.

    function setStyles() {
      var currentColor = localStorage.getItem('bgcolor');
      var currentFont = localStorage.getItem('font');
      var currentImage = localStorage.getItem('image');

      document.getElementById('bgcolor').value = currentColor;
      document.getElementById('font').value = currentFont;
      document.getElementById('image').value = currentImage;

      htmlElem.style.backgroundColor = '#' + currentColor;
      pElem.style.fontFamily = currentFont;
      imgElem.setAttribute('src', currentImage);
    }

**Note**: To see this used within a real world example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webstorage.html#dom-storage-getitem">HTML Living Standard<br />
<span class="small">The definition of 'Storage.getItem' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getItem`

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

-   [Storage.setItem()](setitem)
-   [Using the Web Storage API](../web_storage_api/using_the_web_storage_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage/getItem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage/getItem</a>
