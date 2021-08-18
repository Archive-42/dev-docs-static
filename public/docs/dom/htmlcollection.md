# HTMLCollection

The `HTMLCollection` interface represents a generic collection (array-like object similar to [`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)) of elements (in document order) and offers methods and properties for selecting from the list.

**Note:** This interface is called `HTMLCollection` for historical reasons (before the modern DOM, collections implementing this interface could only have HTML elements as their items).

An `HTMLCollection` in the HTML DOM is live; it is automatically updated when the underlying document is changed.

## Properties

[`HTMLCollection.length`](htmlcollection/length) <span class="badge inline readonly">Read only </span>  
Returns the number of items in the collection.

## Methods

[`HTMLCollection.item()`](htmlcollection/item)  
Returns the specific node at the given zero-based `index` into the list. Returns `null` if the `index` is out of range.

An alternative to accessing `collection[i]` (which instead returns `undefined` when `i` is out-of-bounds). This is mostly useful for non-JavaScript DOM implementations.

<span class="page-not-created">`HTMLCollection.namedItem()`</span>  
Returns the specific node whose ID or, as a fallback, name matches the string specified by `name`. Matching by name is only done as a last resort, only in HTML, and only if the referenced element supports the `name` attribute. Returns `null` if no node exists by the given name.

An alternative to accessing `collection[name]` (which instead returns `undefined` when `name` does not exist). This is mostly useful for non-JavaScript DOM implementations.

## Usage in JavaScript

`HTMLCollection` also exposes its members directly as properties by both name and index. HTML IDs may contain `:` and `.` as valid characters, which would necessitate using bracket notation for property access. Currently `HTMLCollections` does not recognize purely numeric IDs, which would cause conflict with the array-style access, though HTML5 does permit these.

For example, assuming there is one `<form>` element in the document and its `id` is `myForm`:

    var elem1, elem2;

    // document.forms is an HTMLCollection

    elem1 = document.forms[0];
    elem2 = document.forms.item(0);

    alert(elem1 === elem2); // shows: "true"

    elem1 = document.forms.myForm;
    elem2 = document.forms.namedItem("myForm");

    alert(elem1 === elem2); // shows: "true"

    elem1 = document.forms["named.item.with.periods"];

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#htmlcollection">DOM<br />
<span class="small">The definition of 'HTMLCollection' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`HTMLCollection`

1

12

1

8

8

1

1

18

4

10.1

1

1.0

`item`

1

12

1

8

≤12.1

1

1

18

4

≤12.1

1

1.0

`length`

1

12

1

8

≤12.1

Yes

1

18

4

≤12.1

Yes

1.0

`namedItem`

1

12

1

8

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`NodeList`](nodelist)
- [`HTMLFormControlsCollection`](htmlformcontrolscollection), [`HTMLOptionsCollection`](htmloptionscollection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection</a>
