# Gamepad.axes

The `Gamepad.axes` property of the [`Gamepad`](../gamepad) interface returns an array representing the controls with axes present on the device (e.g. analog thumb sticks).

Each entry in the array is a floating point value in the range -1.0 – 1.0, representing the axis position from the lowest value (-1.0) to the highest value (1.0).

## Syntax

    readonly    attribute double[]            axes;

## Example

    function gameLoop() {
      if(navigator.webkitGetGamepads) {
        var gp = navigator.webkitGetGamepads()[0];
      } else {
        var gp = navigator.getGamepads()[0];
      }

      if(gp.axes[0] != 0) {
        b -= gp.axes[0];
      } else if(gp.axes[1] != 0) {
        a += gp.axes[1];
      } else if(gp.axes[2] != 0) {
        b += gp.axes[2];
      } else if(gp.axes[3] != 0) {
        a -= gp.axes[3];
      }

      ball.style.left = a*2 + "px";
      ball.style.top = b*2 + "px";

      var start = rAF(gameLoop);
    };

## Value

An array of <span class="page-not-created">`double`</span> values.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#dom-gamepad-axes">Gamepad<br />
<span class="small">The definition of 'Gamepad.axes' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`axes`

35

21-34

12

29

No

22

15-21

10.1

No

35

25-34

32

22

14-21

10.3

4.0

2.0-3.0

## See also

[Using the Gamepad API](../gamepad_api/using_the_gamepad_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/axes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad/axes</a>
