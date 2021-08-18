&lt;input type="month"&gt;
==========================

[`<input>`](../input) elements of type `month` create input fields that let the user enter a month and year allowing a month and year to be easily entered. The value is a string whose value is in the format "`YYYY-MM`", where `YYYY` is the four-digit year and `MM` is the month number.

The control's UI varies in general from browser to browser; at the moment support is patchy, with only Chrome/Opera and Edge on desktop — and most modern mobile browser versions — having usable implementations. In browsers that don't support `month` inputs, the control degrades gracefully to a simple `<input type="text">`, although there may be automatic validation of the entered text to ensure it's formatted as expected.

For those of you using a browser that doesn't support `month`, the screenshot below shows what it looks like in Chrome and Opera. Clicking the down arrow on the right hand side brings up a date picker that lets you select the month and year.

<img src="data:image/png;base64,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" width="273" height="216" />

The Microsoft Edge `month` control looks like this:

<img src="data:image/png;base64,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" width="227" height="389" />

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString"><code>DOMString</code></a> representing a month and year, or empty.</td></tr><tr class="even"><td><strong>Events</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event"><code>change</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event"><code>input</code></a></td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-autocomplete"><code>autocomplete</code></a>, <a href="../input#attr-list"><code>list</code></a>, <a href="../input#attr-readonly"><code>readonly</code></a>, and <a href="../input#attr-step"><code>step</code></a>.</td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td><code>value</code></td></tr><tr class="odd"><td><strong>Methods</strong></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select"><code>select()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepDown"><code>stepDown()</code></a>, <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/stepUp"><code>stepUp()</code></a>.</td></tr></tbody></table>

Value
-----

