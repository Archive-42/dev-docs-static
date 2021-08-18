# pointer

The `pointer` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) tests whether the user has a pointing device (such as a mouse), and if so, how accurate the _primary_ pointing device is.

**Note:** If you want to test the accuracy of _any_ pointing device, use `any-pointer` instead.

## Syntax

The `pointer` feature is specified as a keyword value chosen from the list below.

`none`  
The primary input mechanism does not include a pointing device.

`coarse`  
The primary input mechanism includes a pointing device of limited accuracy.

`fine`  
The primary input mechanism includes an accurate pointing device.

## Examples

This example creates a small checkbox for users with fine primary pointers and a large checkbox for users with coarse primary pointers.

### HTML

    <input id="test" type="checkbox" />
    <label for="test">Look at me!</label>

### CSS

    input[type="checkbox"] {
      -moz-appearance: none;
      -webkit-appearance: none;
      appearance: none;
      border: solid;
      margin: 0;
    }

    input[type="checkbox"]:checked {
      background: gray;
    }

    @media (pointer: fine) {
      input[type="checkbox"] {
        width: 15px;
        height: 15px;
        border-width: 1px;
        border-color: blue;
      }
    }

    @media (pointer: coarse) {
      input[type="checkbox"] {
        width: 30px;
        height: 30px;
        border-width: 2px;
        border-color: red;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#pointer">Media Queries Level 4<br />
<span class="small">The definition of 'pointer' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pointer`

41

12

64

No

28

9

41

50

64

28

9

5.0

## See also

- [The `any-pointer` media feature](any-pointer)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/pointer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/pointer</a>
