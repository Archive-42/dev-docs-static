# &lt;shape&gt;

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<shape>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) defines the specific form (shape) of a region. The region represents the part of an element to which the [`clip`](clip) property applies.

**Note:** `<shape>` and `rect()` work in conjunction with [`clip`](clip), which has been deprecated in favor of [`clip-path`](clip-path). When possible, use `clip-path` and the [`<basic-shape>`](basic-shape) data type instead.

## Syntax

The `<shape>` data type is specified using the `rect()` function, which produces a region in the form of a rectangle.

`rect()`

    rect(top, right, bottom, left)

#### Values

<img src="data:image/png;base64,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" class="internal rwrap" width="336" height="334" />

_top_  
Is a [`<length>`](length) representing the offset for the top of the rectangle relative to the top border of the element's box.

_right_  
Is a [`<length>`](length) representing the offset for the right of the rectangle relative to the left border of the element's box.

_bottom_  
Is a [`<length>`](length) representing the offset for the bottom of the rectangle relative to the top border of the element's box.

_left_  
Is a [`<length>`](length) representing the offset for the left of the rectangle relative to the left border of the element's box.

## Interpolation

When animated, values of the `<shape>` data type are interpolated over their `top`, `right`, `bottom`, and `left` components, each treated as a real, floating-point number. The speed of the interpolation is determined by the [timing function](easing-function) associated with the animation.

## Example

### Example demonstrating correct use of the rect() function

    img.clip04 {
      clip: rect(10px, 20px, 20px, 10px);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visufx.html#value-def-shape">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '&lt;shape&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines with the <a href="clip"><code>clip</code></a> property.</td></tr></tbody></table>

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

`shape`

1

12

1

5.5

9.5

1.3

37

18

4

14

1

1.0

`rect`

1

12

1

5.5

For Internet Explorer versions 5.5 through 7, the `rect()` function uses spaces (instead of commas) to separate parameters. For Internet Explorer 8 and later versions, only the standard comma-separated syntax is supported.

9.5

1.3

37

18

4

14

1

1.0

## See also

- Related CSS property: [`clip`](clip)
- The `-moz-image-rect()` function has similar coordinate values to `rect()`.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/shape</a>
