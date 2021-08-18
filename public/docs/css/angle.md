# &lt;angle&gt;

The `<angle>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents an angle value expressed in degrees, gradians, radians, or turns. It is used, for example, in [`<gradient>`](gradient)s and in some [`transform`](transform) functions.

## Syntax

The `<angle>` data type consists of a [`<number>`](number) followed by one of the units listed below. As with all dimensions, there is no space between the unit literal and the number. The angle unit is optional after the number `0`.

Optionally, it may be preceded by a single `+` or `-` sign. Positive numbers represent clockwise angles, while negative numbers represent counterclockwise angles. For static properties of a given unit, any angle can be represented by various equivalent values. For example, `90deg` equals `-270deg`, and `1turn` equals `4turn`. For dynamic properties, like when applying an [`animation`](animation) or [`transition`](transition), the effect will nevertheless be different.

### Units

`deg`  
Represents an angle in [degrees](https://en.wikipedia.org/wiki/Degree_%28angle%29). One full circle is `360deg`. Examples: `0deg`, `90deg`, `14.23deg`.

`grad`  
Represents an angle in [gradians](https://en.wikipedia.org/wiki/Gradian). One full circle is `400grad`. Examples: `0grad`, `100grad`, `38.8grad`.

`rad`  
Represents an angle in [radians](https://en.wikipedia.org/wiki/Radian). One full circle is 2π radians which approximates to `6.2832rad`. `1rad` is 180/π degrees. Examples: `0rad`, `1.0708rad`, `6.2832rad`.

`turn`  
Represents an angle in a number of turns. One full circle is `1turn`. Examples: `0turn`, `0.25turn`, `1.2turn`.

## Examples

### Setting a clockwise right angle

<table><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="default internal" width="113" height="111" /></td><td><code>90deg = 100grad = 0.25turn ≈ 1.5708rad</code></td></tr></tbody></table>

### Setting a flat angle

<table><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="default internal" width="111" height="115" /></td><td><code>180deg = 200grad = 0.5turn ≈ 3.1416rad</code></td></tr></tbody></table>

### Setting a counterclockwise right angle

<table><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="default internal" width="115" height="111" /></td><td><code>-90deg = -100grad = -0.25turn ≈ -1.5708rad</code></td></tr></tbody></table>

### Setting a null angle

<table><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAG8AAABvCAMAAADVG25SAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAADtUExURf///wkJCQ0NDff39wQEBAcHB/z8/AAAABtH92+O+f39/jIyMoWFhRQUFENDQ39/fywsLB8fHxsbG+/v7zk5OWlpaYuLiyMjIzU1NREREScnJ8vLy5GRkcHBweHh4fPz85+fn7Ozs+vr60hISLe3t9vb21JSUl9fX3Z2dry8vJmZmW9vb/Hx8fb29rCwsNLS0qurq1paWkVs+FV5+Pf5/2ZmZj4+PkxMTKWlpThi9yNQ9y1Z9+Dm/tTd/cjT/GOF+Q4mhrvJ/GxsbN7e3unp6Xt7e/P1/uru/ggVS7DA+sXFxcTExHiT8M7U6xArmNKNhFcAAAPDSURBVGje7dprd9o2GAfwx7bkP7XxBQj3kHALIRBy2ZK0uzZr6da1277/x5l7lp6TJsh6ZMs5e8HzCiTBD0nWxTJEBQP0srH39t7e23sVxd///HXzAszxh3gQOQDua7WPgNNvHKyPq8I6oQvZiJer0TR4Vav9OR2tlnFDwukm9rE3oUCavP/69ov38PJ9kgLNlVXtto/06nFC5v326O1VCue1Ne1aitvzb5OeeETnt0IcWNHWjkyCp4nPPKIgkWJRWps3RTt4npx5vz5LDNpwLspxM/TOd6Xv9LJW7WFQpnKR6vcqPKILKQtX8QN6G1J6v+zO2fRwWrQt68o8tUdUR7cIF4o5FfJoLvrmXNc5olzvZ3XuEZqmXCrzOI2XgY5pY+ZyOo+OpGvCxRrui/dHboEj0eBzS8yppEdzXLOHOTqk937XLZe4YnqRfqJneBQy9zix43E87f7F43XhBSbE8QJtoQneMLwmZ9nMPEapHqNF22JjzdtAv8lw1sTyfuQUa2sruHACi14gQk0J0SGLXrY25eefSmJ6P/EKirvcbHdt2cvvwRU8y56XOzemIXG9H5glB3kLE2dqMfQm8JV5iSDrHuFd+ebMvO/YGyH15sk9rMBTD8EtthV46m99x99UGXik3FgcDAy879llI9Wy23hdiXegmiPdeiXeUnXBiKtKvLHKw6WB95Zd9lLh+Qgq8QLFjHZicCZm4hFOdiZ/MvJeGXijR6+LxX3tvtDnHv+MkUH9bj7eFKtfwf4zOv9U9J9fmeeVHn8m3qWF+cXEU84vBvOnibdWlW0uKvF6qvUhHVTi9VWHMdduJR5UzXaCVgXeVDH8spCrCrwE5W6lTb2mW/puzMjLOQ71FTNrGS/v/oFz0mPqNZ3crZRv2fOxzL39TSx7p/kFe65lD6Gm+iurXqLroIFr1dMe1XtILHqn0D6NvBO+Nc8HY3zJmTWvyyl1iM+WvAlY9+dNN7Di+Yh4R0JiZsXrcg+rDjG24NXBPu2IMSztnSHmbzki2SrpTZmd9xCOOy3lbSFNuOya0dQQmtqxF7avF7OL88Jey5jLQCmHBb0RhEfm0c97PIK8gVDgcep/w2JWwBuYDISnA98dGnpn4A/zHZdpH7PAwPMH6HtUJjoQdbbXBjpUNnpwxiyvA4RkIVoNyHqg8fysbo0W2YnjFOgNc7xRF0it/nGqLSHCsbfD2xxmmGyT7TheONn3Nmads+2Dt53X7yIAzqKq/4QN40h8cx4monhIlcdwMsZ48gJQofOCvbf39t7/w/sXnrk/zUI/nPgAAAAASUVORK5CYII=" class="default internal" width="111" height="111" /></td><td><code>0 = 0deg = 0grad = 0turn = 0rad</code></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/#angles">CSS Values and Units Module Level 4<br />
<span class="small">The definition of '&lt;angle&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/#angles">CSS Values and Units Module Level 3<br />
<span class="small">The definition of '&lt;angle&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`angle`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`deg`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`grad`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`rad`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`turn`

2

12

13

9

15

4

2

18

14

14

3.2

1.0

## See also

- [CSS data types](css_types)
- The `<gradient>` type
- CSS rotation transforms: `rotate()`, `rotate3d()`, `rotateX()`, `rotateY()`, and `rotateZ()`
- [CSS transforms](css_transforms)
- [Using CSS transforms](css_transforms/using_css_transforms)
- [Using CSS gradients](css_images/using_css_gradients)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/angle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/angle</a>
