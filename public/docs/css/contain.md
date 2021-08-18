# contain

The `contain` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows an author to indicate that an element and its contents are, as much as possible, _independent_ of the rest of the document tree. This allows the browser to recalculate layout, style, paint, size, or any combination of them for a limited area of the DOM and not the entire page, leading to obvious performance benefits.

This property is useful on pages that contain a lot of widgets that are all independent, as it can be used to prevent each widget's internals from having side effects outside of the widget's bounding-box.

**Note:** If applied (with value: `paint`, `strict` or `content`), this property creates:

1.  A new [containing block](containing_block) (for the descendants whose [`position`](position) property is `absolute` or `fixed`).
2.  A new [stacking context](css_positioning/understanding_z_index/the_stacking_context).
3.  A new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context).

## Syntax

    /* Keyword values */
    contain: none;
    contain: strict;
    contain: content;
    contain: size;
    contain: layout;
    contain: style;
    contain: paint;

    /* Multiple keywords */
    contain: size paint;
    contain: size layout paint;

    /* Global values */
    contain: inherit;
    contain: initial;
    contain: unset;

The `contain` property is specified as either one of the following:

- Using a single `none`, `strict`, or `content` keyword.
- Using one or more of the `size`, `layout`, `style`, and `paint` keywords in any order.

### Values

`none`  
Indicates the element renders as normal, with no containment applied.

`strict`  
Indicates that all containment rules except `style` are applied to the element. This is equivalent to `contain: size layout paint`.

`content`  
Indicates that all containment rules except `size` and `style` are applied to the element. This is equivalent to `contain: layout paint`.

`size`  
Indicates that the element can be sized without the need to examine its descendants' sizes.

`layout`  
Indicates that nothing outside the element may affect its internal layout and vice versa.

`style`  
Indicates that, for properties that can have effects on more than just an element and its descendants, those effects don't escape the containing element. Note that this value is marked "at-risk" in the spec and may not be supported everywhere.

`paint`  
Indicates that descendants of the element don't display outside its bounds. If the containing box is offscreen, the browser does not need to paint its contained elements — these must also be offscreen as they are contained completely by that box. And if a descendant overflows the containing element's bounds, then that descendant will be clipped to the containing element's border-box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | strict | content | [ size || layout || style || paint ]

## Examples

### Simple layout

The markup below consists of a number of articles, each with content:

    <h1>My blog</h1>
    <article>
      <h2>Heading of a nice article</h2>
      <p>Content here.</p>
    </article>
    <article>
      <h2>Another heading of another article</h2>
      <img src="graphic.jpg" alt="photo">
      <p>More content here.</p>
    </article>

Each `<article>` and `<img>` is given a border, and the images are floated:

    img {
      float: left;
      border: 3px solid black;
    }

    article {
      border: 1px solid black;
    }

You can immediately see an issue — no effort is made to clear the floating beyond the bottom of the article.

### Float interference

If we were to insert another image at the bottom of the first article, a large portion of the DOM tree may be re-laid out or repainted, and this would interfere further with the layout of the second article:

    <h1>My blog</h1>
    <article>
      <h2>Heading of a nice article</h2>
      <p>Content here.</p>
      <img src="i-just-showed-up.jpg" alt="social">
    </article>
    <article>
      <h2>Another heading of another article</h2>
      <img src="graphic.jpg" alt="photo">
      <p>More content here.</p>
    </article>

As you can see, because of the way floats work, the first image ends up inside the area of the second article:

### Fixing with contain

If we give each `article` the `contain` property with a value of `content`, when new elements are inserted the browser understands it only needs to recalculate the containing element's subtree, and not anything outside it:

    img {
      float: left;
      border: 3px solid black;
    }

    article {
      border: 1px solid black;
      contain: content;
    }

This also means that the first image no longer floats down to the second article, and instead stays inside it's containing element's bounds:

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

`contain`

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

## See also

- [CSS containment](css_containment)
- CSS [`content-visibility`](content-visibility) property
- CSS [`position`](position) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/contain" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/contain</a>
