# HTMLCollection.length

The `HTMLCollection.length` property returns the number of items in a [`HTMLCollection`](../htmlcollection).

## Syntax

    numItems = htmlCollection.length

- `numItems` is an integer value representing the number of items in a `HTMLCollection`.

## Example

The `length` property is often useful in DOM programming. It's often used to test the length of a list, to see if it exists at all. It's also commonly used as the iterator in a `for` loop, as in this example.

    // All the elements with the class ".test" in the document
    var items = document.getElementsByClassName("test");

    // For each test item in the list,
    // append the entire element as a string of HTML
    var gross = "";
    for (var i = 0; i < items.length; i++) {
      gross += items[i].innerHTML;
    }

    // gross is now all the HTML for the test elements

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-htmlcollection-length">DOM<br />
<span class="small">The definition of 'HTMLCollection: length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection/length</a>
