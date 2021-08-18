# &lt;display-inside&gt;

These keywords specify the element’s inner [`display`](display) type, which defines the type of formatting context that lays out its contents (assuming it is a non-replaced element). These keywords are used as values of the `display` property, and can be used for legacy purposes as a single keyword, or as defined in the Level 3 specification alongside a value from the [`<display-outside>`](display-outside) keywords.

## Syntax

Valid `<display-inside>` values:

`flow` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The element lays out its contents using flow layout (block-and-inline layout).

If its outer display type is `inline` or `run-in`, and it is participating in a block or inline formatting context, then it generates an inline box. Otherwise it generates a block container box.

Depending on the value of other properties (such as [`position`](position), [`float`](float), or [`overflow`](overflow)) and whether it is itself participating in a block or inline formatting context, it either establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) (BFC) for its contents or integrates its contents into its parent formatting context.

`flow-root`  
The element generates a block element box that establishes a new [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context), defining where the formatting root lies.

`table`  
These elements behave like HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) elements. It defines a block-level box.

`flex`  
The element behaves like a block element and lays out its content according to the [flexbox model](css_flexible_box_layout).

`grid`  
The element behaves like a block element and lays out its content according to the [grid model](css_grid_layout/basic_concepts_of_grid_layout).

`ruby` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The element behaves like an inline element and lays out its content according to the ruby formatting model. It behaves like the corresponding HTML [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby) elements.

**Note**: Browsers that support the two value syntax, on finding the inner value only, such as when `display: flex` or `display: grid` is specified, will set their outer value to `block`. This will result in expected behavior; for example if you specify an element to be `display: grid`, you would expect that the box created on the grid container would be a block level box.

## Examples

In this example the parent box has been given `display: flow-root` and so establishes a new BFC and contains the floated item.

### HTML

    <div class="box">
      <div class="float">I am a floated box!</div>
      <p>I am content inside the container.</p>
    </div>

### CSS

    .box {
        background-color: rgb(224, 206, 247);
        border: 5px solid rebeccapurple;
        display: flow-root;
    }

    .float {
        float: left;
        width: 200px;
        height: 150px;
        background-color: white;
        border:1px solid black;
        padding: 10px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-display/#typedef-display-inside">CSS Display Module Level 3<br />
<span class="small">The definition of 'display-inside' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td></tr></tbody></table>

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

`display-inside`

No

12-79

38

7

No

No

No

No

38

No

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

`display-inside`

29

21

12

20

Firefox 28 added multi-line flexbox support.

11

IE incorrectly positions inline block content inside flex containers. See the [discussion on Microsoft Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

8

IE incorrectly positions inline block content inside flex containers. See the [discussion on Microsoft Answers](https://answers.microsoft.com/en-us/ie/forum/ie11-iewindows_10/inline-block-content-in-a-flex-container-not/deea64e2-933b-4bd2-a98c-62be16d04b57).

16

15

12.1-15

9

6.1

4.4

≤37

29

25

20

Firefox 28 added multi-line flexbox support.

16

14

12.1-14

9

7

2.0

1.5

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

`display-inside`

57

16

12

52

10

Internet Explorer implements an older version of the specification.

44

10.1

57

57

52

43

10.3

6.0

Samsung Internet added this earlier than the corresponding Chrome version would indicate.

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

`display-inside`

1

12

1

8

7

1

≤37

18

4

14

1

1.0

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

`display-inside`

58

79

53

No

45

13

58

58

53

43

13

7.0

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

`display-inside`

No

No

70

No

No

No

No

No

No

No

No

No

BCD tables only load in the browser

- Chromium bug: <https://bugs.chromium.org/p/chromium/issues/detail?id=804600>

### Support of flow-root

BCD tables only load in the browser

### Support of table

BCD tables only load in the browser

### Support of grid

BCD tables only load in the browser

### Support of flex

BCD tables only load in the browser

### Support of ruby

BCD tables only load in the browser

## See also

- [`display`](display)
  - [`<display-outside>`](display-outside)
  - [`<display-listitem>`](display-listitem)
  - [`<display-internal>`](display-internal)
  - [`<display-box>`](display-box)
  - [`<display-legacy>`](display-legacy)
- [Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)
- [Basic Concepts of Grid Layout](css_grid_layout/basic_concepts_of_grid_layout)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/display-inside</a>
