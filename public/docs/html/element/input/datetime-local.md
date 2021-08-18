&lt;input type="datetime-local"&gt;
===================================

[`<input>`](../input) elements of type `datetime-local` create input controls that let the user easily enter both a date and a time, including the year, month, and day as well as the time in hours and minutes.

The control's UI varies in general from browser to browser; at the moment support is patchy, with only Chrome/Opera and Edge on desktop and most modern versions of mobile browsers having usable implementations. In other browsers, these degrade gracefully to simple `<input type="text">` controls.

The control is intended to represent *a local date and time*, not necessarily *the user's local date and time*. In other words, an implementation should allow any valid combination of year, month, day, hour, and minute - even if such a combination is invalid in the user's local time zone (such as times within a daylight saving time spring-forward transition gap). Some mobile browsers (particularly on iOS) do not currently implement this correctly.

Because of the limited browser support for `datetime-local`, and the variations in how the inputs work, it may currently still be best to use a framework or library to present these, or to use a custom input of your own. Another option is to use separate `date` and `time` inputs, each of which is more widely supported than `datetime-local`.

Some browsers may resort to a text-only input element that validates that the results are legitimate date/time values before letting them be delivered to the server, as well, but you shouldn't rely on this behavior since you can't easily predict it.

For those of you not using a supporting browser, the Chrome/Opera `datetime-local` control looks like the below screenshot. Clicking the down arrow on the right hand side brings up a date picker to allow you to choose a date; you have to enter the time manually.

<img src="data:image/png;base64,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" width="280" height="224" />

The Edge `datetime-local` control looks like the below; clicking the date and the time parts of the value bring up two separate pickers for you, so you can easily set both the date and the time. This is somewhat like having `date` and `time` widgets both created for you and merged into one.

<img src="data:image/png;base64,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" width="320" height="398" />

<img src="data:image/png;base64,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" width="264" height="394" />

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing a date and time (in the local time zone), or empty.</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, and <a href="../input#attr-step"><code>step</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>list</code>, <code>value</code>, <code>valueAsNumber</code>.</td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown"><code>stepDown()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp"><code>stepUp()</code></a></td></tr></tbody></table>

Value
-----

