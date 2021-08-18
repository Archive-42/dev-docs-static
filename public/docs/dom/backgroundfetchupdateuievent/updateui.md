# BackgroundFetchUpdateUIEvent.updateUI()

The `updateUI()` method of the [`BackgroundFetchUpdateUIEvent`](../backgroundfetchupdateuievent) interface updates the title and icon in the user interface to show the status of a background fetch.

This method may only be run once, to notify the user on a failed or a successful fetch.

## Syntax

    let updateUI = BackgroundFetchUpdateUIEvent.updateUI(options);

### Parameters

`options`<span class="badge inline optional">Optional</span>  
An object containing any of the following:

`icons`<span class="badge inline optional">Optional</span>  
A list of one or more image resources, containing icons for use in the user interface. An image resource is an object containing:

`src`  
A [`string`](../domstring) which is a URL of an image.

`sizes`<span class="badge inline optional">Optional</span>  
A [`string`](../domstring) which is equivalent to a [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) `sizes` attribute.

`type`<span class="badge inline optional">Optional</span>  
A [`string`](../domstring) containing an image MIME type.

`label`<span class="badge inline optional">Optional</span>  
A [`string`](../domstring) providing a name for the associated image.

`title`<span class="badge inline optional">Optional</span>  
A [`string`](../domstring) containing text to update the title of the user interface.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

### Exceptions

A [`DOMException`](../domexception) `InvalidStateError`  
Thrown if any of the following are true:

- The [`isTrusted`](../event/istrusted) property is `false`.
- The [`BackgroundFetchUpdateUIEvent`](../backgroundfetchupdateuievent) UI updated flag is already set, indicating that the `updateUI()` method has already been called.
- The [`BackgroundFetchUpdateUIEvent`](../backgroundfetchupdateuievent) is not active.

## Examples

The following example demonstrates updating the UI with a title and image icon on a successful fetch.

    addEventListener('backgroundfetchsuccess', (event) => {
        event.updateUI({ title: 'Episode 5 ready to listen!', 'icon: {
          src: "path/to/success.ico",
          sizes: "16x16 32x32 64x64",
        }' });
      }());
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/background-fetch/#dom-backgroundfetchupdateuievent-updateui">Background Fetch<br />
<span class="small">The definition of 'updateUI()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`updateUI`

74

79

No

No

62

No

No

74

No

53

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchUpdateUIEvent/updateUI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BackgroundFetchUpdateUIEvent/updateUI</a>
