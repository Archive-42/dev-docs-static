# Element.ariaCurrent

The `ariaCurrent` property of the [`Element`](../element) interface reflects the value of the `aria-current` attribute, which indicates the element that represents the current item within a container or set of related elements.

## Syntax

    var ariaCurrent = element.ariaCurrent;
    element.ariaCurrent = ariaCurrent

### Value

A [`DOMString`](../domstring) with one of the following values:

`"page"`  
Represents the current page within a set of pages.

`"step"`  
Represents the current step within a process.

`"location"`  
Represents the current location, for example the current page in a breadcrumbs hierarchy.

`"date"`  
Represents the current date within a collection of dates.

`"time"`  
Represents the current time within a set of times.

`"true"`  
Represents the current item within a set.

`"false"`  
Does not represent the current item within a set.

## Examples

In this example a set of links are used for site navigation. The `aria-current` attribute indicates the current page. The value `page` is incorporated into the screenreader announcement. Using `ariaCurrent` we can update that value.

    <nav>
      <ul>
        <li><a id="link-home" href="/" aria-current="page">Home</a></li>
        <li><a href="/">About</a></li>
        <li><a href="/">Contact</a></li>
      </ul>
    </nav>

    let el = document.getElementById('link-home');
    console.log(el.ariaCurrent); // "page"
    el.ariaCurrent = "tab"
    console.log(el.ariaCurrent); // "tab"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariacurrent">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaCurrent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaCurrent`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

## See also

- [Using the aria-current attribute](https://tink.uk/using-the-aria-current-attribute/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaCurrent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaCurrent</a>
