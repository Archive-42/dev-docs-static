# MouseEvent.region

The `MouseEvent.region` read-only property returns the id of the [canvas hit region](../canvasrenderingcontext2d/addhitregion) affected by the event. If no hit region is affected, `null` is returned.

## Syntax

    var hitRegion = instanceOfMouseEvent.region

### Return value

A [`DOMString`](../domstring) representing the id of the hit region.

## Example

Example of using the `event.region` combined with `CanvasRenderingContext2D.addHitRegion()` method.

    <canvas id="canvas"></canvas>

    <script>
    var canvas = document.getElementById("canvas");
    var ctx = canvas.getContext("2d");

    ctx.beginPath();
    ctx.arc(70, 80, 10, 0, 2 * Math.PI, false);
    ctx.fill();
    ctx.addHitRegion({id: "circle"});

    canvas.addEventListener("mousemove", function(event){
      if(event.region) {
        console.log("hit region: " + event.region);
      }
    });
    </script>

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

`region`

Yes

≤79

30

No

No

No

No

No

30

No

No

No

## See also

- [`MouseEvent`](../mouseevent)
- [`CanvasRenderingContext2D.addHitRegion()`](../canvasrenderingcontext2d/addhitregion)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/region" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/region</a>
