Global attributes
=================

**Global attributes** are attributes common to all HTML elements; they can be used on all elements, though they may have no effect on some elements.

Global attributes may be specified on all [HTML elements](element), *even those not specified in the standard*. That means that any non-standard elements must still permit these attributes, even though using those elements means that the document is no longer HTML5-compliant. For example, HTML5-compliant browsers hide content marked as `<foo hidden>...</foo>`, even though `<foo>` is not a valid HTML element.

In addition to the basic HTML global attributes, the following global attributes also exist:

-   `xml:lang` and `xml:base` — these are inherited from the XHTML specifications and deprecated, but kept for compatibility purposes.
-   The multiple `aria-*` attributes, used for improving accessibility.
-   The [event handler](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) attributes: `onabort`, `onautocomplete`, `onautocompleteerror`, `onblur`, `oncancel`, `oncanplay`, `oncanplaythrough`, `onchange`, `onclick`, `onclose`, `oncontextmenu`, `oncuechange`, `ondblclick`, `ondrag`, `ondragend`, `ondragenter`, `ondragexit`, `ondragleave`, `ondragover`, `ondragstart`, `ondrop`, `ondurationchange`, `onemptied`, `onended`, `onerror`, `onfocus`, `oninput`, `oninvalid`, `onkeydown`, `onkeypress`, `onkeyup`, `onload`, `onloadeddata`, `onloadedmetadata`, `onloadstart`, `onmousedown`, `onmouseenter`, `onmouseleave`, `onmousemove`, `onmouseout`, `onmouseover`, `onmouseup`, `onmousewheel`, `onpause`, `onplay`, `onplaying`, `onprogress`, `onratechange`, `onreset`, `onresize`, `onscroll`, `onseeked`, `onseeking`, `onselect`, `onshow`, `onsort`, `onstalled`, `onsubmit`, `onsuspend`, `ontimeupdate`, `ontoggle`, `onvolumechange`, `onwaiting`.

List of global attributes
-------------------------

[`accesskey`](global_attributes/accesskey)  
Provides a hint for generating a keyboard shortcut for the current element. This attribute consists of a space-separated list of characters. The browser should use the first one that exists on the computer keyboard layout.

[`autocapitalize`](global_attributes/autocapitalize)  
Controls whether and how text input is automatically capitalized as it is entered/edited by the user. It can have the following values:

-   `off` or `none`, no autocapitalization is applied (all letters default to lowercase)
-   `on` or `sentences`, the first letter of each sentence defaults to a capital letter; all other letters default to lowercase
-   `words`, the first letter of each word defaults to a capital letter; all other letters default to lowercase
-   `characters`, all letters should default to uppercase

[`class`](global_attributes/class)  
A space-separated list of the classes of the element. Classes allows CSS and JavaScript to select and access specific elements via the [class selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors) or functions like the method [`Document.getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName).

[`contenteditable`](global_attributes/contenteditable)  
An enumerated attribute indicating if the element should be editable by the user. If so, the browser modifies its widget to allow editing. The attribute must take one of the following values:

-   `true` or the *empty string*, which indicates that the element must be editable;
-   `false`, which indicates that the element must not be editable.

 [`contextmenu`](global_attributes/contextmenu) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The `id` of a [`<menu>`](element/menu) to use as the contextual menu for this element.

[`data-*`](global_attributes/data-*)  
Forms a class of attributes, called custom data attributes, that allow proprietary information to be exchanged between the [HTML](index) and its [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) representation that may be used by scripts. All such custom data are available via the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface of the element the attribute is set on. The [`HTMLOrForeignElement/dataset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset) property gives access to them.

[`dir`](global_attributes/dir)  
An enumerated attribute indicating the directionality of the element's text. It can have the following values:

-   `ltr`, which means *left to right* and is to be used for languages that are written from the left to the right (like English);
-   `rtl`, which means *right to left* and is to be used for languages that are written from the right to the left (like Arabic);
-   `auto`, which lets the user agent decide. It uses a basic algorithm as it parses the characters inside the element until it finds a character with a strong directionality, then it applies that directionality to the whole element.

[`draggable`](global_attributes/draggable)  
An enumerated attribute indicating whether the element can be dragged, using the [Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API). It can have the following values:

-   `true`, which indicates that the element may be dragged
-   `false`, which indicates that the element may not be dragged.

