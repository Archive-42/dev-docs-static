&lt;dfn&gt;: The Definition element
===================================

The **HTML Definition element** (`<dfn>`) is used to indicate the term being defined within the context of a definition phrase or sentence. The [`<p>`](p) element, the [`<dt>`](dt)/[`<dd>`](dd) pairing, or the [`<section>`](section) element which is the nearest ancestor of the `<dfn>` is considered to be the definition of the term.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>, but no <a href="dfn"><code>&lt;dfn&gt;</code></a> element must be a descendant.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>term</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

In HTML5, the [`title`](../global_attributes#attr-title) attribute has special meaning, as noted below.

Usage notes
-----------

There are some not-entirely-obvious aspects to using the `<dfn>` element. We examine those here.

### Specifying the term being defined

The term being defined is identified following these rules:

1.  If the `<dfn>` element has a [`title`](../global_attributes#attr-title) attribute, the value of the `title` attribute is considered to be the term being defined. The element must still have text within it, but that text may be an abbreviation (perhaps using [`<abbr>`](abbr)) or another form of the term.
2.  If the `<dfn>` contains a single child element and does not have any text content of its own, and the child element is an [`<abbr>`](abbr) element with a `title` attribute itself, then the exact value of the `<abbr>` element's `title` is the term being defined.
3.  Otherwise, the text content of the `<dfn>` element is the term being defined. This is shown [in the first example below](#basic_identification_of_a_term).

If the `<dfn>` element has a `title` attribute, it *must* contain the term being defined and no other text.

### Links to `<dfn>` elements

If you include an [`id`](../global_attributes#attr-id) attribute on the `<dfn>` element, you can then link to it using [`<a>`](a) elements. Such links should be uses of the term, with the intent being that the reader can quickly navigate to the term's definition if they're not already aware of it, by clicking on the term's link.

This is shown in the example under [Links to definitions](#links_to_definitions) below.

Examples
--------

Let's take a look at some examples of various usage scenarios.

### Basic identification of a term

This example uses a plain `<dfn>` element to identify the location of a term within the definition.

#### HTML

    <p>The <strong>HTML Definition element</strong>
    (<strong><dfn>&lt;dfn&gt;</dfn></strong>) is used to indicate the
    term being defined within the context of a definition phrase or
    sentence.</p>

Since the `<dfn>` element has no `title`, the text contents of the `<dfn>` element itself are used as the term being defined.

#### Result

This looks like this rendered in your browser:

### Links to definitions

To add links to the definitions, you create the link the same way you always do, with the [`<a>`](a) element.

#### HTML

    <p>The <strong>HTML Definition element</strong>
    (<strong><dfn id="definition-dfn">&lt;dfn&gt;</dfn></strong>) is
    used to indicate the term being defined within the context of a
    definition phrase or sentence.</p>

    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Graece
    donan, Latine voluptatem vocant. Confecta res esset. Duo Reges:
    constructio interrete. Scrupulum, inquam, abeunti; </p>

    <p>Negare non possum. Dat enim intervalla et relaxat. Quonam modo?
    Equidem e Cn. Quid de Pythagora? In schola desinis. </p>

    <p>Ubi ut eam caperet aut quando? Cur iustitia laudatur? Aperiendum
    est igitur, quid sit voluptas; Quid enim? Non est igitur voluptas
    bonum. Urgent tamen et nihil remittunt. Quid enim possumus hoc
    agere divinius? </p>

    <p>Because of all of that, we decided to use the
    <code><a href="#definition-dfn">&lt;dfn&gt;</a></code> element for
    this project.</p>

Here we see the definition — now with an [`id`](../global_attributes#attr-id) attribute, `"definition-dfn"`, which can be used as the target of a link. Later on, a link is created using `<a>` with the [`href`](a#attr-href) attribute set to `"#definition-dfn"` to set up the link back to the definition.

#### Result

The resulting content looks like this:

### Using abbreviations and definitions together

In some cases, you may wish to use an abbreviation for a term when defining it. This can be done by using the `<dfn>` and [`<abbr>`](abbr) elements in tandem, like this:

#### HTML

    <p>The <dfn><abbr title="Hubble Space Telescope">HST</abbr></dfn>
    is among the most productive scientific instruments ever constructed.
    It has been in orbit for over 20 years, scanning the sky and
    returning data and photographs of unprecedented quality and
    detail.</p>

    <p>Indeed, the <abbr title="Hubble Space Telescope">HST</abbr> has
    arguably done more to advance science than any device ever built.</p>

Note the `<abbr>` element nested inside the `<dfn>`. The former establishes that the term is an abbreviation ("HST") and specifies the full term ("Hubble Space Telescope") in its `title` attribute. The latter indicates that the abbreviated term represents a term being defined.

#### Result

The output of the above code looks like this:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-dfn-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;dfn&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-dfn-element">HTML5<br />
<span class="small">The definition of '&lt;dfn&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;dfn&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`dfn`

Yes

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   Elements related to definition lists: [`<dl>`](dl), [`<dt>`](dt), [`<dd>`](dd)
-   [`<abbr>`](abbr)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dfn" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dfn</a>
