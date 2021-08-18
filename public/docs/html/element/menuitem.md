&lt;menuitem&gt;
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<menuitem>` represents a command that a user is able to invoke through a popup menu. This includes context menus, as well as menus that might be attached to a menu button.

A command can either be defined explicitly, with a textual label and optional icon to describe its appearance, or alternatively as an *indirect command* whose behavior is defined by a separate element. Commands can also optionally include a checkbox or be grouped to share radio buttons. (Menu items for indirect commands gain checkboxes or radio buttons when defined against elements `<input type="checkbox">` and `<input type="radio">`.)

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag and must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>The <a href="menu"><code>&lt;menu&gt;</code></a> element, where that element is in the <em>popup menu</em> state. (If specified, the <code>type</code> attribute of the <a href="menu"><code>&lt;menu&gt;</code></a> element must be <code>popup</code>; if missing, the parent element of the <a href="menu"><code>&lt;menu&gt;</code></a> must itself be a <a href="menu"><code>&lt;menu&gt;</code></a> in the <em>popup menu</em> state.)</td></tr><tr class="odd"><td>Permitted ARIA roles</td><td>None</td></tr><tr class="even"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMenuItemElement"><code>HTMLMenuItemElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes); in particular `title` can be used to describe the command, or provide usage hints.

`checked`  
Boolean attribute which indicates whether the command is selected. May only be used when the `type` attribute is `checkbox` or `radio`.

`command`  
Specifies the ID of a separate element, indicating a command to be invoked indirectly. May not be used within a menu item that also includes the attributes `checked`, `disabled`, `icon`, `label`, `radiogroup` or `type`.

`default`  
This Boolean attribute indicates use of the same command as the menu's subject element (such as a `button` or `input`).

`disabled`  
Boolean attribute which indicates that the command is not available in the current state. Note that `disabled` is distinct from `hidden`; the `disabled` attribute is appropriate in any context where a change in circumstances might render the command relevant.

`icon`  
Image URL, used to provide a picture to represent the command.

`label`  
The name of the command as shown to the user. Required when a `command` attribute is not present.

`radiogroup`  
This attribute specifies the name of a group of commands to be toggled as radio buttons when selected. May only be used where the `type` attribute is `radio`.

`type`  
This attribute indicates the kind of command, and can be one of three values.

-   `command`: A regular command with an associated action. This is the missing value default.
-   `checkbox`: Represents a command that can be toggled between two different states.
-   `radio`: Represent one selection from a group of commands that can be toggled as radio buttons.

Example
-------

### HTML

    <!-- A <div> element with a context menu -->
    <div contextmenu="popup-menu">
      Right-click to see the adjusted context menu
    </div>

    <menu type="context" id="popup-menu">
      <menuitem type="checkbox" checked>Checkbox</menuitem>
      <hr>
      <menuitem type="command" label="This command does nothing" icon="https://developer.mozilla.org/static/img/favicon144.png">
        Commands don't render their contents.
      </menuitem>
      <menuitem type="command" label="This command has javascript" onclick="alert('command clicked')">
        Commands don't render their contents.
      </menuitem>
      <hr>
      <menuitem type="radio" radiogroup="group1">Radio Button 1</menuitem>
      <menuitem type="radio" radiogroup="group1">Radio Button 2</menuitem>
    </menu>

### CSS content

    div {
      width: 300px;
      height: 80px;
      background-color: lightgreen;
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/obsolete.html#elementdef-menuitem">HTML 5.2<br />
<span class="small">The definition of '&lt;menuitem&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, made obsolete.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/interactive-elements.html#the-menuitem-element">HTML 5.1<br />
<span class="small">The definition of '&lt;menuitem&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of the <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, initial definition.</td></tr></tbody></table>

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

`menuitem`

No

No

85

\["Only works for `<menuitem>` elements defined within a `<menu>` element assigned to an element via the `contextmenu` attribute.", "The `<menuitem>` element requires a closing tag."\]

8-85

\["Only works for `<menuitem>` elements defined within a `<menu>` element assigned to an element via the `contextmenu` attribute.", "The `<menuitem>` element requires a closing tag."\]

No

No

No

No

No

85

\["Only works for `<menuitem>` elements defined within a `<menu>` element assigned to an element via the `contextmenu` attribute.", "The `<menuitem>` element requires a closing tag."\]

8-85

\["Only works for `<menuitem>` elements defined within a `<menu>` element assigned to an element via the `contextmenu` attribute.", "The `<menuitem>` element requires a closing tag."\]

No

No

No

`checked`

No

No

8

No

No

No

No

No

8

No

No

No

`command`

No

No

8

No

No

No

No

No

8

No

No

No

`default`

No

No

8

No

No

No

No

No

8

No

No

No

`disabled`

No

No

8

No

No

No

No

No

8

No

No

No

`icon`

No

No

8

No

No

No

No

No

8

No

No

No

`radiogroup`

No

No

8

No

No

No

No

No

8

No

No

No

`type`

No

No

8

No

No

No

No

No

8

No

No

No

See also
--------

-   [HTML5 context menus in Firefox (Screencast and Code)](https://hacks.mozilla.org/2011/11/html5-context-menus-in-firefox-screencast-and-code/)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menuitem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/menuitem</a>
