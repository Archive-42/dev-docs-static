# Browser compatibility and Scroll Snap

Firefox initially implemented an early version of the Scroll Snap Specification, called Scroll Snap Points. In Firefox 68 the new version of the specification will be shipped and these old properties removed.

In this article, we consider questions that might arise related to compatibility across browsers and versions of browsers when adding support for scroll-snap to your web site or app.

## What should I do if I used the old Firefox implementation?

If you have only used the old Firefox implementation of the specification, with the properties that are detailed in Scroll Snap Points, you should update your code to use the new specification. This will ensure your scroll snapping works in all browsers which implement the specification, including Firefox. If you do not do this your scroll snapping will no longer work in Firefox 68 and up.

The main things to note are as follows:

- The [`scroll-snap-type-x`](../scroll-snap-type-x) and [`scroll-snap-type-y`](../scroll-snap-type-y) properties have been dropped
- The [`scroll-snap-type`](../scroll-snap-type) property has become a longhand, so the old shorthand syntax like `scroll-snap-type:mandatory` will stop working

## Can I use the old implementation as a fallback?

If you have already used the old implementation as a fallback, or feel you want to support users of old Firefox (or -webkit prefixed Safari), then you can continue to use the old specification as outlined in the example below.

In this initial example we have used the old specification alongside the current specification in order to make scroll snapping work in all browsers which support some form of scroll snapping.

The example adds the [`scroll-snap-points-y`](../scroll-snap-points-y) and [`scroll-snap-destination`](../scroll-snap-destination) properties, which are deprecated, to make scroll snapping work in Firefox. We also added the [`scroll-snap-type`](../scroll-snap-type) property twice, once with the `y` axis value needed for browsers that support the new spec, and once for Firefox pre-68, which supports the property but without the `y` value.

## Do I need to use both specs?

Scroll snapping is one of those nice parts of CSS in which the fallback is that you don't get the enhanced functionality, but everything still works. I would suggest at this point you should implement the new specification only, unless you have data to show a large number of users who would benefit from a fallback version.

If you want to test using [Feature Queries](../@supports) for support of the new spec then we'd suggest testing for [`scroll-snap-align`](../scroll-snap-align) as this property did not exist in the old implementation. However, these properties shouldn't cause any problems to non-supporting browsers due to the way that browsers ignore CSS that they do not understand.

## Why are there two versions of scroll snap?

Finally, you might wonder why we ended up in a scenario where two versions exist at all. This is the reality of developing new CSS — it can't be developed in a vacuum away from browser implementations. At some point browsers need to implement a spec to show that it works, and to discover any problems that only become apparent when the spec is in use alongside other properties in the real world. In such cases we can end up with implementations of older versions available alongside newer versions as browsers are in the process of updating.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Scroll_Snap/Browser_compat" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Scroll_Snap/Browser_compat</a>
