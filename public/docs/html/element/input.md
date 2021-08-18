&lt;input&gt;: The Input (Form Input) element
=============================================

The `<input>` is used to create interactive controls for web-based forms in order to accept data from the user; a wide variety of types of input data and control widgets are available, depending on the device and [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). The `<input>` element is one of the most powerful and complex in all of HTML due to the sheer number of combinations of input types and attributes.

&lt;input&gt; types
-------------------

How an `<input>` works varies considerably depending on the value of its [`type`](#attr-type) attribute, hence the different types are covered in their own separate reference pages. If this attribute is not specified, the default type adopted is `text`.

The available types are as follows:

Type

Description

Basic Examples

[button](input/button)

A push button with no default behavior displaying the value of the [value](#htmlattrdefvalue) attribute, empty by default.

[checkbox](input/checkbox)

A check box allowing single values to be selected/deselected.

[color](input/color)

A control for specifying a color; opening a color picker when active in supporting browsers.

[date](input/date)

A control for entering a date (year, month, and day, with no time). Opens a date picker or numeric wheels for year, month, day when active in supporting browsers.

[datetime-local](input/datetime-local)

A control for entering a date and time, with no time zone. Opens a date picker or numeric wheels for date- and time-components when active in supporting browsers.

[email](input/email)

A field for editing an email address. Looks like a `text` input, but has validation parameters and relevant keyboard in supporting browsers and devices with dynamic keyboards.

[file](input/file)

A control that lets the user select a file. Use the [accept](#htmlattrdefaccept) attribute to define the types of files that the control can select.

[hidden](input/hidden)

A control that is not displayed but whose value is submitted to the server. There is an example in the next column, but it's hidden!

[image](input/image)

A graphical `submit` button. Displays an image defined by the `src` attribute. The [alt](#htmlattrdefalt) attribute displays if the image [src](#htmlattrdefsrc) is missing.

[month](input/month)

A control for entering a month and year, with no time zone.

[number](input/number)

A control for entering a number. Displays a spinner and adds default validation when supported. Displays a numeric keypad in some devices with dynamic keypads.

[password](input/password)

A single-line text field whose value is obscured. Will alert user if site is not secure.

[radio](input/radio)

A radio button, allowing a single value to be selected out of multiple choices with the same [name](#htmlattrdefname) value.

[range](input/range)

A control for entering a number whose exact value is not important. Displays as a range widget defaulting to the middle value. Used in conjunction [min](#htmlattrdefmin) and [max](#htmlattrdefmax) to define the range of acceptable values.

[reset](input/reset)

A button that resets the contents of the form to default values. Not recommended.

[search](input/search)

A single-line text field for entering search strings. Line-breaks are automatically removed from the input value. May include a delete icon in supporting browsers that can be used to clear the field. Displays a search icon instead of enter key on some devices with dynamic keypads.

[submit](input/submit)

A button that submits the form.

[tel](input/tel)

A control for entering a telephone number. Displays a telephone keypad in some devices with dynamic keypads.

[text](input/text)

The default value. A single-line text field. Line-breaks are automatically removed from the input value.

[time](input/time)

A control for entering a time value with no time zone.

[url](input/url)

A field for entering a URL. Looks like a `text` input, but has validation parameters and relevant keyboard in supporting browsers and devices with dynamic keyboards.

[week](input/week)

A control for entering a date consisting of a week-year number and a week number with no time zone.

Obsolete values

[datetime](input/datetime)

<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> A control for entering a date and time (hour, minute, second, and fraction of a second) based on UTC time zone.

Attributes
----------

The `<input>` element is so powerful because of its attributes; the [`type`](#attr-type) attribute, described with examples above, being the most important. Since every `<input>` element, regardless of type, is based on the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface, they technically share the exact same set of attributes. However, in reality, most attributes have an effect on only a specific subset of input types. In addition, the way some attributes impact an input depends on the input type, impacting different input types in different ways.

This section provides a table listing all the attributes with a brief description. This table is followed by a list describing each attribute in greater detail, along with which input types they are associated with.Those that are common to most or all input types are defined in greater detail below. Attributes that are unique to particular input types—or attributes which are common to all input types but have special behaviors when used on a given input type—are instead documented on those types' pages. This element includes the [global attributes](../global_attributes). Those with extra importance as it relates to `<input>` are highlighted.

<table><caption>Attributes for the <a href="input"><code>&lt;input&gt;</code></a> element include <a href="../global_attributes">global HTML attributes</a> and:</caption><thead><tr class="header"><th>Attribute</th><th>Type or Types</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="#htmlattrdefaccept">accept</a></td><td>file</td><td>Hint for expected file type in file upload controls</td></tr><tr class="even"><td><a href="#htmlattrdefalt">alt</a></td><td>image</td><td>alt attribute for the image type. Required for accessibility</td></tr><tr class="odd"><td><a href="#htmlattrdefautocomplete">autocomplete</a></td><td>all</td><td>Hint for form autofill feature</td></tr><tr class="even"><td><a href="#htmlattrdefautofocus">autofocus</a></td><td>all</td><td>Automatically focus the form control when the page is loaded</td></tr><tr class="odd"><td><a href="#htmlattrdefcapture">capture</a></td><td>file</td><td>Media capture input method in file upload controls</td></tr><tr class="even"><td><a href="#htmlattrdefchecked">checked</a></td><td>radio, checkbox</td><td>Whether the command or control is checked</td></tr><tr class="odd"><td><a href="#htmlattrdefdirname">dirname</a></td><td>text, search</td><td>Name of form field to use for sending the element's directionality in form submission</td></tr><tr class="even"><td><a href="#htmlattrdefdisabled">disabled</a></td><td>all</td><td>Whether the form control is disabled</td></tr><tr class="odd"><td><a href="#htmlattrdefform">form</a></td><td>all</td><td>Associates the control with a form element</td></tr><tr class="even"><td><a href="#htmlattrdefformaction">formaction</a></td><td>image, submit</td><td>URL to use for form submission</td></tr><tr class="odd"><td><a href="#htmlattrdefformenctype">formenctype</a></td><td>image, submit</td><td>Form data set encoding type to use for form submission</td></tr><tr class="even"><td><a href="#htmlattrdefformmethod">formmethod</a></td><td>image, submit</td><td>HTTP method to use for form submission</td></tr><tr class="odd"><td><a href="#htmlattrdefformnovalidate">formnovalidate</a></td><td>image, submit</td><td>Bypass form control validation for form submission</td></tr><tr class="even"><td><a href="#htmlattrdefformtarget">formtarget</a></td><td>image, submit</td><td>Browsing context for form submission</td></tr><tr class="odd"><td><a href="#htmlattrdefheight">height</a></td><td>image</td><td>Same as <code>height</code> attribute for <a href="img"><code>&lt;img&gt;</code></a>; vertical dimension</td></tr><tr class="even"><td><a href="#htmlattrdeflist">list</a></td><td>almost all</td><td>Value of the id attribute of the <a href="datalist"><code>&lt;datalist&gt;</code></a> of autocomplete options</td></tr><tr class="odd"><td><a href="#htmlattrdefmax">max</a></td><td>numeric types</td><td>Maximum value</td></tr><tr class="even"><td><a href="#htmlattrdefmaxlength">maxlength</a></td><td>password, search, tel, text, url</td><td>Maximum length (number of characters) of <code>value</code></td></tr><tr class="odd"><td><a href="#htmlattrdefmin">min</a></td><td>numeric types</td><td>Minimum value</td></tr><tr class="even"><td><a href="#htmlattrdefminlength">minlength</a></td><td>password, search, tel, text, url</td><td>Minimum length (number of characters) of <code>value</code></td></tr><tr class="odd"><td><a href="#htmlattrdefmultiple">multiple</a></td><td>email, file</td><td>Boolean. Whether to allow multiple values</td></tr><tr class="even"><td><a href="#htmlattrdefname">name</a></td><td>all</td><td>Name of the form control. Submitted with the form as part of a name/value pair.</td></tr><tr class="odd"><td><a href="#htmlattrdefpattern">pattern</a></td><td>password, text, tel</td><td>Pattern the <code>value</code> must match to be valid</td></tr><tr class="even"><td><a href="#htmlattrdefplaceholder">placeholder</a></td><td>password, search, tel, text, url</td><td>Text that appears in the form control when it has no value set</td></tr><tr class="odd"><td><a href="../attributes/readonly">readonly</a></td><td>almost all</td><td>Boolean. The value is not editable</td></tr><tr class="even"><td><a href="../attributes/required">required</a></td><td>almost all</td><td>Boolean. A value is required or must be check for the form to be submittable</td></tr><tr class="odd"><td><a href="#htmlattrdefsize">size</a></td><td>email, password, tel, text</td><td>Size of the control</td></tr><tr class="even"><td><a href="#htmlattrdefsrc">src</a></td><td>image</td><td>Same as <code>src</code> attribute for <a href="img"><code>&lt;img&gt;</code></a>; address of image resource</td></tr><tr class="odd"><td><a href="#htmlattrdefstep">step</a></td><td>numeric types</td><td>Incremental values that are valid.</td></tr><tr class="even"><td><a href="#htmlattrdeftype">type</a></td><td>all</td><td>Type of form control</td></tr><tr class="odd"><td><a href="#htmlattrdefvalue">value</a></td><td>all</td><td>The initial value of the control.</td></tr><tr class="even"><td><a href="#htmlattrdefwidth">width</a></td><td>image</td><td>Same as <code>width</code> attribute for <a href="img"><code>&lt;img&gt;</code></a></td></tr></tbody></table>

A few additional non-standard attributes are listed following the descriptions of the standard attributes.

### Individual attributes

`accept`  
Valid for the `file` input type only, the `accept` attribute defines which file types are selectable in a `file` upload control. See the [file](input/file) input type.

`alt`  
Valid for the `image` button only, the `alt` attribute provides alternative text for the image, displaying the value of the attribute if the image [`src`](#htmlattrdefsrc) is missing or otherwise fails to load. See the [image](input/image) input type.

`autocomplete`  
(**Not** a Boolean attribute!) The `autocomplete` attribute takes as its value a space-separated string that describes what, if any, type of autocomplete functionality the input should provide. A typical implementation of autocomplete recalls previous values entered in the same input field, but more complex forms of autocomplete can exist. For instance, a browser could integrate with a device's contacts list to autocomplete `email` addresses in an email input field. See [Values](../attributes/autocomplete#values) in [The HTML autocomplete attribute](../attributes/autocomplete) for permitted values.

The `autocomplete` attribute is valid on `hidden`, `text`, `search`, `url`, `tel`, `email`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, `range`, `color`, and `password`. This attribute has no effect on input types that do not return numeric or text data, being valid for all input types except `checkbox`, `radio`, `file`, or any of the button types.

See [The HTML autocomplete attribute](../attributes/autocomplete) for additional information, including information on password security and how `autocomplete` is slightly different for `hidden` than for other input types.

`autofocus`  
A Boolean attribute which, if present, indicates that the input should automatically have focus when the page has finished loading (or when the [`<dialog>`](dialog) containing the element has been displayed).

**Note:** An element with the `autofocus` attribute may gain focus before the <span class="page-not-created">`DOMContentLoaded`</span> event is fired.

No more than one element in the document may have the `autofocus` attribute. If put on more than one element, the first one with the attribute receives focus.

The `autofocus` attribute cannot be used on inputs of type `hidden`, since hidden inputs cannot be focused.

**Warning:** Automatically focusing a form control can confuse visually-impaired people using screen-reading technology and people with cognitive impairments. When `autofocus` is assigned, screen-readers "teleport" their user to the form control without warning them beforehand.

Use careful consideration for accessibility when applying the `autofocus` attribute. Automatically focusing on a control can cause the page to scroll on load. The focus can also cause dynamic keyboards to display on some touch devices. While a screen reader will announce the label of the form control receiving focus, the screen reader will not announce anything before the label, and the sighted user on a small device will equally miss the context created by the preceding content.

`capture`  
Introduced in the HTML Media Capture specification and valid for the `file` input type only, the `capture` attribute defines which media—microphone, video, or camera—should be used to capture a new file for upload with `file` upload control in supporting scenarios. See the [file](input/file) input type.

`checked`  
Valid for both `radio` and `checkbox` types, `checked` is a Boolean attribute. If present on a `radio` type, it indicates that the radio button is the currently selected one in the group of same-named radio buttons. If present on a `checkbox` type, it indicates that the checkbox is checked by default (when the page loads). It does *not* indicate whether this checkbox is currently checked: if the checkbox’s state is changed, this content attribute does not reflect the change. (Only the [`HTMLInputElement`’s `checked` IDL attribute](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) is updated.)

**Note:** Unlike other input controls, a checkboxes and radio buttons value are only included in the submitted data if they are currently `checked`. If they are, the name and the value(s) of the checked controls are submitted.

For example, if a checkbox whose `name` is `fruit` has a `value` of `cherry`, and the checkbox is checked, the form data submitted will include `fruit=cherry`. If the checkbox isn't active, it isn't listed in the form data at all. The default `value` for checkboxes and radio buttons is `on`.

`dirname`  
Valid for `text` and `search` input types only, the `dirname` attribute enables the submission of the directionality of the element. When included, the form control will submit with two name/value pairs: the first being the [`name`](#htmlattrdefname) and [`value`](#htmlattrdefvalue), the second being the value of the `dirname` as the name with the value of `ltr` or `rtl` being set by the browser.

    <form action="page.html" method="post">
      <label>Fruit: <input type="text" name="fruit" dirname="fruit.dir" value="cherry"></label>
      <input type="submit"/>
    </form>
    <!-- page.html?fruit=cherry&fruit.dir=ltr -->

When the form above is submitted, the input cause both the `name` / `value` pair of `fruit=cherry` and the `dirname` / direction pair of `fruit.dir=ltr` to be sent.

`disabled`  
A Boolean attribute which, if present, indicates that the user should not be able to interact with the input. Disabled inputs are typically rendered with a dimmer color or using some other form of indication that the field is not available for use.

Specifically, disabled inputs do not receive the [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) event, and disabled inputs are not submitted with the form.

**Note:** Although not required by the specification, Firefox will by default [persist the dynamic disabled state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of an `<input>` across page loads. Use the [`autocomplete`](#attr-autocomplete) attribute to control this feature.

`form`  
A string specifying the [`<form>`](form) element with which the input is associated (that is, its **form owner**). This string's value, if present, must match the [`id`](../global_attributes#attr-id) of a `<form>` element in the same document. If this attribute isn't specified, the `<input>` element is associated with the nearest containing form, if any.

The `form` attribute lets you place an input anywhere in the document but have it included with a form elsewhere in the document.

**Note:** An input can only be associated with one form.

`formaction`  
Valid for the `image` and `submit` input types only. See the [submit](input/submit) input type for more information.

`formenctype`  
Valid for the `image` and `submit` input types only. See the [submit](input/submit) input type for more information.

`formmethod`  
Valid for the `image` and `submit` input types only. See the [submit](input/submit) input type for more information.

`formnovalidate`  
Valid for the `image` and `submit` input types only. See the [submit](input/submit) input type for more information.

`formtarget`  
Valid for the `image` and `submit` input types only. See the [submit](input/submit) input type for more information.

`height`  
Valid for the `image` input button only, the `height` is the height of the image file to display to represent the graphical submit button. See the [image](input/image) input type.

`id`  
Global attribute valid for all elements, including all the input types, it defines a unique identifier (ID) which must be unique in the whole document. Its purpose is to identify the element when linking. The value is used as the value of the [`<label>`](label)'s `for` attribute to link the label with the form control. See [`<label>`](label).

`inputmode`  
Global value valid for all elements, it provides a hint to browsers as to the type of virtual keyboard configuration to use when editing this element or its contents. Values include `none`, `text`, `tel`, `url`, `email`, `numeric`, `decimal`, and `search`.

`list`  
The value given to the `list` attribute should be the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](datalist) element located in the same document. The `<datalist>` provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

It is valid on `text`, `search`, `url`, `tel`, `email`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, `range`, and `color`.

Per the specifications, the `list` attribute is not supported by the `hidden`, `password`, `checkbox`, `radio`, `file`, or any of the button types.

Depending on the browser, the user may see a custom color palette suggested, tic marks along a range, or even a input that opens like a [`<select>`](select) but allows for non-listed values. Check out the [browser compatibility table](datalist#browser_compatibility) for the other input types.

See the [`<datalist>`](datalist) element.

[`max`](../attributes/max)  
Valid for `date`, `month`, `week`, `time`, `datetime-local`, `number`, and `range`, it defines the greatest value in the range of permitted values. If the [`value`](#attr-value) entered into the element exceeds this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `max` attribute isn't a number, then the element has no maximum value.

There is a special case: if the data type is periodic (such as for dates or times), the value of `max` may be lower than the value of `min`, which indicates that the range may wrap around; for example, this allows you to specify a time range from 10 PM to 4 AM.

`maxlength`  
Valid for `text`, `search`, `url`, `tel`, `email`, and `password`, it defines the maximum number of characters (as UTF-16 code units) the user can enter into the field. This must be an integer value `0` or higher. If no `maxlength` is specified, or an invalid value is specified, the field has no maximum length. This value must also be greater than or equal to the value of `minlength`.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is greater than `maxlength` UTF-16 code units long. By default, browsers prevent users from entering more characters than allowed by the `maxlength` attribute. See [Client-side validation](#client-side_validation) for more information.

`min`  
Valid for `date`, `month`, `week`, `time`, `datetime-local`, `number`, and `range`, it defines the most negative value in the range of permitted values. If the [`value`](#attr-value) entered into the element is less than this this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `min` attribute isn't a number, then the element has no minimum value.

This value must be less than or equal to the value of the `max` attribute. If the `min` attribute is present but is not specified or is invalid, no `min` value is applied. If the `min` attribute is valid and a non-empty value is less than the minimum allowed by the `min` attribute, constraint validation will prevent form submission. See [Client-side validation](#client-side_validation) for more information.

There is a special case: if the data type is periodic (such as for dates or times), the value of `max` may be lower than the value of `min`, which indicates that the range may wrap around; for example, this allows you to specify a time range from 10 PM to 4 AM.

`minlength`  
Valid for `text`, `search`, `url`, `tel`, `email`, and `password`, it defines the minimum number of characters (as UTF-16 code units) the user can enter into the entry field. This must be an non-negative integer value smaller than or equal to the value specified by `maxlength`. If no `minlength` is specified, or an invalid value is specified, the input has no minimum length.

The input will fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation) if the length of the text entered into the field is fewer than `minlength` UTF-16 code units long, preventing form submission. See [Client-side validation](#client-side_validation) for more information.

`multiple`  
The Boolean `multiple` attribute, if set, means the user can enter comma separated email addresses in the email widget or can choose more than one file with the `file` input. See the [email](input/email) and [file](input/file) input type.

`name`  
A string specifying a name for the input control. This name is submitted along with the control's value when the form data is submitted.

##### What's in a name

Consider the `name` a required attribute (even though it's not). If an input has no `name` specified, or `name` is empty, the input's value is not submitted with the form! (Disabled controls, unchecked radio buttons, unchecked checkboxes, and reset buttons are also not sent.)

There are two special cases:

1.  `_charset_` : If used as the name of an `<input>` element of type [hidden](input/hidden), the input's `value` is automatically set by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to the character encoding being used to submit the form.
2.  `isindex`: For historical reasons, the name `isindex` is not allowed.

##### name and radio buttons

The [`name`](#htmlattrdefname) attribute creates a unique behavior for radio buttons.

Only one radio button in a same-named group of radio buttons can be checked at a time. Selecting any radio button in that group automatically deselects any currently-selected radio button in the same group. The value of that one checked radio button is sent along with the name if the form is submitted,

When tabbing into a series of same-named group of radio buttons, if one is checked, that one will receive focus. If they aren't grouped together in source order, if one of the group is checked, tabbing into the group starts when the first one in the group is encountered, skipping all those that aren't checked. In other words, if one is checked, tabbing skips the unchecked radio buttons in the group. If none are checked, the radio button group receives focus when the first button in the same name group is reached.

Once one of the radio buttons in a group has focus, using the arrow keys will navigate through all the radio buttons of the same name, even if the radio buttons are not grouped together in the source order.

##### HTMLFormElement.elements

When an input element is given a `name`, that name becomes a property of the owning form element's [`HTMLFormElement.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements) property. If you have an input whose `name` is set to `guest` and another whose `name` is `hat-size`, the following code can be used:

    let form = document.querySelector("form");

    let guestName = form.elements.guest;
    let hatSize = form.elements["hat-size"];

When this code has run, `guestName` will be the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) for the `guest` field, and `hatSize` the object for the `hat-size` field.

**Warning:** Avoid giving form elements a `name` that corresponds to a built-in property of the form, since you would then override the predefined property or method with this reference to the corresponding input.

`pattern`  
The `pattern` attribute, when specified, is a regular expression that the input's [`value`](../global_attributes#attr-value) must match in order for the value to pass [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). It must be a valid JavaScript regular expression, as used by the [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) type, and as documented in our [guide on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions); the `'u'` flag is specified when compiling the regular expression, so that the pattern is treated as a sequence of Unicode code points, instead of as ASCII. No forward slashes should be specified around the pattern text.

If the `pattern` attribute is present but is not specified or is invalid, no regular expression is applied and this attribute is ignored completely. If the pattern attribute is valid and a non-empty value does not match the pattern, constraint validation will prevent form submission.

**Tip:** If using the `pattern` attribute, inform the user about the expected format by including explanatory text nearby. You can also include a [`title`](#attr-title) attribute to explain what the requirements are to match the pattern; most browsers will display this title as a tooltip. The visible explanation is required for accessibility. The tooltip is an enhancement.

See [Client-side validation](#client-side_validation) for more information.

`placeholder`  
The `placeholder` attribute is a string that provides a brief hint to the user as to what kind of information is expected in the field. It should be a word or short phrase that provides a hint as to the expected type of data, rather than an explanation or prompt. The text *must not* include carriage returns or line feeds. So for example if a field is expected to capture a user's first name, and its label is "First Name", a suitable placeholder might be "e.g. Mustafa".

**Note:** The `placeholder` attribute is not as semantically useful as other ways to explain your form, and can cause unexpected technical issues with your content. See [Labels](#Labels) in [&lt;input&gt;: The Input (Form Input) element](input) for more information.

`readonly`  
A Boolean attribute which, if present, indicates that the user should not be able to edit the value of the input. The `readonly` attribute is supported by the `text`, `search`, `url`, `tel`, `email`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, and `password` input types.

See the [HTML attribute: `readonly`](../attributes/readonly) for more information.

`required`  
`required` is a Boolean attribute which, if present, indicates that the user must specify a value for the input before the owning form can be submitted. The `required` attribute is supported by `text`, `search`, `url`, `tel`, `email`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, `password`, `checkbox`, `radio`, and `file` inputs.

See [Client-side validation](#client-side_validation) and the [HTML attribute: `required`](../attributes/required) for more information.

`size`  
Valid for `email`, `password`, `tel`, and `text` `input` types only. Specifies how much of the input is shown. Basically creates same result as setting CSS `width` property with a few specialities. The actual unit of the value depends on the input type. For `password` and `text`, it is a number of characters (or `em` units) with a default value of `20`, and for others, it is `pixel`s. CSS width takes precedence over size attribute.

`src`  
Valid for the `image` input button only, the `src` is string specifying the URL of the image file to display to represent the graphical submit button. See the [image](input/image) input type.

`step`  
Valid for the numeric input types, including `number`, date/time input types, and `range`, the `step` attribute is a number that specifies the granularity that the value must adhere to.

If not explicitly included:

-   `step` defaults to 1 for `number` and `range`.
-   For the date/time input types, `step` is expressed in seconds, with the **default step being 60 seconds**. The step scale factor is 1000 (which converts the seconds to milliseconds, as used in other algorithms).

The value must be a positive number—integer or float—or the special value `any`, which means no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

If `any` is not explicity set, valid values for the `number`, date/time input types, and `range` input types are equal to the basis for stepping — the `min` value and increments of the step value, up to the `max` value, if specified.

For example, if you have `<input type="number" min="10" step="2">`, then any even integer, `10` or greater, is valid. If omitted, `<input type="number">`, any integer is valid, but floats (like `4.2`) are not valid, because `step` defaults to `1`. For `4.2` to be valid, `step` would have had to be set to `any`, 0.1, 0.2, or any the `min` value would have had to be a number ending in `.2`, such as `<input type="number" min="-5.2">`

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the value is considered invalid in contraint validation and will match the `:invalid` pseudoclass.

See [Client-side validation](#client-side_validation) for more information.

`tabindex`  
Global attribute valid for all elements, including all the input types, an integer attribute indicating if the element can take input focus (is focusable), if it should participate to sequential keyboard navigation. As all input types except for input of type hidden are focusable, this attribute should not be used on form controls, because doing so would require the management of the focus order for all elements within the document with the risk of harming usability and accessibility if done incorrectly.

`title`  
Global attribute valid for all elements, including all input types, containing a text representing advisory information related to the element it belongs to. Such information can typically, but not necessarily, be presented to the user as a tooltip. The title should NOT be used as the primary explanation of the purpose of the form control. Instead, use the [`<label>`](label) element with a `for` attribute set to the form control's `id` attribute. See [Labels](#labels) below.

`type`  
A string specifying the type of control to render. For example, to create a checkbox, a value of `checkbox` is used. If omitted (or an unknown value is specified), the input type `text` is used, creating a plaintext input field.

Permitted values are listed in [Input types](#input_types) above.

`value`  
The input control's value. When specified in the HTML, this is the initial value, and from then on it can be altered or retrieved at any time using JavaScript to access the respective [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) object's `value` property. The `value` attribute is always optional, though should be considered mandatory for `checkbox`, `radio`, and `hidden`.

`width`  
Valid for the `image` input button only, the `width` is the width of the image file to display to represent the graphical submit button. See the [image](input/image) input type.

### Non-standard attributes

The following non-standard attributes are also available on some browsers. As a general rule, you should avoid using them unless it can't be helped.

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>autocorrect</code></td><td>A string indicating whether or not autocorrect is <code>on</code> or <code>off</code>. <strong>Safari only.</strong></td></tr><tr class="even"><td><code>incremental</code></td><td>Whether or not to send repeated <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/search_event"><code>search</code></a> events to allow updating live search results while the user is still editing the value of the field. <strong>WebKit and Blink only (Safari, Chrome, Opera, etc.).</strong></td></tr><tr class="odd"><td><code>mozactionhint</code></td><td>A string indicating the type of action that will be taken when the user presses the Enter or Return key while editing the field; this is used to determine an appropriate label for that key on a virtual keyboard. <strong>Firefox for Android only</strong>.</td></tr><tr class="even"><td><code>orient</code></td><td>Sets the orientation of the range slider. <strong>Firefox only</strong>.</td></tr><tr class="odd"><td><code>results</code></td><td>The maximum number of items that should be displayed in the drop-down list of previous search queries. <strong>Safari only.</strong></td></tr><tr class="even"><td><code>webkitdirectory</code></td><td>A Boolean indicating whether or not to only allow the user to choose a directory (or directories, if <code>multiple</code> is also present)</td></tr></tbody></table>

 `autocorrect` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
A Safari extension, the `autocorrect` attribute is a string which indicates whether or not to activate automatic correction while the user is editing this field. Permitted values are:

`on`  
Enable automatic correction of typos, as well as processing of text substitutions if any are configured.

`off`  
Disable automatic correction and text substitutions.

 `incremental` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The Boolean attribute `incremental` is a WebKit and Blink extension (so supported by Safari, Opera, Chrome, etc.) which, if present, tells the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to process the input as a live search. As the user edits the value of the field, the user agent sends `search` events to the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) object representing the search box. This allows your code to update the search results in real time as the user edits the search.

If `incremental` is not specified, the `search` event is only sent when the user explicitly initiates a search (such as by pressing the Enter or Return key while editing the field).

The `search` event is rate-limited so that it is not sent more frequently than an implementation-defined interval.

 `mozactionhint` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
A Mozilla extension, supported by Firefox for Android, which provides a hint as to what sort of action will be taken if the user presses the Enter or Return key while editing the field. This information is used to decide what kind of label to use on the Enter key on the virtual keyboard.

**Note:** This [has been standardized](https://html.spec.whatwg.org/#input-modalities:-the-enterkeyhint-attribute) as the global attribute [`enterkeyhint`](../global_attributes#attr-enterkeyhint), but is not yet widely implemented. To see the status of the change being implemented in Firefox, see [bug 1490661](https://bugzilla.mozilla.org/show_bug.cgi?id=1490661).

Permitted values are: `go`, `done`, `next`, `search`, and `send`. The browser decides, using this hint, what label to put on the enter key.

 `orient` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
[`<progress>`](progress)[`<meter>`](meter)`orient``horizontal``vertical`

 `results` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The `results` attribute—supported only by Safari—is a numeric value that lets you override the maximum number of entries to be displayed in the [`<input>`](input) element's natively-provided drop-down menu of previous search queries.

The value must be a non-negative decimal number. If not provided, or an invalid value is given, the browser's default maximum number of entries is used.

 `webkitdirectory` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The Boolean `webkitdirectory` attribute, if present, indicates that only directories should be available to be selected by the user in the file picker interface. See [`HTMLInputElement.webkitdirectory`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/webkitdirectory) for additional details and examples.

**Note:** Though originally implemented only for WebKit-based browsers, `webkitdirectory` is also usable in Microsoft Edge as well as Firefox 50 and later. However, even though it has relatively broad support, it is still not standard and should not be used unless you have no alternative.

Methods
-------

The following methods are provided by the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface which represents `<input>` elements in the DOM. Also available are those methods specified by the parent interfaces, [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement), [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element), [`Node`](https://developer.mozilla.org/en-US/docs/Web/API/Node), and [`EventTarget`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget).

<span class="page-not-created">`checkValidity()`</span>  
Immediately runs the validity check on the element, triggering the document to fire the [`invalid`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/invalid_event) event at the element if the value isn't valid.

[`reportValidity()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/reportValidity)  
Returns `true` if the element's value passes validity checks; otherwise, returns `false`.

[`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select)  
Selects the entire content of the `<input>` element, if the element's content is selectable. For elements with no selectable text content (such as a visual color picker or calendar date input), this method does nothing.

<span class="page-not-created">`setCustomValidity()`</span>  
Sets a custom message to display if the input element's value isn't valid.

[`setRangeText()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setRangeText)  
Sets the contents of the specified range of characters in the input element to a given string. A `selectMode` parameter is available to allow controlling how the existing content is affected.

[`setSelectionRange()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/setSelectionRange)  
Selects the specified range of characters within a textual input element. Does nothing for inputs which aren't presented as text input fields.

[`stepDown()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown)  
Decrements the value of a numeric input by one, by default, or by the specified number of units.

[`stepUp()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp)  
Increments the value of a numeric input by one or by the specified number of units.

CSS
---

Inputs, being replaced elements, have a few features not applicable to non form elements. There are CSS selectors that can specification target form controls based on their UI features, also known as UI pseudo-classes. The input element can also be targeted by type with attribute selectors. There are some properties that are especially useful as well.

### UI pseudo-classes

<table><caption>Captions super relevant to the <a href="input"><code>&lt;input&gt;</code></a> element:</caption><thead><tr class="header"><th>Pseudo-class</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:enabled"><code>:enabled</code></a></td><td>Any currently enabled element that can be activated (selected, clicked on, typed into, etc.) or accept focus and also has a disabled state, in which it can't be activated or accept focus.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:disabled"><code>:disabled</code></a></td><td>Any currently disabled element that has an enabled state, meaning it otherwise could be activated (selected, clicked on, typed into, etc.) or accept focus were it not disabled.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-only"><code>:read-only</code></a></td><td>Element not editable by the user</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write"><code>:read-write</code></a></td><td>Element that is editable by the user.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:placeholder-shown"><code>:placeholder-shown</code></a></td><td>Element that is currently displaying <a href="#attr-placeholder">placeholder text</a>, including <a href="input"><code>&lt;input&gt;</code></a> and <a href="textarea"><code>&lt;textarea&gt;</code></a> elements with the <a href="#htmlattrdefplaceholder">placeholder</a> attribute present that has, as of yet, no value.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:default"><code>:default</code></a></td><td>Form elements that are the default in a group of related elements. Matches <a href="input/checkbox">checkbox</a> and <a href="input/radio">radio</a> input types that were checked on page load or render.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:checked"><code>:checked</code></a></td><td>Matches <a href="input/checkbox">checkbox</a> and <a href="input/radio">radio</a> input types that are currently checked (and the (<a href="option"><code>&lt;option&gt;</code></a> in a <a href="select"><code>&lt;select&gt;</code></a> that is currently selected).</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate"><code>:indeterminate</code></a></td><td><a href="input/checkbox">checkbox</a> elements whose indeterminate property is set to true by JavaScript, <a href="input/radio">radio</a> elements, when all radio buttons with the same name value in the form are unchecked, and <a href="progress"><code>&lt;progress&gt;</code></a> elements in an indeterminate state</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:valid"><code>:valid</code></a></td><td>Form controls that can have constraint validation applied and are currently valid.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid"><code>:invalid</code></a></td><td>Form controls that have constraint validation applied and are currently not valid. Matches a form control whose value doesn't match the constraints set on it by it's attributes, such as <a href="#htmlattrdefrequired">required</a>, <a href="#htmlattrdefpattern">pattern</a> , <a href="#htmlattrdefstep">step</a> and <a href="#htmlattrdefmax">max</a>.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:in-range"><code>:in-range</code></a></td><td>A non-empty input whose current value is within the range limits specified by the <a href="#htmlattrdefmin">min</a> and <a href="#htmlattrdefmax">max</a> attributes and the <a href="#htmlattrdefstep">step</a> .</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range"><code>:out-of-range</code></a></td><td>A non-empty input whose current value is NOT within the range limits specified by the <a href="#htmlattrdefmin">min</a> and <a href="#htmlattrdefmax">max</a> attributes or does not adher to the <a href="#htmlattrdefstep">step</a> constraint.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:required"><code>:required</code></a></td><td><a href="input"><code>&lt;input&gt;</code></a>, <a href="select"><code>&lt;select&gt;</code></a>, or <a href="textarea"><code>&lt;textarea&gt;</code></a> element that has the <a href="#attr-required"><code>required</code></a> attribute set on it. Only matches elements that can be required. The attribute included on a non-requirable element will not make for a match.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:optional"><code>:optional</code></a></td><td><a href="input"><code>&lt;input&gt;</code></a>, <a href="select"><code>&lt;select&gt;</code></a>, or <a href="textarea"><code>&lt;textarea&gt;</code></a> element that does NOT have the <a href="#attr-required"><code>required</code></a> attribute set on it. Does not match elements that can't be required.</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:blank"><code>:blank</code></a></td><td><a href="input"><code>&lt;input&gt;</code></a> and <a href="textarea"><code>&lt;textarea&gt;</code></a> elements that currently have no value.</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid"><code>:user-invalid</code></a></td><td>Similar to <code>:invalid</code>, but is activated on blur. Matches invalid input but only after the user interaction, such as by focusing on the control, leaving the control, or attempting to submit the form containing the invalid control.</td></tr></tbody></table>

#### Examples

We can style a checkbox label based on whether the checkbox is checked or not. In this example, we are styling the [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) and [`font-weight`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) of the [`<label>`](label) that comes immediately after a checked input. We haven't applied any styles if the `input` is not checked.

    input:checked + label {
      color: red;
      font-weight: bold;
    }

### Attribute selectors

It is possible to target different types of form controls based on their [type](#htmlattrdeftype) using [attribute selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors). CSS attribute selectors match elements based on either just the presence of a attribute or the value of a given attribute.

    /* matches a password input */
    input[type="password"] {}

    /* matches a form control whose valid values are limited to a range of values*/
    input[min][max] {}

    /* matches a form control with a pattern attribute */
     input[pattern] {}

### ::placeholder

By default, the appearance of placeholder text is a translucent or light gray. The [`::placeholder`](https://developer.mozilla.org/en-US/docs/Web/CSS/::placeholder) pseudo-element is the input's [placeholder text](https://developer.mozilla.org/en-US/docs/Learn/Forms#the_placeholder_attribute). It can be styled with a limited subset of CSS properties.

    ::placeholder {
      color: blue;
    }

Only the subset of CSS properties that apply to the [`::first-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line) pseudo-element can be used in a rule using `::placeholder` in its selector.

### appearance

The [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) property enables the displaying of (almost) any element as a platform-native style based on the operating system's theme as well as the removal of any platform-native styling with the `none` value.

You could make a `<div>` look like a radio button with `div {appearance: radio;} `or a radio look like a checkbox with `[type="checkbox] {appearance: checkbox;}`, but don't.

Setting `appearance: none` removes platform native borders, but not functionality.

### caret-color

A property specific to text entry-related elements is the CSS [`caret-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/caret-color) property, which lets you set the color used to draw the text input caret:

#### HTML

    <label for="textInput">Note the red caret:</label>
    <input id="textInput" class="custom" size="32">

#### CSS

    input.custom {
      caret-color: red;
      font: 16px "Helvetica", "Arial", "sans-serif"
    }

#### Result

### object-position and object-fit

In certain cases (typically involving non-textual inputs and specialized interfaces), the `<input>` element is a [replaced element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element). When it is, the position and size of the element's size and positioning within its frame can be adjusted using the CSS [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) and [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) properties

### Styling

For more information about adding color to elements in HTML, see:

-   [Applying color to HTML elements using CSS](../applying_color).

Also see:

-   [Styling HTML forms,](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms) [advanced styling for HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling), and
-   the [compatibility table of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls).

Additional features
-------------------

### Labels

Labels are needed to associate assistive text with an `<input>`. The [`<label>`](label) element provides explanatory information about a form field that is *always* appropriate (aside from any layout concerns you have). It's never a bad idea to use a `<label>` to explain what should be entered into an `<input>` or [`<textarea>`](textarea).

#### Associated labels

The semantic pairing of `<input>` and `<label>` elements is useful for assistive technologies such as screen readers. By pairing them using the `<label>`'s [`for`](label#attr-for) attribute, you bond the label to the input in a way that lets screen readers describe inputs to users more precisely.

It does not suffice to have plain text adjacent to the `<input>` element,. Rather, usability and accessibility requires the inclusion of either implicit or explicit [`<label>`](label):

    <!-- inaccessible -->
    <p>Enter your name: <input id="name" type="text" size="30"></p>

    <!-- implicit label -->
    <p><label>Enter your name: <input id="name" type="text" size="30"></label></p>

    <!-- explicit label -->
    <p><label for="name">Enter your name: </label><input id="name" type="text" size="30"></p>

The first example is inaccessible: no relationship exists between the prompt and the `<input>` element.

In addition to an accessible name, the label provides a larger 'hit' area for mouse and touch screen users to click on or touch. By pairing a `<label>` with an `<input>`, clicking on either one will focus the `<input>`. If you use plain text to "label" your input, this won't happen. Having the prompt part of the activation area for the input is helpful for people with motor control conditions.

As web developers, it's important that we never assume that people will know all the things that we know. The diversity of people using the web—and by extension your web site—practically guarantees that some of your site's visitors will have some variation in thought processes and/or circumstances that leads them to interpret your forms very differently from you without clear and properly-presented labels.

#### Placeholders are not accessible

The [`placeholder`](#attr-placeholder) attribute lets you specify text that appears within the `<input>` element's content area itself when it is empty. The placeholder should never be required in order to understand your forms. It is not a label, and should not be used as a substitute, because it isn't. The placeholder is used to provide a hint as to what an inputted value should look like, not an explanation or prompt.

Not only is the placeholder not accessible to screen readers, but once the user enters any text into the form control, or if the form control already has a value, the placeholder disappears. Browsers with automatic page translation features may skip over attributes when translating, meaning the `placeholder` may not get translated.

Don't use the [`placeholder`](#attr-placeholder) attribute if you can avoid it. If you need to label an `<input>` element, use the [`<label>`](label) element.

### Client-side validation

**Warning:** Client-side validation is useful, but it does *not* guarantee that the server will receive valid data. If the data must be in a specific format, *always* verify it also on the server-side, and return a [`400` HTTP response](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/400) if the format is invalid.

In addition to using CSS to style inputs based on the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) or [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) UI states based on the current state of each input, as noted in the [UI pseudo-classes](#ui_pseudo-classes) section above, the browser provides for client-side validation on (attempted) form submission. On form submission, if there is a form control that fails constraint validation, supporting browsers will display an error message on the first invalid form control; displaying a default message based on the error type, or a message set by you.

Some input types and other attributes place limits on what values are valid for a given input. For example, `<input type="number" min="2" max="10" step="2">` means only the number 2, 4, 6, 8, or 10 are valid. Several errors could occur, including a `rangeUnderflow` error if the value is less than 2, `rangeOverflow` if greater than 10, `stepMismatch` if the value is a number between 2 and 10, but not an even integer (does not match the requirements of the `step` attribute), or `typeMismatch` if the value is not a number.

For the input types whose domain of possible values is periodic (that is, at the highest possible value, the values wrap back around to the beginning rather than ending), it's possible for the values of the [`max`](../global_attributes#attr-max) and [`min`](../global_attributes#attr-min) properties to be reversed, which indicates that the range of permitted values starts at `min`, wraps around to the lowest possible value, then continues on until `max` is reached. This is particularly useful for dates and times, such as when you want to allow the range to be from 8 PM to 8 AM:

    <input type="time" min="20:00" max="08:00" name="overnight">

Specific attributes and their values can lead to a specific error [`ValidityState`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState):

<table><caption>Validity object errors depend on the <a href="input"><code>&lt;input&gt;</code></a> attributes and their values:</caption><thead><tr class="header"><th>Attribute</th><th>Relevant property</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><a href="#htmlattrdefmax">max</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow"><code>validityState.rangeOverflow</code></a></td><td>Occurs when the value is greater than the maximum value as defined by the <code>max</code> attribute</td></tr><tr class="even"><td><a href="#htmlattrdefmaxlength">maxlength</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong"><code>validityState.tooLong</code></a></td><td>Occurs when the number of characters is greater than the number allowed by the <code>maxlength</code> property</td></tr><tr class="odd"><td><a href="#htmlattrdefmin">min</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow"><code>validityState.rangeUnderflow</code></a></td><td>Occurs when the value is less than the minimum value as defined by the <code>min</code> attribute</td></tr><tr class="even"><td><a href="#htmlattrdefminlength">minlength</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort"><code>validityState.tooShort</code></a></td><td>Occurs when the number of characters is less than the number required by the <code>minlength</code> property</td></tr><tr class="odd"><td><a href="#htmlattrdefpattern">pattern</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch"><code>validityState.patternMismatch</code></a></td><td>Occurs when a pattern attribute is included with a valid regular expression and the <code>value</code> does not match it.</td></tr><tr class="even"><td><a href="#htmlattrdefrequired">required</a></td><td><span class="page-not-created"><code>validityState.valueMissing</code></span></td><td>Occurs when the <code>required</code> attribute is present but the value is <code>null</code> or radio or checkbox is not checked.</td></tr><tr class="odd"><td><a href="#htmlattrdefstep">step</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch"><code>validityState.stepMismatch</code></a></td><td>The value doesn't match the step increment. Increment default is <code>1</code>, so only integers are valid on<code> type="number"</code> is step is not included. <code>step="any"</code> will never throw this error.</td></tr><tr class="even"><td><a href="#htmlattrdeftyoe">type</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch"><code>validityState.typeMismatch</code></a></td><td>Occurs when the value is not of the correct type, for example a email does not contain an <code>@</code> or a url doesn't contain a protocol.</td></tr></tbody></table>

If a form control doesn't have the `required` attribute, no value, or an empty string, is not invalid. Even if the above attributes are present, with the exception of `required`, and empty string will not lead to an error.

We can set limits on what values we accept, and supporting browsers will natively validate these form values and alert the user if there is a mistake when the form is submitted.

In addition to the errors described in the table above, the `validityState` interface contains the `badInput`, `valid`, and `customError` boolean readonly properties. The validity object includes:

-   <span class="page-not-created">`validityState.valueMissing`</span>
-   [`validityState.typeMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/typeMismatch)
-   [`validityState.patternMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/patternMismatch)
-   [`validityState.tooLong`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooLong)
-   [`validityState.tooShort`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/tooShort)
-   [`validityState.rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)
-   [`validityState.rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow)
-   [`validityState.stepMismatch`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/stepMismatch)
-   [`validityState.badInput`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/badInput)
-   <span class="page-not-created">`validityState.valid`</span>
-   <span class="page-not-created">`validityState.customError`</span>

For each of these Boolean properties, a value of `true` indicates that the specified reason validation may have failed is true, with the exception of the `valid` property, which is `true` if the element's value obeys all constraints.

If there is an error, supporting browsers will both alert the user and prevent the form from being submitted. A word of caution: if a custom error is set to a truthy value (anything other than the empty string or `null`), the form will be prevented from being submitted. If there is no custom error message, and none of the other properties return true, `valid` will be true, and the form can be submitted.

    function validate(input) {
      let validityState_object = input.validity;
      if(validityState_object.valueMissing) {
         input.setCustomValidity('A value is required');
      } else if (input.rangeUnderflow) {
        input.setCustomValidity('Your value is too low');
      } else if (input.rangeOverflow) {
        input.setCustomValidity('Your value is too high');
      } else {
        input.setCustomValidity('');
      }
    }

The last line, setting the custom validity message to the error string is vital. If the user makes an error, and the validity is set, it will fail to submit, even if all of the values are valid, until the message is `null`.

#### Example

If you want to present a custom error message when a field fails to validate, you need to use the [Constraint validation features](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation#constraint_validation_interfaces) available on `<input>` (and related) elements. Take the following form:

    <form>
      <label for="name">Enter username (upper and lowercase letters): </label>
      <input type="text" name="name" id="name" required pattern="[A-Za-z]+">
      <button>Submit</button>
    </form>

The basic HTML form validation features will cause this to produce a default error message if you try to submit the form with either no valid filled in, or a value that does not match the `pattern`.

If you wanted to instead display custom error messages, you could use JavaScript like the following:

    const nameInput = document.querySelector('input');
    const form = document.querySelector('form');

    nameInput.addEventListener('input', () => {
      nameInput.setCustomValidity('');
      nameInput.checkValidity();
    });

    nameInput.addEventListener('invalid', () => {
      if(nameInput.value === '') {
        nameInput.setCustomValidity('Enter your username!');
      } else {
        nameInput.setCustomValidity('Usernames can only contain upper and lowercase letters. Try again!');
      }
    });

The example renders like so:

In brief:

-   We check the valid state of the input element every time its value is changed by running the `checkValidity()` method via the `input` event handler.
-   If the value is invalid, an `invalid` event is raised, and the `invalid` event handler function is run. Inside this function we work out whether the value is invalid because it is empty, or because it doesn't match the pattern, using an `if()` block, and set a custom validity error message.
-   As a result, if the input value is invalid when the submit button is pressed, one of the custom error messages will be shown.
-   If it is valid, it will submit as you'd expect. For this to happen, the custom validity has to be cancelled, by invoking `setCustomValidity()` with an empty string value. We therefore do this every time the `input` event is raised. If you don't do this, and a custom validity was previously set, the input will register as invalid, even if it current contains a valid value on submission.

**Note:** Always validate input constraints both client side and server side. Constraint validation doesn't remove the need for validation on the *server side*. Invalid values can still be sent by older browsers or by bad actors.

**Note**: Firefox supported a proprietary error attribute — `x-moz-errormessage` — for many versions, which allowed you set custom error messages in a similar way. This has been removed as of version 66 (see [bug 1513890](https://bugzilla.mozilla.org/show_bug.cgi?id=1513890)).

### Localization

The allowed inputs for certain `<input>` types depend on the locale. In some locales, 1,000.00 is a valid number, while in other locales the valid way to enter this number is 1.000,00.

Firefox uses the following heuristics to determine the locale to validate the user's input (at least for `type="number"`):

-   Try the language specified by a `lang`/`xml:lang` attribute on the element or any of its parents.
-   Try the language specified by any `Content-Language` HTTP header. Or,
-   If none specified, use the browser's locale.

### Technical summary

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, listed, submittable, resettable, form-associated element, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>. If the <a href="#attr-type"><code>type</code></a> is not <code>hidden</code>, then labelable element, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag and must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><ul><li><code>type=button</code>: <code>button</code></li><li><code>type=checkbox</code>: <code>checkbox</code></li><li><code>type=email</code><ul><li>with no <code>list</code> attribute: <code>textbox</code></li><li>with <code>list</code> attribute: <code>combobox</code></li></ul></li><li><code>type=image</code>: <code>button</code></li><li><code>type=number</code>: <code>spinbutton</code></li><li><code>type=radio</code>: <code>radio</code></li><li><code>type=range</code>: <code>slider</code></li><li><code>type=reset</code>: <code>button</code></li><li><code>type=search</code><ul><li>with no <code>list</code> attribute: <code>searchbox</code></li><li>with <code>list</code> attribute: <code>combobox</code></li></ul></li><li><code>type=submit</code>: <code>button</code></li><li><code>type=tel</code><ul><li>with no <code>list</code> attribute: <code>textbox</code></li><li>with <code>list</code> attribute: <code>combobox</code></li></ul></li><li><code>type=text</code><ul><li>with no <code>list</code> attribute: <code>textbox</code></li><li>with <code>list</code> attribute: <code>combobox</code></li></ul></li><li><code>type=url</code><ul><li>with no <code>list</code> attribute: <code>textbox</code></li><li>with <code>list</code> attribute: <code>combobox</code></li></ul></li><li><code>type=color|date|datetime-local|file|hidden|month|password|time|week</code>: <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">no corresponding role</a></li></ul></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><ul><li><code>type=button</code>: <code>link</code>, <code>menuitem</code>, <code>menuitemcheckbox</code>, <code>menuitemradio</code>, <code>option</code>, <code>radio</code>, <code>switch</code>, <code>tab</code></li><li><code>type=checkbox</code>: <code>button</code> when used with <code>aria-pressed</code>, <code>menuitemcheckbox</code>, <code>option</code>, <code>switch</code></li><li><code>type=image</code>: <code>link</code>, <code>menuitem</code>, <code>menuitemcheckbox</code>, <code>menuitemradio</code>, <code>radio</code>, <code>switch</code></li><li><code>type=radio</code>: <code>menuitemradio</code></li><li><code>type=text</code> with no <code>list</code> attribute: <code>combobox</code>, <code>searchbox</code>, <code>spinbutton</code></li><li><code>type=color|date|datetime|datetime-local|email|file|hidden|month|number|password|range|reset|search|submit|tel|url|week</code> or <code>text</code> with <code>list</code> attribute: no <code>role</code> permitted</li></ul></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement"><code>HTMLInputElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#the-input-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;input&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/html-media-capture/#the-capture-attribute">HTML Media Capture<br />
<span class="small">The definition of 'capture attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <code>capture</code> attribute</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#the-input-element">HTML5<br />
<span class="small">The definition of '&lt;input&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/interact/forms.html#h-17.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;form&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Accessibility concerns
----------------------

### Labels

When including inputs, it is an accessibility requirement to add labels along side. This is needed so those who use assistive technologies can tell what the input is for. Also, clicking or touching a label gives focus to the label's associated form control. This improves the accessibility and usability for sighted users, increases the area a user can click or touch to activate the form control. This is especially useful (and even needed) for radio buttons and checkboxes, which are tiny. For more information about labels in general see [Labels](#labels) .

The following is an example of how to associate the `<label>` with an `<input>` element in the above style. You need to give the `<input>` an `id` attribute. The `<label>` then needs a `for` attribute whose value is the same as the input's `id`.

    <label for="peas">Do you like peas?</label>
    <input type="checkbox" name="peas" id="peas">

### Size

Interactive elements such as form input should provide an area large enough that it is easy to activate them. This helps a variety of people, including people with motor control issues and people using non-precise forms of input such as a stylus or fingers. A minimum interactive size of 44×44 [CSS pixels](https://www.w3.org/TR/WCAG21/#dfn-css-pixels) is recommended.

-   [Understanding Success Criterion 2.5.5: Target Size | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/target-size.html)
-   [Target Size and 2.5.5 | Adrian Roselli](https://adrianroselli.com/2019/06/target-size-and-2-5-5.html)
-   [Quick test: Large touch targets - The A11Y Project](https://a11yproject.com/posts/large-touch-targets/)

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

`input-button`

1

12

1

Yes

Yes

1

Yes

18

4

Yes

Yes

1.0

`input-checkbox`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`input-color`

20

14

29

No

12

12.1

4.4

25

27

Firefox for Android doesn't allow the user to choose a custom color, only one of the predefined ones.

12

12.2

1.5

`input-date`

20

12

57

No

11

14.1

Yes

Yes

57

11

5

Yes

`input-datetime-local`

20

12

No

See [bug 888320](https://bugzil.la/888320) and [TPE DOM/Date time input types](https://wiki.mozilla.org/TPE_DOM/Date_time_input_types).

No

11

14.1

Yes

Yes

Yes

11

Yes

Yes

`input-email`

5

12

Yes

10

11

Yes

?

?

4

Yes

3.1

\["Doesn't do validation, but instead offers a custom 'email' keyboard, which is designed to make entering email addresses easier.", "The custom 'email' keyboard does not provide a comma key, so users cannot enter multiple email addresses.", "Automatically applies a default style of `opacity: 0.4` to disable textual `<input>` elements, including those of type 'email'. Other major browsers don't currently share this particular default style."\]

?

`input-file`

1

12

1

You can set as well as get the value of `HTMLInputElement.files` in all modern browsers; this was most recently added to Firefox, in version 57 (see [bug 1384030](https://bugzil.la/1384030)).

Yes

11

1

Yes

Yes

4

11

Yes

Yes

`input-hidden`

1

12

1

Yes

2

1

Yes

Yes

4

Yes

Yes

Yes

`input-image`

Yes

12

Yes

Yes

Yes

Yes

Yes

?

Yes

Yes

Yes

?

`input`

Yes

12

1

Yes

Yes

1

1

Yes

4

Yes

1

Yes

`align`

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

`usemap`

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

`x-moz-errormessage`

No

No

Yes-66

No

No

No

No

No

Yes-66

No

No

No

`input-month`

20

12

No

See [bug 888320](https://bugzil.la/888320).

No

11

No

The input type is recognized, but there is no month-specific control. See [bug 200416](https://webkit.org/b/200416).

Yes

Yes

No

Yes

Yes

Yes

`input-number`

Yes

12

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`input-password`

1

12

1

2

2

1

?

Yes

4

Yes

Yes

Yes

`input-radio`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`input-range`

4

12

23

10

11

3.1

4.4

2-4.4

Pre-Chromium Android WebView recognizes the `range` type, but doesn't implement a range-specific control.

57

52

Yes

5.1

7.0

`input-reset`

1

12

1

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a `<button>` across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

1

Yes

Yes

4

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a `<button>` across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

Yes

`input-search`

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

`input-submit`

1

12

1

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

1

Yes

Yes

4

Unlike other browsers, Firefox by default [persists the dynamic disabled state](http://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing) of a across page loads. Use the `autocomplete` attribute to control this feature.

Yes

Yes

Yes

`input-tel`

3

The field type doesn't demonstrate any special behavior.

12

Yes

10

11

4

The field type doesn't demonstrate any special behavior.

≤37

18

Yes

11

3

1.0

`input-text`

1

12

1

Yes

Yes

1

Yes

Yes

4

Yes

Yes

Yes

`input-time`

20

12

57

No

10

14.1

Yes

25

57

Yes

Yes

1.5

`input-url`

1

12

Yes

10

11

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`input-week`

20

12

No

See [bug 888320](https://bugzil.la/888320).

No

11

No

See [bug 200416](https://webkit.org/b/200416).

Yes

Yes

Yes

Yes

No

See [bug 200416](https://webkit.org/b/200416).

Yes

See also
--------

-   [Form constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation)
-   [Your first HTML form](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form)
-   [How to structure an HTML form](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form)
-   [The native form widgets](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls)
-   [Sending form data](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data)
-   [Form data validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)
-   [How to build custom form widgets](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_build_custom_form_controls)
-   [HTML forms in legacy browsers](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML_forms_in_legacy_browsers)
-   [Styling HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
-   [Advanced styling for HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Advanced_form_styling)
-   [CSS property compatibility table](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input</a>
