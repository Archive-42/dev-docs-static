title
=====

The `title` [global attribute](../global_attributes) contains text representing advisory information related to the element it belongs to.

Some typical uses:

-   Labeling [`<iframe>`](../element/iframe) elements for assistive technology
-   Providing a programmatically associated label for an [`<input>`](../element/input) element as a fallback for a real [`<label>`](../element/label)
-   Labeling controls in [data tables](../element/table)

Additional semantics are attached to the `title` attributes of the [`<link>`](../element/link), [`<abbr>`](../element/abbr), [`<input>`](../element/input), and [`<menuitem>`](../element/menuitem) elements.

Multiline titles
----------------

The `title` attribute may contain several lines. Each `U+000A LINE FEED` (`LF`) character represents a line break. Some caution must be taken, as this means the following renders across two lines:

### HTML

    <p>Newlines in <code>title</code> should be taken into account,
    like <abbr title="This is a
    multiline title">example</abbr>.</p>

### Result

Title attribute inheritance
---------------------------

If an element has no `title` attribute, then it inherits it from its parent node, which in turn may inherit it from its parent, and so on.

If this attribute is set to the empty string, it means its ancestors' `title`s are irrelevant and shouldn't be used in the tooltip for this element.

### HTML

    <div title="CoolTip">
      <p>Hovering here will show “CoolTip”.</p>
      <p title="">Hovering here will show nothing.</p>
    </div>

### Result

Accessibility concerns
----------------------

Use of the `title` attribute is highly problematic for:

-   People using touch-only devices
-   People navigating with keyboards
-   People navigating with assistive technology such as screen readers or magnifiers
-   People experiencing fine motor control impairment
-   People with cognitive concerns

This is due to inconsistent browser support, compounded by the additional assistive technology parsing of the browser-rendered page. If a tooltip effect is desired, it is better to [use a more accessible technique](https://inclusive-components.design/tooltips-toggletips/) that can be accessed with the above browsing methods.

-   [3.2.5.1. The title attribute | W3C HTML 5.2: 3. Semantics, structure, and APIs of HTML documents](https://www.w3.org/TR/html/dom.html#the-title-attribute)
-   [Using the HTML title attribute – updated | The Paciello Group](https://developer.paciellogroup.com/blog/2013/01/using-the-html-title-attribute-updated/)
-   [Tooltips & Toggletips - Inclusive Components](https://inclusive-components.design/tooltips-toggletips/)
-   [The Trials and Tribulations of the Title Attribute - 24 Accessibility](https://www.24a11y.com/2017/the-trials-and-tribulations-of-the-title-attribute/)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#the-title-attribute">HTML Living Standard<br />
<span class="small">The definition of 'title' in that specification.</span></a></td></tr></tbody></table>

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

`title`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`multi-line-support`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

?

?

Yes

See also
--------

-   All [global attributes](../global_attributes).
-   [`HTMLElement.title`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/title) that reflects this attribute.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/title</a>
