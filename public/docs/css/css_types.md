# CSS data types

**CSS data types** define typical values (including keywords and units) accepted by CSS properties and functions. They are a special kind of [component value type](https://www.w3.org/TR/css3-values/#component-types).

The most commonly-used types are defined in the [CSS Values and Units](css_values_and_units) specification. This specification also defines [functional notations](css_functions), which allow for more complex types or processing. Other types are defined in the specifications to which they apply.

Below you will find a reference to the types that you are most likely to come across, however it is not a comprehensive reference for all types defined in every CSS specification.

## Syntax

In formal CSS syntax, data types are denoted by a keyword placed between the inequality signs "`<`" and "`>`".

## Textual data types

These types include keywords and identifiers as well as strings, and urls.

Pre-defined keywords  
Keywords with a pre-defined meaning, for example the value of `collapse` for the [`border-collapse`](border-collapse) property.

CSS-wide keyword: `initial`  
The value specified as the property's initial value.

CSS-wide keyword: `inherit`  
The computed value of the property on the element's parent.

CSS-wide keyword: `unset`  
Acts as `inherit` or `initial` depending on whether the property is inherited or not.

`<custom-ident>`  
A user-defined identifier, for example the name assigned using the [`grid-area`](grid-area) property. See more information on the [`<custom-ident>`](custom-ident) page.

`<dashed-ident>`  
A `<custom-ident>` with the additional restriction that it must start with two dashes, for example with [CSS Custom Properties](using_css_custom_properties). See more information on the <span class="page-not-created">`<dashed-ident>`</span> page.

`<string>`  
A quoted string, such as used for a value of the [`content`](content) property. See more information on the [`<string>`](string) type.

`<url>`  
A pointer to a resource, for example as the value of [`background-image`](background-image). See more information on the [`<url>()`](<url()>) page.

## Numeric data types

These data types are used to indicate quantities, indexes, and positions. The majority of these are defined in the Values and Units specification, however additional types are described in other specifications where they are specific to that specification alone — for example the `fr` unit in [CSS Grid Layout](https://www.w3.org/TR/css-grid-1/#fr-unit).

`<integer>`  
One or more decimal units 0 through 9. See more information on the [`<integer>`](integer) page.

`<number>`  
Real numbers which may also have a fractional component, for example 1 or 1.34. See more information on the [`<number>`](number) page.

`<dimension>`  
A number with a unit attached to it, for example 23px or 15em. See more information on the [`<dimension>`](dimension) page.

`<percentage>`  
A number with a percentage sign attached to it, for example 10%. See more information on the [`<percentage>`](percentage) page.

`<ratio>`  
A ratio, written with the syntax `<number> / <number>`. See more information on the [`<ratio>`](ratio) page.

`<flex>`  
A flexible length introduced for [CSS Grid Layout](css_grid_layout), written as a `<dimension>` with the `fr` unit attached and used for grid track sizing. See more information on the [`<flex>`](flex_value) page.

## Quantities

These types are used to specify distance and other quantities.

&lt;length&gt;  
Lengths are a `<dimension>` and refer to distances. See more information on the [`<length>`](length) page.

`<angle>`  
Angles are used in properties such as [`<linear-gradient>()`](<linear-gradient()>) and are a &lt;dimension&gt; with one of `deg`, `grad`, `rad`, or `turn` units attached. See more information on the [`<angle>`](angle) page.

`<time>`  
Duration units are a `<dimension>` with an `s` or `ms` unit. See more information on the [`<time>`](time) page.

`<frequency>`  
Frequencies are a `<dimension>` with a `Hz` or `kHz` unit attached. See more information on the [`<frequency>`](frequency) page.

`<resolution>`  
Is a &lt;dimension&gt; with a unit identifier of `dpi`, `dpcm`, `dppx`, or `x`. See more information on the [`<resolution>`](resolution) page.

## Combinations of types

Some CSS properties can take a dimension or a percentage value. In this case the percentage value will be resolved to a quantity that matches the allowable dimension. Properties which can accept a percentage in addition to a dimension will use one of the types listed below.

`<length-percentage>`  
A type that can accept a length or a percentage as a value. See more information on the [`<length-percentage>`](length-percentage) page.

`<frequency-percentage>`  
A type that can accept a frequency or a percentage as a value. See more information on the [`<frequency-percentage>`](frequency-percentage) page.

`<angle-percentage>`  
A type that can accept an angle or a percentage as a value. See more information on the [`<angle-percentage>`](angle-percentage) page.

`<time-percentage>`  
A type that can accept a time or a percentage as a value. See more information on the [`<time-percentage>`](time-percentage) page.

## Color

[The CSS Color Specification](https://www.w3.org/TR/css-color-3/) defines the [`<color>`](color_value) data type, and other types which relate to color in CSS.

`<color>`  
Specified as a keyword or a numerical color value. See more information on the [`<color>`](color_value) page.

`<alpha-value>`  
Specifies the transparency of a color. May be a `<number>`, in which case 0 is fully transparent and 1 is fully opaque, or a `<percentage>`, in which case 0% is fully transparent and 100% fully opaque.

## Images

[The CSS Images Specification](https://www.w3.org/TR/css-images-3/) defines the data types which deal with images, including gradients.

`<image>`  
A url reference to an image or a color gradient. See more information on the [`<image>`](image) page.

`<color-stop-list>`  
A list of two or more color stops with optional transition information using a color hint.

`<linear-color-stop>`  
A `<color>` and a `<length-percentage>` to indicate the color stop for this part of the gradient.

`<linear-color-hint>`  
A `<length-percentage>` to indicate how the color interpolates.

`<ending-shape>`  
Used for radial gradients; can have a keyword value of `circle` or `ellipse`.

`<size>`  
Determines the size of the radial gradient's ending shape. This accepts a value of a keyword or a `<length>` but not a percentage.

## 2D positioning

The [`<position>`](position_value) data type is interpreted as defined for the [`<background-position>`](background-position) property.

[`<position>`](position_value)  
Defines the position of an object area. Accepts a keyword value such as `top` or `left`, or a `<length-percentage>`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/">CSS Values and Units Module Level 4</a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/">CSS Values and Units Module Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- [CSS Units and Values](css_values_and_units)
- [Introduction to CSS: Values and Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [CSS Functional Notation](css_functions)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types</a>
