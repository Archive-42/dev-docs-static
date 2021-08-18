# transform

The `transform` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets you rotate, scale, skew, or translate an element. It modifies the coordinate space of the CSS [visual formatting model](visual_formatting_model).

If the property has a value different than `none`, a [stacking context](css_positioning/understanding_z_index/the_stacking_context) will be created. In that case, the element will act as a [containing block](containing_block) for any `position: fixed;` or `position: absolute;` elements that it contains.

Only transformable elements can be `transform`ed. That is, all elements whose layout is governed by the CSS box model except for: [non-replaced inline boxes](visual_formatting_model#inline-level_elements_and_inline_boxes), [table-column boxes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col), and [table-column-group boxes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/colgroup).

## Syntax

    /* Keyword values */
    transform: none;

    /* Function values */
    transform: matrix(1.0, 2.0, 3.0, 4.0, 5.0, 6.0);
    transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
    transform: perspective(17px);
    transform: rotate(0.5turn);
    transform: rotate3d(1, 2.0, 3.0, 10deg);
    transform: rotateX(10deg);
    transform: rotateY(10deg);
    transform: rotateZ(10deg);
    transform: translate(12px, 50%);
    transform: translate3d(12px, 50%, 3em);
    transform: translateX(2em);
    transform: translateY(3in);
    transform: translateZ(2px);
    transform: scale(2, 0.5);
    transform: scale3d(2.5, 1.2, 0.3);
    transform: scaleX(2);
    transform: scaleY(0.5);
    transform: scaleZ(0.3);
    transform: skew(30deg, 20deg);
    transform: skewX(30deg);
    transform: skewY(1.07rad);

    /* Multiple function values */
    transform: translateX(10px) rotate(10deg) translateY(5px);
    transform: perspective(500px) translate(10px, 0, 20px) rotateY(3deg);

    /* Global values */
    transform: inherit;
    transform: initial;
    transform: unset;

The `transform` property may be specified as either the keyword value `none` or as one or more `<transform-function>` values.

If [`perspective()`](<transform-function/perspective()>) is one of multiple function values, it must be listed first.

### Values

[`<transform-function>`](transform-function)  
One or more of the [CSS transform functions](transform-function) to be applied. The transform functions are multiplied in order from left to right, meaning that composite transforms are effectively applied in order from right to left.

`none`  
Specifies that no transform should be applied.

## Accessibility concerns

Scaling/zooming animations are problematic for accessibility, as they are a common trigger for certain types of migraine. If you need to include such animations on your website, you should provide a control to allow users to turn off animations, preferably site-wide.

Also, consider making use of the [`prefers-reduced-motion`](@media/prefers-reduced-motion) media feature — use it to write a [media query](media_queries) that will turn off animations if the user has reduced animation specified in their system preferences.

Find out more:

- [MDN Understanding WCAG, Guideline 2.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.3_%e2%80%94_seizures_and_physical_reactions_do_not_design_content_in_a_way_that_is_known_to_cause_seizures_or_physical_reactions)
- [Understanding Success Criterion 2.3.3 | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the size of bounding box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a transform</td></tr><tr class="odd"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    none | <transform-list>where
    <transform-list> = <transform-function>+where
    <transform-function> = <matrix()> | <translate()> | <translateX()> | <translateY()> | <scale()> | <scaleX()> | <scaleY()> | <rotate()> | <skew()> | <skewX()> | <skewY()> | <matrix3d()> | <translate3d()> | <translateZ()> | <scale3d()> | <scaleZ()> | <rotate3d()> | <rotateX()> | <rotateY()> | <rotateZ()> | <perspective()>where
    <matrix()> = matrix( <number>#{6} )
    <translate()> = translate( <length-percentage> , <length-percentage>? )
    <translateX()> = translateX( <length-percentage> )
    <translateY()> = translateY( <length-percentage> )
    <scale()> = scale( <number> , <number>? )
    <scaleX()> = scaleX( <number> )
    <scaleY()> = scaleY( <number> )
    <rotate()> = rotate( [ <angle> | <zero> ] )
    <skew()> = skew( [ <angle> | <zero> ] , [ <angle> | <zero> ]? )
    <skewX()> = skewX( [ <angle> | <zero> ] )
    <skewY()> = skewY( [ <angle> | <zero> ] )
    <matrix3d()> = matrix3d( <number>#{16} )
    <translate3d()> = translate3d( <length-percentage> , <length-percentage> , <length> )
    <translateZ()> = translateZ( <length> )
    <scale3d()> = scale3d( <number> , <number> , <number> )
    <scaleZ()> = scaleZ( <number> )
    <rotate3d()> = rotate3d( <number> , <number> , <number> , [ <angle> | <zero> ] )
    <rotateX()> = rotateX( [ <angle> | <zero> ] )
    <rotateY()> = rotateY( [ <angle> | <zero> ] )
    <rotateZ()> = rotateZ( [ <angle> | <zero> ] )
    <perspective()> = perspective( <length> )where
    <length-percentage> = <length> | <percentage>

## Examples

### Translating and rotating an element

#### HTML

    <div>Transformed element</div>

#### CSS

    div {
      border: solid red;
      transform: translate(30px, 20px) rotate(20deg);
      width: 140px;
      height: 60px;
    }

#### Result

### More examples

Please see [Using CSS transforms](css_transforms/using_css_transforms) and [`<transform-function>`](transform-function) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#transform-functions">CSS Transforms Level 2<br />
<span class="small">The definition of 'transform' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds 3D transform functions.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-transforms/#transform-property">CSS Transforms Level 1<br />
<span class="small">The definition of 'transform' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transform`

36

1

12

12

16

49

44

10

Internet Explorer does not support the global values `initial` and `unset`.

11

9

Internet Explorer 5.5 or later supports a proprietary [Matrix Filter](<https://msdn.microsoft.com/en-us/library/ms533014(VS.85,loband).aspx>) which can be used to achieve a similar effect.

23

15

12.1-15

10.5-15

9

3.1

37

2

Android 2.3 has a bug where input forms will "jump" when typing, if any container element has a `-webkit-transform`.

36

18

16

49

44

24

14

12.1-14

11-14

9

3.2

3.0

1.0

`3d`

12

12

16

10

Internet Explorer 9.0 or earlier has no support for 3D transforms. Mixing 3D and 2D transform functions, such as `-ms-transform:rotate(10deg) translateZ(0);`, will prevent the entire property from being applied.

15

4

3

18

16

14

3.2

1.0

## See also

- [Using CSS transforms](css_transforms/using_css_transforms)
- [`<transform-function>`](transform-function) data type with all the transform functions explained.
- Online tool to visualize CSS Transform functions: [CSS Transform Playground](https://css-transform.moro.es/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform</a>
