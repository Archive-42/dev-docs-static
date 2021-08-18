# box-sizing

The `box-sizing` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how the total width and height of an element is calculated.

By default in the [CSS box model](css_box_model/introduction_to_the_css_box_model), the `width` and `height` you assign to an element is applied only to the element's content box. If the element has any border or padding, this is then added to the `width` and `height` to arrive at the size of the box that's rendered on the screen. This means that when you set `width` and `height`, you have to adjust the value you give to allow for any border or padding that may be added. For example, if you have four boxes with `width: 25%;`, if any has left or right padding or a left or right border, they will not by default fit on one line within the constraints of the parent container.

The `box-sizing` property can be used to adjust this behavior:

- `content-box` gives you the default CSS box-sizing behavior. If you set an element's width to 100 pixels, then the element's content box will be 100 pixels wide, and the width of any border or padding will be added to the final rendered width, making the element wider than 100px.
- `border-box` tells the browser to account for any border and padding in the values you specify for an element's width and height. If you set an element's width to 100 pixels, that 100 pixels will include any border or padding you added, and the content box will shrink to absorb that extra width. This typically makes it much easier to size elements.

  `box-sizing: border-box` is the default styling that browsers use for the [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), and [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) elements, and for [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements whose type is `radio`, `checkbox`, `reset`, `button`, `submit`, `color`, or `search`.

**Note:** It is often useful to set `box-sizing` to `border-box` to layout elements. This makes dealing with the sizes of elements much easier, and generally eliminates a number of pitfalls you can stumble on while laying out your content. On the other hand, when using `position: relative` or `position: absolute`, use of `box-sizing: content-box` allows the positioning values to be relative to the content, and independent of changes to border and padding sizes, which is sometimes desirable.

## Syntax

The `box-sizing` property is specified as a single keyword chosen from the list of values below.

### Values

`content-box`  
This is the initial and default value as specified by the CSS standard. The [`width`](width) and [`height`](height) properties include the content, but does not include the padding, border, or margin. For example, `.box {width: 350px; border: 10px solid black;}` renders a box that is 370px wide.

Here, the dimensions of the element are calculated as: _width = width of the content_, and _height = height of the content_. (Borders and padding are not included in the calculation.)

`border-box`  
The [`width`](width) and [`height`](height) properties include the content, padding, and border, but do not include the margin. Note that padding and border will be inside of the box. For example, `.box {width: 350px; border: 10px solid black;}` renders a box that is 350px wide, with the area for content being 330px wide. The content box can't be negative and is floored to 0, making it impossible to use `border-box` to make the element disappear.

Here the dimensions of the element are calculated as: _width = border + padding + width of the content_, and _height = border + padding + height of the content_.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>content-box</code></td></tr><tr class="even"><td>Applies to</td><td>all elements that accept width or height</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    content-box | border-box

## Examples

### Box sizes with content-box and border-box

This example shows how different `box-sizing` values alter the rendered size of two otherwise identical elements.

#### HTML

    <div class="content-box">Content box</div>
    <br>
    <div class="border-box">Border box</div>

#### CSS

    div {
      width: 160px;
      height: 80px;
      padding: 20px;
      border: 8px solid red;
      background: yellow;
    }

    .content-box {
      box-sizing: content-box;
      /* Total width: 160px + (2 * 20px) + (2 * 8px) = 216px
         Total height: 80px + (2 * 20px) + (2 * 8px) = 136px
         Content box width: 160px
         Content box height: 80px */
    }

    .border-box {
      box-sizing: border-box;
      /* Total width: 160px
         Total height: 80px
         Content box width: 160px - (2 * 20px) - (2 * 8px) = 104px
         Content box height: 80px - (2 * 20px) - (2 * 8px) = 24px */
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-3/#box-sizing">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'box-sizing' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`box-sizing`

10

`box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

1

12

12

29

1

Before Firefox 23, `box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

49

44

8

`box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

7

5.1

3

4

`box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

2

18

`box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

18

29

4

Before Firefox 23, `box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

49

44

14

`box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

14

6

1

1.0

`box-sizing` is not respected when the height is calculated from [`window.getComputedStyle()`](https://developer.mozilla.org/docs/Web/API/Window/getComputedStyle).

1.0

`padding-box`

No

No

1-50

No

No

No

No

No

4-50

No

No

No

## See also

- [CSS box model](css_box_model/introduction_to_the_css_box_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing</a>
