# ident

**Draft**

This page is not complete.

The `<ident>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) denotes an arbitrary string used as an [identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier).

## Syntax

The syntax of `<custom-ident>` is similar to CSS identifiers (such as property names), except that it is [case-sensitive](https://en.wikipedia.org/wiki/Case_sensitivity). It consists of one or more characters, where characters can be any of the following:

- any alphabetical character (`A` to `Z`, or `a` to `z`),
- any decimal digit (`0` to `9`),
- a hyphen (`-`),
- an underscore (`_`),
- an escaped character (preceded by a backslash, `\`),
- a [Unicode](https://en.wikipedia.org/wiki/Unicode) character (in the format of a backslash, `\`, followed by one to six hexadecimal digits, representing its Unicode code point)

Note that `id1`, `Id1`, `iD1` and `ID1` are all different identifiers as they are [case-sensitive](https://en.wikipedia.org/wiki/Case_sensitivity). On the other hand, as there are several ways to escape a character, `toto\?` and `toto\3F` are the same identifiers.

## Examples

### Valid identifiers

    nono79        A mix of alphanumeric characters and numbers
    ground-level    A mix of alphanumeric characters and a dash
    -test           A dash followed by alphanumeric characters
    --toto          A custom-property like identifier
    _internal       An underscore followed by alphanumeric characters
    \22 toto        A Unicode character followed by a sequence of alphanumeric characters
    bili\.bob       A correctly escaped period

### Invalid identifiers

    34rem     It must not start with a decimal digit.
    -12rad      It must not start with a dash followed by a decimal digit.
    bili.bob    Only alphanumeric characters, _, and - needn't be escaped.
    'bilibob'   This would be a <string>.
    "bilibob"   This would be a <string>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#css-identifier">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '<code>&lt;ident&gt;</code>' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#css-identifier">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '<code>&lt;ident&gt;</code>' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`<custom-ident>`](custom-ident) – A restricted subset of `<ident>` values excluding <span style="white-space: nowrap;">CSS-wide</span> keywords, [`custom properties`](--*) and other <span style="white-space: nowrap;">per-property</span> values.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/ident" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/ident</a>
