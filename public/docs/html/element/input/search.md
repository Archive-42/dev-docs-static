&lt;input type="search"&gt;
===========================

[`<input>`](../input) elements of type `search` are text fields designed for the user to enter search queries into. These are functionally identical to `text` inputs, but may be styled differently by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing the value contained in the search field.</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported Common Attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-maxlength"><code>maxlength</code></a>, <a href="../input#attr-minlength"><code>minlength</code></a>, <a href="../input#attr-pattern"><code>pattern</code></a>, <a href="../input#attr-placeholder"><code>placeholder</code></a>, <a href="../input#attr-required"><code>required</code></a>, <a href="../input#attr-size"><code>size</code></a>.</td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText"><code>setRangeText()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange"><code>setSelectionRange()</code></a>.</td></tr></tbody></table>

Value
-----

The [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the value contained in the search field. You can retrieve this using the <span class="page-not-created">`HTMLInputElement.value`</span> property in JavaScript.

    searchTerms = mySearch.value;

If no validation constraints are in place for the input (see [Validation](#validation) for more details), the value can be any text string or an empty string (`""`).

Additional attributes
---------------------

In addition to the attributes that operate on all [`<input>`](../input) elements regardless of their type, search field inputs support the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The id of the &lt;datalist&gt; element that contains the optional pre-defined autocomplete options</td></tr><tr class="even"><td><code>maxlength</code></td><td>The maximum number of characters the input should accept</td></tr><tr class="odd"><td><code>minlength</code></td><td>The minimum number of characters long the input can be and still be considered valid</td></tr><tr class="even"><td><code>pattern</code></td><td>A regular expression the input's contents must match in order to be valid</td></tr><tr class="odd"><td><code>placeholder</code></td><td>An exemplar value to display in the input field whenever it is empty</td></tr><tr class="even"><td><code>readonly</code></td><td>A Boolean attribute indicating whether or not the contents of the input should be read-only</td></tr><tr class="odd"><td><code>size</code></td><td>A number indicating how many characters wide the input field should be</td></tr><tr class="even"><td><code>spellcheck</code></td><td>Controls whether or not to enable spell checking for the input field, or if the default spell checking configuration should be used</td></tr></tbody></table>

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

### `maxlength`

The maximum number of characters (as UTF-16 code units) the user can enter into the search field. This must be an integer value 0 or higher. If no `maxlength` is specified, or an invalid value is specified, the search field has no maximum length. This value must also be greater than or equal to the value of `minlength`.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is greater than `maxlength` UTF-16 code units long.

### `minlength`

The minimum number of characters (as UTF-16 code units) the user can enter into the search field. This must be a non-negative integer value smaller than or equal to the value specified by `maxlength`. If no `minlength` is specified, or an invalid value is specified, the search input has no minimum length.

The search field will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is fewer than `minlength` UTF-16 code units long.

### `pattern`

The `pattern` attribute, when specified, is a regular expression that the input's [`value`](../../global_attributes#attr-value) must match in order for the value to pass [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). It must be a valid JavaScript regular expression, as used by the [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) type, and as documented in our [guide on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions); the `'u'` flag is specified when compiling the regular expression, so that the pattern is treated as a sequence of Unicode code points, instead of as ASCII. No forward slashes should be specified around the pattern text.

If the specified pattern is not specified or is invalid, no regular expression is applied and this attribute is ignored completely.

**Tip:** Use the [`title`](../input#attr-title) attribute to specify text that most browsers will display as a tooltip to explain what the requirements are to match the pattern. You should also include other explanatory text nearby.

See the section [Specifying a pattern](#specifying_a_pattern) for details and an example.

### `placeholder`

The `placeholder` attribute is a string that provides a brief hint to the user as to what kind of information is expected in the field. It should be a word or short phrase that demonstrates the expected type of data, rather than an explanatory message. The text *must not* include carriage returns or line feeds.

If the control's content has one directionality ([LTR](https://developer.mozilla.org/en-US/docs/Glossary/ltr) or [RTL](https://developer.mozilla.org/en-US/docs/Glossary/rtl)) but needs to present the placeholder in the opposite directionality, you can use Unicode bidirectional algorithm formatting characters to override directionality within the placeholder; see [Overriding BiDi using Unicode control characters](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm#overriding_bidi_using_unicode_control_characters) in [The Unicode Bidirectional Text Algorithm](https://developer.mozilla.org/en-US/docs/Web/Guide/Unicode_Bidrectional_Text_Algorithm) for those characters.

**Note:** Avoid using the `placeholder` attribute if you can. It is not as semantically useful as other ways to explain your form, and can cause unexpected technical issues with your content. See [Labels and placeholders](../input#labels_and_placeholders) in [&lt;input&gt;: The Input (Form Input) element](../input) for more information.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited by the user. Its `value` can, however, still be changed by JavaScript code directly setting the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property.

**Note:** Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### `size`

The `size` attribute is a numeric value indicating how many characters wide the input field should be. The value must be a number greater than zero, and the default value is 20. Since character widths vary, this may or may not be exact and should not be relied upon to be so; the resulting input may be narrower or wider than the specified number of characters, depending on the characters and the font ([`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) settings in use).

This does *not* set a limit on how many characters the user can enter into the field. It only specifies approximately how many can be seen at a time. To set an upper limit on the length of the input data, use the `maxlength` attribute.

### `spellcheck`

`spellcheck` is a global attribute which is used to indicate whether or not to enable spell checking for an element. It can be used on any editable content, but here we consider specifics related to the use of `spellcheck` on [`<input>`](../input) elements. The permitted values for `spellcheck` are:

`false`  
Disable spell checking for this element.

`true`  
Enable spell checking for this element.

"" (empty string) or no value  
Follow the element's default behavior for spell checking. This may be based upon a parent's `spellcheck` setting or other factors.

An input field can have spell checking enabled if it doesn't have the [readonly](#readonly) attribute set and is not disabled.

The value returned by reading `spellcheck` may not reflect the actual state of spell checking within a control, if the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) preferences override the setting.

Non-standard attributes
-----------------------

The following non-standard attributes are available to search input fields. As a general rule, you should avoid using them unless it can't be helped.

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>autocorrect</code></td><td>Whether or not to allow autocorrect while editing this input field. <strong>Safari only.</strong></td></tr><tr class="even"><td><code>incremental</code></td><td>Whether or not to send repeated <code>search</code> events to allow updating live search results while the user is still editing the value of the field. <strong>WebKit and Blink only (Safari, Chrome, Opera, etc.).</strong></td></tr><tr class="odd"><td><code>mozactionhint</code></td><td>A string indicating the type of action that will be taken when the user presses the Enter or Return key while editing the field; this is used to determine an appropriate label for that key on a virtual keyboard. <strong>Firefox for Android only.</strong></td></tr><tr class="even"><td><code>results</code></td><td>The maximum number of items that should be displayed in the drop-down list of previous search queries. <strong>Safari only.</strong></td></tr></tbody></table>

### `autocorrect` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

A Safari extension, the `autocorrect` attribute is a string which indicates whether or not to activate automatic correction while the user is editing this field. Permitted values are:

`on`  
Enable automatic correction of typos, as well as processing of text substitutions if any are configured.

`off`  
Disable automatic correction and text substitutions.

### `incremental` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

The Boolean attribute `incremental` is a WebKit and Blink extension (so supported by Safari, Opera, Chrome, etc.) which, if present, tells the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to process the input as a live search. As the user edits the value of the field, the user agent sends `search` events to the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) object representing the search box. This allows your code to update the search results in real time as the user edits the search.

If `incremental` is not specified, the `search` event is only sent when the user explicitly initiates a search (such as by pressing the Enter or Return key while editing the field).

The `search` event is rate-limited so that it is not sent more frequently than an implementation-defined interval.

### `mozactionhint` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

A Mozilla extension, supported by Firefox for Android, which provides a hint as to what sort of action will be taken if the user presses the Enter or Return key while editing the field. This information is used to decide what kind of label to use on the Enter key on the virtual keyboard.

**Note:** This [has been standardized](https://html.spec.whatwg.org/#input-modalities:-the-enterkeyhint-attribute) as the global attribute [`enterkeyhint`](../../global_attributes#attr-enterkeyhint), but is not yet widely implemented. To see the status of the change being implemented in Firefox, see [bug 1490661](https://bugzilla.mozilla.org/show_bug.cgi?id=1490661).

Permitted values are: `go`, `done`, `next`, `search`, and `send`. The browser decides, using this hint, what label to put on the enter key.

### `results` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

The `results` attribute—supported only by Safari—is a numeric value that lets you override the maximum number of entries to be displayed in the [`<input>`](../input) element's natively-provided drop-down menu of previous search queries.

The value must be a non-negative decimal number. If not provided, or an invalid value is given, the browser's default maximum number of entries is used.

Using search inputs
-------------------

`<input>` elements of type `search` are very similar to those of type `text`, except that they are specifically intended for handling search terms. They are basically equivalent in behavior, but user agents may choose to style them differently by default (and, of course, sites may use stylesheets to apply custom styles to them).

### Basic example

    <form>
      <div>
        <input type="search" id="mySearch" name="q">
        <button>Search</button>
      </div>
    </form>

This renders like so:

`q` is the most common `name` given to search inputs, although it's not mandatory. When submitted, the data name/value pair sent to the server will be `q=searchterm`.

You must remember to set a [`name`](../input#attr-name) for your input, otherwise nothing will be submitted.

### Differences between search and text types

The main basic differences come in the way browsers handle them. The first thing to note is that some browsers show a cross icon that can be clicked on to remove the search term instantly if desired. The following screenshot comes from Chrome:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJAAAAAfCAMAAAA/frSHAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAADnUExURbvd/r3e/gAAAK7Q8v///8jIyN3d3XCu6ufy/4PB/fL4/93t/s3Nzfb29ujz/83l/o/G/XWz73+9+f79/+zs7HGv67nb/PHx8yuX1Y+44dacSv/17/f9/wAJUvjXrf/ou/3+9wADMdX2/wBRoACEyf/+7cXt/0me1s3t/wB7ve/r79ukWQESd+b7/zICAN/V0pEzAP/21qprAM+GAKaPlE8FAOvr69eyhABpvbTX7wA0e7zj96ZWAIrL7755AMeilMeKMLaCSaWSe83j93uLpb6KUmRNhPjWnL6KSdeSMHt5c/fjzoOmvQMhWiEAAAFlSURBVFjD7dfXboMwFAZgY44BA2EGMppFQlazR9PddO/3f57GoUl7gdTepHal/BcGJF988sDHCAQL2oN+BdItjXcs/QvkG7aEeEeyDX8DMiSH8o8jGZ8g3Xao5wYqzwSuRx1bT0CWRL2CHHKdsFAueFSyEpCGqCtzX9SyS5G2BQWhxnm3a2HwHaQiPqCMYhJTyTAQUgUAZUmS7M+givwX40M2yaSDDg5h085i9pbbLUghJKcQJUeIkgoqYlxuwTNrexg3Sg8Y9+u7BJlMsmAuMw1UKXfgOm7O6zDLQzEPk2ELlue7BLHJWsCCPdJAxe6619v89ajNQM1xdH8HHEeod8LO2Sp+H03XIwQwusWXHNdQNTqtXcVP/cFk3IaXLlQf67WLPM9ddozxWac5xdFqyirDRu1mtbIHXP9Dfon18rf9k28uf2rhzjKxTnvh6qGkYlTFqRiFq6nFu3UIdy/bX6X/FegDCSZkW2jTIpgAAAAASUVORK5CYII=" width="144" height="31" />

In addition, modern browsers also tend to automatically store search terms previously entered across domains, which then come up as autocomplete options when subsequent searches are performed in search inputs on that domain. This helps users who tend to do searches on the same or similar search queries over time. This screenshot is from Firefox:

<img src="data:image/png;base64,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" width="171" height="83" />At this point, let's look at some useful techniques you can apply to your search forms.

### Setting placeholders

You can provide a useful placeholder inside your search input that could give a hint on what to do using the [`placeholder`](../input#attr-placeholder) attribute. Look at the following example:

    <form>
      <div>
        <input type="search" id="mySearch" name="q"
         placeholder="Search the site...">
        <button>Search</button>
      </div>
    </form>

You can see how the placeholder is rendered below:

### Search form labels and accessibility

One problem with search forms is their accessibility; a common design practice is not to provide a label for the search field (although there might be a magnifying glass icon or similar), as the purpose of a search form is normally fairly obvious for sighted users due to placement ([this example shows a typical pattern](https://mdn.github.io/learning-area/accessibility/aria/website-aria-roles/)).

This could, however, cause confusion for screenreader users, since they will not have any verbal indication of what the search input is. One way around this that won't impact on your visual design is to use [WAI-ARIA](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics) features:

-   A `role` attribute of value `search` on the `<form>` element will cause screenreaders to announce that the form is a search form.
-   If that isn't enough, you can use an `aria-label` attribute on the [`<input>`](../input) itself. This should be a descriptive text label that will be read out by the screenreader; it's used as a non-visual equivalent to `<label>`.

Let's have a look at an example:

    <form role="search">
      <div>
        <input type="search" id="mySearch" name="q"
         placeholder="Search the site..."
         aria-label="Search through site content">
        <button>Search</button>
      </div>
    </form>

You can see how this is rendered below:

There is no visual difference from the previous example, but screenreader users have way more information available to them.

**Note**: See [Signposts/Landmarks](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#signpostslandmarks) for more information about such accessibility features.

### Physical input element size

The physical size of the input box can be controlled using the [`size`](../input#attr-size) attribute. With it, you can specify the number of characters the input box can display at a time. In this example, for instance, the search box is 30 characters wide:

    <form>
      <div>
        <input type="search" id="mySearch" name="q"
        placeholder="Search the site..." size="30">
        <button>Search</button>
      </div>
    </form>

The result is this wider input box:

Validation
----------

`<input>` elements of type `search` have the same validation features available to them as regular `text` inputs. It is less likely that you'd want to use validation features in general for search boxes. In many cases, users should just be allowed to search for anything, but there are a few cases to consider, such as searches against data of a known format.

**Note**: HTML form validation is *not* a substitute for scripts that ensure that the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data (or data which is too large, is of the wrong type, and so forth) is entered into your database.

### A note on styling

There are useful pseudo-classes available for styling valid/invalid form elements: [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid). In this section, we'll use the following CSS, which will place a check (tick) next to inputs containing valid values, and a cross next to inputs containing invalid values.

    input:invalid ~ span:after {
        content: '✖';
        padding-left: 5px;
        position: absolute;
    }

    input:valid ~ span:after {
        content: '✓';
        padding-left: 5px;
        position: absolute;
    }

The technique also requires a [`<span>`](../span) element to be placed after the form element, which acts as a holder for the icons. This was necessary because some input types on some browsers don't display icons placed directly after them very well.

### Making input required

You can use the [`required`](../input#attr-required) attribute as an easy way of making entering a value required before form submission is allowed:

    <form>
      <div>
        <input type="search" id="mySearch" name="q"
        placeholder="Search the site..." required>
        <button>Search</button>
        <span class="validity"></span>
      </div>
    </form>

This renders like so:

In addition, if you try to submit the form with no search term entered into it, the browser will show a message. The following example is from Firefox:

<img src="data:image/png;base64,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" alt="form field with attached message that says Please fill out this field" width="209" height="114" />

Different messages will be shown when you try to submit the form with different types of invalid data contained inside the inputs; see the below examples.

### Input value length

You can specify a minimum length, in characters, for the entered value using the [`minlength`](../input#attr-minlength) attribute; similarly, use [`maxlength`](../input#attr-maxlength) to set the maximum length of the entered value.

The example below requires that the entered value be 4–8 characters in length.

    <form>
      <div>
        <label for="mySearch">Search for user</label>
        <input type="search" id="mySearch" name="q"
        placeholder="User IDs are 4–8 characters in length" required
        size="30" minlength="4" maxlength="8">
        <button>Search</button>
        <span class="validity"></span>
      </div>
    </form>

This renders like so:

If you try to submit the form with less than 4 characters, you'll be given an appropriate error message (which differs between browsers). If you try to go beyond 8 characters in length, the browser won't let you.

### Specifying a pattern

You can use the [`pattern`](../input#attr-pattern) attribute to specify a regular expression that the inputted value must follow to be considered valid (see [Validating against a regular expression](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_against_a_regular_expression) for a simple crash course).

Let's look at an example. Say we wanted to provide a product ID search form, and the IDs were all codes of two letters followed by four numbers. The following example covers it:

    <form>
      <div>
        <label for="mySearch">Search for product by ID:</label>
        <input type="search" id="mySearch" name="q"
        placeholder="two letters followed by four numbers" required
        size="30" pattern="[A-z]{2}[0-9]{4}">
        <button>Search</button>
        <span class="validity"></span>
      </div>
    </form>

This renders like so:

Examples
--------

You can see a good example of a search form used in context at our [website-aria-roles](https://github.com/mdn/learning-area/tree/master/accessibility/aria/website-aria-roles) example ([see it live](https://mdn.github.io/learning-area/accessibility/aria/website-aria-roles/)).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#text-(type=text)-state-and-search-state-(type=search)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="search"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#text-typetext-state-and-search-state-typesearch">HTML 5.1<br />
<span class="small">The definition of '&lt;input type="search"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`search`

5

12

4

10

10.6

5

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
-   [`<input>`](../input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface it's based upon
-   `<input type="text">`
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/search</a>
