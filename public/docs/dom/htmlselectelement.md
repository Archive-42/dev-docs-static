HTMLSelectElement
=================

The `HTMLSelectElement` interface represents a [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) HTML Element. These elements also share all of the properties and methods of other HTML elements via the [`HTMLElement`](htmlelement) interface.

Properties
----------

*This interface inherits the properties of [`HTMLElement`](htmlelement), and of [`Element`](element) and [`Node`](node).*

[`HTMLSelectElement.autofocus`](htmlselectelement/autofocus)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-autofocus) HTML attribute, which indicates whether the control should have input focus when the page loads, unless the user overrides it, for example by typing in a different control. Only one form-associated element in a document can have this attribute specified.

[`HTMLSelectElement.disabled`](htmlselectelement/disabled)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`disabled`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-disabled) HTML attribute, which indicates whether the control is disabled. If it is disabled, it does not accept clicks.

 [`HTMLSelectElement.form`](htmlselectelement/form)<span class="badge inline readonly">Read only </span>   
An [`HTMLFormElement`](htmlformelement) referencing the form that this element is associated with. If the element is not associated with of a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) element, then it returns `null`.

 [`HTMLSelectElement.labels`](htmlselectelement/labels)<span class="badge inline readonly">Read only </span>   
A [`NodeList`](nodelist) of [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) elements associated with the element.

<span class="page-not-created">`HTMLSelectElement.length`</span>  
An `unsigned long` The number of [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements in this `select` element.

<span class="page-not-created">`HTMLSelectElement.multiple`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`multiple`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-multiple) HTML attribute, which indicates whether multiple items can be selected.

<span class="page-not-created">`HTMLSelectElement.name`</span>  
A [`DOMString`](domstring) reflecting the [`name`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-name) HTML attribute, containing the name of this control used by servers and DOM search functions.

 [`HTMLSelectElement.options`](htmlselectelement/options)<span class="badge inline readonly">Read only </span>   
An [`HTMLOptionsCollection`](htmloptionscollection) representing the set of [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) ([`HTMLOptionElement`](htmloptionelement)) elements contained by this element.

<span class="page-not-created">`HTMLSelectElement.required`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`required`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-required) HTML attribute, which indicates whether the user is required to select a value before submitting the form.

[`HTMLSelectElement.selectedIndex`](htmlselectelement/selectedindex)  
A `long` reflecting the index of the first selected [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) element. The value `-1` indicates no element is selected.

 [`HTMLSelectElement.selectedOptions`](htmlselectelement/selectedoptions)<span class="badge inline readonly">Read only </span>   
An [`HTMLCollection`](htmlcollection) representing the set of [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) elements that are selected.

<span class="page-not-created">`HTMLSelectElement.size`</span>  
A `long` reflecting the [`size`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select#attr-size) HTML attribute, which contains the number of visible items in the control. The default is 1, unless `multiple` is `true`, in which case it is 4.

 [`HTMLSelectElement.type`](htmlselectelement/type)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) represeting the form control's type. When `multiple` is `true`, it returns `"select-multiple"`; otherwise, it returns `"select-one"`.

 <span class="page-not-created">`HTMLSelectElement.validationMessage`</span><span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing a localized message that describes the validation constraints that the control does not satisfy (if any). This attribute is the empty string if the control is not a candidate for constraint validation (`willValidate` is false), or it satisfies its constraints.

 <span class="page-not-created">`HTMLSelectElement.validity`</span><span class="badge inline readonly">Read only </span>   
A [`ValidityState`](validitystate) reflecting the validity state that this control is in.

<span class="page-not-created">`HTMLSelectElement.value`</span>  
A [`DOMString`](domstring) reflecting the value of the form control. Returns the `value` property of the first selected option element if there is one, otherwise the empty string.

 <span class="page-not-created">`HTMLSelectElement.willValidate`</span><span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the button is a candidate for constraint validation. It is `false` if any conditions bar it from constraint validation.

Methods
-------

*This interface inherits the methods of [`HTMLElement`](htmlelement), and of [`Element`](element) and [`Node`](node).*

[`HTMLSelectElement.add()`](htmlselectelement/add)  
Adds an element to the collection of `option` elements for this `select` element.

 <span class="page-not-created">`HTMLSelectElement.blur()`</span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Removes input focus from this element. *This method is now implemented on [`HTMLElement`](htmlelement)*.

[`HTMLSelectElement.checkValidity()`](htmlselectelement/checkvalidity)  
Checks whether the element has any constraints and whether it satisfies them. If the element fails its constraints, the browser fires a cancelable [`invalid`](htmlinputelement/invalid_event) event at the element (and returns `false`).

 <span class="page-not-created">`HTMLSelectElement.focus()`</span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Gives input focus to this element. *This method is now implemented on [`HTMLElement`](htmlelement)*.

