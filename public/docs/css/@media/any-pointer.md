# any-pointer

The `any-pointer` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) tests whether the user has _any_ pointing device (such as a mouse), and if so, how accurate it is.

**Note:** If you want to test the accuracy of the _primary_ pointing device, use `pointer` instead.

## Syntax

The `any-pointer` feature is specified as a keyword value chosen from the list below.

`none`  
No pointing device is available.

`coarse`  
At least one input mechanism includes a pointing device of limited accuracy.

`fine`  
At least one input mechanism includes an accurate pointing device.

**Note:** More than one value can match if the available devices have different characteristics, although `none` only matches when none of them are pointing devices.

## Examples

This example creates a small checkbox for users with at least one fine pointer and a large checkbox for users with at least one coarse pointer. The big checkbox takes precedence because it is declared after the small one.

### HTML

    <input id="test" type="checkbox" />
    <label for="test">Look at me!</label>

### CSS

    input[type="checkbox"]:checked {
      background: gray;
    }

    @media (any-pointer: fine) {
      input[type="checkbox"] {
        -moz-appearance: none;
        -webkit-appearance: none;
        appearance: none;
        width: 15px;
        height: 15px;
        border: 1px solid blue;
      }
    }

    @media (any-pointer: coarse) {
      input[type="checkbox"] {
        -moz-appearance: none;
        -webkit-appearance: none;
        appearance: none;
        width: 30px;
        height: 30px;
        border: 2px solid red;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#descdef-media-any-pointer">Media Queries Level 4<br />
<span class="small">The definition of 'any-pointer' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`any-pointer`

41

12

64

No

28

9

41

41

64

28

9

4.0

## See also

- [The `pointer` media feature](pointer)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-pointer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/any-pointer</a>
