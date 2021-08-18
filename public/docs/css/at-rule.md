# At-rules

**At-rules** are [CSS statements](syntax#css_statements) that instructs CSS how to behave. They begin with an at sign, '`@`' (`U+0040 COMMERCIAL AT`), followed by an identifier and includes everything up to the next semicolon, '`;`' (`U+003B SEMICOLON`), or the next [CSS block](syntax#css_declarations_blocks), whichever comes first.

## Syntax

### Regular

    /* General structure */
    @IDENTIFIER (RULE);

    /* Example: tells browser to use UTF-8 character set */
    @charset "utf-8";

There are several regular at-rules, designated by their identifiers, each with a different syntax:

- [`@charset`](@charset) — Defines the character set used by the style sheet.
- [`@import`](@import) — Tells the CSS engine to include an external style sheet.
- [`@namespace`](@namespace) — Tells the CSS engine that all its content must be considered prefixed with an XML namespace.

### Nested

    @IDENTIFIER (RULE) {

    }

A subset of nested statements, which can be used as a statement of a style sheet as well as inside of conditional group rules.

- [`@media`](@media) — A conditional group rule that will apply its content if the device meets the criteria of the condition defined using a _media query_.
- [`@supports`](@supports) — A conditional group rule that will apply its content if the browser meets the criteria of the given condition.
- [`@document`](@document) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> — A conditional group rule that will apply its content if the document in which the style sheet is applied meets the criteria of the given condition. _(deferred to Level 4 of CSS Spec)_
- [`@page`](@page) — Describes the aspect of layout changes that will be applied when printing the document.
- [`@font-face`](@font-face) — Describes the aspect of an external font to be downloaded.
- [`@keyframes`](@keyframes) — Describes the aspect of intermediate steps in a CSS animation sequence.
- [`@viewport`](@viewport) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> — Describes the aspects of the viewport for small screen devices. _(currently at the Working Draft stage)_
- [`@counter-style`](@counter-style) — Defines specific counter styles that are not part of the predefined set of styles. _(at the Candidate Recommendation stage, but only implemented in Gecko as of writing)_
- [`@font-feature-values`](@font-feature-values) (plus `@swash`, `@ornaments`, `@annotation`, `@stylistic`, `@styleset` and `@character-variant`) — Define common names in [`font-variant-alternates`](font-variant-alternates) for feature activated differently in OpenType. _(at the Candidate Recommendation stage, but only implemented in Gecko as of writing)_
- [`@property`](@property) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> — Describes the aspect of custom properties and variables. _(currently at the Working Draft stage)_
- [`@color-profile`](@color-profile) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> — Allows a color profile to be defined for use by the [`color()`](<color_value/color()>) function.

## Conditional group rules

Much like the values of properties, each at-rule has a different syntax. Nevertheless, several of them can be grouped into a special category named **conditional group rules**. These statements share a common syntax and each of them can include _nested statements_—either _rulesets_ or _nested at-rules_. Furthermore, they all convey a common semantic meaning—they all link some type of condition, which at any time evaluates to either **true** or **false**. If the condition evaluates to **true**, then all of the statements within the group will be applied.

Conditional group rules are defined in [CSS Conditionals Level 3](https://dev.w3.org/csswg/css3-conditional/) and are:

- [`@media`](@media),
- [`@supports`](@supports),
- [`@document`](@document). _(deferred to Level 4 of CSS Spec)_

Since each conditional group may also contain nested statements, there may be an unspecified amount of nesting.

## Index

C

- [`@charset`](@charset)
- [`@color-profile`](@color-profile) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`@counter-style`](@counter-style)

D

- [`@document`](@document) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

F

- [`@font-face`](@font-face)
- [`@font-feature-values`](@font-feature-values)

I

- [`@import`](@import)

K

- [`@keyframes`](@keyframes)

M

- [`@media`](@media)

N

- [`@namespace`](@namespace)

P

- [`@page`](@page)
- [`@property`](@property) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

S

- [`@supports`](@supports)

V

- [`@viewport`](@viewport) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/">CSS Conditional Rules Module Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://compat.spec.whatwg.org/#css-at-rules">Compatibility Standard<br />
<span class="small">The definition of 'CSS At-rules' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Standardizes <code>@-webkit-keyframes</code>.</td></tr></tbody></table>

## See also

- CSS Key Concepts: [CSS syntax](syntax), [at-rule](at-rule), [comments](comments), [specificity](specificity) and [inheritance](inheritance), the [box](css_box_model/introduction_to_the_css_box_model), [layout modes](layout_mode) and [visual formatting models](visual_formatting_model), and [margin collapsing](css_box_model/mastering_margin_collapsing), or the [initial](initial_value), [computed](computed_value), [resolved](resolved_value), [specified](specified_value), [used](used_value), and [actual](actual_value) values. Definitions of [value syntax](value_definition_syntax), [shorthand properties](shorthand_properties) and [replaced elements](replaced_element).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule</a>
