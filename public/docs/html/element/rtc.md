&lt;rtc&gt;: The Ruby Text Container element
============================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<rtc>` embraces semantic annotations of characters presented in a ruby of [`<rb>`](rb) elements used inside of [`<ruby>`](ruby) element. [`<rb>`](rb) elements can have both pronunciation ([`<rt>`](rt)) and semantic ([`<rtc>`](rtc)) annotations.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a> or <a href="rt"><code>&lt;rt&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>The closing tag can be omitted if it is immediately followed by a <a href="rb"><code>&lt;rb&gt;</code></a>, <a href="rtc"><code>&lt;rtc&gt;</code></a> or <a href="rt"><code>&lt;rt&gt;</code></a> element opening tag or by its parent closing tag.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="ruby"><code>&lt;ruby&gt;</code></a> element.</td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Examples
--------

    <div class="info">
      <ruby>
        <rbc>
          <rb>旧</rb><rt>jiù</rt>
          <rb>金</rb><rt>jīn</rt>
          <rb>山</rb><rt>shān</rt>
        </rbc>
        <rtc>San Francisco</rtc>
      </ruby>
    </div>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-rtc-element">HTML 5.2<br />
<span class="small">The definition of '&lt;rtc&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/textlevel-semantics.html#the-rtc-element">HTML 5.1<br />
<span class="small">The definition of '&lt;rtc&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/text-level-semantics.html#the-rtc-element">HTML5<br />
<span class="small">The definition of '&lt;rtc&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`rtc`

No

No

33

No

No

No

No

No

33

No

No

No

See also
--------

-   [`<ruby>`](ruby)
-   [`<rp>`](rp)
-   [`<rb>`](rb)
-   [`<rt>`](rt)
-   [`<rbc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rbc)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc</a>
