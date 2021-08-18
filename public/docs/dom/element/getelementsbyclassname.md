# Element.getElementsByClassName()

The [`Element`](../element) method `getElementsByClassName()` returns a live [`HTMLCollection`](../htmlcollection) which contains every descendant element which has the specified class name or names.

The method [`getElementsByClassName()`](../document/getelementsbyclassname) on the [`Document`](../document) interface works essentially the same way, except it acts on the entire document, starting at the document root.

## Syntax

    var elements = element.getElementsByClassName(names);

### Parameters

`names`  
A [`DOMString`](../domstring) containing one or more class names to match on, separated by whitespace.

### Return value

An [`HTMLCollection`](../htmlcollection) providing a live-updating list of every element which is a member of every class in `names`.

## Usage notes

As always, the returned collection is _live_, meaning that it always reflects the current state of the DOM tree rooted at the element on which the function was called. As new elements that match `names` are added to the subtree, they immediately appear in the collection. Similarly, if an existing element that doesn't match `names` has its set of classes adjusted so that it matches, it immediately appears in the collection.

The opposite is also true; as elements no longer match the set of names, they are immediately removed from the collection.

In [quirks mode](https://developer.mozilla.org/en-US/docs/Web/HTML/Quirks_Mode_and_Standards_Mode), the class names are compared in a case-insensitive fashion. Otherwise, they're case sensitive.

## Examples

### Matching a single class

To look for elements that include among their classes a single specified class, we just provide that class name when calling `getElementsByClassName()`:

    element.getElementsByClassName('test');

This example finds all elements that have a class of `test`, which are also a descendant of the element that has the `id` of `main`:

    document.getElementById('main').getElementsByClassName('test');

### Matching multiple classes

To find elements whose class lists include both the `red` and `test` classes:

    element.getElementsByClassName('red test');

### Examining the results

You can use either the [`item()`](../htmlcollection/item) method on the returned `HTMLCollection` or standard array syntax to examine individual elements in the collection. However <span class="underline">**the following code will not work**</span> as one might expect because `"matches"` will change as soon as any `"colorbox"` class is removed.

    var matches = element.getElementsByClassName('colorbox');

    for (var i=0; i<matches.length; i++) {
      matches[i].classList.remove('colorbox');
      matches.item(i).classList.add('hueframe');
    }

Instead, use another method, such as:

    var matches = element.getElementsByClassName('colorbox');

    while (matches.length > 0) {
      matches.item(0).classList.add('hueframe');
      matches[0].classList.remove('colorbox');
    }

This code finds descendant elements with the `"colorbox"` class, adds the class `"hueframe"`, by calling `item(0), `then removes `"colorbox" `(using array notation). Another element (if any are left) will then become `item(0)`.

### Filtering the results using array methods

We can also use methods of <span class="page-not-created">`Array.prototype`</span> on any [`HTMLCollection`](../htmlcollection) by passing the [`HTMLCollection`](../htmlcollection) as the method's `this` value. Here we'll find all [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) elements that have a class of `test`:

    var testElements = document.getElementsByClassName('test');
    var testDivs = Array.prototype.filter.call(testElements, function(testElement) {
      return testElement.nodeName === 'DIV';
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getelementsbyclassname">DOM<br />
<span class="small">The definition of 'Element.getElementsByClassName()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`getElementsByClassName`

1

16

12-16

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

3

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

9

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

9.5

6

1

18

4

10.1

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName</a>