A [`DOMString`](https://developer.mozilla.org/en-US/docs/Web/API/DOMString) representing the value of the month and year entered into the input, in the form YYYY-MM (four or more digit year, then a hyphen ("`-`"), followed by the two-digit month). The format of the month string used by this input type is described in [Format of a valid local month string](../../date_and_time_formats#format_of_a_valid_local_month_string) in [Date and time formats used in HTML](../../date_and_time_formats).

You can set a default value for the input control by including a month and year inside the [`value`](../input#attr-value) attribute, like so:

    <label for="bday-month">What month were you born in?</label>
    <input id="bday-month" type="month" name="bday-month" value="2017-06">

One thing to note is that the displayed date format differs from the actual `value`; most [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) display the month and year in a locale-appropriate form, based on the set locale of the user's operating system, whereas the date `value` is always formatted `yyyy-MM`.

When the above value is submitted to the server, for example, it will look like `bday-month=1978-06`.

You can also get and set the date value in JavaScript using the <span class="page-not-created">`HTMLInputElement.value`</span> property, for example:

    var monthControl = document.querySelector('input[type="month"]');
    monthControl.value = '1978-06';

Additional attributes
---------------------

In addition to the attributes common to [`<input>`](../input) elements, month inputs offer the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>list</code></td><td>The id of the &lt;datalist&gt; element that contains the optional pre-defined autocomplete options</td></tr><tr class="even"><td><code>max</code></td><td>The latest year and month to accept as a valid input</td></tr><tr class="odd"><td><code>min</code></td><td>The earliest year and month to accept as a valid input</td></tr><tr class="even"><td><code>readonly</code></td><td>A Boolean which, if present, indicates that the input's value can't be edited</td></tr><tr class="odd"><td><code>step</code></td><td>A stepping interval to use when incrementing and decrementing the value of the input field</td></tr></tbody></table>

### `list`

The values of the list attribute is the [`id`](https://developer.mozilla.org/en-US/docs/Web/API/Element/id) of a [`<datalist>`](../datalist) element located in the same document. The [`<datalist>`](../datalist) provides a list of predefined values to suggest to the user for this input. Any values in the list that are not compatible with the [`type`](../input#attr-type) are not included in the suggested options. The values provided are suggestions, not requirements: users can select from this predefined list or provide a different value.

### `max`

The latest year and month, in the string format discussed in the [Value](#value) section above, to accept. If the [`value`](../input#attr-value) entered into the element exceeds this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If the value of the `max` attribute isn't a valid string in "`yyyy-MM`" format, then the element has no maximum value.

This value must specify a year-month pairing later than or equal to the one specified by the `min` attribute.

### `min`

The latest year and month to accept, in the same "`yyyy-MM`" format described above. If the [`value`](../input#attr-value) of the element is less than this, the element fails [constraint validation](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation). If a value is specified for `min` that isn't a valid year and month string, the input has no minimum value.

This value must be a year-month pairing which is earlier than or equal to the one specified by the `max` attribute.

### `readonly`

A Boolean attribute which, if present, means this field cannot be edited by the user. Its `value` can, however, still be changed from JavaScript code that directly sets the value of the <span class="page-not-created">`HTMLInputElement.value`</span> property.

**Note:** Because a read-only field cannot have a value, `required` does not have any effect on inputs with the `readonly` attribute also specified.

### `step`

The `step` attribute is a number that specifies the granularity that the value must adhere to, or the special value `any`, which is described below. Only values which are equal to the basis for stepping (`min` if specified, [`value`](../input#attr-value) otherwise, and an appropriate default value if neither of those is provided) are valid.

A string value of `any` means that no stepping is implied, and any value is allowed (barring other constraints, such as `min` and `max`).

**Note:** When the data entered by the user doesn't adhere to the stepping configuration, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may round to the nearest valid value, preferring numbers in the positive direction when there are two equally close options.

For `month` inputs, the value of `step` is given in months, with a scaling factor of 1 (since the underlying numeric value is also in months). The default value of `step` is 1 month.

Using month inputs
------------------

Date-related inputs (including `month`) sound convenient at first glance; they promise an easy UI for choosing dates, and they normalize the data format sent to the server, regardless of the user's locale. However, there are issues with `<input type="month">` because at this time, many major browsers don't yet support it.

We'll look at basic and more complex uses of `<input type="month">`, then offer advice on mitigating the browser support issue in the section [Handling browser support](#handling_browser_support)).

### Basic uses of month

The simplest use of `<input type="month">` involves a basic [`<input>`](../input) and [`<label>`](../label) element combination, as seen below:

    <form>
      <label for="bday-month">What month were you born in?</label>
      <input id="bday-month" type="month" name="bday-month">
    </form>

### Setting maximum and minimum dates

You can use the [`min`](../input#attr-min) and [`max`](../input#attr-max) attributes to restrict the range of dates that the user can choose. In the following example we specify a minimum month of `1900-01` and a maximum month of `1999-12`:

    <form>
      <label for="bday-month">What month were you born in?</label>
      <input id="bday-month" type="month" name="bday-month"
             min="1900-01" max="1999-12">
    </form>

The result here is that:

-   Only months between in January 1900 and December 1999 can be selected; months outside that range can't be scrolled to in the control.
-   Depending on what browser you are using, you might find that months outside the specified range might not be selectable in the month picker (e.g. Edge), or invalid (see [Validation](#validation)) but still available (e.g. Chrome).

### Controlling input size

`<input type="month">` doesn't support form sizing attributes such as [`size`](../input#attr-size). You'll have to resort to [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) for sizing needs.

Validation
----------

By default, `<input type="month">` does not apply any validation to entered values. The UI implementations generally don't let you enter anything that isn't a date — which is helpful — but you can still submit the form with the `month` input empty, or enter an invalid date (e.g. the 32nd of April).

To help avoid this, you can use [`min`](../input#attr-min) and [`max`](../input#attr-max) to restrict the available dates (see [Setting maximum and minimum dates](#setting_maximum_and_minimum_dates)), and in addition use the [`required`](../input#attr-required) attribute to make filling in the date mandatory. As a result, supporting browsers will display an error if you try to submit a date that is outside the set bounds, or an empty date field.

Let's look at an example; here we've set minimum and maximum dates, and also made the field required:

    <form>
      <div>
        <label for="month">What month would you like to visit us (Summer months only, please)?</label>
        <input id="month" type="month" name="month"
               min="2017-06" max="2017-09" required>
        <span class="validity"></span>
      </div>
      <div>
          <input type="submit" value="Submit form">
      </div>
    </form>

If you try to submit the form without both the month and year specified (or with a date outside the set bounds), the browser displays an error. Try playing with the example now:

Here's a screenshot for those of you who aren't using a supporting browser:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAApQAAABbCAMAAAD6MOVGAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAKCUExURf///wAAALvd//n5+f39/fT09Pf39/7+/rHY/+fz//38/Pv7+/qrIPHx8enp6ebk5nCu6oPB/e7u7tbW1uHg4dzb28bGxtHR0aysrNLS0uvr69ra2oK/+/r7+rq6uuPv+7rc/XCt6ff//7na+///9/n4+AAIUdX4/+3s7FIFAP/71vLy8v//8Y/N77HV/8LBwdmgT/b296ZWAABOpZrU+Ofo50ic1s3NzavO9//7/wADMObx/vDw8PH//97e3v/3zjECAP/759TT1AAHSs33/wETfPb5//jXpvXQlLbZ+N2mYUIDAGEHAP/11ePj483y/9CTQ4F/fyiLzd78/5TS9bDV9PjUnP7ovqTX9ksEAP/xzuDr9wEXkP7px+b9/5VIAOayd26s5PLJi5QyAFdaVaxlAP/Zp73q/4a85EsMSv/63wAGQQBxtK6DfY3L+/Ht2nq/7gBNkG00AAEMYu7MpblzAMKkfu/x96dJAPfZuf/ktAA2nwBgqNvu/qvV/kWRznYLAE+k2MOWbO29hMzn/oA2AACDxGej1U6Ku6p3O/ju7cbx/y9XiLSztJe61gA2kPv//5prS3icwYeGjAIbnDk/R923iiuW1tC/pU2BqoWjt6jP7CgmGY1iMGGXxtaWT5FaAP//+//38tnk8sGES4wPAKS6xanh//qyNtbRvAAxYLXl/uTBl73I1dmmcr1+LwA0fqXD2X+v2XJzZl6t4NDb5uvc0wBMfveBAJyWdrnJtpqCTYxAQzF+us2KJb2ukbPR0UlsmHyBpEtIMdSZar/i9b3b6gAvE6msorSVYDAibo5mdQBKX0o2KVM2gaWUtUufzi5yoWJ9fHQOMd+hAM3x1hlbvwEAABWzSURBVHja7Fr7U9NXFr+HUSPr1Ee7v+x2lp2NadhkolJA2mRlSTaE14CAIDHIayGAMrxBBAQFQYqCWKRYQEXsog5gFa2jA+ITW6vbdh/dP2jPufd+vyQQKbNLRmbMmQk33+89937P43PP4xsYC1CAAhSgAAUoQAEK0OqSJi54TdGf4gI+eecx2doZtLaos1UTcMu7Ta1BldvWFlUGtQbc8k5TXGfl1jVGf6jsfBsZXHf0f176/gr57ku9zqxAv6pgpjkTTJtrVyrGOs7Pybwl+s18Z973eP7HdOMo08W9JZtWBXuVknwIDtq29fiayt7Ht24LUgRd17SdLDwUuvr2sp0C6P1tPsBgImt2wXQ/7PPFVoYcW9UFo75YXsCxFeHmJFhiaax3iXE5ummFTBZj/UKrLFoJEb/8muVbGyLT6R9ccFdBze0ullsLYHdl+sHE/W+WwlNPD9nyP1NAGbSmGp0gD1DGgyWRsVvg8A8qbzBdOFTi90JHXq4rynt+l3RwMTjy6BAXAvhwnO1rtGTEikCpSdMLNZRxOd4EiGSmirtMN+6DeZfv5xG/pJS/X+Sy+aCkCK2uGEoFJsO7mK4R9Wty3VvtXiV3O1tiU996eobWxigVlBv/H1pdZTxBWQ8Alm9v4V9/oLKDznE8tODXI/eY0eBtwLAv5Jf/ABzihxi87Se9+iV+Ilb2wDCJr6RfBiXKFem9yJdov5A7UTZfUkAsS5K7p+VEsxTDOUz1HV2rbN2U5MglNl1OT0m5sONtgnLP3g/37lkelOGg0r3VB2VZW10oc1otpSzmcA8acPgV2DEuX7DOWy6i28B6SGTnfwN5LcvRQPZL6bfAcDCbeNjbAPb9KKHFPhVe8wREQtR0vBzsezE5381O4mrBa+v/8a6pf35Yy/GlG4dLUBfKeQfdo6ze/SxPdxIriW/ZyflhdnKwN1R11v2ZXr6o3j04nGc7DRYRCIVoTbUvLSM8YpadGnQH2fqthzh//Y9u+37dRP9nQjYqG5R9+RQz/RoPoSODVma7qvG0FUFNKzP9TZWzquHZE6tlR1MtdGttT36arYXRqstQk0GFB/R26ibmrl+2Y6Q1e08KgXRDl4cfwoNQYzK8fFCl2LRhcH5a6CV1zZ15/b2BbIZ6ls253RtNFYPc3Fcfn9O+PVBu3r1+3frdm5cFpS1fweSoP8rwNAyBYQDtrACjJVqxe8gVoW2GavY4J9pWVHNQVN0v7jTS6Q2vLkCcGNvKtU1WRwbWQuXE7bR2H8USoGYiXwQ0Xb4jQxeuj2VOR57CS/GCp3gCJcLBNiZ4TeF4HkzXMnXFjtAyrCV0jciTpo9VQGl64hKLOghKRf/E4vWv3CokWjx69AKUc16nFeUvjOD8ZcnVbLwypQKiGMkmUqLYV0wJMIoIVmBPpboOxJFS5GywQsRELeifnobIehy/Pg3Q14AbJtSlZic7qsYA3HCAEpnnpBSIQHeerjvg0McLNi21zXG9FF0R8Y5ZshkdPl4AF8rCPAu3XlVQntn9OR8O8qv1dPGrTZs2+YyTW+hlpGbLnuVAyWyXBSY/80u/XQIttp9nDY7oxmpyyT6KIFhbTrE0eyzmZFm4XYksBLSrPoNyXpKlB32JcZumiyO0RkM7pkmMpAWWUlkT7GCF+AmLUnnJ2Xw7xFcz1aVK+s6CE6zZEd1MmG+2tig8C2mNbiRZZqh2SYCRkFeQo+VpmZ6NiZfd5tjAER8eXsn5Ywzl0dmJHGAkG1P4cV85RRm8RetRGmhysYWryWOqnOER0SzM3sOcpDDitgQFNF2LMhVNh4S0QSbxmUXMXphUBTImR2EOisL7kapNsxCwTfxRiq5og1hWIEGpa9SnsiPVC/l8NUHZkJ7+HHuCm+npd5nGmZ6+H0uEdKREH4DY+x776JuP2Ht7xTuVS5wGF4OSUhXRDb+A0lZkn8nRFsPI61AmXJhkj2W6Cy7Mrx6grLS1wY3HXbwQO0JuLIEo4ehjWtWRJbI2MiaXY2tUbvq5R+X1BGUHqaIAz1RUl4HgLSBolbVF/G4xKPmiW+JIXqm7fjYk5DsFZLY2wlWBfGgJtMe8zuMT2MNY+pgEZZQXKOUU3pib8qpXNawBMOgqcnJ+AozREMlZmjlwolIMwyFnQ3YFL1SKHpOqQHyXxiiugGJTjJh120VslrpqaWmJXYAST9w94+FQv4DSVNFjqjjAytKPO9ND2VdV+J1l32EpAxk+APHBOjbgHmDrPhCXAxx7IYtBeUtmb8uUX1AZRrUqdtVdMnmRlW3XzuVhKPMEJYmBgYNAWYxnGoG3FJRqwZ6mn339UD+DiVXh9QTlFXKK2rt0wMhcKTpqB9XPbwAlHcsDXv0O3Ta2YTRTT4Ipf/pVlESfCfPnCZ+glFMo009aD1DWJ/LHiTJDBSUBxugSoCRwclDyyGv2BqWcVAXyBqWwKUvBjEdKahRdOSjjFVDark0/ecT8EynXMwKlcSBDV4Eg0hEoMczXn/eFh7+wT9zr3Z/gKGgQbe9enL5vqX2OJdEfoGwmrJW1cdeKU60PLYBSHlbUlno8ExtUwi1P35R+ndC+AMp270iJe0K100pXCm8KuYa2w20LKeyp3TeGYL70BPmlhYMyaTEowxwTBszfBbTQxAszEk0XjjFdxB0RgKBHoC/mPMutFQDzSt+4r5wiGyt5iArYBCrmjMmODEVOzp/gESmzXRx3ZW1URxSe8AalnFQFWgDlAdWm8ZGs3louYrrQVYBSpm8uP2liZuKgKaDcSaQMb77wdc/DyxcwfTc/13I88j/YTlUc8IWH3ywazyLy/rwYlLcJjyNj9HeHP0BpKqKc85g7ymhAq2HGDYPRIZf9+sHwuqf/oIBiutZOLdENkiaT5VrP5VFCwuYBQyE2M4aWib5wR56aSWWrk4NljMKLXf53aTC5nV3RhyK8+6ry4XywUp3w9hd7WXLOEei7KTMs1puypkzTZyRgxRfjgu6JU10CZChaITzCrkGJ5igGExHIeDiVheVEC1CibHRb7iunUBt7qXKAMgkF3diz46lT5eRnAQviXGs1x50oG7vQCpNPGyyp2S5PUCqTikAxCESqYeLRjk+lTbMQ941dwuJSV7QFaj8l9MQF9IIjiZBZgAdFgvJ7cvyx4w9p2PfUSrGpUlzsr6Vh65sZFkCpuZmOCcv5PPrqAig12T6z9xJQMjekL210xqmgoh7cL5jE1ExvmrLKZUuFXSM8chqgpgEcWP3xhzqTAbqZ85nWNsZfAjQZ9Jft20kw4u7GL/oZgH8NuWBa6lmALuvgbpO82JTCs+TeO/QypLPJgNtMjkgFs3kllTIG39C70CYrPBibHIkWv3RM9vXjulf4mXCBPagebd6tlVkfRbsAD2prVNPeruY/oMCzqmS7234xl7Qh2Xq4HGJfMcXP+g2lECgnQM+DFYbzPOUcHrLC9OwpsAxYoXe2FuzXsckeNeEffSIaSDaeNz0npUDoLAtdH7IVQY1i03j4oXY6Vby+FLp2CJvV4HMmycyPv+TVFAbdoi71PeXOT5GOb9wvBvr7qXLBh53LMCiGudow0Hq/FWvKqRQCp6niIg+ePrP3UlB+eMlH983G6V2Qbc5PmGRm/tZH/dlX/HdSnMgjX5l9/ACBnz9u9uLewJb5nybJi48xczaNhpk3eOzbUS5fW2yJU/m8hfF4F77wizWJptFt/r3PR5s34EeRjTHPfc3yhnmhfpn6b3vn/9y0ecdxaY7s1anlni3H2CYJpHZOxmbBMMeX4IRgQgiEOOFb0oZSRlhKR3oELkDKgFFKKNB2S8Y2+iXdKMmWttvRjWYBftl212tZt3Z3u93t/9nn80iy5dhOHNBqSXnecEh6/OTRJ+jlz/M8kp7PB3/faddTKjttBU4uW/TmIs+yswZNqv5v5ZaUM2Mbzo6cXxA30deOyc/hB3H4ouGYksy0YcZ9es8e6DXOwcHNOqUTLwClNKbMQGlbVQhKiXZzvgvT/VXV7ie6rdD05DYMkkeomn3HH+/H3p39x4XMNOcPWj1mtKkFX+QO1ZfdXtiQlJ3Mvu2pRe9Tmlqd0rS/vDp9vewmBH/Hyo/ima1fjzPaQGlbqFIsafUzljkL429duVBGG+7W6cCMprJbcL9mJtcYraCskFQyl6K7Av6tcIsrF0od4KAP2fIZeEIov/ddGUi73a4GcylLAinezqcCzAqGkqqIHv99ys1Z1aq1OVfFfrx2/u7s3fnaxd+npFqxUC77zfM1OXoWtVMS2V9Tkp4lf/P1k7Wrv7PZppXoFTaglr1GZ22ejki6du2avLf2yNon0onxDpuWolfZaFreasbVxXTymc8OfvbMydUnVz+xTqy5WKGRKJYGnfosY933wj5b6rQPoKbuxZjYvSnczfbjj6fxi5V2TbSceReVvqjsWO7URjWrOUg0MzN/F5dqxu7Oz8xIRQdrD9Y+psYqtZJMJqXSBLeJitWTbkfa8WXy6upqiyUUslpjHMdFXM4UR6rEUk5XBEpiVmsoFLKUVWBiNQFTxpJeaDOyS5hEJDNAIpFcJCmmUxG5UiSVFpOIJYAZAzTLpxD5ViCXiCWl0sxMApIW2UECjxFH0iXyaW/2uYzoTfOiK+lwRCQ0yyn8VoQsiCWl0tRMApLgG10uURT9PM/H4850ayKuqhhPtKad8XicJ/KXSyLK5QKvjVhSKs0KpcSkNcILAbfbnUr5vF5vAtQg5NQUGrAw4SXylUspEFgZEPiINUMlvYzmZDLE8ULFEtMkPV38CoFX+Up6Ic0GJWEylmytMJTlFa3JmEQlhdKcjjJk5US3wWx3i5w1VMBV2kKiENBIghiiwJfLUVq5CJ8ymO0pPsJZC7jKkBBwaHUOR0AIUUq+dSjRUULnzTniXoPZ7o07OOjAJVepKhcDWp4lIFJKyuAo7cRRupwJgxmfwIdM4CrtC1yl4NLyLC6BYlKW3hsdpWhAKEV0lXn9d3ZsPB3PvlQ8siDe+rmpzO6bgcVCMLspJuWAEhwllxTThoMyLSY5cJULoVTGxjYMDnNdWcL115O5P71hEzMwS/b62x4sFus0RTEpw5BS6r15oUop7f/46Vx93K9H46sEXu6/cweVyorzfnYnc6jtOVzG1dTE3N4fxG69CYPlT4+RPXlt9CBGPGFw2X5TU3BMVSO3OapvEUq59+ZbM1AuZBKo1CWUrbzcfxeG8se46Hi6o/OFOqb3DeaLH7LsxIvrwn8n4VheqRvcu4NlMWoDbtoPhTFuWR/LbvtvpgaFssxDyqQYz0L5dL70CWUc+u/8QaVCUXSI/eb9p5i+X9YxG95hNky8GN3YuC5Mwvn2b2vvBAZJqFKyefXfzED4ox3sASZbg0JZVig5AmWD9lDGih7k6M7Y0iX5aiBQckWhZJj7f9vdfEyB8jJGOl73o3Y8gA1CKSUCgc2658GpnmnEgmwNCmV5oYy4/E5PHpS5u6Dgu6tWfTXbwnTvXjo5S/BsV2MfewSr3r5Err0U2FstpZ3e4R516c/Z/dkSpU7+ORs8Tj8MKotCuXUGI4f8ufM8o0B5ZVMulOczUIYRyssUSj1NvkuEMnq0+VcfsNvbt3QtHS3tJfbmzMDXO7FqL8kEBAfqz/vq2xmlndOfq6MK3h6erc2WKHXyzylDmTf9VijqZB8xh8In+reNbz3cyGzYfvH40cs5UHZKEx1EceiNjnNtH1Eo9QUlXxqUAEZ/uJEAEnWn8C5g0OPD8PzRADmSCxlb8FbzIwvjmMxCCQcM3zLik8LLBG+xU2NbuvaP+GqlpGpyA4xt6x8vjE2SNGv3sa50rtR8d7gAlPxiUGI+A/Z6XfAG2zx3jfniP8+zF1pyoOy+SqLrvgQOs/sqJlLAPQqlEaEMvroXQTm0m2Wbp5gB2LAvkyM2U4j3WTDs6kDbepWnbFsfPZrJCEE+34I/xX4fb8rIDZDsL7ADJRjJk/0NoRrDeebHVy0GZeY+pU2O/BiUY/ssGuKnqYnep9QXlA6AMlAKlDCu637tEoAS3XjqYvTG9n2fPui50/tCy+3t+6I3/qIUYtODw8eYLWEVlHAQ3Vj/ZfS3o6rPT9Ue33iqpVNpYBLnOL2wgZIfAN232OfIuf40vvVGPpQBgNKRD6VH06fVoodyom8oD7/9iz1dw8cAlIHwdbf79eG3mGmP7/X6t3ax78/XMZlCHNHBVAXqqaAEug7DXp/qc+ySN0wglFID0rQHKkHJmQdu3yfhy3iurpMFx5RFoNT2zRJvnHKiJygfPny4EMpv5uY+HyewYY/a/M+eK7D5oL4neraNbX5ZKSwO5SXpg+znwOB5hFJqQAUlh0nJmv91jbSBDjpcKpRWb0IzXykmvFbKiZ6gzLtPid03Xn0CJXgvJhI9/Eodc6W+JzTJjAxNjEiFkyVBqcy+JSilBlrUnnLTJD6QIec6gikZSoXSFglU1WikqkCEvuSr9zGlBMZA1/o7Z+rvjQyN7hs6Nf9JuL7nzOijkQ9PtciFCpQD2PVmJjq5UPaxPzs4kIVSbkAF5SB7M36W3U/ONXzv/lUYU346qnpzwlYMSvioOqTRGvNqiqRRoMQb2ZhHY/QAsyPMNs/V92AWwN9/qRSidgB7UA+rSlDCXnAIoNxRT6A8/mt2L7khvgugnGiRG8hACU7zLPTfNyexzvEPWfa9q+uZXaPtJXhKqhUFZa5CZLR1x0p6a4YbUxWWoMwdGIUmLu/JYjCSec+Rs6irLuUpqVbQREdfolDSiQ6FkqqMUBrkfUoK5UqC0iBvnlMozQ1l7rNvg6jYs28qCiWFkur/BKXfkFD6KZQmhTLvzXNjQRmiMa7MCWXuwjGDqKrIGh0qU0AZMzCUMQql6ajMrvsWEnZD2W5PCIXXfVMZH0o5Qobf6U4ZiUp7yi3PcxZGyKAyyfQb+2/BnWioqfkpaJWehQbW1DQk3EK8cCwhKrMMKh0ufzztCbh9JNh+VaJKnwLLUD53wJOO+10OOqQ0KZRS/50U+XhaaAUuMT+Ez+fVoaTsEG4gslVIx3nMNlUgPiWVGQaVUiRfF1DpRCw9gQCmLtGnwDYPIukEJl2FI/lSmaP/xlGlRCViCfLgH90JjEIBkjKTBWOeU5kASjk7BFLpRyyd6XRa0K3SQCQg6ZeYDNFEOiZ2ldCBc5iP0Y8Z8JBMvYok4vNjlkiOo3l0zO0qLegrMU2oSxT9fl6/wuyMLkAygn6SZhwzPZUkxbcjCWDqWklCJBejTJoZSolKBUtMrByJOPQpNE3KroxI0iy2ZqeyEjPQKwnodS0p3TfN970CqEQskUuQVc9CAy3oJSvtlEmzU0mwBC6RTF0LTayUkKRMmptKCUsCpv6FhspIUiZNTSViKZOpc0mG2iiTKwJLBUzdSzGXXriVgaWBRC8aBZMCSUVFRUVFRaW1/gcwtmbsOSDhWgAAAABJRU5ErkJggg==" width="660" height="91" />

Here's the CSS used in the above example. Here we make use of the [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid) and [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid) CSS properties to style the input based on whether or not the current value is valid. We had to put the icons on a [`<span>`](../span) next to the input, not on the input itself, because in Chrome the generated content is placed inside the form control, and can't be styled or shown effectively.

    div {
      margin-bottom: 10px;
      position: relative;
    }

    input[type="number"] {
      width: 100px;
    }

    input + span {
      padding-right: 30px;
    }

    input:invalid+span:after {
      position: absolute;
      content: '✖';
      padding-left: 5px;
    }

    input:valid+span:after {
      position: absolute;
      content: '✓';
      padding-left: 5px;
    }

**Important**: HTML form validation is *not* a substitute for scripts that ensure that the entered data is in the proper format. It's far too easy for someone to make adjustments to the HTML that allow them to bypass the validation, or to remove it entirely. It's also possible for someone to bypass your HTML entirely and submit the data directly to your server. If your server-side code fails to validate the data it receives, disaster could strike when improperly-formatted data is submitted (or data which is too large, of the wrong type, and so forth).

Handling browser support
------------------------

As mentioned above, the major problem with using date inputs at the time of writing is that many major browsers don't yet implement them all; only Chrome/Opera and Edge support it on desktop, and most modern browsers on mobile. As an example, the `month` picker on Chrome for Android looks like this:

<img src="data:image/png;base64,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" width="360" height="640" />

Non-supporting browsers gracefully degrade to a text input, but this creates problems both in terms of consistency of user interface (the presented control will be different), and data handling.

The second problem is the more serious of the two. As mentioned earlier, with a `month` input the actual value is always normalized to the format `yyyy-mm`. On the other hand, in its default configuration, a `text` input has no idea what format the date should be in, and this is an issue because of the number of different ways in which people write dates. For example:

-   `mmyyyy` (072018)
-   `mm/yyyy` (07/2018)
-   `mm-yyyy` (07-2018)
-   `yyyy-mm` (2018-07)
-   `Month yyyy` (July 2018)
-   ... and so forth.

One way around this is to put a [`pattern`](../input#attr-pattern) attribute on your `month` input. Even though the `month` input doesn't use it, if the browser falls back to treating it like a `text` input, the pattern will be used. For example, try viewing the following demo in a browser that doesn't support `month` inputs:

    <form>
      <div>
        <label for="month">What month would you like to visit us? (Summer months only, yyyy-mm)</label>
        <input id="month" type="month" name="month"
               min="2017-06" max="2017-09" required
               pattern="[0-9]{4}-[0-9]{2}">
        <span class="validity"></span>
      </div>
      <div>
          <input type="submit" value="Submit form">
      </div>
    </form>

If you try submitting it, you'll see that the browser now displays an error message (and highlights the input as invalid) if your entry doesn't match the pattern `nnnn-nn`, where `n` is a number from 0 to 9. Of course, this doesn't stop people from entering invalid dates (such as `0000-42`), or incorrectly formatted dates that follow the pattern.

There's also the problem that the user won't necessarily know which of the many date formats is expected. We have work left to do.

The best way to deal with dates in forms in a cross-browser way (until all of the major browsers have supported them for a while) is to get the user to enter the month and year in separate controls ([`<select>`](../select) elements being popular; see below for an implementation), or use JavaScript libraries such as the [jQuery date picker](https://jqueryui.com/datepicker/) plugin.

Examples
--------

In this example, we create two sets of UI elements, each designed to let the user select a month and year. The first is a native `month` input, and the other is a pair of [`<select>`](../select) elements that allow choosing a month and year independently, for compatibility with browsers that don't yet support `<input type="month">`.

### HTML

The form that requests the month and year looks like this:

    <form>
      <div class="nativeDatePicker">
        <label for="month-visit">What month would you like to visit us?</label>
        <input type="month" id="month-visit" name="month-visit">
        <span class="validity"></span>
      </div>
      <p class="fallbackLabel">What month would you like to visit us?</p>
      <div class="fallbackDatePicker">
        <div>
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
      </div>
    </form>

The [`<div>`](../div) with the ID `nativeDatePicker` uses the `month` input type to request the month and year, while the `<div>` with the ID `fallbackDatePicker` instead uses a pair of `<select>` elements. The first requests the month, and the second the year.

The `<select>` for choosing the month is hardcoded with the names of the months, as they don't change (leaving localization out of things). The list of available year values is dynamically generated depending on the current year (see the code comments below for detailed explanations of how these functions work).

### JavaScript

The JavaScript code that handles selecting which approach to use and to set up the list of years to include in the non-native year `<select>` follows.

The part of the example that may be of most interest is the feature detection code. In order to detect whether the browser supports `<input type="month">`, we create a new [`<input>`](../input) element, try setting its `type` to `month`, then immediately check what its type is set to. Browsers that don't support type `month` will return `text`, since that's What month falls back to when not supported. If `<input type="month">` is not supported, we hide the native picker and show the fallback picker UI instead.

    // define variables
    var nativePicker = document.querySelector('.nativeDatePicker');
    var fallbackPicker = document.querySelector('.fallbackDatePicker');
    var fallbackLabel = document.querySelector('.fallbackLabel');

    var yearSelect = document.querySelector('#year');
    var monthSelect = document.querySelector('#month');

    // hide fallback initially
    fallbackPicker.style.display = 'none';
    fallbackLabel.style.display = 'none';

    // test whether a new date input falls back to a text input or not
    var test = document.createElement('input');

    try {
      test.type = 'month';
    } catch (e) {
      console.log(e.description);
    }

    // if it does, run the code inside the if() {} block
    if(test.type === 'text') {
      // hide the native picker and show the fallback
      nativePicker.style.display = 'none';
      fallbackPicker.style.display = 'block';
      fallbackLabel.style.display = 'block';

      // populate the years dynamically
      // (the months are always the same, therefore hardcoded)
      populateYears();
    }

    function populateYears() {
      // get the current year as a number
      var date = new Date();
      var year = date.getFullYear();

      // Make this year, and the 100 years before it available in the year <select>
      for(var i = 0; i <= 100; i++) {
        var option = document.createElement('option');
        option.textContent = year-i;
        yearSelect.appendChild(option);
      }
    }

**Note**: Remember that some years have 53 weeks in them (see [Weeks per year](https://en.wikipedia.org/wiki/ISO_week_date#Weeks_per_year))! You'll need to take this into consideration when developing production apps.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#month-state-(type=month)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="month"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`month`

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

See also
--------

-   The generic [`<input>`](../input) element and the interface used to manipulate it, [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
-   [Date and time formats used in HTML](../../date_and_time_formats)
-   [Date and Time picker tutorial](https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls#date_and_time_picker)
-   `<input type="datetime-local">`, `<input type="date">`, `<input type="time">`, and `<input type="week">`
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/month" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/month</a>
