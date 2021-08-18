&lt;ul&gt;: The Unordered List element
======================================

The `<ul>` represents an unordered list of items, typically rendered as a bulleted list.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, and if the <code>&lt;ul&gt;</code> element's children include at least one <a href="li"><code>&lt;li&gt;</code></a> element, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="li"><code>&lt;li&gt;</code></a>, <a href="script"><code>&lt;script&gt;</code></a> and <a href="template"><code>&lt;template&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>list</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>directory</code>, <code>group</code>, <code>listbox</code>, <code>menu</code>, <code>menubar</code>, <code>none</code>, <code>presentation</code>, <code>radiogroup</code>, <code>tablist</code>, <code>toolbar</code>, <code>tree</code></td></tr><tr class="odd"><td>DOM Interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLUListElement"><code>HTMLUListElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `compact` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This Boolean attribute hints that the list should be rendered in a compact style. The interpretation of this attribute depends on the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), and it doesn't work in all browsers.

**Warning:** Do not use this attribute, as it has been deprecated: use [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) instead. To give a similar effect as the `compact` attribute, the CSS property [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) can be used with a value of `80%`.

 `type` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute sets the bullet style for the list. The values defined under HTML3.2 and the transitional version of HTML 4.0/4.01 are:

-   `circle`
-   `disc`
-   `square`

A fourth bullet type has been defined in the WebTV interface, but not all browsers support it: `triangle`.

If not present and if no [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property applies to the element, the user agent selects a bullet type depending on the nesting level of the list.

**Warning:** Do not use this attribute, as it has been deprecated; use the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property instead.

Usage notes
-----------

-   The `<ul>` element is for grouping a collection of items that do not have a numerical ordering, and their order in the list is meaningless. Typically, unordered-list items are displayed with a bullet, which can be of several forms, like a dot, a circle, or a square. The bullet style is not defined in the HTML description of the page, but in its associated CSS, using the [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property.
-   The `<ul>` and [`<ol>`](ol) elements may be nested as deeply as desired. Moreover, the nested lists may alternate between `<ol>` and `<ul>` without restriction.
-   The [`<ol>`](ol) and `<ul>` elements both represent a list of items. They differ in that, with the [`<ol>`](ol) element, the order is meaningful. As a rule of thumb to determine which one to use, try changing the order of the list items; if the meaning is changed, the [`<ol>`](ol) element should be used, otherwise you can use `<ul>`.

Examples
--------

### Simple example

    <ul>
      <li>first item</li>
      <li>second item</li>
      <li>third item</li>
    </ul>

The above HTML will output:

### Nesting a list

    <ul>
      <li>first item</li>
      <li>second item
      <!-- Look, the closing </li> tag is not placed here! -->
        <ul>
          <li>second item first subitem</li>
          <li>second item second subitem
          <!-- Same for the second nested unordered list! -->
            <ul>
              <li>second item second subitem first sub-subitem</li>
              <li>second item second subitem second sub-subitem</li>
              <li>second item second subitem third sub-subitem</li>
            </ul>
          </li> <!-- Closing </li> tag for the li that
                      contains the third unordered list -->
          <li>second item third subitem</li>
        </ul>
      <!-- Here is the closing </li> tag -->
      </li>
      <li>third item</li>
    </ul>

The above HTML will output:

### Ordered list inside unordered list

    <ul>
      <li>first item</li>
      <li>second item
      <!-- Look, the closing </li> tag is not placed here! -->
        <ol>
          <li>second item first subitem</li>
          <li>second item second subitem</li>
          <li>second item third subitem</li>
        </ol>
      <!-- Here is the closing </li> tag -->
      </li>
      <li>third item</li>
    </ul>

The above HTML will output:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-ul-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;ul&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-ul-element">HTML5<br />
<span class="small">The definition of '&lt;ul&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`ul`

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

`compact`

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

`type`

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

-   Other list-related HTML Elements: [`<ol>`](ol), [`<li>`](li), [`<menu>`](menu)
-   CSS properties that may be specially useful to style the `<ul>` element:
    -   the [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) property, to choose the way the ordinal displays.
    -   [CSS counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters), to handle complex nested lists.
    -   the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) property, to simulate the deprecated [`compact`](#attr-compact) attribute.
    -   the [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property, to control the list indentation.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul</a>
