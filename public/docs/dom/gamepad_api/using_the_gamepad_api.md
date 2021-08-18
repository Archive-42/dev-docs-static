# Using the Gamepad API

HTML5 introduced many of the necessary components for rich, interactive game development. Technologies like `<canvas>`, WebGL, `<audio>`, and `<video>`, along with JavaScript implementations, have matured to the point where they can now support many tasks previously requiring native code. The Gamepad API is a way for developers and designers to access and use gamepads and other game controllers.

The [Gamepad API](../gamepad_api) introduces new events on the [`Window`](../window) object for reading gamepad and controller (hereby referred to as _gamepad_) state. In addition to these events, the API also adds a [`Gamepad`](../gamepad) object, which you can use to query the state of a connected gamepad, and a [`navigator.getGamepads()`](../navigator/getgamepads) method which you can use to get a list of gamepads known to the page.

## Connecting to a gamepad

When a new gamepad is connected to the computer, the focused page first receives a [`gamepadconnected`](../window/gamepadconnected_event) event. If a gamepad is already connected when the page loaded, the [`gamepadconnected`](../window/gamepadconnected_event) event is dispatched to the focused page when the user presses a button or moves an axis.

In Firefox, gamepads are only exposed to a page when the user interacts with one with the page visible. This helps prevent gamepads being used for fingerprinting the user. Once one gamepad has been interacted with, other gamepads that are connected will automatically be visible.

You can use [`gamepadconnected`](../window/gamepadconnected_event) like this:

    window.addEventListener("gamepadconnected", function(e) {
      console.log("Gamepad connected at index %d: %s. %d buttons, %d axes.",
        e.gamepad.index, e.gamepad.id,
        e.gamepad.buttons.length, e.gamepad.axes.length);
    });

Each gamepad has a unique ID associated with it, which is available on the event's [`gamepad`](../gamepadevent/gamepad) property.

## Disconnecting a gamepad

When a gamepad is disconnected, and if a page has previously received data for that gamepad (e.g. [`gamepadconnected`](../window/gamepadconnected_event)), a second event is dispatched to the focused window, `gamepaddisconnected`:

    window.addEventListener("gamepaddisconnected", function(e) {
      console.log("Gamepad disconnected from index %d: %s",
        e.gamepad.index, e.gamepad.id);
    });

The gamepad's [`index`](../gamepad/index) property will be unique per-device connected to the system, even if multiple controllers of the same type are used. The `index` property also functions as the index into the [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) returned by [`Navigator.getGamepads()`](../navigator/getgamepads).

    var gamepads = {};

    function gamepadHandler(event, connecting) {
      var gamepad = event.gamepad;
      // Note:
      // gamepad === navigator.getGamepads()[gamepad.index]

      if (connecting) {
        gamepads[gamepad.index] = gamepad;
      } else {
        delete gamepads[gamepad.index];
      }
    }

    window.addEventListener("gamepadconnected", function(e) { gamepadHandler(e, true); }, false);
    window.addEventListener("gamepaddisconnected", function(e) { gamepadHandler(e, false); }, false);

This previous example also demonstrates how the `gamepad` property can be held after the event has completed — a technique we will use for device state querying later.

## Querying the Gamepad object

As you can see, the **gamepad** events discussed above include a `gamepad` property on the event object, which returns a [`Gamepad`](../gamepad) object. We can use this in order to determine which gamepad (i.e., its ID) had caused the event, since multiple gamepads might be connected at once. We can do much more with the [`Gamepad`](../gamepad) object, including holding a reference to it and querying it to find out which buttons and axes are being pressed at any one time. Doing so is often desirable for games or other interactive web pages that need to know the state of a gamepad now vs. the next time an event fires.

Performing such checks tends to involve using the [`Gamepad`](../gamepad) object in conjunction with an animation loop (e.g., [`requestAnimationFrame`](../window/requestanimationframe)), where developers want to make decisions for the current frame based on the state of the gamepad or gamepads.

The [`Navigator.getGamepads()`](../navigator/getgamepads) method returns an array of all devices currently visible to the webpage, as [`Gamepad`](../gamepad) objects (the first value is always `null`, so `null` will be returned if there are no gamepads connected.) This can then be used to get the same information. For example, the first code example above you be rewritten as shown below:

    window.addEventListener("gamepadconnected", function(e) {
      var gp = navigator.getGamepads()[e.gamepad.index];
      console.log("Gamepad connected at index %d: %s. %d buttons, %d axes.",
        gp.index, gp.id,
        gp.buttons.length, gp.axes.length);
    });

