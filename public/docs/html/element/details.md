&lt;details&gt;: The Details disclosure element
===============================================

The `<details>` creates a disclosure widget in which information is visible only when the widget is toggled into an "open" state. A summary or label must be provided using the [`<summary>`](summary) element.

A disclosure widget is typically presented onscreen using a small triangle which rotates (or twists) to indicate open/closed status, with a label next to the triangle. The contents of the `<summary>` element are used as the label for the disclosure widget.

**Note:** The common use of a triangle which rotates or twists around to represent opening or closing the widget is why these are sometimes called "twisties."

A `<details>` widget can be in one of two states. The default *closed* state displays only the triangle and the label inside `<summary>` (or a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)-defined default string if no `<summary>`). This might look like the following:

<figure><img src="data:image/png;base64,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" width="191" height="26" /></figure>Here we see a standard disclosure widget with the label "System Requirements", in its default closed state. When the user clicks on the widget or focuses it then presses the space bar, it "twists" open, revealing its contents:

<figure><img src="data:image/png;base64,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" width="640" height="96" /></figure>From there, you can use CSS to style the disclosure widget, and you can programmatically open and close the widget by setting/removing its [`open`](#attr-open) attribute.

By default when closed, the widget is only tall enough to display the disclosure triangle and summary. When open, it expands to display the details contained within.

**Note:** Unfortunately, at this time there's no built-in way to animate the transition between open and closed.

Fully standards-compliant implementations automatically apply the CSS `display`: list-item to the [`<summary>`](summary) element. You can use this to customize its appearance further. See [Customizing the disclosure widget](#customizing_the_disclosure_widget) for further details.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, sectioning root, interactive content, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>One <a href="summary"><code>&lt;summary&gt;</code></a> element followed by <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>group</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement"><code>HTMLDetailsElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`open`  
This Boolean attribute indicates whether or not the details — that is, the contents of the `<details>` element — are currently visible. The details are shown when this attribute exists, or hidden when this attribute is absent. By default this attribute is absent which means the details are not visible.

**Note:** You have to remove this attribute entirely to make the details hidden. `open="false"` makes the details visible because this attribute is Boolean.

Events
------

In addition to the usual events supported by HTML elements, the `<details>` element supports the `toggle` event, which is dispatched to the `<details>` element whenever its state changes between open and closed. It is sent *after* the state is changed, although if the state changes multiple times before the browser can dispatch the event, the events are coalesced so that only one is sent.

You can use an event listener for the `toggle` event to detect when the widget changes state:

    details.addEventListener("toggle", event => {
      if (details.open) {
        /* the element was toggled open */
      } else {
        /* the element was toggled closed */
      }
    });

Examples
--------

### A simple disclosure example

This example shows a simple `<details>` element with a `<summary>`.

    <details>
      <summary>System Requirements</summary>
      <p>Requires a computer running an operating system. The computer
      must have some memory and ideally some kind of long-term storage.
      An input device as well as some form of output device is
      recommended.</p>
    </details>

The result of this HTML is:

### Creating an open disclosure box

To start the `<details>` box in its open state, add the Boolean `open` attribute:

    <details open>
      <summary>System Requirements</summary>
      <p>Requires a computer running an operating system. The computer
      must have some memory and ideally some kind of long-term storage.
      An input device as well as some form of output device is
      recommended.</p>
    </details>

This results in:

### Customizing the appearance

Now let's apply some CSS to customize the appearance of the disclosure box.

#### CSS

    details {
      font: 16px "Open Sans", Calibri, sans-serif;
      width: 620px;
    }

    details > summary {
      padding: 2px 6px;
      width: 15em;
      background-color: #ddd;
      border: none;
      box-shadow: 3px 3px 4px black;
      cursor: pointer;
    }

    details > p {
      border-radius: 0 0 10px 10px;
      background-color: #ddd;
      padding: 2px 6px;
      margin: 0;
      box-shadow: 3px 3px 4px black;
    }

    details[open] > summary {
      background-color: #ccf;
    }

This CSS creates a look similar to a tabbed interface, where clicking the tab opens it to reveal its contents.

The selector `details[open]` can be used to style the element which is open.

#### HTML

    <details>
      <summary>System Requirements</summary>
      <p>Requires a computer running an operating system. The computer
      must have some memory and ideally some kind of long-term storage.
      An input device as well as some form of output device is
      recommended.</p>
    </details>

#### Result

### Customizing the disclosure widget

The disclosure triangle itself can be customized, although this is not as broadly supported. There are variations in how browsers support this customization due to experimental implementations as the element was standardized, so we'll have to use multiple approaches for a while.

The [`<summary>`](summary) element supports the [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style) shorthand property and its longhand properties, such as [`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type), to change the disclosure triangle to whatever you choose (usually with [`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image)). For example, we can remove the disclosure widget icon by setting `list-style: none`.

Chrome doesn't support this yet, however, so we also need to use its non-standard `::-webkit-details-marker` [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) to customize the appearance in that browser.

#### CSS

    details {
      font: 16px "Open Sans", Calibri, sans-serif;
      width: 620px;
    }

    details > summary {
      padding: 2px 6px;
      width: 15em;
      background-color: #ddd;
      border: none;
      box-shadow: 3px 3px 4px black;
      cursor: pointer;
      list-style: none;
    }

    details > summary::-webkit-details-marker {
      display: none;
    }

    details > p {
      border-radius: 0 0 10px 10px;
      background-color: #ddd;
      padding: 2px 6px;
      margin: 0;
      box-shadow: 3px 3px 4px black;
    }

This CSS creates a look similar to a tabbed interface, where activating the tab expands and opens it to reveal its contents.

#### HTML

    <details>
      <summary>System Requirements</summary>
      <p>Requires a computer running an operating system. The computer
      must have some memory and ideally some kind of long-term storage.
      An input device as well as some form of output device is
      recommended.</p>
    </details>

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/interactive-elements.html#the-details-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;details&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/interactive-elements.html#the-details-element">HTML 5.1<br />
<span class="small">The definition of '&lt;details&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`details`

12

79

49

Before Firefox 57, there was a bug meaning that `<details>` elements can't be made open by default using the `open` attribute if they have a CSS `animation` active on them.

No

15

6

Yes

Yes

49

There is a bug meaning that `<details>` elements can't be made open by default using the `open` attribute if they have a CSS `animation` active on them.

14

6.1

Yes

`open`

12

79

49

No

15

6

4

Yes

49

14

6.1

Yes

See also
--------

-   [`<summary>`](summary)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details</a>