A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the value of the date entered into the input. The format of the date and time value used by this input type is described in [Local date and time strings](../../date_and_time_formats#local_date_and_time_strings) in [Date and time formats used in HTML](../../date_and_time_formats).

You can set a default value for the input by including a date and time inside the [`value`](../input#attr-value) attribute, like so:

    <label for="party">Enter a date and time for your party booking:</label>
    <input id="party" type="datetime-local" name="partydate" value="2017-06-01T08:30">

One thing to note is that the displayed date and time formats differ from the actual `value`; the displayed date and time are formatted according to the user's locale as reported by their operating system, whereas the date/time `value` is always formatted `yyyy-MM-ddThh:mm`. When the above value submitted to the server, for example, it will look like `partydate=2017-06-01T08:30`.

**Note:** Also bear in mind that if such data is submitted via HTTP `GET`, the colon character will need to be escaped for inclusion in the URL parameters, e.g. `partydate=2017-06-01T08%3A30`. See [`encodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) for one way to do this.

You can also get and set the date value in JavaScript using the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) `value` property, for example:

    var dateControl = document.querySelector('input[type="datetime-local"]');
    dateControl.value = '2017-06-01T08:30';

There are several methods provided by JavaScript's [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) that can be used to convert numeric date information into a properly-formatted string, or you can do it manually. For example, the [`Date.toISOString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString) method can be used for this purpose.

Additional attributes
---------------------

In addition to the attributes common to all [`<input>`](../input) elements, datetime-local inputs offer the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>max</code></td><td>The latest date and time to accept</td></tr><tr class="even"><td><code>min</code></td><td>The earliest date and time to accept</td></tr><tr class="odd"><td><code>step</code></td><td>The stepping interval to use for this input, such as when clicking arrows on spinner controls or performing validation</td></tr></tbody></table>

### `max`

The latest date and time to accept. If the [`value`](../input#attr-value) entered into the element is later than this timestamp, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `max` attribute isn't a valid string which follows the format `yyyy-MM-ddThh:mm`, then the element has no maximum value.

This value must specify a date string later than or equal to the one specified by the `min` attribute.

### `min`

The earliest date and time to accept; timestamps earlier than this will cause the element to fail [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `min` attribute isn't a valid string which follows the format `yyyy-MM-ddThh:mm`, then the element has no minimum value.

This value must specify a date string earlier than or equal to the one specified by the `max` attribute.

### `step`

The `step` attribute is a number that specifies the granularity that the value must adhere to, or the special value `any`, which is described below. Only values which are equal to the basis for stepping (`min` if specified, [`value`](../input#attr-value) otherwise, and an appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may round to the nearest valid value, preferring numbers in the positive direction when there are two equally close options.

For `datetime-local` inputs, the value of `step` is given in seconds, with a scaling factor of 1000 (since the underlying numeric value is in milliseconds). The default value of `step` is 60, indicating 60 seconds (or 1 minute, or 60,000 milliseconds).

*At this time, it's unclear what a value of `any` means for `step` when used with `datetime-local` inputs. This will be updated as soon as that information is determined.*

Using datetime-local inputs
---------------------------

Date/time inputs sound convenient at first glance; they provide an easy UI for choosing dates and times, and they normalize the data format sent to the server, regardless of the user's locale. However, there are issues with `<input type="datetime-local">` because of the limited browser support.

We'll look at basic and more complex uses of `<input type="datetime-local">`, then offer advice on mitigating the browser support issue later on (see [Handling browser support](#handling_browser_support)).

### Basic uses of datetime-local

The simplest use of `<input type="datetime-local">` involves a basic `<input>` and [`<label>`](../label) element combination, as seen below:

    <form>
        <label for="party">Enter a date and time for your party booking:</label>
        <input id="party" type="datetime-local" name="partydate">
    </form>

### Setting maximum and minimum dates and times

You can use the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes to restrict the dates/times that can be chosen by the user. In the following example we are setting a minimum datetime of `2017-06-01T08:30` and a maximum datetime of `2017-06-30T16:30`:

      <form>
        <label for="party">Enter a date and time for your party booking:</label>
        <input id="party" type="datetime-local" name="partydate" min="2017-06-01T08:30" max="2017-06-30T16:30">
      </form>

The result here is that:

-   Only days in June 2017 can be selected — only the "days" part of the date value will be editable, and dates outside June can't be scrolled to in the datepicker widget.
-   Depending on what browser you are using, you might find that times outside the specified values might not be selectable in the time picker (e.g. Edge), or invalid (see [Validation](#validation)) but still available (e.g. Chrome).

**Note**: You should be able to use the [`step`](../input#attr-step) attribute to vary the number of days jumped each time the date is incremented (e.g. maybe you only want to make Saturdays selectable). However, this does not seem to work effectively in any implementation at the time of writing.

### Controlling input size

`<input type="datetime-local">` doesn't support form control sizing attributes such as [`size`](../input#attr-size). You'll have to resort to [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) for customizing the sizes of these elements.

### Setting timezones

One thing the `datetime-local` input type doesn't provide is a way to set the time zone and/or locale of the date/time control. This was available in the `datetime` input type, but this type is now obsolete, having been removed from the spec. The main reasons why this was removed are a lack of implementation in browsers, and concerns over the user interface/experience. It is easier to just have a control (or controls) for setting the date/time and then deal with the locale in a separate control.

For example, if you are creating a system where the user is likely to already be logged in, with their locale already set, you could provide the timezone in a `hidden` input type. For example:

    <input type="hidden" id="timezone" name="timezone" value="-08:00">

On the other hand, if you were required to allow the user to enter a timezone along with a date/time input, you could provide a means of inputting a timezone, such as a [`<select>`](../select) element:

    <select name="timezone_offset" id="timezone-offset" class="span5">
        <option value="-12:00">(GMT -12:00) Eniwetok, Kwajalein</option>
        <option value="-11:00">(GMT -11:00) Midway Island, Samoa</option>
        <option value="-10:00">(GMT -10:00) Hawaii</option>
        <option value="-09:50">(GMT -9:30) Taiohae</option>
        <option value="-09:00">(GMT -9:00) Alaska</option>
        <option value="-08:00">(GMT -8:00) Pacific Time (US &amp; Canada)</option>

      ...

    </select>

In either case, the date/time and time zone values would be submitted to the server as separate data points, and then you'd need to store them appropriately in the database on the server-side.

**Note**: The above code snippet is taken from [All world timezones in an HTML select element](https://gist.github.com/nodesocket/3919205).

Validation
----------

By default, `<input type="datetime-local">` does not apply any validation to entered values. The UI implementations generally don't let you enter anything that isn't a date/time — which is helpful — but a user might still fill in no value and submit, or enter an invalid date and/or time (e.g. the 32nd of April).

You can use [`min`](../input#attr-min) and [`max`](../input#attr-max) to restrict the available dates (see [Setting maximum and minimum dates](#setting_maximum_and_minimum_dates)), and you can use the [`required`](../input#attr-required) attribute to make filling in the date/time mandatory. As a result, supporting browsers will display an error if you try to submit a date that is outside the set bounds, or an empty date field.

Let's look at an example; here we've set minimum and maximum date/time values, and also made the field required:

    <form>
        <div>
            <label for="party">Choose your preferred party date and time (required, June 1st 8.30am to June 30th 4.30pm):</label>
            <input id="party" type="datetime-local" name="partydate" min="2017-06-01T08:30" max="2017-06-30T16:30" required>
            <span class="validity"></span>
        </div>
        <div>
            <input type="submit" value="Book party!">
        </div>
    </form>

If you try to submit the form with an incomplete date (or with a date outside the set bounds), the browser displays an error. Try playing with the example now:

Here's a screenshot for those of you who aren't using a supporting browser:

<img src="data:image/png;base64,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" width="558" height="100" />

Here's the CSS used in the above example. Here we make use of the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS properties to style the input based on whether or not the current value is valid. We had to put the icons on a [`<span>`](../span) next to the input, not on the input itself, because in Chrome the generated content is placed inside the form control, and can't be styled or shown effectively.

    div {
        margin-bottom: 10px;
        display: flex;
        align-items: center;
    }

    label {
      display: inline-block;
      width: 300px;
    }

    input:invalid+span:after {
        content: '✖';
        padding-left: 5px;
    }

    input:valid+span:after {
        content: '✓';
        padding-left: 5px;
    }

**Important**: HTML form validation is *not* a substitute for scripts that ensure that the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data is submitted (or data which is too large, is of the wrong type, and so forth).

Handling browser support
------------------------

As mentioned above, the major problem with using date inputs at the time of writing is browser support — only Chrome/Opera and Edge support it on desktop, and most modern browsers on mobile. As an example, the `datetime-local` picker on Firefox for Android looks like this:

<img src="data:image/png;base64,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" width="360" height="640" />

Non-supporting browsers gracefully degrade to a text input, but this creates problems both in terms of consistency of user interface (the presented control will be different), and data handling.

The second problem is the most serious; as we mentioned earlier, with a `datetime-local` input, the actual value is always normalized to the format `yyyy-mm-ddThh:mm`. With a text input on the other hand, by default the browser has no recognition of what format the date should be in, and there are lots of different ways in which people write dates and times, for example:

-   `ddmmyyyy`
-   `dd/mm/yyyy`
-   `mm/dd/yyyy`
-   `dd-mm-yyyy`
-   `mm-dd-yyyy`
-   `mm-dd-yyyy hh:mm` (12 hour clock)
-   `mm-dd-yyyy HH:mm` (24 hour clock)
-   etc.

One way around this is to put a [`pattern`](../input#attr-pattern) attribute on your `datetime-local` input. Even though the `datetime-local` input doesn't use it, the text input fallback will. For example, try viewing the following demo in a non-supporting browser:

    <form>
      <div>
        <label for="party">Choose your preferred party date and time (required, June 1st 8.30am to June 30th 4.30pm):</label>
        <input id="party" type="datetime-local" name="partydate"
               min="2017-06-01T08:30" max="2017-06-30T16:30"
               pattern="[0-9]{4}-[0-9]{2}-[0-9]{2}T[0-9]{2}:[0-9]{2}" required>
        <span class="validity"></span>
      </div>
      <div>
        <input type="submit" value="Book party!">
      </div>
      <input type="hidden" id="timezone" name="timezone" value="-08:00">
    </form>

If you try submitting it, you'll see that the browser now displays an error message (and highlights the input as invalid) if your entry doesn't match the pattern `nnnn-nn-nnTnn:nn`, where `n` is a number from 0 to 9. Of course, this doesn't stop people from entering invalid dates, or incorrectly formatted dates and times.

And what user is going to understand the pattern they need to enter the time and date in?

We still have a problem.

The best way to deal with dates in forms in a cross-browser way at the moment is to get the user to enter the day, month, year, and time in separate controls ([`<select>`](../select) elements being popular — see below for an implementation), or use JavaScript libraries such as [jQuery date picker](https://jqueryui.com/datepicker/), and the [jQuery timepicker plugin](https://timepicker.co/).

The Y2K38 Problem (often server-side)
-------------------------------------

JavaScript uses double precision floating points to store dates, as with all numbers, meaning that JavaScript code will not suffer from the Y2K38 problem unless integer coercion/bit-hacks are used because all JavaScript bit operators use 32-bit signed 2s-complement integers.

The problem is with the server side of things: storage of dates greater than 2<sup>31</sup>-1. To fix this problem, you must store all dates using either unsigned 32-bit integers, signed 64-bit integers, or double-precision floating points on the server. If your server is written in PHP, the fix may be as simple as upgrading to PHP 8 or 7, and upgrading your hardware to x86\_64 or IA64. If you are stuck with other hardware, you can try to emulate 64-bit hardware inside a 32-bit virtual machine, but most VMs don't support this kind of virtualization, stability may suffer, and performance will definately suffer greatly.

The Y10k Problem (often client-side)
------------------------------------

In many servers, dates are stored as numbers instead of as strings--numbers of a fixed size and agnostic of format (aside from endianness). After the year 10,000, those numbers will just be a little bit bigger than before, so many servers will not see issues with forms submitted after the year 10,000.

The problem is with the client side of things: parsing of dates with more than 4 digits in the year.

    <!--midnight of January 1st, 10000: the exact time of Y10K-->
    <input type="datetime-local" value="+010000-01-01T05:00"/>

It's that simple. Just prepare your code for any number of digits. Do not only prepare for 5 digits. Here is JavaScript code for programmatically setting the value:

    function setValue(element, date) {
        var isoString = date.toISOString()
        element.value = isoString.substring(0, (isoString.indexOf("T")|0) + 6|0);
    }

Why worry about the Y10K problem if it is going to happen many centuries after your death? Exactly because you will already be dead, so the companies using your software will be stuck using your software without any other coder who knows the system well enough to come in and fix it.

Examples
--------

In this example we create two sets of UI elements for choosing datetimes — a native `<input type="datetime-local">` picker, and a set of five [`<select>`](../select) elements for choosing dates and times in older browsers that don't support the native input.

The HTML looks like so:

    <form>
      <div class="nativeDateTimePicker">
        <label for="party">Choose a date and time for your party:</label>
        <input type="datetime-local" id="party" name="bday">
        <span class="validity"></span>
      </div>
      <p class="fallbackLabel">Choose a date and time for your party:</p>
      <div class="fallbackDateTimePicker">
        <div>
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
        <div>
          <span>
            <label for="hour">Hour:</label>
            <select id="hour" name="hour">
            </select>
          </span>
          <span>
            <label for="minute">Minute:</label>
            <select id="minute" name="minute">
            </select>
          </span>
        </div>
      </div>
    </form>

The months are hard-coded (as they are always the same), while the day and year values are dynamically generated depending on the currently selected month and year, and the current year respectively (see the code comments below for detailed explanations of how these functions work.) We also decided to dynamically generate the hours and minutes, as there are so many of them!

The other part of the code that may be of interest is the feature detection code — to detect whether the browser supports `<input type="datetime-local">`, we create a new [`<input>`](../input) element, try setting its `type` to `datetime-local`, then immediately check what its type is set to. Browsers that don't support `datetime-local` return `text`, since that's what `datetime-local` falls back to. If `<input type="datetime-local">` is not supported, we hide the native picker and show the fallback picker UI ([`<select>`](../select)) instead.

    // define variables
    var nativePicker = document.querySelector('.nativeDateTimePicker');
    var fallbackPicker = document.querySelector('.fallbackDateTimePicker');
    var fallbackLabel = document.querySelector('.fallbackLabel');

    var yearSelect = document.querySelector('#year');
    var monthSelect = document.querySelector('#month');
    var daySelect = document.querySelector('#day');
    var hourSelect = document.querySelector('#hour');
    var minuteSelect = document.querySelector('#minute');

    // hide fallback initially
    fallbackPicker.style.display = 'none';
    fallbackLabel.style.display = 'none';

    // test whether a new datetime-local input falls back to a text input or not
    var test = document.createElement('input');

    try {
      test.type = 'datetime-local';
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
      populateHours();
      populateMinutes();
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
      if(month === 'January' || month === 'March' || month === 'May' || month === 'July' || month === 'August' || month === 'October' || month === 'December') {
        dayNum = 31;
      } else if(month === 'April' || month === 'June' || month === 'September' || month === 'November') {
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

    function populateHours() {
      // populate the hours <select> with the 24 hours of the day
      for(var i = 0; i <= 23; i++) {
        var option = document.createElement('option');
        option.textContent = (i < 10) ? ("0" + i) : i;
        hourSelect.appendChild(option);
      }
    }

    function populateMinutes() {
      // populate the minutes <select> with the 60 hours of each minute
      for(var i = 0; i <= 59; i++) {
        var option = document.createElement('option');
        option.textContent = (i < 10) ? ("0" + i) : i;
        minuteSelect.appendChild(option);
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#local-date-and-time-state-(type=datetime-local)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="datetime-local"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#local-date-and-time-state-(type=datetime-local)">HTML5<br />
<span class="small">The definition of '&lt;input type="datetime-local"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`datetime-local`

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

See also
--------

-   The generic [`<input>`](../input) element and the interface used to manipulate it, [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
-   `<input type="date">` and `<input type="time">`
-   [Date and time formats used in HTML](../../date_and_time_formats)
-   [Date and Time picker tutorial](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#date_and_time_picker)
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local</a>
