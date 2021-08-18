# CSS Containment

The aim of the CSS Containment specification is to improve performance of web pages by allowing developers to isolate a subtree of the page from the rest of the page. If the browser knows that a part of the page is independent, rendering can be optimized and performance improved. The specification defines a single CSS property [`contain`](contain). This document describes the basic aims of the specification.

## Basic example

Many webpages contain a number of sections which are independent of each other. For example a listing of article headlines and content, as in the mark-up below.

    <h1>My blog</h1>
    <article>
      <h2>Heading of a nice article</h2>
      <p>Content here.</p>
    </article>
    <article>
      <h2>Another heading of another article</h2>
      <p>More content here.</p>
    </article>

Each article has the [`contain`](contain) property with a value of `content` applied in the CSS.

    article {
      contain: content;
    }

Each article is independent of the other articles on the page, and so they have been given `contain: content` in order to indicate to the browser that this is the case. The browser can then use this information to make decisions about how to render the content. For example, it might not render articles that are outside the viewable area.

If we give each `<article>` the `contain` property with a value of `content`, when new elements are inserted the browser understands it does not need to relayout or repaint any area outside of the containing element's subtree, although if the `<article>` is styled such that its size depends on its contents (e.g. with `height: auto`), then the browser may need to account for its size changing).

We have told it by way of the `contain` property that each article is independent.

The `content` value is shorthand for `contain: layout paint`. It tells the browser that the internal layout of the element is totally separate from the rest of the page, and that everything about the element is painted inside its bounds. Nothing can visibly overflow.

This information is something that is usually known, and in fact quite obvious, to the web developer creating the page. However browsers cannot guess at your intent and cannot assume that an article will be entirely self-contained. Therefore this property gives you a nice way to explain to the browser this fact, and allow it to make performance optimizations based on that knowledge.

## Key concepts and terminology

This specification defines only one property, the [`contain`](contain) property. The values for this property indicate the type of containment that you want to apply to that element.

### Layout containment

    article {
      contain: layout;
    }

Layout is normally scoped to the entire document, which means that if you move one element the entire document needs to be treated as if things could have moved anywhere. By using `contain: layout` you can tell the browser it only needs to check this element — everything inside the element is scoped to that element and does not affect the rest of the page, and the containing box establishes an independent formatting context.

In addition:

- `float` layout will be performed independently.
- Margins won't collapse across a layout containment boundary
- The layout container will be a containing block for `absolute`/`fixed` position descendants.
- The containing box creates a stacking context, therefore [`z-index`](z-index) can be used.

### Paint containment

    article {
      contain: paint;
    }

Paint containment essentially clips the box to the padding edge of the principal box. There can be no visible overflow. The same things are true for `paint` containment as `layout` containment (see above).

Another advantage is that if the containing box is offscreen, the browser does not need to paint its contained elements — these must also be offscreen as they are contained completely by that box.

### Size containment

    article {
      contain: size;
    }

Size containment does not offer much in the way of performance optimizations when used on its own. However, it means that the size of the element's children cannot affect the size of the element itself — its size is computed as if it had no children.

If you turn on `contain: size` you need to also specify the size of the element you have applied this to. It will end up being zero-sized in most cases, if you don't manually give it a size.

### Style containment

    article {
      contain: style;
    }

Despite the name, style containment does not provide scoped styles such as you would get with the [Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM). The main use case is to prevent situations where a [CSS Counter](css_lists_and_counters/using_css_counters) could be changed in an element, which could then affect the rest of the tree.

Using `contain: style` would ensure that the [`counter-increment`](counter-increment) and [`counter-set`](counter-set) properties created new counters scoped to that subtree only.

**Note**: `style` containment is "at-risk" in the spec and may not be supported everywhere (it's not currently supported in Firefox).

### Special values

There are two special values of contain:

- `content`
- `strict`

We encountered the first in the example above. Using `contain: content` turns on `layout` and `paint` containment. The specification describes this value as being "reasonably safe to apply widely". It does not apply `size` containment, so you would not be at risk of a box ending up zero-sized due to a reliance on the size of its children.

To gain as much containment as possible use `contain: strict`, which behaves the same as `contain: size layout paint`, or perhaps the following to also add `style` containment in browsers that support it:

    contain: strict;
    contain: strict style;

## Reference

### CSS Properties

- [`contain`](contain)
- [`content-visibility`](content-visibility)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-contain-2/#contain-property">CSS Containment Module Level 2<br />
<span class="small">The definition of 'contain' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added <code>style</code> keyword</td></tr></tbody></table>

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

`CSS_Containment`

85

85

No

No

71

No

85

85

No

60

No

No

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

`CSS_Containment`

52

79

69

Firefox does not support the `style` value.

41

No

40

No

52

52

41

Firefox does not support the `style` value.

41

No

6.0

BCD tables only load in the browser

BCD tables only load in the browser

## External resources

- [An Introduction to CSS Containment](https://blogs.igalia.com/mrego/2019/01/11/an-introduction-to-css-containment/)
- [Everything You Need to Know About the CSS `will-change` Property](https://dev.opera.com/articles/css-will-change-property)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Containment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Containment</a>
