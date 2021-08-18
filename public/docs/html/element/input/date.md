&lt;input type="date"&gt;
=========================

[`<input>`](../input) elements of `type="date"` create input fields that let the user enter a date, either with a textbox that validates the input or a special date picker interface.

The resulting value includes the year, month, and day, but *not* the time. The [time](time) and [datetime-local](datetime-local) input types support time and date+time input.

The input UI generally varies from browser to browser; see [Browser compatibility](#browser_compatibility) for further details. In unsupported browsers, the control degrades gracefully to `<input type="text">`.

Among browsers with custom interfaces for selecting dates are Chrome, Edge, and Opera, whose date control looks like so:

<img src="data:image/png;base64,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" alt="Chrome&#39;s date input as of November 2020" width="237" height="326" />

And the Firefox date control looks like this:

<img src="data:image/png;base64,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" alt="Another “dd/mm/yyyy” textbox that expands into a selectable calendar control." width="263" height="264" />

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing a date in YYYY-MM-DD format, or empty</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, and <a href="../input#attr-step"><code>step</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>list</code>, <code>value</code>, <code>valueAsDate</code>, <code>valueAsNumber</code>.</td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown"><code>stepDown()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp"><code>stepUp()</code></a></td></tr></tbody></table>

Value
-----

A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the date entered in the input. The date is formatted according to ISO8601, described in [Format of a valid date string](../../date_and_time_formats#format_of_a_valid_date_string) in [Date and time formats used in HTML](../../date_and_time_formats).

You can set a default value for the input with a date inside the [`value`](../input#attr-value) attribute, like so:

    <input type="date" value="2017-06-01">

`value` — the displayed date is formatted *based on the locale of the user's browser*, but the parsed `value` is always formatted `yyyy-mm-dd`.

You can get and set the date value in JavaScript with the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` and `valueAsNumber` properties. For example:

    var dateControl = document.querySelector('input[type="date"]');
    dateControl.value = '2017-06-01';
    console.log(dateControl.value); // prints "2017-06-01"
    console.log(dateControl.valueAsNumber); // prints 1496275200000, a JavaScript timestamp (ms)

This code finds the first [`<input>`](../input) element whose `type` is `date`, and sets its value to `2017-06-01` (June 1<sup>st</sup>, 2017). It then reads that value back in string and number formats.

Additional attributes
---------------------

Along with the attributes common to all [`<input>`](../input) elements, `date` inputs have the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>max</code></td><td>The latest acceptable date</td></tr><tr class="even"><td><code>min</code></td><td>The earliest acceptable date</td></tr><tr class="odd"><td><code>step</code></td><td>The <em>stepping interval</em>, when clicking up and down spinner buttons and validating the date</td></tr></tbody></table>

### `max`

The latest date to accept. If the [`value`](../input#attr-value) entered into the element occurs afterward, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `max` attribute isn't a possible date string in the format `yyyy-mm-dd`, then the element has no maximum date value.

If both the `max` and `min` attributes are set, this value must be a date string **later than or equal to** the one in the `min` attribute.

### `min`

The earliest date to accept. If the [`value`](../input#attr-value) entered into the element occurs beforehand, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `min` attribute isn't a possible date string in the format `yyyy-mm-dd`, then the element has no minimum date value.

If both the `max` and `min` attributes are set, this value must be a date string **earlier than or equal to** the one in the `max` attribute.

### `step`

The `step` attribute is a number that specifies the granularity that the value must adhere to, or the special value `any`, which is described below. Only values which are equal to the basis for stepping (`min` if specified, [`value`](../input#attr-value) otherwise, and an appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may round to the nearest valid value, preferring numbers in the positive direction when there are two equally close options.

For `date` inputs, the value of `step` is given in days; and is treated as a number of milliseconds equal to 86,400,000 times the `step` value (the underlying numeric value is in milliseconds). The default value of `step` is 1, indicating 1 day.

Specifying `any` as the value for `step` has the same effect as `1` for `date` inputs.

Using date inputs
-----------------

Date inputs sound convenient — they provide an easy interface for choosing dates, and they normalize the data format sent to the server regardless of the user's locale. However, there are currently issues with `<input type="date">` because of its limited browser support.

In this section, we'll look at basic and then more complex uses of `<input type="date">`, and offer advice on mitigating the browser support issue later (see [Handling browser support](#handling_browser_support)).

Hopefully, over time browser support will become ubiquitous, and this problem will fade away.

### Basic uses of date

The simplest use of `<input type="date">` involves one `<input>` combined with its [`<label>`](../label), as seen below:

    <form action="https://example.com">
      <label>
        Enter your birthday:
        <input type="date" name="bday">
      </label>

      <p><button>Submit</button></p>
    </form>

This HTML submits the entered date under the key `bday` to `https://example.com` — resulting in a URL like `https://example.com/?bday=1955-06-08`.

### Setting maximum and minimum dates

You can use the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes to restrict the dates that can be chosen by the user. In the following example, we set a minimum date of `2017-04-01` and a maximum date of `2017-04-30`:

    <form>
      <label for="party">Choose your preferred party date:
        <input type="date" name="party" min="2017-04-01" max="2017-04-30">
      </label>
    </form>

The result is that only days in April 2017 can be selected — the month and year parts of the textbox will be uneditable, and dates outside April 2017 can't be selected in the picker widget.

**Note**: You *should* be able to use the [`step`](../input#attr-step) attribute to vary the number of days jumped each time the date is incremented (e.g. to only make Saturdays selectable). However, this does not seem to be in any implementation at the time of writing.

### Controlling input size

`<input type="date">` doesn't support form sizing attributes such as [`size`](../input#attr-size). Prefer [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) for sizing it.

Validation
----------

By default, `<input type="date">` doesn't validate the entered value beyond its format. The interfaces generally don't let you enter anything that isn't a date — which is helpful — but you can leave the field empty or enter an invalid date in browsers where the input falls back to type `text` (like the 32nd of April).

If you use [`min`](../input#attr-min) and [`max`](../input#attr-max) to restrict the available dates (see [Setting maximum and minimum dates](#setting_maximum_and_minimum_dates)), supporting browsers will display an error if you try to submit a date that is out of bounds. However, you'll need to double-check the submitted results to ensure the value is within these dates, if the date picker isn't fully supported on the user's device.

You can also use the [`required`](../input#attr-required) attribute to make filling in the date mandatory — an error will be displayed if you try to submit an empty date field. This should work in most browsers, even if they fall back to a text input.

Let's look at an example of minimum and maximum dates, and also made a field required:

    <form>
      <label>
        Choose your preferred party date (required, April 1st to 20th):
        <input type="date" name="party" min="2017-04-01" max="2017-04-20" required>
        <span class="validity"></span>
      </label>

      <p>
        <button>Submit</button>
      </p>
    </form>

If you try to submit the form with an incomplete date (or with a date outside the set bounds), the browser displays an error. Try playing with the example now:

Here's a screenshot for those of you who aren't using a supporting browser:

<img src="data:image/png;base64,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" alt="The input field has an overlaid speech balloon, with an orange exclamation mark icon and the message “Please fill in this field.”" width="634" height="90" />

Here's the CSS used in the above example. We make use of the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) to add an icon next to the input, based on whether or not the current value is valid. We had to put the icon on a [`<span>`](../span) next to the input, not on the input itself, because in Chrome at least the input's generated content is placed inside the form control, and can't be styled or shown effectively.

    label {
      display: flex;
      align-items: center;
    }

    span::after {
      padding-left: 5px;
    }

    input:invalid + span::after {
      content: '✖';
    }

    input:valid+span::after {
      content: '✓';
    }

**Important**: Client-side form validation *is no substitute* for validating on the server. It's easy for someone to modify the HTML, or bypass your HTML entirely and submit the data directly to your server. If your server fails to validate the received data, disaster could strike with data that is badly-formatted, too large, of the wrong type, etc.

Handling browser support
------------------------

As mentioned, the major problem with date inputs at the time of writing is [browser support](#browser_compatibility). As an example, the date picker on Firefox for Android looks like this:

<img src="data:image/png;base64,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" alt="A popup calendar picker modal floats above the web page and browser UI." width="360" height="640" />

Unsupporting browsers gracefully degrade to a text input, but this creates problems in consistency of user interface (the presented controls are different) and data handling.

The second problem is the more serious one; with date input supported, the value is normalized to the format `yyyy-mm-dd`. But with a text input, the browser has no recognition of what format the date should be in, and there are many different formats in which people write dates. For example:

-   `ddmmyyyy`
-   `dd/mm/yyyy`
-   `mm/dd/yyyy`
-   `dd-mm-yyyy`
-   `mm-dd-yyyy`
-   `Month dd, yyyy`

One way around this is the [`pattern`](../input#attr-pattern) attribute on your date input. Even though the date picker doesn't use it, the text input fallback will. For example, try viewing the following in a unsupporting browser:

    <form>
      <label for="bday">Enter your birthday:
        <input type="date" name="bday" required pattern="\d{4}-\d{2}-\d{2}">
        <span class="validity"></span>
      </label>
      <p>
        <button>Submit</button>
      </p>
    </form>

If you submit it, you'll see that the browser displays an error and highlights the input as invalid if your entry doesn't match the pattern `####-##-##` (where `#` is a digit from 0 to 9). Of course, this doesn't stop people from entering invalid dates, or incorrect formats. So we still have a problem.

At the moment, the best way to deal with dates in forms in a cross-browser way is to have the user enter the day, month, and year in separate controls, or to use a JavaScript library such as [jQuery date picker](https://jqueryui.com/datepicker/).

Examples
--------

In this example, we create 2 sets of UI elements for choosing dates: a native `<input type="date">` picker and a set of 3 [`<select>`](../select) elements for older browsers that don't support the native date input.

### HTML

The HTML looks like so:

    <form>
        <div class="nativeDatePicker">
          <label for="bday">Enter your birthday:</label>
          <input type="date" id="bday" name="bday">
          <span class="validity"></span>
        </div>
        <p class="fallbackLabel">Enter your birthday:</p>
        <div class="fallbackDatePicker">
          <span>
            <label for="day">Day:</label>
            <select id="day" name="day">
            </select>
          </span>
          <span>
            <label for="month">Month:</label>
            <select id="month" name="month">
              <option selected>January</option>
              <option>February</option>
              <option>March</option>
              <option>April</option>
              <option>May</option>
              <option>June</option>
              <option>July</option>
              <option>August</option>
              <option>September</option>
              <option>October</option>
              <option>November</option>
              <option>December</option>
            </select>
          </span>
          <span>
            <label for="year">Year:</label>
            <select id="year" name="year">
            </select>
          </span>
        </div>
    </form>

The months are hardcoded (as they are always the same), while the day and year values are dynamically generated depending on the currently selected month and year, and the current year (see the code comments below for detailed explanations of how these functions work.)

### JavaScript

The other part of the code that may be of interest is the feature detection code — to detect whether the browser supports `<input type="date">`.

We create a new [`<input>`](../input) element, try setting its `type` to `date`, then immediately check what its type is — unsupporting browsers will return `text`, because the `date` type falls back to type `text`. If `<input type="date">` isn't supported, we hide the native picker and show the fallback ([`<select>`](../select)) instead.

    // define variables
    var nativePicker = document.querySelector('.nativeDatePicker');
    var fallbackPicker = document.querySelector('.fallbackDatePicker');
    var fallbackLabel = document.querySelector('.fallbackLabel');

    var yearSelect = document.querySelector('#year');
    var monthSelect = document.querySelector('#month');
    var daySelect = document.querySelector('#day');

    // hide fallback initially
    fallbackPicker.style.display = 'none';
    fallbackLabel.style.display = 'none';

    // test whether a new date input falls back to a text input or not
    var test = document.createElement('input');

    try {
      test.type = 'date';
    } catch (e) {
      console.log(e.description);
    }

    // if it does, run the code inside the if() {} block
    if(test.type === 'text') {
      // hide the native picker and show the fallback
      nativePicker.style.display = 'none';
      fallbackPicker.style.display = 'block';
      fallbackLabel.style.display = 'block';

      // populate the days and years dynamically
      // (the months are always the same, therefore hardcoded)
      populateDays(monthSelect.value);
      populateYears();
    }

    function populateDays(month) {
      // delete the current set of <option> elements out of the
      // day <select>, ready for the next set to be injected
      while(daySelect.firstChild){
        daySelect.removeChild(daySelect.firstChild);
      }

      // Create variable to hold new number of days to inject
      var dayNum;

      // 31 or 30 days?
      if(month === 'January' | month === 'March' | month === 'May' | month === 'July' | month === 'August' | month === 'October' | month === 'December') {
        dayNum = 31;
      } else if(month === 'April' | month === 'June' | month === 'September' | month === 'November') {
        dayNum = 30;
      } else {
      // If month is February, calculate whether it is a leap year or not
      var year = yearSelect.value;
      var isLeap = new Date(year, 1, 29).getMonth() == 1;
      isLeap ? dayNum = 29 : dayNum = 28;
      }

      // inject the right number of new <option> elements into the day <select>
      for(i = 1; i <= dayNum; i++) {
        var option = document.createElement('option');
        option.textContent = i;
        daySelect.appendChild(option);
      }

      // if previous day has already been set, set daySelect's value
      // to that day, to avoid the day jumping back to 1 when you
      // change the year
      if(previousDay) {
        daySelect.value = previousDay;

        // If the previous day was set to a high number, say 31, and then
        // you chose a month with less total days in it (e.g. February),
        // this part of the code ensures that the highest day available
        // is selected, rather than showing a blank daySelect
        if(daySelect.value === "") {
          daySelect.value = previousDay - 1;
        }

        if(daySelect.value === "") {
          daySelect.value = previousDay - 2;
        }

        if(daySelect.value === "") {
          daySelect.value = previousDay - 3;
        }
      }
    }

    function populateYears() {
      // get this year as a number
      var date = new Date();
      var year = date.getFullYear();

      // Make this year, and the 100 years before it available in the year <select>
      for(var i = 0; i <= 100; i++) {
        var option = document.createElement('option');
        option.textContent = year-i;
        yearSelect.appendChild(option);
      }
    }

    // when the month or year <select> values are changed, rerun populateDays()
    // in case the change affected the number of available days
    yearSelect.onchange = function() {
      populateDays(monthSelect.value);
    }

    monthSelect.onchange = function() {
      populateDays(monthSelect.value);
    }

    //preserve day selection
    var previousDay;

    // update what day has been set to previously
    // see end of populateDays() for usage
    daySelect.onchange = function() {
      previousDay = daySelect.value;
    }

**Note**: Remember that some years have 53 weeks in them (see [Weeks per year](https://en.wikipedia.org/wiki/ISO_week_date#Weeks_per_year))! You'll need to take this into consideration when developing production apps.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#date-state-(type=date)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="date"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sec-forms.html#date-state-typedate">HTML5<br />
<span class="small">The definition of '&lt;input type="date"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`date`

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

See also
--------

-   The generic [`<input>`](../input) element and the interface used to manipulate it, [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
-   [Date and Time picker tutorial](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types#date_and_time_pickers)
-   [Date and time formats used in HTML](../../date_and_time_formats)
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date</a>
