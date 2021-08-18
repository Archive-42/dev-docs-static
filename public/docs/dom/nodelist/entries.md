NodeList.entries()
==================

The `NodeList.entries()` method returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing to go through all key/value pairs contained in this object. The values are [`Node`](../node) objects.

Syntax
------

    list.entries();

### Return value

Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols).

Example
-------

    var node = document.createElement("div");
    var kid1 = document.createElement("p");
    var kid2 = document.createTextNode("hey");
    var kid3 = document.createElement("span");
    node.appendChild(kid1);
    node.appendChild(kid2);
    node.appendChild(kid3);

    var list = node.childNodes;

    // Using for..of
    for(var entry of list.entries()) {
      console.log(entry);
    }

results in:

    Array [ 0, <p> ]
    Array [ 1, #text "hey" ]
    Array [ 2, <span> ]

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

`entries`

51

16

50

No

38

10

51

51

50

?

10

5.0

See also
--------

-   [`Node`](../node)
-   [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeList/entries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeList/entries</a>
