&lt;pre&gt;: The Preformatted Text element
==========================================

The `<pre>` represents preformatted text which is to be presented exactly as written in the HTML file. The text is typically rendered using a non-proportional ("[monospace](https://developer.mozilla.org/en-US/docs/XUL/Style/monospace)") font. Whitespace inside this element is displayed as written.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLPreElement"><code>HTMLPreElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

 `cols` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Contains the *preferred* count of characters that a line should have. It was a non-standard synonym of [`width`](#attr-width). To achieve such an effect, use CSS [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) instead.

 `width` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Contains the *preferred* count of characters that a line should have. Though technically still implemented, this attribute has no visual effect; to achieve such an effect, use CSS [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) instead.

 `wrap` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Is a *hint* indicating how the overflow must happen. In modern browser this hint is ignored and no visual effect results in its present; to achieve such an effect, use CSS [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space) instead.

Example
-------

### HTML

    <p>Using CSS to change the font color is easy.</p>
    <pre>
    body {
      color: red;
    }
    </pre>

### Result

Accessibility concerns
----------------------

It is important to provide an alternate description for any images or diagrams created using preformatted text. The alternate description should clearly and concisely describe the image or diagram's content.

People experiencing low vision conditions and browsing with the aid of assistive technology such as a screen reader may not understand what the preformatted text characters are representing when they are read out in sequence.

A combination of the [`<figure>`](figure) and [`<figcaption>`](figcaption) elements, supplemented by a combination of an [`id`](../global_attributes#attr-id) and the [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) `role` and `aria-labelledby` attributes allow the preformatted text to be announced as an image, with the `figcaption` serving as the image's alternate description.

### Example

    <figure role="img" aria-labelledby="cow-caption">
      <pre>
      ___________________________
    < I'm an expert in my field. >
      ---------------------------
             \   ^__^
              \  (oo)\_______
                 (__)\       )\/\
                     ||----w |
                     ||     ||
      </pre>
      <figcaption id="cow-caption">
        A cow saying, "I'm an expert in my field." The cow is illustrated using preformatted text characters.
      </figcaption>
    </figure>

-   [MDN Understanding WCAG, Guideline 1.1 explanations](#)
-   [H86: Providing text alternatives for ASCII art, emoticons, and leetspeak | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H86.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-pre-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;pre&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No significant change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-pre-element">HTML5<br />
<span class="small">The definition of '&lt;pre&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change from <a href="https://www.w3.org/TR/html401/">HTML 4.01 Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.3.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;pre&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecated the <code>cols</code> attribute</td></tr></tbody></table>

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

`pre`

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

`cols`

No

No

1-29

No

No

No

No

No

4-29

No

No

No

`width`

Yes

Specifying the `width` attribute has no layout effect.

12

Specifying the `width` attribute has no layout effect.

1

Since Firefox 29, specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

4

Since Firefox 29, specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

Yes

Specifying the `width` attribute has no layout effect.

`wrap`

?

?

1

?

?

?

?

?

4

?

?

?

See also
--------

-   CSS: [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space), [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
-   Related element: [`<code>`](code)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/pre</a>
