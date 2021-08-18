&lt;input type="range"&gt;
==========================

[`<input>`](../input) elements of type `range` let the user specify a numeric value which must be no less than a given value, and no more than another given value. The precise value, however, is not considered important. This is typically represented using a slider or dial control rather than a text entry box like the [number](number) input type. Because this kind of widget is imprecise, it shouldn't typically be used unless the control's exact value isn't important.

If the user's browser doesn't support type `range`, it will fall back and treat it as a `text` input.

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> containing the string representation of the selected numeric value; use <span class="page-not-created"><code>valueAsNumber</code></span> to get the value as a <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number"><code>Number</code></a>.</td></tr><tr class="even"><td><strong>Events</strong></td><td><code>change</code> and <code>input</code></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-max"><code>max</code></a>, <a href="../input#attr-min"><code>min</code></a>, and <a href="../input#attr-step"><code>step</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>list</code>, <code>value</code>, and <code>valueAsNumber</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown"><code>stepDown()</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp"><code>stepUp()</code></a></td></tr></tbody></table>

### Validation

There is no pattern validation available; however, the following forms of automatic validation are performed:

-   If the [`value`](../input#attr-value) is set to something which can't be converted into a valid floating-point number, validation fails because the input is suffering from a bad input.
-   The value won't be less than [`min`](../input#attr-min). The default is 0.
-   The value won't be greater than [`max`](../input#attr-max). The default is 100.
-   The value will be a multiple of [`step`](../input#attr-step). The default is 1.

### Value

The [`value`](../input#attr-value) attribute contains a [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) which contains a string representation of the selected number. The value is never an empty string (`""`). The default value is halfway between the specified minimum and maximum—unless the maximum is actually less than the minimum, in which case the default is set to the value of the `min` attribute. The algorithm for determining the default value is:

    defaultValue = (rangeElem.max < rangeElem.min) ? rangeElem.min
                   : rangeElem.min + (rangeElem.max - rangeElem.min)/2;

If an attempt is made to set the value lower than the minimum, it is set to the minimum. Similarly, an attempt to set the value higher than the maximum results in it being set to the maximum.

Additional attributes
---------------------

In addition to the attributes shared by all [`<input>`](../input) elements, range inputs offer the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The id of the &lt;datalist&gt; element that contains optional pre-defined options</td></tr><tr class="even"><td><code>max</code></td><td>The maximum permitted value</td></tr><tr class="odd"><td><code>min</code></td><td>The minimum permitted value</td></tr><tr class="even"><td><code>step</code></td><td>The stepping interval, used both for user interface and validation purposes</td></tr></tbody></table>

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

See the [range control with hash marks](#a_range_control_with_hash_marks) below for an example of how the options on a range are denoted in supported browsers

### `max`

The greatest value in the range of permitted values. If the [`value`](../input#attr-value) entered into the element exceeds this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `max` attribute isn't a number, then the element has no maximum value.

This value must be greater than or equal to the value of the `min` attribute. See the HTML [`max`](../../attributes/max) attribute.

### `min`

The lowest value in the range of permitted values. If the [`value`](../input#attr-value) of the element is less than this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If a value is specified for `min` that isn't a valid number, the input has no minimum value.

This value must be less than or equal to the value of the `max` attribute. See the [HTML `min `attribute.](../../attributes/min)

### `step`

The `step` attribute is a number that specifies the granularity that the value must adhere to, or the special value `any`, which is described below. Only values which are equal to the basis for stepping (`min` if specified, [`value`](../input#attr-value) otherwise, and an appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may round to the nearest valid value, preferring numbers in the positive direction when there are two equally close options.

The default stepping value for `range` inputs is 1, allowing only integers to be entered, *unless* the stepping base is not an integer; for example, if you set `min` to -10 and `value` to 1.5, then a `step` of 1 will allow only values such as 1.5, 2.5, 3.5,... in the positive direction and -0.5, -1.5, -2.5,... in the negative direction. See the [HTML `step` attribute](../../attributes/step).

### Non Standard Attributes

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>attr-orient</code></td><td>Sets the orientation of the range slider. <strong>Firefox only.</strong></td></tr></tbody></table>

 `orient` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Similar to the -moz-orient non-standard CSS property impacting the [`<progress>`](../progress) and [`<meter>`](../meter) elements, the `orient` attribute defines the orientation of the range slider. Values include `horizontal`, meaning the range is rendered horizontally, and `vertical`, where the range is rendered vertically.

Note: The following input attributes do not apply to the input range: `accept`, `alt`, `checked`, `dirname`, `formaction`, `formenctype`, `formmethod`, `formnovalidate`, `formtarget`, `height`, `maxlength`, `minlength`, `multiple`, `pattern`, `placeholder`, `readonly`, `required`, `size`, `src`, and `width`. Any of these attributes, if included, will be ignored.

Examples
--------

While the `number` type lets users enter a number with optional constraints forcing their value to be between a minimum and a maximum value, it does require that they enter a specific value. The `range` input type lets you ask the user for a value in cases where the user may not even care—or know—what the specific numeric value selected is.

A few examples of situations in which range inputs are commonly used:

-   Audio controls such as volume and balance, or filter controls.
-   Color configuration controls such as color channels, transparency, brightness, etc.
-   Game configuration controls such as difficulty, visibility distance, world size, and so forth.
-   Password length for a password manager's generated passwords.

As a rule, if the user is more likely to be interested in the percentage of the distance between minimum and maximum values than the actual number itself, a range input is a great candidate. For example, in the case of a home stereo volume control, users typically think "set volume at halfway to maximum" instead of "set volume to 0.5".

### Specifying the minimum and maximum

By default, the minimum is 0 and the maximum is 100. If that's not what you want, you can easily specify different bounds by changing the values of the [`min`](../input#attr-min) and/or [`max`](../input#attr-max) attributes. These can be any floating-point value.

For example, to ask the user for a value between -10 and 10, you can use:

    <input type="range" min="-10" max="10">

### Setting the value's granularity

By default, the granularity, is 1, meaning that the value is always an integer. You can change the [`step`](../../global_attributes#attr-step) attribute to control the granularity. For example, If you need a value between 5 and 10, accurate to two decimal places, you should set the value of `step` to 0.01:

    <input type="range" min="5" max="10" step="0.01">

If you want to accept any value regardless of how many decimal places it extends to, you can specify a value of `any` for the [`step`](../input#attr-step) attribute:

    <input type="range" min="0" max="3.14" step="any">

This example lets the user select any value between 0 and π without any restriction on the fractional part of the value selected.

### Adding hash marks and labels

The HTML specification gives browsers some flexibility on how to present the range control. Nowhere is this flexibility more apparent than in the area of hash marks and, to a lesser degree, labels. The specification describes how to add custom points to the range control using the [`list`](../input#attr-list) attribute and a [`<datalist>`](../datalist) element, but does not have any requirements or even recommendations for standardized hash or tick marks along the length of the control.

#### Range control mockups

Since browsers have this flexibility, and to date none support all of the features HTML defines for range controls, here are some mockups to show you what you might get on macOS in a browser which supports them.

##### An unadorned range control

This is what you get if you don't specify a [`list`](../input#attr-list) attribute, or if the browser doesn't support it.

HTML

Examples

    <input type="range">

Screenshot

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAALgAAAAcCAMAAADlYIUNAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAA/UExURe3t7djY2M3NzdPT0+vr69/f3+Xl5TuZ/P///7i4uPPz87+/v/7+/sXFxTyZ+jKB1pycnIKy57S0tOPs9a+vrxERjQAAAACySURBVFjD7da7DoMwDAXQ+EnIo7S0//+tRaUVpFMGGIx8tizRleU4DsE55z5YABFB2FhuReFUEguqqdwCHFcMYqnekOJPAjs1Z+S4WU52GiXu2WkW0Ca4wsH3P27DOaZnEzzcxx7UHfys3MNUmuClL3i+fsVPQ389TmamCjXBycxU4bwvuWY7+4rU7QfiaunPpyrf3FIpWAIjyrIdCo4QbFHM82vOxrba9YmqKgfn3DW9ARgwEq47uxhyAAAAAElFTkSuQmCC" alt="Screenshot of a plain slider control on macOS" width="184" height="28" />

Live

##### A range control with hash marks

This range control is using a `list` attribute specifying the ID of a [`<datalist>`](../datalist) which defines a series of hash marks on the control. There are eleven of them, so that there's one at 0% as well as at each 10% mark. Each point is represented using an [`<option>`](../option) element with its [`value`](../option#attr-value) set to the range's value at which a mark should be drawn.

HTML

Examples

    <input type="range" list="tickmarks">

    <datalist id="tickmarks">
      <option value="0"></option>
      <option value="10"></option>
      <option value="20"></option>
      <option value="30"></option>
      <option value="40"></option>
      <option value="50"></option>
      <option value="60"></option>
      <option value="70"></option>
      <option value="80"></option>
      <option value="90"></option>
      <option value="100"></option>
    </datalist>

Screenshot

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAALgAAAAcCAMAAADlYIUNAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAA5UExURe3t7a6urtTU1Orq6p+fn+bm5ru7u7i4uP///5eXl+Li4tzc3MnJycPDw5qams7OzsbGxvn5+Y6OjoRxXNMAAADASURBVFjD7dXBDoMgEEVROjg4DpjB/v/Htk0XgittJfqidyULyNGAOHd3d926PQd/L7ahYc9B+cxP3r7YCeCaKGlLeKOtwtmJy9xwq7SJkxcRnxjsxHNS+aRgcrYo36Ihyb2RCKDck8mckUeBa5Ky8qd47ogrONPe64e+Td1UwaduzaSw/vVauftB6oZVs8LxX/wneKDj9/i4gI8ohxMWnhfwjAI3rdxqKPCYS7nmiHPlh8dcwLny33SeA2LfAfcC49ET62URHmEAAAAASUVORK5CYII=" alt="Screenshot of a plain slider control on macOS" width="184" height="28" />

Live

##### A range control with hash marks and labels

You can add labels to your range control by adding the [`label`](../option#attr-label) attribute to the [`<option>`](../option) elements corresponding to the tick marks you wish to have labels for.

HTML

Examples

    <input type="range" list="tickmarks">

    <datalist id="tickmarks">
      <option value="0" label="0%"></option>
      <option value="10"></option>
      <option value="20"></option>
      <option value="30"></option>
      <option value="40"></option>
      <option value="50" label="50%"></option>
      <option value="60"></option>
      <option value="70"></option>
      <option value="80"></option>
      <option value="90"></option>
      <option value="100" label="100%"></option>
    </datalist>

Screenshot

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAALgAAAAsCAMAAADhGoKgAAACFlBMVEXt7e3j7e2tra26urqXl5efn5/n5+e4uLj///8kJCTt7ebt7eHt7erh4eK8vLzS0tJ+IyHGxsbLy8vV1NXs7O3j4+Pq6erq6urf5ezm7e2x2e3F5e7q7e3t5sPi4ODZ1tZYIlieSB3OnFEjHpDt6uNEj8PDw8PPz8/o6OjIyMjl5eXky5NkIyIkIlgjHZnt68bFkUEddLDt4cLg7e1YJCMjH4bc3N3kxpPiyaKHsNHpzJrO5+4iRpft48ltIyJwq9La7e12IyKxdha23O6QxuXX2dvg3t6XSB7kypnT6+0gVZ7t69Dt7dfKnmUjIH+s1OCsbBgahbscfLuo0OgjIWvjzatzr9dEkca+vr6wsLCdnZ35+fl7s9vu7u7jxY3YsXGOweCrdhfIx6Tt6urq4+Dcv5+4fhNJJCOaydx/uN/jz7XZ3Obc1c1Vg7fEp3KOVx3MqXofZpXs2rB7pcrt5se2y8POlEjA4+6iVxy24u6ibRnmwobSrGeIt8iOjo7q3MTl6u3i4uZVibt+SB9Um8fGilJUlcsfYaMhRZ5IIWTauoBgpc91fWK40eu6hEKIwd3V1q6sfkNEj7+bsMrt49BJI0lFg7YdfK3FxckiSFhgoM/OsI6SIkeDpr5YH4bq57/t47sgVaOYIyDA4O7Y7eCdVxyximCRR0dtSCBVg6ckI0mgwcpFfLLr0am84NzQ48zE6u21kGmVmpcPAAAC+klEQVRYw+2W91MaQRSA30WjtxyEjqAEFFTkhFghdtEYe++9xZrYYuJEjSaa3nvvvdf/MHuCgzCTyR6RcW7mvh/23d3MW75793YeACIiIgJiRK3Hazm3HNKEvo3UfJBb3QaeeYnmI/6Q6DbiVUeUOIoQaoE69KUFMh0T/IUrcT4qg9plhB5SzDJy5UMlWebhomoKMosQOga+gNdvBqjDj/9NTUkuzLnefVyydEgWO0Ko9P5pYwxrhBVXVaGi99WLrISyNAdRYh66Vk1JG5sMbeiAL5xsTov/lec8QVQwlwfSshsqVoeKV6yeEMTr7kw90gPzvhfAkvEyfkHR0JhEVvDrefuovdmxIEko9oX+guH6nyWDZAUroICpGGz79HmY7E2DsaDH2a1vmYoygH5r1tPx5zMFWaQfC4vHxwGkJ/kC87v161ASkIu/wS9Zq1j9gHL5i4/eBUlpx6Y4wLxzYZYwNTVYHD8bsA47juaTdFp9FW6VFpAMNaW+vtWaz9dbM6XneoRZbOeCEZ+Zm5Zz5OLHHVyPtPsCwHf0I2Fi7CpBcq2iGGZwcw+4PPhoXI7jXfGxi557s09goD4us2QSpKXNcH6SXFxamkHl4MPpDVCj6GWeLaVfIMnOGUfOBpi/HwuFCnTGyFv89FmE8LdlbiM0bYAr1irIQaTilyjuR7kG9QbpjQdGmEPOWLIJYFrDg4O7kqyHNHpM3jSTjBthGzvyyZaY9P6wMQBH1sR/BSIifnZv581/b8aDyO282XKtYU+xGt6b7by4RqtSq7SaMIqHqVVYZR/dp2TD2CrhgbXraJrW2VmBnXhWpaU5ZCphmUepymkv5aooAXmnyM30JmZ5imC8Y8w22o/NHCMUcZmd3opdJhRxNRsgzqq3eX95RHR46O4JEO/pJkmKkBOLh8s7OpIOJJIoa8/OVzwkcR4VDxvJQeLJQjmcghVXBokrhSJu0wZ4a21CEXcrZVu8ZUq3YEa+urNr1yZdnWrBjHwAHetHByIiIn/lD/JakW8Cw3ZoAAAAAElFTkSuQmCC" alt="Screenshot of a plain slider control on macOS" width="184" height="44" />

Live

**Note**: Currently, no browser fully supports these features. Firefox doesn't support hash marks and labels at all, for example, while Chrome supports hash marks but doesn't support labels. Version 66 (66.0.3359.181) of Chrome supports labels but the [`<datalist>`](../datalist) tag has to be styled with CSS as its [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property is set to `none` by default, hiding the labels.

### Change the orientation

By default, if a browser renders a range input as a slider, it will render it so that the knob slides left and right. When supported, we will be able to make the range vertical, to slide up and down with CSS by declaring a height value greater than the width value. This is not actually implemented yet by any of the major browsers. (See Firefox [bug 981916](https://bugzilla.mozilla.org/show_bug.cgi?id=981916), [Chrome bug 341071](https://bugs.chromium.org/p/chromium/issues/detail?id=341071)). It also, perhaps, may still be [under discussion](https://github.com/whatwg/html/issues/4177).

In the meantime, we can make the range vertical by rotating it using CSS transforms, or, by targeting each browser engine with their own method, which includes setting the [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) to `slider-vertical`, by using a non-standard `orient` attribute in Firefox, or by changing the text direction for Internet Explorer and Edge.

Consider this range control:

    <input type="range" id="volume" min="0" max="11" value="7" step="1">

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMgAAADIBAMAAABfdrOtAAAAHlBMVEX////Hx8fl5eXw8PD29vbc3Nz9/f3Q0NCsrKzAwMAvuntVAAAA0ElEQVR42u3VvWrCUBgG4ODfniyurVqylqC7g91LaXfBFC9AO3Qspd6Dd6vlRFwEg/htzzOcDDnw8p4vh2QZQVZPH+NlcEbvbVpX78Eh1fNpCSwyOa9hPlOHWehUqvTo3Hheg8e8hb+0uf9z6WVxPaVNRv6b9nYvhuTXQ1o12TW1b23Syrb5yF4jBz9qBv8QGTJrBh95GwfrVKEMvSfdzXmNq1L+VylDR3Ic+XBSl0UW7OV7/zUP/2vVi2UGAAAAAAAAAAAAAAAAAAAAAAB3cgAZeRxEuc3EXQAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

This control is horizontal (at least on most if not all major browsers; others might vary).

### Standards

According to the specification, making it vertical requires adding CSS to change the dimensions of the control so that it's taller than it is wide, like this:

#### CSS

    #volume {
      height: 150px;
      width: 50px;
    }

#### HTML

    <input type="range" id="volume" min="0" max="11" value="7" step="1">

#### Result

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMgAAADIBAMAAABfdrOtAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAQkaVRYdFhNTDpjb20uYWRvYmUueG1wAAAAAAA8eDp4bXBtZXRhIHhtbG5zOng9ImFkb2JlOm5zOm1ldGEvIiB4OnhtcHRrPSJYTVAgQ29yZSA1LjQuMCI+CiAgIDxyZGY6UkRGIHhtbG5zOnJkZj0iaHR0cDovL3d3dy53My5vcmcvMTk5OS8wMi8yMi1yZGYtc3ludGF4LW5zIyI+CiAgICAgIDxyZGY6RGVzY3JpcHRpb24gcmRmOmFib3V0PSIiCiAgICAgICAgICAgIHhtbG5zOnRpZmY9Imh0dHA6Ly9ucy5hZG9iZS5jb20vdGlmZi8xLjAvIgogICAgICAgICAgICB4bWxuczpleGlmPSJodHRwOi8vbnMuYWRvYmUuY29tL2V4aWYvMS4wLyIKICAgICAgICAgICAgeG1sbnM6ZGM9Imh0dHA6Ly9wdXJsLm9yZy9kYy9lbGVtZW50cy8xLjEvIgogICAgICAgICAgICB4bWxuczp4bXA9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8iPgogICAgICAgICA8dGlmZjpSZXNvbHV0aW9uVW5pdD4yPC90aWZmOlJlc29sdXRpb25Vbml0PgogICAgICAgICA8dGlmZjpDb21wcmVzc2lvbj41PC90aWZmOkNvbXByZXNzaW9uPgogICAgICAgICA8dGlmZjpYUmVzb2x1dGlvbj43MjwvdGlmZjpYUmVzb2x1dGlvbj4KICAgICAgICAgPHRpZmY6T3JpZW50YXRpb24+MTwvdGlmZjpPcmllbnRhdGlvbj4KICAgICAgICAgPHRpZmY6WVJlc29sdXRpb24+NzI8L3RpZmY6WVJlc29sdXRpb24+CiAgICAgICAgIDxleGlmOlBpeGVsWERpbWVuc2lvbj4yMDA8L2V4aWY6UGl4ZWxYRGltZW5zaW9uPgogICAgICAgICA8ZXhpZjpDb2xvclNwYWNlPjE8L2V4aWY6Q29sb3JTcGFjZT4KICAgICAgICAgPGV4aWY6UGl4ZWxZRGltZW5zaW9uPjIwMDwvZXhpZjpQaXhlbFlEaW1lbnNpb24+CiAgICAgICAgIDxkYzpzdWJqZWN0PgogICAgICAgICAgICA8cmRmOkJhZy8+CiAgICAgICAgIDwvZGM6c3ViamVjdD4KICAgICAgICAgPHhtcDpNb2RpZnlEYXRlPjIwMTctMDQtMjdUMTE6MDQ6NTY8L3htcDpNb2RpZnlEYXRlPgogICAgICAgICA8eG1wOkNyZWF0b3JUb29sPlBpeGVsbWF0b3IgMy42PC94bXA6Q3JlYXRvclRvb2w+CiAgICAgIDwvcmRmOkRlc2NyaXB0aW9uPgogICA8L3JkZjpSREY+CjwveDp4bXBtZXRhPgru/DiWAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAHlBMVEX////Hx8fz8/Pk5OTc3Nzr6+v7+/vQ0NCsrKzAwMCDrzdtAAAAxUlEQVR42u3bvQ7BUBiA4VKaGHEDTdCwisTOYDWxugcuwmX762I0fF/SeN7hnK1PTttzOrUoJEmS9FU5TUB6YwgEAoFAIBAIBAKBQCAQCATyS9Xyvj9FI/NNszgcY43++jkMr7HIrH6N59ClVLv3VE5C71a7hFskUtafeXsJRAbtxVehSDuPOr+SlGeS8nal7JOUHZ9zdqWcwjnfE994CAQCgUAgEAgEAoFAIBAIBAKBQCAQCAQCgUAgf4Gk/JIrSZKkTvcACcIXxrBsGbIAAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

Unfortunately, no major browsers currently support vertical range controls directly.

### transform: rotate(-90deg)

You can, however, create a vertical range control by drawing a horizontal range control on its side. The easiest way is to use CSS: by applying a [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) to rotate the element, you can make it vertical. Let's take a look.

#### HTML

The HTML needs to be updated to wrap the [`<input>`](../input) in a [`<div>`](../div) to let us correct the layout after the transform is performed (since transforms don't automatically affect the layout of the page):

    <div class="slider-wrapper">
      <input type="range" min="0" max="11" value="7" step="1">
    </div>

#### CSS

Now we need some CSS. First is the CSS for the wrapper itself; this specifies the display mode and size we want so that the page lays out correctly; in essence, it's reserving an area of the page for the slider so that the rotated slider fits into the reserved space without making a mess of things.

    .slider-wrapper {
      display: inline-block;
      width: 20px;
      height: 150px;
      padding: 0;
    }

Then comes the style information for the `<input>` element within the reserved space:

    .slider-wrapper input {
      width: 150px;
      height: 20px;
      margin: 0;
      transform-origin: 75px 75px;
      transform: rotate(-90deg);
    }

The size of the control is set to be 150 pixels long by 20 pixels tall. The margins are set to 0 and the [`transform-origin`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin) is shifted to the middle of the space the slider rotates through; since the slider is configured to be 150 pixels wide, it rotates through a box which is 150 pixels on each side. Offsetting the origin by 75px on each axis means we will rotate around the center of that space. Finally, we rotate counter-clockwise by 90°. The result: a range input which is rotated so the maximum value is at the top and the minimum value is at the bottom.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMgAAADIBAMAAABfdrOtAAAAHlBMVEX////Hx8fl5eXw8PDc3Nz8/Pz29vbQ0NCsrKzAwMDD9v8WAAAAxklEQVR42u3VQQ7BQBiA0YaULQt7TYVt4wRCYi0h1s5A3MDCCXpepV04gH8SvG8xs3yZaWcmy94aj7L4IBAIBAKBQCAQCATy4fb3W7kLNgbrzXF2CUaWVTMsprELmT/H/jkUOVSvqTiF7lY7DVeRSNlOvWsksu0+TR2JdNuU11+/kiTfJMnfleScJDnxSe6uNLdwkvekeRknuTceAoFAIBAIBAKBQCAQCAQCgUAgEAgEAoFAIBDIzyPFNJMkSZIkSZIkSfr3HkdHH5p8MTRIAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

### appearance property

The [`appearance`](https://developer.mozilla.org/en-US/docs/Web/CSS/appearance) property has a non-standard value of `slider-vertical` that, well, makes sliders vertical.

#### HTML

We use the same HTML as in the previous examples:

    <input type="range" min="0" max="11" value="7" step="1">

#### CSS

We target just the inputs with a type of range:

    input[type="range"] {
      -webkit-appearance: slider-vertical;
    }

### orient attribute

In Firefox only, there is a non-standard `orient` property.

#### HTML

Use similar HTML as in the previous examples, we add the attribute with a value of `vertical`:

    <input type="range" min="0" max="11" value="7" step="1" orient="vertical">

### writing-mode: bt-lr;

The [`writing-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode) property should generally not be used to alter text direction for internationalization or localization purposes, but can be used for special effects.

#### HTML

We use the same HTML as in the previous examples:

    <input type="range" min="0" max="11" value="7" step="1">

#### CSS

We target just the inputs with a type of range, changing the writing mode from the default to `bt-lr`, or bottom-to-top and left-to-right:

    input[type="range"] {
      writing-mode: bt-lr;
    }

### Putting it all together

As each of the above examples works in different browsers, you can put all of them in a single example to make it work cross browser:

#### HTML

We keep the `orient` attribute with a value of `vertical` for Firefox:

    <input type="range" min="0" max="11" value="7" step="1" orient="vertical">

#### CSS

We target just the inputs with a type of range, changing the writing mode from the default to `bt-lr`, or bottom-to-top and left-to-right, for Edge and Internet Explorer, and add `-webkit-appearance: slider-vertical` for all -webkit-based browsers:

    input[type="range"] {
      writing-mode: bt-lr;
      -webkit-appearance: slider-vertical;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#range-state-(type=range)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="range"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#range-state-typerange">HTML 5.1<br />
<span class="small">The definition of '&lt;input type="range"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`range`

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

`tick_marks`

Yes

≤79

No

See [bug 841942](https://bugzil.la/841942).

?

Yes

No

Yes

Yes

No

See [bug 841942](https://bugzil.la/841942).

Yes

No

Yes

`vertical_orientation`

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

12

The slider can be oriented vertically by setting the `writing-mode: bt-lr` style on the `input` element.

No

See [bug 840820](https://bugzil.la/840820) and [bug 981916](https://bugzil.la/981916).

10

The slider can be oriented vertically by setting the `writing-mode: bt-lr` style on the `input` element.

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

No

See [bug 840820](https://bugzil.la/840820) and [bug 981916](https://bugzil.la/981916).

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

Yes

The slider can be oriented vertically by setting the non-standard `-webkit-appearance: slider-vertical` style on the `input` element. You shouldn't use this, since it's proprietary, unless you include appropriate fallbacks for users of other browsers.

See also
--------

-   [HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
-   [`<input>`](../input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface it's based upon
-   `<input type="number">`
-   [`validityState.rangeOverflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeOverflow) and [`validityState.rangeUnderflow`](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState/rangeUnderflow)
-   [Controlling multiple parameters with ConstantSourceNode](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Controlling_multiple_parameters_with_ConstantSourceNode)
-   [Styling the range element](https://css-tricks.com/sliding-nightmare-understanding-range-input)
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range</a>
