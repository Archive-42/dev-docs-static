# DocumentFragment.querySelector()

The `DocumentFragment.querySelector()` method returns the first element, or `null` if no matches are found, within the [`DocumentFragment`](../documentfragment) (using depth-first pre-order traversal of the document's nodes) that matches the specified group of selectors.

If the selector matches an ID and this ID is erroneously used several times in the document, it returns the first matching element.

If the selectors specified in parameter are invalid a [`DOMException`](../domexception) with a `SYNTAX_ERR` value is raised.

## Syntax

    element = documentfragment.querySelector(selectors);

### Parameters

_selectors_  
Is a [`DOMString`](../domstring) containing one or more CSS selectors separated by commas.

## Examples

### Basic example

In this basic example, the first element in the [`DocumentFragment`](../documentfragment) with the class "`myclass`" is returned:

    var el = documentfragment.querySelector(".myclass");

### CSS syntax and the method's argument

The string argument pass to `querySelector` must follow the CSS syntax. To match ID or selectors that do not follow the CSS syntax (by using semicolon or space inappropriately for example), it's mandatory to escape the wrong character with a double back slash:

    <div id="foo\bar"></div>
    <div id="foo:bar"></div>

    <script>
    document.querySelector('#foo\bar')    // Does not match anything
    document.querySelector('#foo\\\\bar') // Match the first div
    document.querySelector('#foo:bar')     // Does not match anything
    document.querySelector('#foo\\:bar')   // Match the second div
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dev.w3.org/2006/webapi/selectors-api2/#queryselector">Selectors API Level 2<br />
<span class="small">The definition of 'DocumentFragment.querySelector' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/selectors-api/">Selectors API Level 1</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/selectors-api/#queryselector">Selectors API Level 1<br />
<span class="small">The definition of 'DocumentFragment.querySelector' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`querySelector`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

4

1

18

4

10.1

3

1.0

## See also

- The [`DocumentFragment`](../documentfragment) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelector" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/querySelector</a>
