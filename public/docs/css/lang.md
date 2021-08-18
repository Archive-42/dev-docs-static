# :lang()

The `:lang()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches elements based on the language they are determined to be in.

    /* Selects any <p> in English (en) */
    p:lang(en) {
      quotes: '\201C' '\201D' '\2018' '\2019';
    }

**Note:** In HTML, the language is determined by a combination of the [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-lang) attribute, the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element, and possibly by information from the protocol (such as HTTP headers). For other document types there may be other document methods for determining the language.

## Syntax

### Formal syntax

    :lang( <language-code> )

### Parameter

`<language-code>`  
A [`<string>`](string) representing the language you want to target. Acceptable values are specified in the [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) spec.

## Examples

In this example, the `:lang()` pseudo-class is used to match the parents of quote elements ([`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q)) using [child combinators](child_combinator). Note that this doesn't illustrate the only way to do this, and that the best method to use depends on the type of document. Also note that [Unicode](https://developer.mozilla.org/en-US/docs/Glossary/Unicode) values are used to specify some of the special quote characters.

### HTML

    <div lang="en"><q>This English quote has a <q>nested</q> quote inside.</q></div>
    <div lang="fr"><q>This French quote has a <q>nested</q> quote inside.</q></div>
    <div lang="de"><q>This German quote has a <q>nested</q> quote inside.</q></div>

### CSS

    :lang(en) > q { quotes: '\201C' '\201D' '\2018' '\2019'; }
    :lang(fr) > q { quotes: '« ' ' »'; }
    :lang(de) > q { quotes: '»' '«' '\2039' '\203A'; }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#lang-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':lang()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds wildcard language matching and comma-separated list of languages.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#lang-pseudo">Selectors Level 3<br />
<span class="small">The definition of ':lang()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#lang">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of ':lang()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:lang`

1

12

1

8

8

3.1

1

18

4

10.1

3.1

1.0

## See also

- Language-related pseudo-classes: [`:lang`](:lang), [`:dir`](:dir)
- HTML [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-lang) attribute
- HTML [`translate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-translate) attribute
- [BCP 47 - Tags for Identifying Languages](https://datatracker.ietf.org/doc/html/bcp47)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:lang" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:lang</a>