[`enterkeyhint`](global_attributes/enterkeyhint)  
Hints what action label (or icon) to present for the enter key on virtual keyboards.

 [`exportparts`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/exportparts) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Used to transitively export shadow parts from a nested shadow tree into a containing light tree.

[`hidden`](global_attributes/hidden)  
A Boolean attribute indicates that the element is not yet, or is no longer, *relevant*. For example, it can be used to hide elements of the page that can't be used until the login process has been completed. The browser won't render such elements. This attribute must not be used to hide content that could legitimately be shown.

[`id`](global_attributes/id)  
Defines a unique identifier (ID) which must be unique in the whole document. Its purpose is to identify the element when linking (using a fragment identifier), scripting, or styling (with CSS).

[`inputmode`](global_attributes/inputmode)  
Provides a hint to browsers as to the type of virtual keyboard configuration to use when editing this element or its contents. Used primarily on [`<input>`](element/input) elements, but is usable on any element while in [`contenteditable`](#attr-contenteditable) mode.

[`is`](global_attributes/is)  
Allows you to specify that a standard HTML element should behave like a registered custom built-in element (see [Using custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) for more details).

**Note:** The `item*` attributes are part of the [WHATWG HTML Microdata feature](https://html.spec.whatwg.org/multipage/microdata.html#microdata).

[`itemid`](global_attributes/itemid)  
The unique, global identifier of an item.

[`itemprop`](global_attributes/itemprop)  
Used to add properties to an item. Every HTML element may have an `itemprop` attribute specified, where an `itemprop` consists of a name and value pair.

[`itemref`](global_attributes/itemref)  
Properties that are not descendants of an element with the `itemscope` attribute can be associated with the item using an `itemref`. It provides a list of element ids (not `itemid`s) with additional properties elsewhere in the document.

[`itemscope`](global_attributes/itemscope)  
`itemscope` (usually) works along with [`itemtype`](#attr-itemtype) to specify that the HTML contained in a block is about a particular item. `itemscope` creates the Item and defines the scope of the `itemtype` associated with it. `itemtype` is a valid URL of a vocabulary (such as [schema.org](https://schema.org/)) that describes the item and its properties context.

[`itemtype`](global_attributes/itemtype)  
Specifies the URL of the vocabulary that will be used to define `itemprop`s (item properties) in the data structure. [`itemscope`](#attr-itemscope) is used to set the scope of where in the data structure the vocabulary set by `itemtype` will be active.

[`lang`](global_attributes/lang)  
Helps define the language of an element: the language that non-editable elements are in, or the language that editable elements should be written in by the user. The attribute contains one “language tag” (made of hyphen-separated “language subtags”) in the format defined in [*Tags for Identifying Languages (BCP47)*](https://www.ietf.org/rfc/bcp/bcp47.txt). [**xml:lang**](#attr-xml:lang) has priority over it.

[`nonce`](global_attributes/nonce)  
A cryptographic nonce ("number used once") which can be used by [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) to determine whether or not a given fetch will be allowed to proceed.

[`part`](global_attributes/part)  
A space-separated list of the part names of the element. Part names allows CSS to select and style specific elements in a shadow tree via the [`::part`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part) pseudo-element.

[`slot`](global_attributes/slot)  
Assigns a slot in a [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) shadow tree to an element: An element with a `slot` attribute is assigned to the slot created by the [`<slot>`](element/slot) element whose [`name`](element/slot#attr-name) attribute's value matches that `slot` attribute's value.

[`spellcheck`](global_attributes/spellcheck)  
An enumerated attribute defines whether the element may be checked for spelling errors. It may have the following values:

-   `true`, which indicates that the element should be, if possible, checked for spelling errors;
-   `false`, which indicates that the element should not be checked for spelling errors.

[`style`](global_attributes/style)  
Contains [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) styling declarations to be applied to the element. Note that it is recommended for styles to be defined in a separate file or files. This attribute and the [`<style>`](element/style) element have mainly the purpose of allowing for quick styling, for example for testing purposes.

[`tabindex`](global_attributes/tabindex)  
An integer attribute indicating if the element can take input focus (is *focusable*), if it should participate to sequential keyboard navigation, and if so, at what position. It can take several values:

-   a *negative value* means that the element should be focusable, but should not be reachable via sequential keyboard navigation;
-   `0` means that the element should be focusable and reachable via sequential keyboard navigation, but its relative order is defined by the platform convention;
-   a *positive value* means that the element should be focusable and reachable via sequential keyboard navigation; the order in which the elements are focused is the increasing value of the [**tabindex**](#attr-tabindex). If several elements share the same tabindex, their relative order follows their relative positions in the document.

[`title`](global_attributes/title)  
Contains a text representing advisory information related to the element it belongs to. Such information can typically, but not necessarily, be presented to the user as a tooltip.

[`translate`](global_attributes/translate)  
An enumerated attribute that is used to specify whether an element's attribute values and the values of its [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node children are to be translated when the page is localized, or whether to leave them unchanged. It can have the following values:

-   empty string and `yes`, which indicates that the element will be translated.
-   `no`, which indicates that the element will not be translated.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#global-attributes">HTML Living Standard<br />
<span class="small">The definition of 'Global attributes' in that specification.</span></a></td></tr></tbody></table>

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

`accesskey`

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

`autocapitalize`

43

79

83

?

?

No

43

43

83

?

5

?

`autocomplete`

66

\["Support added for `autocomplete` on the `<textarea>` and `<select>` elements.", "Chrome does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

Yes

\["Originally only supported on the `<input>` element.", "Chrome does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

≤79

Yes

No

Yes

?

66

\["Support added for `autocomplete` on the `<textarea>` and `<select>` elements.", "WebView does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

Yes

\["Originally only supported on the `<input>` element.", "WebView does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

66

\["Support added for `autocomplete` on the `<textarea>` and `<select>` elements.", "Chrome does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

Yes

\["Originally only supported on the `<input>` element.", "Chrome does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

Yes

Yes

?

9.0

\["Support added for `autocomplete` on the `<textarea>` and `<select>` elements.", "Samsung Internet does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

Yes

\["Originally only supported on the `<input>` element.", "Samsung Internet does not accept `off` as a value. See [bug 587466](https://crbug.com/587466)."\]

`class`

Yes

12

32

Yes

Yes

Yes

Yes

Yes

32

Yes

Yes

Yes

`contenteditable`

Yes

12

3

5.5

9

Yes

Yes

Yes

4

Yes

Yes

Yes

`contextmenu`

No

No

9

No

No

No

No

No

32-56

Support for the `contextmenu` attribute has been removed from Firefox for Android (See [bug 1424252](https://bugzil.la/1424252)).

No

No

No

`data_attributes`

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

`dir`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`draggable`

Yes

12

2

Yes

12

Yes

Yes

Yes

4

Yes

Yes

Yes

`enterkeyhint`

77

79

79

No

66

13.1

77

77

79

57

13.4

12.0

`exportparts`

73

79

72

No

60

13.1

73

73

79

?

13.4

No

`hidden`

Yes

12

Yes

11

Yes

Yes

4

Yes

Yes

Yes

Yes

Yes

`id`

Yes

12

32

Yes-32

`id` is a true global attribute only since Firefox 32.

Yes

Yes

Yes

Yes

Yes

32

Yes-32

`id` is a true global attribute only since Firefox 32.

Yes

Yes

Yes

`inputmode`

66

79

23

\["Before version 77, Firefox does not support `inputmode` when `contenteditable` is `true`.", "Before version 75, Firefox accepts values from an earlier specification. From version 75, it accepts values from the WHATWG Living Standard. See [bug 1509527](https://bugzil.la/1509527)."\]

17-23

No

53

No

66

66

79

68

47

12.2

9.0

`is`

67

79

63

No

54

No

See [bug 182671](https://webkit.org/b/182671).

67

67

63

48

No

See [bug 182671](https://webkit.org/b/182671).

9.0

`itemid`

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

`itemprop`

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

`itemref`

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

`itemscope`

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

`itemtype`

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

`lang`

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

`nonce`

Yes

Yes

31

No

Yes

Yes

Yes

Yes

31

Yes

Yes

Yes

`part`

73

79

72

69-72

No

60

13.1

73

73

No

?

13.4

No

`slot`

53

≤79

63

?

40

10

53

53

63

41

10

6.0

`spellcheck`

9

12

Yes

11

Yes

Yes

47

47

57

37

9.3

5.0

`style`

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

`tabindex`

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

`translate`

19

79

No

No

15

6

4.4

25

No

14

6

1.5

See also
--------

-   [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element) and [`GlobalEventHandlers`](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers) interfaces that allow to query most global attributes.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes</a>
