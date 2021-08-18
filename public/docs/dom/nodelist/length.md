# NodeList.length

The `NodeList.length` property returns the number of items in a [`NodeList`](../nodelist).

## Syntax

    numItems = nodeList.length

- `numItems` is an integer value representing the number of items in a `NodeList`.

## Example

The `length` property is often useful in DOM programming. It's often used to test the length of a list, to see if it exists at all. It's also commonly used as the iterator in a `for` loop, as in this example.

    // All the paragraphs in the document
    const items = document.getElementsByTagName("p");

    // For each item in the list,
    // append the entire element as a string of HTML
    let gross = "";
    for (let i = 0; i < items.length; i++) {
      gross += items[i].innerHTML;
    }

    // gross is now all the HTML for the paragraphs

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodelist-length">DOM<br />
<span class="small">The definition of 'NodeList: length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

5

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeList/length</a>