The [`Gamepad`](../gamepad) object's properties are as follows:

- `id`: A string containing some information about the controller. This is not strictly specified, but in Firefox it will contain three pieces of information separated by dashes (`-`): two 4-digit hexadecimal strings containing the USB vendor and product id of the controller, and the name of the controller as provided by the driver. This information is intended to allow you to find a mapping for the controls on the device as well as display useful feedback to the user.
- `index`: An integer that is unique for each gamepad currently connected to the system. This can be used to distinguish multiple controllers. Note that disconnecting a device and then connecting a new device may reuse the previous index.
- `mapping`: A string indicating whether the browser has remapped the controls on the device to a known layout. Currently there is only one supported known layout — the [standard gamepad](https://dvcs.w3.org/hg/gamepad/raw-file/default/gamepad.html#remapping). If the browser is able to map controls on the device to that layout the `mapping` property will be set to the string `standard`.
- `connected`: A boolean indicating whether the gamepad is still connected to the system. If this is so the value is `True`; if not, it is `False`.
- `buttons`: An array of [`GamepadButton`](../gamepadbutton) objects representing the buttons present on the device. Each [`GamepadButton`](../gamepadbutton) has a `pressed` and a `value` property:
  - The `pressed` property is a boolean indicating whether the button is currently pressed (`true`) or unpressed (`false`).
  - The `value` property is a floating point value used to enable representing analog buttons, such as the triggers on many modern gamepads. The values are normalized to the range 0.0..1.0, with 0.0 representing a button that is not pressed, and 1.0 representing a button that is fully pressed.
- `axes`: An array representing the controls with axes present on the device (e.g. analog thumb sticks). Each entry in the array is a floating point value in the range -1.0 - 1.0, representing the axis position from the lowest value (-1.0) to the highest value (1.0).
- `timestamp`: This returns a [`DOMHighResTimeStamp`](../domhighrestimestamp) representing the last time the data for this gamepad was updated, allowing developers to determine if the `axes` and `button` data have been updated from the hardware. The value must be relative to the `navigationStart` attribute of the [`PerformanceTiming`](../performancetiming) interface. Values are monotonically increasing, meaning that they can be compared to determine the ordering of updates, as newer values will always be greater than or equal to older values. Note that this property is not currently supported in Firefox.

**Note**: The Gamepad object is available on the [`gamepadconnected`](../window/gamepadconnected_event) event rather than the [`Window`](../window) object itself, for security reasons. Once we have a reference to it, we can query its properties for information about the current state of the gamepad. Behind the scenes, this object will be updated every time the gamepad's state changes.

### Using button information

Let's look at a simple example that displays connection information for one gamepad (it ignores subsequent gamepad connections) and allows you to move a ball around the screen using the four gamepad buttons on the right hand side of the gamepad. You can [view the demo live](https://chrisdavidmills.github.io/gamepad-buttons/), and [find the source code](https://github.com/chrisdavidmills/gamepad-buttons/tree/master) on Github.

To start with, we declare some variables: The `gamepadInfo` paragraph that the connection info is written into, the `ball` that we want to move, the `start` variable that acts as the ID for `requestAnimation Frame`, the `a` and `b` variables that act as position modifiers for moving the ball, and the shorthand variables that will be used for the [`requestAnimationFrame()`](../window/requestanimationframe) and [`cancelAnimationFrame()`](../window/cancelanimationframe) cross browser forks.

    var gamepadInfo = document.getElementById("gamepad-info");
    var ball = document.getElementById("ball");
    var start;
    var a = 0;
    var b = 0;

Next we use the [`gamepadconnected`](../window/gamepadconnected_event) event to check for a gamepad being connected. When one is connected, we grab the gamepad using [`Navigator.getGamepads()`](../navigator/getgamepads)`[0]`, print information about the gamepad into our gamepad info `div`, and fire the `gameLoop()` function that starts the whole ball movement process up.

    window.addEventListener("gamepadconnected", function(e) {
      var gp = navigator.getGamepads()[e.gamepad.index];
      gamepadInfo.innerHTML = "Gamepad connected at index " + gp.index + ": " + gp.id + ". It has " + gp.buttons.length + " buttons and " + gp.axes.length + " axes.";

      gameLoop();
    });

Now we use the [`gamepaddisconnected`](../window/gamepaddisconnected_event) event to check if the gamepad is disconnected again. If so, we stop the [`requestAnimationFrame()`](../window/requestanimationframe) loop (see below) and revert the gamepad information back to what it was originally.

    window.addEventListener("gamepaddisconnected", function(e) {
      gamepadInfo.innerHTML = "Waiting for gamepad.";

      cancelRequestAnimationFrame(start);
    });

Chrome does things differently here. Instead of constantly storing the gamepad's latest state in a variable it only stores a snapshot, so to do the same thing in Chrome you have to keep polling it and then only use the [`Gamepad`](../gamepad) object in code when it is available. We have done this below using [`WindowOrWorkerGlobalScope.setInterval`](../windoworworkerglobalscope/setinterval); once the object is available the gamepad info is outputted, the game loop is started, and the interval is cleared using [`WindowOrWorkerGlobalScope.clearInterval`](../windoworworkerglobalscope/clearinterval). Note that in older versions of Chrome [`Navigator.getGamepads()`](../navigator/getgamepads) is implemented with a `webkit` prefix. We attempt to detect and handle both the prefixed version and the standard version of the function for backwards compatibility.

    var interval;

    if (!('ongamepadconnected' in window)) {
      // No gamepad events available, poll instead.
      interval = setInterval(pollGamepads, 500);
    }

    function pollGamepads() {
      var gamepads = navigator.getGamepads ? navigator.getGamepads() : (navigator.webkitGetGamepads ? navigator.webkitGetGamepads : []);
      for (var i = 0; i < gamepads.length; i++) {
        var gp = gamepads[i];
        if (gp) {
          gamepadInfo.innerHTML = "Gamepad connected at index " + gp.index + ": " + gp.id +
            ". It has " + gp.buttons.length + " buttons and " + gp.axes.length + " axes.";
          gameLoop();
          clearInterval(interval);
        }
      }
    }

Now on to the main game loop. In each execution of the loop we check if one of four buttons is being pressed; if so, we update the values of the `a` and `b` movement variables appropriately, then update the [`left`](https://developer.mozilla.org/en-US/docs/Web/CSS/left) and [`top`](https://developer.mozilla.org/en-US/docs/Web/CSS/top) properties, changing their values to the current values of `a` and `b` respectively. This has the effect of moving the ball around the screen. In current versions of Chrome (version 34 as of this writing) the button values are stored as an array of double values, instead of [`GamepadButton`](../gamepadbutton) objects. This is fixed in development versions.

After all this is done, we use our `requestAnimationFrame()` to request the next animation frame, running `gameLoop()` again.

    function buttonPressed(b) {
      if (typeof(b) == "object") {
        return b.pressed;
      }
      return b == 1.0;
    }

    function gameLoop() {
      var gamepads = navigator.getGamepads ? navigator.getGamepads() : (navigator.webkitGetGamepads ? navigator.webkitGetGamepads : []);
      if (!gamepads) {
        return;
      }

      var gp = gamepads[0];
      if (buttonPressed(gp.buttons[0])) {
        b--;
      } else if (buttonPressed(gp.buttons[2])) {
        b++;
      }
      if (buttonPressed(gp.buttons[1])) {
        a++;
      } else if (buttonPressed(gp.buttons[3])) {
        a--;
      }

      ball.style.left = a * 2 + "px";
      ball.style.top = b * 2 + "px";

      start = requestAnimationFrame(gameLoop);
    }

## Complete example: Displaying gamepad state

This example shows how to use the [`Gamepad`](../gamepad) object, as well as the [`gamepadconnected`](../window/gamepadconnected_event) and [`gamepaddisconnected`](../window/gamepaddisconnected_event) events in order to display the state of all gamepads connected to the system. You can find a [working demo](https://luser.github.io/gamepadtest/) and look at the [full source code](https://github.com/luser/gamepadtest) on Github.

    var haveEvents = 'ongamepadconnected' in window;
    var controllers = {};

    function connecthandler(e) {
      addgamepad(e.gamepad);
    }

    function addgamepad(gamepad) {
      controllers[gamepad.index] = gamepad;

      var d = document.createElement("div");
      d.setAttribute("id", "controller" + gamepad.index);

      var t = document.createElement("h1");
      t.appendChild(document.createTextNode("gamepad: " + gamepad.id));
      d.appendChild(t);

      var b = document.createElement("div");
      b.className = "buttons";
      for (var i = 0; i < gamepad.buttons.length; i++) {
        var e = document.createElement("span");
        e.className = "button";
        //e.id = "b" + i;
        e.innerHTML = i;
        b.appendChild(e);
      }

      d.appendChild(b);

      var a = document.createElement("div");
      a.className = "axes";

      for (var i = 0; i < gamepad.axes.length; i++) {
        var p = document.createElement("progress");
        p.className = "axis";
        //p.id = "a" + i;
        p.setAttribute("max", "2");
        p.setAttribute("value", "1");
        p.innerHTML = i;
        a.appendChild(p);
      }

      d.appendChild(a);

      // See https://github.com/luser/gamepadtest/blob/master/index.html
      var start = document.getElementById("start");
      if (start) {
        start.style.display = "none";
      }

      document.body.appendChild(d);
      requestAnimationFrame(updateStatus);
    }

    function disconnecthandler(e) {
      removegamepad(e.gamepad);
    }

    function removegamepad(gamepad) {
      var d = document.getElementById("controller" + gamepad.index);
      document.body.removeChild(d);
      delete controllers[gamepad.index];
    }

    function updateStatus() {
      if (!haveEvents) {
        scangamepads();
      }

      var i = 0;
      var j;

      for (j in controllers) {
        var controller = controllers[j];
        var d = document.getElementById("controller" + j);
        var buttons = d.getElementsByClassName("button");

        for (i = 0; i < controller.buttons.length; i++) {
          var b = buttons[i];
          var val = controller.buttons[i];
          var pressed = val == 1.0;
          if (typeof(val) == "object") {
            pressed = val.pressed;
            val = val.value;
          }

          var pct = Math.round(val * 100) + "%";
          b.style.backgroundSize = pct + " " + pct;

          if (pressed) {
            b.className = "button pressed";
          } else {
            b.className = "button";
          }
        }

        var axes = d.getElementsByClassName("axis");
        for (i = 0; i < controller.axes.length; i++) {
          var a = axes[i];
          a.innerHTML = i + ": " + controller.axes[i].toFixed(4);
          a.setAttribute("value", controller.axes[i] + 1);
        }
      }

      requestAnimationFrame(updateStatus);
    }

    function scangamepads() {
      var gamepads = navigator.getGamepads ? navigator.getGamepads() : (navigator.webkitGetGamepads ? navigator.webkitGetGamepads() : []);
      for (var i = 0; i < gamepads.length; i++) {
        if (gamepads[i]) {
          if (gamepads[i].index in controllers) {
            controllers[gamepads[i].index] = gamepads[i];
          } else {
            addgamepad(gamepads[i]);
          }
        }
      }
    }

    window.addEventListener("gamepadconnected", connecthandler);
    window.addEventListener("gamepaddisconnected", disconnecthandler);

    if (!haveEvents) {
     setInterval(scangamepads, 500);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/gamepad/#gamepad-interface">Gamepad<br />
<span class="small">The definition of 'Gamepad' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Using_the_Gamepad_API`

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

`buttons`

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

`connected`

35

25-34

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

`displayId`

55-80

Only works on desktop in an [experimental version of Chrome](https://webvr.info/get-chrome/) (other builds won't return any devices when `Navigator.getVRDisplays()` is invoked).

79-80

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

55-80

Currently supported only by Google Daydream.

55

?

No

6.0-13.0

Currently supported only by Google Daydream.

`hand`

No

15-79

55

No

No

No

No

No

55

No

No

No

`hapticActuators`

No

15-79

55

No

No

No

No

No

55

No

No

No

`id`

35

21-34

12

29

No

22

15-21

No

No

35

25-34

32

22

14-21

No

4.0

2.0-3.0

`index`

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

`mapping`

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

`pose`

No

15-79

55

No

No

No

No

No

55

No

No

No

`timestamp`

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

`vibrationActuator`

68

79

No

No

55

No

No

68

No

48

No

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API/Using_the_Gamepad_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API/Using_the_Gamepad_API</a>
