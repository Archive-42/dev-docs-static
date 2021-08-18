# @import

The `@import` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) is used to import style rules from other style sheets.

## Syntax

    @import url;
    @import url list-of-media-queries;
    @import url supports( supports-query );
    @import url supports( supports-query ) list-of-media-queries;

where:

_url_  
Is a [`<string>`](string) or a [`<url>()`](<url()>) representing the location of the resource to import. The URL may be absolute or relative.

_list-of-media-queries_  
Is a comma-separated list of [media queries](media_queries/using_media_queries) conditioning the application of the CSS rules defined in the linked URL. If the browser does not support any these queries, it does not load the linked resource.

_supports-query_  
Is either a [`<supports-condition>`](@supports#syntax) or a [`<declaration>`](syntax#css_declarations).

## Description

Imported rules must precede all other types of rules, except [`@charset`](@charset) rules; as it is not a [nested statement](syntax#nested_statements), `@import` cannot be used inside [conditional group at-rules](at-rule#conditional_group_rules).

So that [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)s can avoid retrieving resources for unsupported media types, authors may specify media-dependent `@import` rules. These conditional imports specify comma-separated [media queries](media_queries/using_media_queries) after the URL. In the absence of any media query, the import is unconditional. Specifying `all` for the medium has the same effect.

## Formal syntax

    @import [ <string> | <url> ] [ <media-query-list> ]?;where
    <media-query-list> = <media-query>#where
    <media-query> = <media-condition> | [ not | only ]? <media-type> [ and <media-condition-without-or> ]?where
    <media-condition> = <media-not> | <media-and> | <media-or> | <media-in-parens>
    <media-type> = <ident>
    <media-condition-without-or> = <media-not> | <media-and> | <media-in-parens>where
    <media-not> = not <media-in-parens>
    <media-and> = <media-in-parens> [ and <media-in-parens> ]+
    <media-or> = <media-in-parens> [ or <media-in-parens> ]+
    <media-in-parens> = ( <media-condition> ) | <media-feature> | <general-enclosed>where
    <media-feature> = ( [ <mf-plain> | <mf-boolean> | <mf-range> ] )
    <general-enclosed> = [ <function-token> <any-value> ) ] | ( <ident> <any-value> )where
    <mf-plain> = <mf-name> : <mf-value>
    <mf-boolean> = <mf-name>
    <mf-range> = <mf-name> [ '<' | '>' ]? '='? <mf-value> | <mf-value> [ '<' | '>' ]? '='? <mf-name> | <mf-value> '<' '='? <mf-name> '<' '='? <mf-value> | <mf-value> '>' '='? <mf-name> '>' '='? <mf-value>where
    <mf-name> = <ident>
    <mf-value> = <number> | <dimension> | <ident> | <ratio>

## Examples

### Importing CSS rules

    @import 'custom.css';
    @import url("chrome://communicator/skin/");

### Importing CSS rules conditionally

    @import url("fineprint.css") print;
    @import url("bluish.css") speech;
    @import "common.css" screen;
    @import url('landscape.css') screen and (orientation:landscape);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-cascade/#at-import">CSS Cascading and Inheritance Level 4<br />
<span class="small">The definition of 'the <code>@import</code> rule' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extended the syntax to support the <a href="@supports"><code>@supports</code></a> syntax.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-cascade-3/#at-ruledef-import">CSS Cascading and Inheritance Level 3<br />
<span class="small">The definition of '@import' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-3/#media0">Media Queries<br />
<span class="small">The definition of '@import' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Extended the syntax to support any media query and not only simple <a href="@media#media_types">media types</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/cascade.html#at-import">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of '@import' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added support for <a href="string"><code>&lt;string&gt;</code></a> to denote the url of a stylesheet,<br />
and requirement to insert the <code>@import</code> rule at the beginning of the CSS document.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#the-cascade">CSS Level 1<br />
<span class="small">The definition of '@import' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`@import`

1

12

1

5.5

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- [`@media`](@media)
- [`@supports`](@supports)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@import" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@import</a>
