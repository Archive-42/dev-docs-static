&lt;kbd&gt;: The Keyboard Input element
=======================================

The **HTML Keyboard Input element** (`<kbd>`) represents a span of inline text denoting textual user input from a keyboard, voice input, or any other text entry device. By convention, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) defaults to rendering the contents of a `<kbd>` element using its default monospace font, although this is not mandated by the HTML standard.

`<kbd>` may be nested in various combinations with the [`<samp>`](samp) (Sample Output) element to represent various forms of input or output based on visual cues.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

Usage notes
-----------

Other elements can be used in tandem with `<kbd>` to represent more specific scenarios:

-   Nesting a `<kbd>` element within another `<kbd>` element represents an actual key or other unit of input as a portion of a larger input. See [Representing keystrokes within an input](#representing_keystrokes_within_an_input) below.
-   Nesting a `<kbd>` element inside a [`<samp>`](samp) element represents input that has been echoed back to the user by the system. See [Echoed input](#echoed_input), below, for an example.
-   Nesting a `<samp>` element inside a `<kbd>` element, on the other hand, represents input which is based on text presented by the system, such as the names of menus and menu items, or the names of buttons displayed on the screen. See the example under [Representing onscreen input options](#representing_onscreen_input_options) below.

You can define a custom style to override the browser's default font selection for the `<kbd>` element, although the user's preferences may potentially override your CSS.

Examples
--------

### Basic example

    <p>Use the command <kbd>help mycommand</kbd> to view documentation
    for the command "mycommand".</p>

### Representing keystrokes within an input

To describe an input comprised of multiple keystrokes, you can nest multiple `<kbd>` elements, with an outer `<kbd>` element representing the overall input and each individual keystroke or component of the input enclosed within its own `<kbd>`.

#### Unstyled

First, let's look at what this looks like as just plain HTML.

##### HTML

    <p>You can also create a new document using the keyboard shortcut
    <kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd>.</p>

This wraps the entire key sequence in an outer `<kbd>` element, then each individual key within its own, in order to denote the components of the sequence.

**Note:** You don't need to do all this wrapping; you can choose to simplify it by leaving out the external `<kbd>` element. In other words, simplifying this to just `<kbd>Ctrl</kbd>+<kbd>N</kbd>` would be perfectly valid.

Depending on your style sheet, though, you may find it useful to do this kind of nesting.

##### Result

The output looks like this without a style sheet applied:

#### With custom styles

We can make more sense of this by adding some CSS:

##### CSS

We add a new style for `<kbd>` elements, `key`, which we can apply when rendering keyboard keys:

    kbd.key {
      border-radius: 3px;
      padding: 1px 2px 0;
      border: 1px solid black;
    }

##### HTML

Then we update the HTML to use this class on the keys in the output to be presented:

    <p>You can also create a new document by pressing <kbd><kbd class="key">Ctrl</kbd>+<kbd class="key">N</kbd></kbd>.</p>

##### Result

The result is just what we want!

### Echoed input

Nesting a `<kbd>` element inside a [`<samp>`](samp) element represents input that has been echoed back to the user by the system.

    <p>If a syntax error occurs, the tool will output the initial
    command you typed for your review:</p>
    <blockquote>
      <samp><kbd>custom-git ad my-new-file.cpp</kbd></samp>
    </blockquote>

### Representing onscreen input options

Nesting a `<samp>` element inside a `<kbd>` element represents input which is based on text presented by the system, such as the names of menus and menu items, or the names of buttons displayed on the screen.

For example, you can explain how to choose the "New Document" option in the "File" menu using HTML that looks like this:

    <p>To create a new file, choose the menu option
    <kbd><kbd><samp>File</samp></kbd>⇒<kbd><samp>New
    Document</samp></kbd></kbd>.</p>

    <p>Don't forget to click the <kbd><samp>OK</samp></kbd> button
    to confirm once you've entered the name of the new file.</p>

This does some interesting nesting. For the menu option description, the entire input is enclosed in a `<kbd>` element. Then, inside that, both the menu and menu item names are contained within both `<kbd>` and `<samp>`, indicating an input which is selected from a screen widget.

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-kbd-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;kbd&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-kbd-element">HTML5<br />
<span class="small">The definition of '&lt;kbd&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Expanded to include any user input, like voice input and individual keystrokes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;kbd&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`kbd`

Yes

12

1

Before Firefox 4, creating a &lt;kbd&gt; element incorrectly resulted in an `HTMLSpanElement` object, instead of the expected `HTMLElement`.

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

-   [`<code>`](code)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd</a>
