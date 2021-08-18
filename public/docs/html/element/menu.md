&lt;menu&gt;
============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `<menu>` represents a group of commands that a user can perform or activate. This includes both list menus, which might appear across the top of a screen, as well as [context menus](#context_menu), such as those that might appear underneath a button after it has been clicked.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><p><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>. If the element's children include at least one <a href="li"><code>&lt;li&gt;</code></a> element: <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#palpable_content">Palpable content</a>.</p></td></tr><tr class="even"><td>Permitted content</td><td><p>If the element is in the <em>list menu</em> state: <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>, or alternatively, zero or more occurrences of <a href="li"><code>&lt;li&gt;</code></a>, <a href="script"><code>&lt;script&gt;</code></a>, and <a href="template"><code>&lt;template&gt;</code></a>. (<em>list menu</em> is the default state, unless the parent element is a <a href="menu"><code>&lt;menu&gt;</code></a> in the <em>context menu</em> state.)</p><p>If the element is in the <em>context menu</em> state: zero or more occurrences, in any order, of <a href="menu"><code>&lt;menu&gt;</code></a> (<em>context menu</em> state only), <a href="menuitem"><code>&lt;menuitem&gt;</code></a>, <a href="hr"><code>&lt;hr&gt;</code></a>, <a href="script"><code>&lt;script&gt;</code></a>, and <a href="template"><code>&lt;template&gt;</code></a>.</p></td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>list</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>directory</code>, <code>group</code>, <code>listbox</code>, <code>menu</code>, <code>menubar</code>, <code>none</code>, <code>presentation</code>, <code>radiogroup</code>, <code>tablist</code>, <code>toolbar</code> or <code>tree</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMenuElement"><code>HTMLMenuElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `label` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The name of the menu as shown to the user. Used within nested menus, to provide a label through which the submenu can be accessed. Must only be specified when the parent element is a [`<menu>`](menu) in the *context menu* state.

`type`  
This attribute indicates the kind of menu being declared, and can be one of two values.

-   `context` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> : Indicates the *popup menu* state, which represents a group of commands activated through another element. This might be as a button menu referenced by a [`menu`](button#attr-menu) attribute of a [`<button>`](button) element, or as context menu for an element with a [`contextmenu`](../global_attributes#attr-contextmenu) attribute. This value is the default if the attribute is missing and the parent element is also a `<menu>` element.
-   `toolbar`: Indicates the *toolbar* state, which represents a toolbar consisting of a series of commands for user interaction. This might be in the form of an unordered list of [`<li>`](li) elements, or, if the element has no `<li>` element children, [flow content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content) describing available commands. This value is the default if the attribute is missing.

Usage notes
-----------

The [`<menu>`](menu) and [`<ul>`](ul) elements both represent an unordered list of items. The key difference is that [`<ul>`](ul) primarily contains items for display, whilst [`<menu>`](menu) is intended for interactive items, to act on.

An HTML menu can be used to create context menus (typically activated by right-clicking another element) or toolbars.

**[Context menus](#context_menu)** consist of a `<menu>` element which contains [`<menuitem>`](menuitem) elements for each selectable option in the menu, `<menu>` elements for submenus within the menu, and [`<hr>`](hr) elements for separator lines to break up the menu's content into sections. Context menus are then attached to the element they're activated from using either the associated element's [`contextmenu`](../global_attributes#attr-contextmenu) attribute or, for [button-activated menus](#button_menu) attached to [`<button>`](button) elements, the [`menu`](button#attr-menu) attribute.

**[Toolbar menus](#toolbar)** consist of a `<menu>` element whose content is described in one of two ways: either as an unordered list of items represented by [`<li>`](li) elements (each representing a command or option the user can utilize), or (if there are no `<li>` elements), [flow content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content) describing the available commands and options.

This element was deprecated in HTML4, but reintroduced in HTML5.1 and the HTML living standard. This document describes the current Firefox implementation. Type 'list' is likely to change to 'toolbar' according to HTML5.1.

Examples
--------

### Context menu

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

#### HTML

    <!-- A <div> element with a context menu -->
    <div contextmenu="popup-menu">
      Right-click to see the adjusted context menu
    </div>

    <menu type="context" id="popup-menu">
      <menuitem>Action</menuitem>
      <menuitem>Another action</menuitem>
      <hr/>
      <menuitem>Separated action</menuitem>
    </menu>

#### CSS

    div {
      width: 300px;
      height: 80px;
      background-color: lightgreen;
    }

#### Result

### Menu button

Menu buttons haven't been implemented in any known browsers yet. The [`type`](#attr-type) attribute on the `<menu>` element is now obsolete.

[`<menuitem>`](menuitem) element is obsolete.

#### HTML

    <!-- A button, which displays a menu when clicked. -->
    <button type="menu" menu="popup-menu">
      Dropdown
    </button>

    <menu type="context" id="popup-menu">
      <menuitem>Action</menuitem>
      <menuitem>Another action</menuitem>
      <hr/>
      <menuitem>Separated action</menuitem>
    </menu>

#### Result

### Toolbar

Toolbar menus haven't been implemented in any known browsers yet.

#### HTML

    <!-- A context menu for a simple editor,
       - containing two menu buttons. -->
    <menu type="toolbar">
      <li>
        <button type="menu" menu="file-menu">File</button>
        <menu type="context" id="file-menu">
          <menuitem label="New..." onclick="newFile()">
          <menuitem label="Save..." onclick="saveFile()">
        </menu>
      </li>
      <li>
        <button type="menu" menu="edit-menu">Edit</button>
        <menu type="context" id="edit-menu">
          <menuitem label="Cut..." onclick="cutEdit()">
          <menuitem label="Copy..." onclick="copyEdit()">
          <menuitem label="Paste..." onclick="pasteEdit()">
        </menu>
      </li>
    </menu>

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/grouping-content.html#the-menu-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;menu&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML 5.2</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/interactive-elements.html#the-menu-element">HTML 5.1<br />
<span class="small">The definition of '&lt;menu&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`menu`

No

≤18-79

8

No

No

No

No

No

8

Nested menus are not supported.

No

No

No

`button_menus`

No

No

No

No

No

No

No

No

No

No

No

No

`hr_separator`

No

No

51

No

No

No

No

No

51

No

No

No

`label`

No

No

8

No

No

No

No

No

8

Nested menus are not supported.

No

No

No

See also
--------

-   Other list-related HTML Elements: [`<ol>`](ol), [`<ul>`](ul), [`<li>`](li), [`<hr>`](hr), and the obsolete [`<dir>`](dir).
-   The [`contextmenu`](../global_attributes#attr-contextmenu) [global attribute](../global_attributes) can be used on an element to refer to the `id` of a `menu` with [`type="context"`](#attr-type).

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menu</a>
