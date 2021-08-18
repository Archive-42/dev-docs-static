# Path2D()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Path2D()` constructor returns a newly instantiated `Path2D` object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of [SVG path](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths) data.

## Syntax

    new Path2D();
    new Path2D(path);
    new Path2D(d);

### Parameters

`path` <span class="badge inline optional">Optional</span>  
When invoked with another `Path2D` object, a copy of the `path` argument is created.

`d` <span class="badge inline optional">Optional</span>  
When invoked with a string consisting of [SVG path](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths) data, a new path is created from that description.

## Examples

### Creating and copying paths

This example creates and copies a `Path2D` path.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let path1 = new Path2D();
    path1.rect(10, 10, 100,100);

    let path2 = new Path2D(path1);
    path2.moveTo(220, 60);
    path2.arc(170, 60, 50, 0, 2 * Math.PI);

    ctx.stroke(path2);

### Using SVG paths

This example creates a `Path2D` path using [SVG path data](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths). The path will move to point (`M10 10`) and then move horizontally 80 points to the right (`h 80`), then 80 points down (`v 80`), then 80 points to the left (`h -80`), and then back to the start (`Z`).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let p = new Path2D('M10 10 h 80 v 80 h -80 Z');
    ctx.fill(p);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-path2d">HTML Living Standard<br />
<span class="small">The definition of 'Path2D()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Path2D`

36

14

Before Edge 79, the constructor for `Path2D` objects does not support invocation with a string consisting of SVG path data.

31

No

23

7

37

36

31

24

7

3.0

## See also

- [`Path2D`](../path2d), the interface this constructor belongs to

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Path2D/Path2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Path2D/Path2D</a>
