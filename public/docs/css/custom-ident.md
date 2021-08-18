# &lt;custom-ident&gt;

The `<custom-ident>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) denotes an arbitrary user-defined string used as an [identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier). It is case-sensitive, and certain values are forbidden in various contexts to prevent ambiguity.

## Syntax

The syntax of `<custom-ident>` is similar to CSS identifiers (such as property names), except that it is [case-sensitive](https://en.wikipedia.org/wiki/Case_sensitivity). It consists of one or more characters, where characters can be any of the following:

- any alphabetical character (`A` to `Z`, or `a` to `z`),
- any decimal digit (`0` to `9`),
- a hyphen (`-`),
- an underscore (`_`),
- an escaped character (preceded by a backslash, `\`),
- a [Unicode](https://en.wikipedia.org/wiki/Unicode) character (in the format of a backslash, `\`, followed by one to six hexadecimal digits, representing its Unicode code point)

Note that `id1`, `Id1`, `iD1` and `ID1` are all different identifiers as they are [case-sensitive](https://en.wikipedia.org/wiki/Case_sensitivity). On the other hand, as there are several ways to escape a character, `toto\?` and `toto\3F` are the same identifiers.

### Forbidden values

A `<custom-ident>` must not be placed between single or double quotes as this would be identical to a [`<string>`](string). Moreover, the first character must not be a decimal digit, nor a hyphen (`-`) followed by a decimal digit or another hyphen.

To prevent ambiguity, each property that uses `<custom-ident>` forbids the use of specific values:

[`animation-name`](animation-name)  
Forbids the global CSS values (`unset`, `initial`, and `inherit`), as well as `none`.

[`counter-reset`](counter-reset)  
[`counter-increment`](counter-increment)  
Forbids the global CSS values (`unset`, `initial`, and `inherit`), as well as `none`.

[`@counter-style`](@counter-style)  
[`list-style-type`](list-style-type)  
Forbids the global CSS values (`unset`, `initial`, and `inherit`), as well as the values `none`, `inline`, and `outside`. Also, quite a few predefined values are implemented by the different browsers: `disc`, `circle`, `square`, `decimal`, `cjk-decimal`, `decimal-leading-zero`, `lower-roman`, `upper-roman`, `lower-greek`, `lower-alpha`, `lower-latin`, `upper-alpha`, `upper-latin`, `arabic-indic`, `armenian`, `bengali`, `cambodian`, `cjk-earthly-branch`, `cjk-heavenly-stem`, `cjk-ideographic`, `devanagari`, `ethiopic-numeric`, `georgian`, `gujarati`, `gurmukhi`, `hebrew`, `hiragana`, `hiragana-iroha`, `japanese-formal`, `japanese-informal`, `kannada`, `katakana`, `katakana-iroha`, `khmer`, `korean-hangul-formal`, `korean-hanja-formal`, `korean-hanja-informal`, `lao`, `lower-armenian`, `malayalam`, `mongolian`, `myanmar`, `oriya`, `persian`, `simp-chinese-formal`, `simp-chinese-informal`, `tamil`, `telugu`, `thai`, `tibetan`, `trad-chinese-formal`, `trad-chinese-informal`, `upper-armenian`, `disclosure-open`, and `disclosure-close`.

[`grid-row-start`](grid-row-start)  
[`grid-row-end`](grid-row-end)  
[`grid-column-start`](grid-column-start)  
[`grid-column-end`](grid-column-end)  
Forbids the `span` value.

[`will-change`](will-change)  
Forbids the global CSS values (`unset`, `initial`, and `inherit`), as well as the values `will-change`, `auto`, `scroll-position`, and `contents`.

## Examples

### Valid identifiers

    nono79            A mix of alphanumeric characters and numbers
    ground-level      A mix of alphanumeric characters and a dash
    -test             A dash followed by alphanumeric characters
    _internal         An underscore followed by alphanumeric characters
    \22 toto          A Unicode character followed by a sequence of alphanumeric characters
    bili\.bob         A correctly escaped period

### Invalid identifiers

    34rem             It must not start with a decimal digit.
    -12rad            It must not start with a dash followed by a decimal digit.
    bili.bob          Only alphanumeric characters, _, and - needn't be escaped.
    --toto            It must not start with two dashes. This would be a custom property.
    'bilibob'         This would be a <string>.
    "bilibob"         This would be a <string>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#custom-idents">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '<code>&lt;custom-ident&gt;</code>' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-will-change/#valdef-will-change-custom-ident">CSS Will Change Module Level 1<br />
<span class="small">The definition of '<code>&lt;custom-ident&gt;</code> for <code>will-change</code>' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines which values are excluded for <a href="will-change"><code>will-change</code></a>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#typedef-counter-style-name">CSS Counter Styles Level 3<br />
<span class="small">The definition of '<code>&lt;custom-ident&gt;</code> for <code>list-style-type</code>' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Uses <code>&lt;custom-ident&gt;</code> instead of a finite list of keywords. Defines which values are excluded for <a href="list-style-type"><code>list-style-type</code></a> and <a href="@counter-style"><code>@counter-style</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-lists-3/#counter-properties">CSS Lists Module Level 3<br />
<span class="small">The definition of '<code>&lt;custom-ident&gt;</code> for <code>counter-*</code>' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Renames <code>&lt;identifier&gt;</code> to <code>&lt;custom-ident&gt;</code>. Adds its usage to the new <code>counter-set</code> property.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#typedef-single-animation-name">CSS Animations Level 1<br />
<span class="small">The definition of '<code>&lt;custom-ident&gt;</code> for <code>animation-name</code>' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines which values are excluded for <a href="animation-name"><code>animation-name</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#custom-idents">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '<code>&lt;custom-ident&gt;</code>' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Renames <code>&lt;identifier&gt;</code> to <code>&lt;custom-ident&gt;</code>. Makes it a pseudo-type and forbids the use of excluded values.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/syndata.html#value-def-identifier">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '<code>&lt;identifier&gt;</code>' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

## See also

- [`<ident>`](ident)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident</a>
