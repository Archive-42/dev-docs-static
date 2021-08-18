NodeList
========

`NodeList` objects are collections of [nodes](node), usually returned by properties such as [`Node.childNodes`](node/childnodes) and methods such as [`document.querySelectorAll()`](document/queryselectorall).

Although `NodeList` is not an `Array`, it is possible to iterate over it with `forEach()`. It can also be converted to a real `Array` using [`Array.from()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from).

However, some older browsers have not implemented `NodeList.forEach()` nor `Array.from()`. This can be circumvented by using [`Array.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) — see this document's [Example](#example).

Live vs. Static NodeLists
-------------------------

Although they are both considered `NodeList`s, there are 2 varieties of NodeList: *live* and *static*.

### Live NodeLists

In some cases, the `NodeList` is *live*, which means that changes in the DOM automatically update the collection.

For example, [`Node.childNodes`](node/childnodes) is live:

    const parent = document.getElementById('parent');
    let child_nodes = parent.childNodes;
    console.log(child_nodes.length); // let's assume "2"
    parent.appendChild(document.createElement('div'));
    console.log(child_nodes.length); // outputs "3"

### Static NodeLists

In other cases, the `NodeList` is *static,* where any changes in the DOM does not affect the content of the collection. The ubiquitous [`document.querySelectorAll()`](document/queryselectorall) method returns a *static* `NodeList`.

It's good to keep this distinction in mind when you choose how to iterate over the items in the `NodeList`, and whether you should cache the list's `length`.

Properties
----------

[`NodeList.length`](nodelist/length)  
The number of nodes in the `NodeList`.

Methods
-------

[`NodeList.item()`](nodelist/item)  
Returns an item in the list by its index, or `null` if the index is out-of-bounds.

An alternative to accessing `nodeList[i]` (which instead returns `undefined` when `i` is out-of-bounds). This is mostly useful for non-JavaScript DOM implementations.

[`NodeList.entries()`](nodelist/entries)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing code to go through all key/value pairs contained in the collection. (In this case, the keys are numbers starting from `0` and the values are nodes.)

[`NodeList.forEach()`](nodelist/foreach)  
Executes a provided function once per `NodeList` element, passing the element as an argument to the function.

[`NodeList.keys()`](nodelist/keys)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols), allowing code to go through all the keys of the key/value pairs contained in the collection. (In this case, the keys are numbers starting from `0`.)

[`NodeList.values()`](nodelist/values)  
Returns an [`iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols) allowing code to go through all values (nodes) of the key/value pairs contained in the collection.

Example
-------

It's possible to loop over the items in a `NodeList` using a [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) loop:

    for (let i = 0; i < myNodeList.length; i++) {
      let item = myNodeList[i];
    }

**Don't use `for...in` to enumerate the items in `NodeList`s**, since they will *also* enumerate its `length` and `item` properties and cause errors if your script assumes it only has to deal with [`element`](element) objects. Also, `for..in` is not guaranteed to visit the properties in any particular order.

`for...of` loops **will** loop over `NodeList` objects correctly:

    const list = document.querySelectorAll('input[type=checkbox]');
    for (let checkbox of list) {
      checkbox.checked = true;
    }

Recent browsers also support iterator methods ([`forEach()`](nodelist/foreach)) as well as [`entries()`](nodelist/entries), [`values()`](nodelist/values), and [`keys()`](nodelist/keys).

There is also an Internet Explorer-compatible way to use [`Array.prototype.forEach`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) for iteration:

    const list = document.querySelectorAll('input[type=checkbox]');
    Array.prototype.forEach.call(list, function (checkbox) {
      checkbox.checked = true;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-nodelist">DOM<br />
<span class="small">The definition of 'NodeList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-536297177">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'NodeList' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-536297177">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'NodeList' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-536297177">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'NodeList' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`NodeList`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

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

`forEach`

51

16

50

No

38

10

51

51

50

41

10

5.0

`item`

1

12

1

5

Yes

1

Yes

Yes

4

Yes

1

Yes

`keys`

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

`length`

1

12

1

5

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`values`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeList</a>
