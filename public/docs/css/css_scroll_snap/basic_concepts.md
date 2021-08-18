# Basic concepts of CSS Scroll Snap

The [CSS Scroll Snap specification](https://drafts.csswg.org/css-scroll-snap-1/) gives us a way to snap scrolling to certain points as the user scrolls through a document. This can be helpful in creating a more app-like experience on mobile or even on the desktop for some types of applications.

## Basics of Scroll Snap

The key properties of the Scroll Snap specification are [`scroll-snap-type`](../scroll-snap-type) and [`scroll-snap-align`](../scroll-snap-align). The `scroll-snap-type` property is used on the [scroll container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container) to state the type and direction of scrolling.

The `scroll-snap-align` property must be used on child elements in order to set the position that scrolling will snap to. The below example demonstrates scroll snapping along the `y` axis, with `scroll-snap-align` used on the section element to dictate the point the scrolling should stop.

## Using scroll-snap-type

The [`scroll-snap-type`](../scroll-snap-type) property needs to know the direction in which scroll snapping happens. This could be `x` or `y`, or the logical mappings `block` or `inline`. You can also use the keyword `both` to have scroll snapping work along both axes.

You can also pass in the keywords `mandatory`, or `proximity`. The `mandatory` keyword tells the browser whether the content _has_ to snap to a certain point, no matter where the scroll is. The `proximity` keyword means that it may snap to the point, but does not have to.

Using `mandatory` gives a very consistent experience — you know that the browser will always snap to each defined point. This means you can be confident that something you expect to be at the top of the screen will be when scrolling finishes. However, it can cause problems if the content is larger than you expect — users may find themselves in the frustrating position of never being able to scroll and view a certain point in the content. Therefore, use of mandatory should be carefully considered and only used in situations where you know how much content is on the screen at any one time.

The `proximity` value will only snap to a position when it is close by, the exact distance being left to the browser to decide. In the example below you can change the value between `mandatory` and `proximity` to see the effect this has on the scroll experience.

## Using scroll-snap-align

The [`scroll-snap-align`](../scroll-snap-align) property can take a value of `start`, `end`, or `center` — indicating the point the content should snap to in the scroll container. In the below example you can change the value of `scroll-snap-align` to see how this changes the scroll behavior.

## Padding the scroll container

If you do not want the content to snap right to the edge of the scroll container you can use the [`scroll-padding`](../scroll-padding) property or its equivalent longhand values to set some padding.

In the below example I have set `scroll-padding` to 40 pixels. When we snap to the start of the second and third sections, the scrolling stops 40 pixels away from the start of the section. Try changing the `scroll-padding` value to see how this changes the distance.

This is potentially useful if you have a fixed element, for example a navigation bar, which could end up overlapping scrolled content. By using `scroll-padding` you can reserve a space for it as in the example below where my `<h1>` remains on screen as the content scrolls beneath it. Without padding, the heading would overlap some of the content when snapping happens.

## Margins on scroll children

The [`scroll-margin`](../scroll-margin) property can be set on child elements, essentially defining an outset from the defined box. This allows for different amounts of space for different child elements, and can be used in conjunction with `scroll-padding` on the parent. Try this in the example below.

## The scroll-snap-stop property

The [`scroll-snap-stop`](../scroll-snap-stop) property tells the browser whether it should snap to each defined snap point — meaning that in our examples above we would stop at the start of each section — or be able to skip past sections. This property has fewer browser implementations than the rest of the specification.

It could be helpful in ensuring users see each section of the scroller and don't accidentally zip past them. However it could be problematic in making the scrolling experience slower if the user is looking for a particular section.

**Note**: the `scroll-snap-stop` property is currently marked at risk in the current Candidate Recommendation spec, therefore it may be removed.

## Browser compatibility

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Scroll_Snap/Basic_concepts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Scroll_Snap/Basic_concepts</a>
