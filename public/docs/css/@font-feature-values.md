# @font-feature-values

The `@font-feature-values` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) lets you use a common name in the [`font-variant-alternates`](font-variant-alternates) property for features activated differently in OpenType. This can help simplify your CSS when using multiple fonts.

The `@font-feature-values` at-rule may be used either at the top level of your CSS or inside any [CSS conditional-group at-rule](at-rule#conditional_group_rules).

## Syntax

### Feature value blocks

`@swash`  
Specifies a feature name that will work with the [`swash()`](<font-variant-alternates#swash()>) functional notation of [`font-variant-alternates`](font-variant-alternates). A swash feature value definition allows only one value: `ident1: 2` is valid, but `ident2: 2 4` isn't.

`@annotation`  
Specifies a feature name that will work with the [`annotation()`](<font-variant-alternates#annotation()>) functional notation of [`font-variant-alternates`](font-variant-alternates). An annotation feature value definition allows only one value: `ident1: 2` is valid, but `ident2: 2 4` isn't.

`@ornaments`  
Specifies a feature name that will work with the [`ornaments()`](<font-variant-alternates#ornaments()>) functional notation of [`font-variant-alternates`](font-variant-alternates). An ornaments feature value definition allows only one value: `ident1: 2` is valid, but `ident2: 2 4` isn't.

`@stylistic`  
Specifies a feature name that will work with the [`stylistic()`](<font-variant-alternates#stylistic()>) functional notation of [`font-variant-alternates`](font-variant-alternates). A stylistic feature value definition allows only one value: `ident1: 2` is valid, but `ident2: 2 4` isn't.

`@styleset`  
Specifies a feature name that will work with the [`styleset()`](<font-variant-alternates#styleset()>) functional notation of [`font-variant-alternates`](font-variant-alternates). A styleset feature value definition allows an unlimited number of values: `ident1: 2 4 12 1` maps to the OpenType values `ss02`, `ss04`, `ss12`, and `ss01`. Note that values higher than `99` are valid, but don't map to any OpenType values and are ignored.

`@character-variant`  
Specifies a feature name that will work with the [`character-variant()`](<font-variant-alternates#character-variant()>) functional notation of [`font-variant-alternates`](font-variant-alternates). A character-variant feature value definition allows either one or two values: `ident1: 3` maps to `cv03=1`, and `ident2: 2 4` maps to `cv02=4`, but `ident2: 2 4 5` is invalid.

## Formal syntax

    @font-feature-values <family-name># {
      <feature-value-block-list>
    }where
    <family-name> = <string> | <custom-ident>+
    <feature-value-block-list> = <feature-value-block>+where
    <feature-value-block> = <feature-type> '{' <feature-value-declaration-list> '}'where
    <feature-type> = @stylistic | @historical-forms | @styleset | @character-variant | @swash | @ornaments | @annotation
    <feature-value-declaration-list> = <feature-value-declaration>where
    <feature-value-declaration> = <custom-ident>: <integer>+;

## Examples

### Using @styleset in a @font-feature-values rule

    /* At-rule for "nice-style" in Font One */
    @font-feature-values Font One {
      @styleset {
        nice-style: 12;
      }
    }

    /* At-rule for "nice-style" in Font Two */
    @font-feature-values Font Two {
      @styleset {
        nice-style: 4;
      }
    }

    …

    /* Apply the at-rules with a single declaration */
    .nice-look {
      font-variant-alternates: styleset(nice-style);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-feature-values">CSS Fonts Module Level 4<br />
<span class="small">The definition of '@font-feature-values' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`@font-feature-values`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`annotation`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`character-variant`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`historical-forms`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`ornaments`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`styleset`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`stylistic`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

`swash`

No

No

34

No

No

9.1

No

No

34

No

9.3

No

## See also

- The [`font-variant-alternates`](font-variant-alternates) property that uses values that this at-rule defines.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-feature-values</a>
