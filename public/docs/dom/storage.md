Storage
=======

The `Storage` interface of the [Web Storage API](web_storage_api) provides access to a particular domain's session or local storage. It allows, for example, the addition, modification, or deletion of stored data items.

To manipulate, for instance, the session storage for a domain, a call to [`Window.sessionStorage`](window/sessionstorage) is made; whereas for local storage the call is made to [`Window.localStorage`](window/localstorage).

Properties
----------

 [`Storage.length`](storage/length) <span class="badge inline readonly">Read only </span>   
Returns an integer representing the number of data items stored in the `Storage` object.

Methods
-------

[`Storage.key()`](storage/key)  
When passed a number `n`, this method will return the name of the nth key in the storage.

[`Storage.getItem()`](storage/getitem)  
When passed a key name, will return that key's value.

[`Storage.setItem()`](storage/setitem)  
When passed a key name and value, will add that key to the storage, or update that key's value if it already exists.

[`Storage.removeItem()`](storage/removeitem)  
When passed a key name, will remove that key from the storage.

[`Storage.clear()`](storage/clear)  
When invoked, will empty all keys out of the storage.

Examples
--------

Here we access a `Storage` object by calling `localStorage`. We first test whether the local storage contains data items using `!localStorage.getItem('bgcolor')`. If it does, we run a function called `setStyles()` that grabs the data items using [`Storage.getItem()`](storage/getitem) and uses those values to update page styles. If it doesn't, we run another function, `populateStorage()`, which uses [`Storage.setItem()`](storage/setitem) to set the item values, then runs `setStyles()`.

    if(!localStorage.getItem('bgcolor')) {
      populateStorage();
    } else {
      setStyles();
    }

    function populateStorage() {
      localStorage.setItem('bgcolor', document.getElementById('bgcolor').value);
      localStorage.setItem('font', document.getElementById('font').value);
      localStorage.setItem('image', document.getElementById('image').value);

      setStyles();
    }

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

**Note**: To see this running as a complete working example, see our [Web Storage Demo](https://mdn.github.io/dom-examples/web-storage/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#storage">HTML Living Standard<br />
<span class="small">The definition of 'Storage' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Storage`

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

-   [Using the Web Storage API](web_storage_api/using_the_web_storage_api)
-   [`Window.localStorage`](window/localstorage)
-   [`Window.sessionStorage`](window/sessionstorage)
-   [`CacheStorage`](cachestorage)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage</a>
