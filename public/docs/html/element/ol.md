&lt;ol&gt;: The Ordered List element
====================================

The `<ol>` represents an ordered list of items — typically rendered as a numbered list.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, and if the <code>&lt;ol&gt;</code> element's children include at least one <a href="li"><code>&lt;li&gt;</code></a> element, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">palpable content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="li"><code>&lt;li&gt;</code></a>, <a href="script"><code>&lt;script&gt;</code></a> and <a href="template"><code>&lt;template&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>list</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>directory</code>, <code>group</code>, <code>listbox</code>, <code>menu</code>, <code>menubar</code>, <code>none</code>, <code>presentation</code>, <code>radiogroup</code>, <code>tablist</code>, <code>toolbar</code>, <code>tree</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOListElement"><code>HTMLOListElement</code></a></td></tr></tbody></table>

Attributes
----------

This element also accepts the [global attributes](../global_attributes).

`reversed`  
This Boolean attribute specifies that the list’s items are in reverse order. Items will be numbered from high to low.

`start`  
An integer to start counting from for the list items. Always an Arabic numeral (1, 2, 3, etc.), even when the numbering `type` is letters or Roman numerals. For example, to start numbering elements from the letter "d" or the Roman numeral "iv," use `start="4"`.

`type`  
Sets the numbering type:

-   `a` for lowercase letters
-   `A` for uppercase letters
-   `i` for lowercase Roman numerals
-   `I` for uppercase Roman numerals
-   `1` for numbers (default)

The specified type is used for the entire list unless a different [`type`](li#attr-type) attribute is used on an enclosed [`<li>`](li) element.

**Note:** Unless the type of the list number matters (like legal or technical documents where items are referenced by their number/letter), use the CSS [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property instead.

Usage notes
-----------

Typically, ordered list items display with a preceding [marker](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker), such as a number or letter.

The `<ol>` and [`<ul>`](ul) elements may nest as deeply as desired, alternating between `<ol>` and `<ul>` however you like.

The `<ol>` and [`<ul>`](ul) elements both represent a list of items. The difference is with the `<ol>` element, the order is meaningful. For example:

-   Steps in a recipe
-   Turn-by-turn directions
-   The list of ingredients in decreasing proportion on nutrition information labels

To determine which list to use, try changing the order of the list items; if the meaning changes, use the `<ol>` element — otherwise you can use [`<ul>`](ul).

Examples
--------

### Simple example

    <ol>
      <li>Fee</li>
      <li>Fi</li>
      <li>Fo</li>
      <li>Fum</li>
    </ol>

The above HTML will output:

### Using Roman Numeral type

    <ol type="i">
      <li>Introduction</li>
      <li>List of Greivances</li>
      <li>Conclusion</li>
    </ol> 

The above HTML will output:

### Using the start attribute

    <p>Finishing places of contestants not in the winners’ circle:</p>

    <ol start="4">
      <li>Speedwalk Stu</li>
      <li>Saunterin’ Sam</li>
      <li>Slowpoke Rodriguez</li>
    </ol>

The above HTML will output:

### Nesting lists

    <ol>
      <li>first item</li>
      <li>second item  <!-- closing </li> tag not here! -->
        <ol>
          <li>second item first subitem</li>
          <li>second item second subitem</li>
          <li>second item third subitem</li>
        </ol>
      </li>            <!-- Here's the closing </li> tag -->
      <li>third item</li>
    </ol>

The above HTML will output:

### Unordered list inside ordered list

    <ol>
      <li>first item</li>
      <li>second item  <!-- closing </li> tag not here! -->
        <ul>
          <li>second item first subitem</li>
          <li>second item second subitem</li>
          <li>second item third subitem</li>
        </ul>
      </li>            <!-- Here's the closing </li> tag -->
      <li>third item</li>
    </ol>

The above HTML will output:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-ol-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;ol&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since last W3C snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-ol-element">HTML5<br />
<span class="small">The definition of 'HTMLOListElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>reversed</code> and <code>start</code> attributed; un-deprecated <code>type</code></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/lists.html#h-10.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;ol&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecated <code>compact</code> and <code>type</code>.</td></tr></tbody></table>

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

`ol`

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

`reversed`

18

≤79

18

No

Yes

6

Yes

Yes

18

Yes

Yes

Yes

`start`

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

-   Other list-related HTML Elements: [`<ul>`](ul), [`<li>`](li), [`<menu>`](menu)
-   CSS properties that may be specially useful to style the `<ol>` element:
    -   the [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) property, to choose the way the ordinal displays
    -   [CSS counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters), to handle complex nested lists
    -   the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) property, to simulate the deprecated [`compact`](#attr-compact) attribute
    -   the [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property, to control the list indentation

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol</a>
