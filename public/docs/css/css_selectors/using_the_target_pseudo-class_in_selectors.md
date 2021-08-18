# Using the :target pseudo-class in selectors

When a URL points at a specific piece of a document, it can be difficult for the user to notice. Find out how you can use some simple CSS to draw attention to the target of a URL and improve the user's experience.

## Picking a Target

The [pseudo-class](../pseudo-classes) [`:target`](../:target) is used to style the target element of a URL containing a fragment identifier. For example, the URL `https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors/Using_the_:target_pseudo-class_in_selectors#example` contains the fragment identifier `#example`. In HTML, identifiers are found as the values of either `id` or `name` attributes, since the two share the same namespace. Thus, the example URL would point to the heading "example" in this document.

Suppose you wish to style any `h2` element that is the target of a URL, but do not want any other kind of element to get a target style. This is simple enough:

    h2:target { font-weight: bold; }

It's also possible to create styles that are specific to a particular fragment of the document. This is done using the same identifying value that is found in the URI. Thus, to add a border to the `#example` fragment, we would write:

    #example:target { border: 1px solid black; }

## Targeting all elements

If the intent is to create a "blanket" style that will apply to all targeted elements, then the universal selector comes in handy:

    :target { color: red; }

## Example

In the following example, there are five links that point to elements in the same document. Selecting the "First" link, for example, will cause `<h1 id="one">` to become the target element. Note that the document may jump to a new scroll position, since target elements are placed on the top of the browser window if possible.

    <h4 id="one">...</h4> <p id="two">...</p>
    <div id="three">...</div> <a id="four">...</a> <em id="five">...</em>

    <a href="#one">First</a>
    <a href="#two">Second</a>
    <a href="#three">Third</a>
    <a href="#four">Fourth</a>
    <a href="#five">Fifth</a>

## Conclusion

In cases where a fragment identifier points to a portion of the document, readers may become confused about which part of the document they're supposed to be reading. By styling the target of a URI, reader confusion can be reduced or eliminated.

## See also

- [`:target`](../:target)

### Original Document Information

- Author(s): Eric Meyer, Standards Evangelist, Netscape Communications
- Original Copyright Information: Copyright © 2001-2003 Netscape. All rights reserved.
- Note: This reprinted article was originally part of the DevEdge site.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors/Using_the_:target_pseudo-class_in_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS*Selectors/Using_the*:target_pseudo-class_in_selectors</a>
