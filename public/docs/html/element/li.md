&lt;li&gt;
==========

The `<li>` is used to represent an item in a list. It must be contained in a parent element: an ordered list ([`<ol>`](ol)), an unordered list ([`<ul>`](ul)), or a menu ([`<menu>`](menu)). In menus and unordered lists, list items are usually displayed using bullet points. In ordered lists, they are usually displayed with an ascending counter on the left, such as a number or letter.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The end tag can be omitted if the list item is immediately followed by another <a href="li"><code>&lt;li&gt;</code></a> element, or if there is no more content in its parent element.</td></tr><tr class="even"><td>Permitted parents</td><td>An <a href="ul"><code>&lt;ul&gt;</code></a>, <a href="ol"><code>&lt;ol&gt;</code></a>, or <a href="menu"><code>&lt;menu&gt;</code></a> element. Though not a conforming usage, the obsolete <a href="dir"><code>&lt;dir&gt;</code></a> can also be a parent.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>listitem</code> when child of an <code>ol</code>, <code>ul</code> or <code>menu</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>menuitem</code>, <code>menuitemcheckbox</code>, <code>menuitemradio</code>, <code>option</code>, <code>none</code>, <code>presentation</code>, <code>radio</code>, <code>separator</code>, <code>tab</code>, <code>treeitem</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLLIElement"><code>HTMLLIElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`value`  
This integer attribute indicates the current ordinal value of the list item as defined by the [`<ol>`](ol) element. The only allowed value for this attribute is a number, even if the list is displayed with Roman numerals or letters. List items that follow this one continue numbering from the value set. The **value** attribute has no meaning for unordered lists ([`<ul>`](ul)) or for menus ([`<menu>`](menu)).

**Note**: This attribute was deprecated in HTML4, but reintroduced in HTML5.

 `type` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This character attribute indicates the numbering type:

-   `a`: lowercase letters
-   `A`: uppercase letters
-   `i`: lowercase Roman numerals
-   `I`: uppercase Roman numerals
-   `1`: numbers

This type overrides the one used by its parent [`<ol>`](ol) element, if any.

**Note:** This attribute has been deprecated; use the CSS [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) property instead.

Examples
--------

For more detailed examples, see the [`<ol>`](ol) and [`<ul>`](ul) pages.

### Ordered list

    <ol>
        <li>first item</li>
        <li>second item</li>
        <li>third item</li>
    </ol>

### Ordered list with a custom value

    <ol type="I">
        <li value="3">third item</li>
        <li>fourth item</li>
        <li>fifth item</li>
    </ol>

### Unordered list

    <ul>
        <li>first item</li>
        <li>second item</li>
        <li>third item</li>
    </ul>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-li-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;li&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/grouping-content.html#the-li-element">HTML5<br />
<span class="small">The definition of '&lt;li&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/lists.html#h-10.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;li&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The <code>type</code> attribute has been deprecated.</td></tr></tbody></table>

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

`li`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`type`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

`value`

1

12

1

≤6

≤12.1

≤4

1

18

4

≤12.1

≤3

1.0

See also
--------

-   Other list-related HTML Elements: [`<ul>`](ul), [`<ol>`](ol), [`<menu>`](menu), and the obsolete [`<dir>`](dir);
-   CSS properties that may be specially useful to style the `<li>` element:
    -   the [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) property, to choose the way the ordinal is displayed,
    -   [CSS counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters/Using_CSS_counters), to handle complex nested lists,
    -   the [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property, to control the indent of the list item.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li</a>
