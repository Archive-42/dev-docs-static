# Document.getElementsByName()

The `getElementsByName()` method of the [`Document`](../document) object returns a [`NodeList`](../nodelist) Collection of elements with a given [`name`](../index) in the document.

## Syntax

    var elements = document.getElementsByName(name);

- elements is a live [`NodeList`](../nodelist) Collection, meaning it automatically updates as new elements with the same `name` are added to/removed from the document.
- name is the value of the `name` attribute of the element(s).

## Example

    <!DOCTYPE html>
    <html lang="en">
    <title>Example: using document.getElementsByName</title>

    <input type="hidden" name="up">
    <input type="hidden" name="down">

    <script>
      var up_names = document.getElementsByName("up");
      console.log(up_names[0].tagName); // displays "INPUT"
    </script>
    </html>

## Notes

The [`name`](../index) attribute can only be applied in (X)HTML documents.

The returned [`NodeList`](../nodelist) Collection contains _all_ elements with the given `name`, such as [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), and even elements which do not support the `name` attribute at all.

The **getElementsByName** method works differently in IE10 and below. There, `getElementsByName()` also returns elements that have an [`id` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) with the specified value. Be careful not to use the same string as both a `name` and an `id`.

The **getElementsByName** method works differently in IE. There, `getElementsByName()` does not return all elements which may not have a `name` attribute (such as `<span>`).

Both IE and Edge return an [`HTMLCollection`](../htmlcollection), not a [`NodeList`](../nodelist)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-getelementsbyname">HTML Living Standard<br />
<span class="small">The definition of 'Document.getElementsByName()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-71555259">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'Document.getElementsByName()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`getElementsByName`

1

12

Before Edge 79, this method returns an `HTMLCollection`, not a `NodeList`.

1

5

Returns an `HTMLCollection`, not a `NodeList`

5

1

1

18

4

10.1

1

1.0

## See also

- [`document.getElementById()`](getelementbyid) to return a reference to an element by its unique `id`
- [`document.getElementsByTagName()`](getelementsbytagname) to return references to elements with the same [tag name](../element/tagname)
- [`document.querySelector()`](queryselector) to return references to elements via CSS selectors like `'div.myclass'`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName</a>
