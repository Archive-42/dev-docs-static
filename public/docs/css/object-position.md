# object-position

The `object-position` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the alignment of the selected [replaced element](replaced_element)'s contents within the element's box. Areas of the box which aren't covered by the replaced element's object will show the element's background.

You can adjust how the replaced element's object's intrinsic size (that is, its natural size) is adjusted to fit within the element's box using the [`object-fit`](object-fit) property.

## Syntax

    /* <position> values */
    object-position: center top;
    object-position: 100px 50px;

    /* Global values */
    object-position: inherit;
    object-position: initial;
    object-position: unset;

### Values

[`<position>`](position_value)  
From one to four values that define the 2D position of the element. Relative or absolute offsets can be used.

**Note:** The position can be set so that the replaced element is drawn outside its box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>50% 50%</code></td></tr><tr class="even"><td>Applies to</td><td>replaced elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>refer to width and height of element itself</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>repeatable list of simple list of length, percentage, or calc</td></tr></tbody></table>

## Formal syntax

    <position>where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Positioning image content

#### HTML

Here we see HTML that includes two [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) elements, each displaying the MDN logo.

    <img id="object-position-1" src="https://mdn.mozillademos.org/files/12668/MDN.svg" alt="MDN Logo"/>
    <img id="object-position-2" src="https://mdn.mozillademos.org/files/12668/MDN.svg" alt="MDN Logo"/>

#### CSS

The CSS includes default styling for the `<img>` element itself, as well as separate styles for each of the two images.

    img {
      width: 300px;
      height: 250px;
      border: 1px solid black;
      background-color: silver;
      margin-right: 1em;
      object-fit: none;
    }

    #object-position-1 {
      object-position: 10px;
    }

    #object-position-2 {
      object-position: 100% 10%;
    }

The first image is positioned with its left edge inset 10 pixels from the left edge of the element's box. The second image is positioned with its right edge flush against the right edge of the element's box and is located 10% of the way down the height of the element's box.

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-3/#the-object-position">CSS Images Module Level 3<br />
<span class="small">The definition of 'object-position' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`object-position`

32

79

16-79

Only supported for `<img>` elements.

36

No

19

11.6-15

10

4.4.3

32

36

19

12-14

10

2.0

`three_value_syntax`

32-68

16-79

36-70

No

19-55

11.6-15

10-13.1

4.4.3-68

32-68

36-79

19-48

12-14

10-13.4

2.0-10.0

## See also

- Other image-related CSS properties: [`object-fit`](object-fit), [`image-orientation`](image-orientation), [`image-rendering`](image-rendering), [`image-resolution`](image-resolution).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/object-position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/object-position</a>
