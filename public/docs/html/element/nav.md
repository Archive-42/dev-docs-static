&lt;nav&gt;: The Navigation Section element
===========================================

The `<nav>` represents a section of a page whose purpose is to provide navigation links, either within the current document or to other documents. Common examples of navigation sections are menus, tables of contents, and indexes.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#sectioning_content">sectioning content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>navigation</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

-   It's not necessary for all links to be contained in a `<nav>` element. `<nav>` is intended only for major block of navigation links; typically the [`<footer>`](footer) element often has a list of links that don't need to be in a [`<nav>`](nav) element.
-   A document may have several [`<nav>`](nav) elements, for example, one for site navigation and one for intra-page navigation. `aria-labelledby` can be used in such case to promote accessibility, see [example](heading_elements#labeling_section_content).
-   User agents, such as screen readers targeting disabled users, can use this element to determine whether to omit the initial rendering of navigation-only content.

Examples
--------

In this example, a `<nav>` block is used to contain an unordered list ([`<ul>`](ul)) of links. With appropriate CSS, this can be presented as a sidebar, navigation bar, or drop-down menu.

    <nav class="menu">
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>

The semantics of the `nav` element is that of providing links. However a `nav` element doesn’t have to contain a list, it can contain other kinds of content as well. In this navigation block, links are provided in prose:

    <nav>
      <h2>Navigation</h2>
      <p>You are on my home page. To the north lies <a href="/blog">my
      blog</a>, from whence the sounds of battle can be heard. To the east
      you can see a large mountain, upon which many <a
      href="/school">school papers</a> are littered. Far up thus mountain
      you can spy a little figure who appears to be me, desperately
      scribbling a <a href="/school/thesis">thesis</a>.</p>
      <p>To the west are several exits. One fun-looking exit is labeled <a
      href="https://games.example.com/">"games"</a>. Another more
      boring-looking exit is labeled <a
      href="https://isp.example.net/">ISP™</a>.</p>
      <p>To the south lies a dark and dank <a href="/about">contacts
      page</a>. Cobwebs cover its disused entrance, and at one point you
      see a rat run quickly out of the page.</p>
    </nav>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/sections.html#the-nav-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;nav&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change since latest W3C snapshot.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sections.html#the-nav-element">HTML5<br />
<span class="small">The definition of '&lt;nav&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`nav`

5

12

4

9

11.1

5

Yes

Yes

4

11.1

4.2

Yes

See also
--------

-   Other section-related elements: [`<body>`](body), [`<article>`](article), [`<section>`](section), [`<aside>`](aside), [`<h1>`](heading_elements), [`<h2>`](heading_elements), [`<h3>`](heading_elements), [`<h4>`](heading_elements), [`<h5>`](heading_elements), [`<h6>`](heading_elements), [`<hgroup>`](hgroup), [`<header>`](header), [`<footer>`](footer), [`<address>`](address);
-   [Sections and outlines of an HTML5 document](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines).
-   [ARIA: Navigation role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Navigation_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav</a>
