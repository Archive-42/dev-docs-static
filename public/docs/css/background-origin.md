# background-origin

The `background-origin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the background's origin: from the border start, inside the border, or inside the padding.

Note that `background-origin` is ignored when [`background-attachment`](background-attachment) is `fixed`.

## Syntax

    /* Keyword values */
    background-origin: border-box;
    background-origin: padding-box;
    background-origin: content-box;

    /* Global values */
    background-origin: inherit;
    background-origin: initial;
    background-origin: unset;

The `background-origin` property is specified as one of the keyword values listed below.

### Values

`border-box`  
The background is positioned relative to the border box.

`padding-box`  
The background is positioned relative to the padding box.

`content-box`  
The background is positioned relative to the content box.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>padding-box</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <box>#where
    <box> = border-box | padding-box | content-box

## Examples

### Setting background origins

    .example {
      border: 10px double;
      padding: 10px;
      background: url('image.jpg');
      background-position: center left;
      background-origin: content-box;
    }

    #example2 {
      border: 4px solid black;
      padding: 10px;
      background: url('image.gif');
      background-repeat: no-repeat;
      background-origin: border-box;
    }

    div {
      background-image: url('logo.jpg'), url('mainback.png'); /* Applies two images to the background */
      background-position: top right, 0px 0px;
      background-origin: content-box, padding-box;
    }

### Using two gradients

In this example the box has a thick dotted border. The first gradient uses the `padding-box` as the `background-origin` and therefore the background sits inside the border. The second uses the `content-box` and so only displays behind the content.

    .box {
      margin: 10px 0;
      color: #fff;
      background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,0.6) 60%, rgba(252,176,69,1) 100%),
      radial-gradient(circle, rgba(255,255,255,1) 0%, rgba(0,0,0,1) 28%);
      border: 20px dashed black;
      padding: 20px;
      width: 400px;
      background-origin: padding-box, content-box;
      background-repeat: no-repeat;
    }

    <div class="box">Hello!</div>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-background-origin">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-origin' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`background-origin`

1

1-64

Chrome accepts alternate synonyms to its values: `padding`, `border`, and `content`.

12

4

49

1-4

Used the `-moz-background-clip: padding | border` syntax.

9

In IE 7 and before, Internet explorer was behaving as if `background-origin: border-box` was set. In Internet Explorer 8, as if `background-origin: padding-box`, the regular default value, was set.

10.5

15-51

Opera accepts alternate synonyms to its values: `padding`, `border`, and `content`.

3

3

Webkit accepts alternate synonyms to its values: `padding`, `border`, and `content`.

4.1

4.1-64

WebView accepts alternate synonyms to its values: `padding`, `border`, and `content`.

18

18-64

Chrome accepts alternate synonyms to its values: `padding`, `border`, and `content`.

14

49

11

14-47

Opera accepts alternate synonyms to its values: `padding`, `border`, and `content`.

1

1

Webkit accepts alternate synonyms to its values: `padding`, `border`, and `content`.

1.0

1.0-9.0

Chrome accepts alternate synonyms to its values: `padding`, `border`, and `content`.

`content-box`

1

12

4

9

In IE 7 and IE 9 of Internet Explorer, it always behaved like `background-clip: padding` if `overflow: hidden | auto | scroll`.

10.5

3

4.1

18

14

11

1

1.0

## See also

- [`background-clip`](background-clip)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-origin</a>