[`HTMLSelectElement.item()`](htmlselectelement/item)  
Gets an item from the options collection for this [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element. You can also access an item by specifying the index in array-style brackets or parentheses, without calling this method explicitly.

[`HTMLSelectElement.namedItem()`](htmlselectelement/nameditem)  
Gets the item in the options collection with the specified name. The name string can match either the `id` or the `name` attribute of an option node. You can also access an item by specifying the name in array-style brackets or parentheses, without calling this method explicitly.

[`HTMLSelectElement.remove()`](htmlselectelement/remove)  
Removes the element at the specified index from the options collection for this `select` element.

<span class="page-not-created">`HTMLSelectElement.reportValidity()`</span>  
This method reports the problems with the constraints on the element, if any, to the user. If there are problems, it fires a cancelable [`invalid`](htmlinputelement/invalid_event) event at the element, and returns `false`; if there are no problems, it returns `true`.

[`HTMLSelectElement.setCustomValidity()`](htmlselectelement/setcustomvalidity)  
Sets the custom validity message for the selection element to the specified message. Use the empty string to indicate that the element does *not* have a custom validity error.

Events
------

Listen to these events using [`addEventListener()`](eventtarget/addeventlistener) or by assigning an event listener to the `oneventname` property of this interface:

 [`input`](htmlelement/input_event) event  
Fires when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.

Example
-------

### Get information about the selected option

    /* assuming we have the following HTML
    <select id='s'>
        <option>First</option>
        <option selected>Second</option>
        <option>Third</option>
    </select>
    */

    var select = document.getElementById('s');

    // return the index of the selected option
    console.log(select.selectedIndex); // 1

    // return the value of the selected option
    console.log(select.options[select.selectedIndex].value) // Second

A better way to track changes to the user's selection is to watch for the [`change`](htmlelement/change_event) event to occur on the `<select>`. This will tell you when the value changes, and you can then update anything you need to. See [the example provided](htmlelement/change_event#select_element) in the documentation for the `change` event for details.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlselectelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Since the latest snapshot, <a href="https://www.w3.org/TR/html52/">HTML5</a>, it adds the <code>autocomplete</code> property and the <code>reportValidity()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#htmlselectelement">HTML5<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Is a snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>.<br />
It adds the <code>autofocus</code>, <code>form</code>, <code>required</code>, <code>labels</code>, <code>selectedOptions</code>, <code>willValidate</code>, <code>validity</code> and <code>validationMessage</code> properties.<br />
The <code>tabindex</code> property and the <code>blur()</code> and <code>focus()</code> methods have been moved to <a href="htmlelement"><code>HTMLElement</code></a>.<br />
The methods <code>item()</code>, <code>namedItem()</code>, <code>checkValidity()</code> and <code>setCustomValidity()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-94282980">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td><code>options</code> now returns an <a href="htmloptionscollection"><code>HTMLOptionsCollection</code></a>.<br />
<code>length</code> now returns an <code>unsigned long</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-94282980">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLSelectElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`HTMLSelectElement`

1

12

1

You should watch for [change](https://developer.mozilla.org/docs/Web/Events/change) events on [`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select) instead of watching `<option>` elements for events. See [bug 1090602](https://bugzil.la/1090602) and [Multiprocess Firefox Web content compatibility](https://developer.mozilla.org/docs/Mozilla/Firefox/Multiprocess_Firefox/Web_content_compatibility) for details.

1

2

1

1

18

4

10.1

1

1.0

`add`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`autocomplete`

66

79

59

No

53

≤12.1-15

9

66

66

59

47

≤12.1-14

9

9.0

`autofocus`

1

12

4

10

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`blur`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`checkValidity`

4

12

4

10

9

5

≤37

18

4

10.1

4

1.0

`disabled`

1

12

1

5.5

9

3

1

18

4

10.1

1

1.0

`focus`

1

12

1

5

≤12.1

1

1

18

4

≤12.1

1

1.0

`form`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`item`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`labels`

6

18

56

No

≤12.1

5.1

≤37

18

56

≤12.1

5

1.0

`length`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`multiple`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`name`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`namedItem`

1

12

`namedItem` does not appear to take the `name` attribute into account (only the `id` attribute) on Internet Explorer and Edge. There is a [bug report](https://connect.microsoft.com/IE/feedbackdetail/view/2414092/) to Microsoft about this.

1

6

`namedItem` does not appear to take the `name` attribute into account (only the `id` attribute) on Internet Explorer and Edge. There is a [bug report](https://connect.microsoft.com/IE/feedbackdetail/view/2414092/) to Microsoft about this.

≤12.1

3

1

18

4

≤12.1

1

1.0

`options`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`remove`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`reportValidity`

40

17

49

No

27

10.1

40

40

64

27

10.3

4.0

`required`

10

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`selectedIndex`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`selectedOptions`

19

12

26

No

9

6

≤37

25

26

10.1

6

1.5

`setCustomValidity`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`size`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`type`

1

12

1

1

2

3

1

18

4

10.1

1

1.0

`validationMessage`

4

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`validity`

3

12

4

10

≤12.1

5

≤37

18

4

≤12.1

4

1.0

`value`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`willValidate`

1

12

4

10

≤12.1

4

1

18

4

≤12.1

3

1.0

See also
--------

-   The [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) HTML element, which implements this interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLSelectElement</a>
