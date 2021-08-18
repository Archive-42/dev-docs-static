# EffectTiming.easing

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`EffectTiming`](../effecttiming) dictionary's `easing` property in the [Web Animations API](../web_animations_api) specifies the timing function used to scale the time to produce easing effects, where _easing_ is the rate of the animation's change over time.

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `easing`. The value of easing corresponds directly to <span class="page-not-created">`AnimationEffectTimingReadOnly.easing`</span> in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffect`](../animationeffect), [`KeyframeEffect`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

## Syntax

    var timingProperties = {
      easing: <easing-function>
    }

    timingProperties.easing = <easing-function>

### Value

A string defining the timing function to use for easing transitions during the animation process. Accepts several pre-defined [`DOMString`](../domstring) values, a `steps()` timing function like `steps(5, end)`, or a custom `cubic-bezier` value like `cubic-bezier(0.42, 0, 0.58, 1)`. Defaults to `linear`. Available values include:

`linear`  
A constant rate of change, neither accelerating nor deccelerating.

`cubic-bezier(<number>, <number>, <number>, <number>)`  
<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MzUgNTEwIiBzdHlsZT0iZm9udC1zaXplOjIzcHg7Zm9udC1mYW1pbHk6c2Fucy1zZXJpZiI+PGRlZnM+PHN0eWxlPi5heGlzLC50aWNrTWFya3tzdHJva2U6IzAwMDtzdHJva2Utd2lkdGg6MS41O2ZpbGw6bm9uZTtzdHJva2UtbGluZWNhcDpzcXVhcmV9LmNvbnRyb2xQb2ludHtmaWxsOiNmZmY7c3Ryb2tlOiMwMDA7c3Ryb2tlLXdpZHRoOjN9LmhhbmRsZUxpbmV7ZmlsbDpub25lO3N0cm9rZTojMDAwO3N0cm9rZS13aWR0aDoyfS5heGlzTGFiZWx7dGV4dC1hbmNob3I6bWlkZGxlfS5heGlzVmFsdWV7ZmlsbDpncmF5fS5heGlzVmFsdWUudmVydHt0ZXh0LWFuY2hvcjplbmR9LmF4aXNWYWx1ZS5ob3J6e3RleHQtYW5jaG9yOm1pZGRsZX0ucG9pbnRMYWJlbHtmaWxsOiMwMDA7Zm9udC1zaXplOjI1cHh9PC9zdHlsZT48L2RlZnM+PGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTEwIDQyMCkiPjxwYXRoIHN0eWxlPSJzdHJva2U6bm9uZTtmaWxsOiNmZmYiIGQ9Ik0wLTQwMGg0MDBWMEgweiIvPjxwYXRoIGQ9Ik00MDAgMHYtNDAwTTAtNDAwaDQwMCIgc3R5bGU9InN0cm9rZTpncmF5O3N0cm9rZS13aWR0aDoxLjU7c3Ryb2tlLWRhc2hhcnJheTozIDQ7ZmlsbDpub25lIi8+PHBhdGggY2xhc3M9ImF4aXMiIGQ9Ik0wIDB2LTQwMCIvPjxwYXRoIGNsYXNzPSJ0aWNrTWFyayIgZD0iTTAtMjAwaC0yME0wLTQwMGgtMjAiLz48dGV4dCB4PSItMzAiIHk9Ii0yMDAiIGR5PSIuM2VtIiBjbGFzcz0iYXhpc1ZhbHVlIHZlcnQiPjAuNTwvdGV4dD48dGV4dCB4PSItMzAiIHk9Ii00MDAiIGR5PSIuM2VtIiBjbGFzcz0iYXhpc1ZhbHVlIHZlcnQiPjE8L3RleHQ+PHRleHQgeD0iMjAwIiB5PSItODAiIGNsYXNzPSJheGlzTGFiZWwiIHRyYW5zZm9ybT0icm90YXRlKC05MCkiPk91dHB1dCBwcm9ncmVzczwvdGV4dD48cGF0aCBjbGFzcz0iYXhpcyIgZD0iTTAgMGg0MDAiLz48cGF0aCBjbGFzcz0idGlja01hcmsiIGQ9Ik0yMDAgMHYyME00MDAgMHYyMCIvPjx0ZXh0IHg9IjIwMCIgeT0iMjAiIGR5PSIxLjFlbSIgY2xhc3M9ImF4aXNWYWx1ZSBob3J6Ij4wLjU8L3RleHQ+PHRleHQgeD0iNDAwIiB5PSIyMCIgZHk9IjEuMWVtIiBjbGFzcz0iYXhpc1ZhbHVlIGhvcnoiPjE8L3RleHQ+PHRleHQgeD0iMjAwIiB5PSI4MCIgY2xhc3M9ImF4aXNMYWJlbCI+SW5wdXQgcHJvZ3Jlc3M8L3RleHQ+PHRleHQgeD0iLTI1IiB5PSIyNSIgY2xhc3M9ImF4aXNWYWx1ZSI+MDwvdGV4dD48cGF0aCBjbGFzcz0iaGFuZGxlTGluZSIgZD0ibTAgMCAyNDAtNDAiLz48Y2lyY2xlIGN4PSIyNDAiIGN5PSItNDAiIHI9IjEwIiBjbGFzcz0iY29udHJvbFBvaW50Ii8+PHRleHQgeD0iMjYwIiB5PSItNDAiIGR5PSIuNGVtIiBjbGFzcz0icG9pbnRMYWJlbCI+UDE8L3RleHQ+PHBhdGggY2xhc3M9ImhhbmRsZUxpbmUiIGQ9Ik00MDAtNDAwIDgwLTI4MCIvPjxjaXJjbGUgY3g9IjgwIiBjeT0iLTI4MCIgcj0iMTAiIGNsYXNzPSJjb250cm9sUG9pbnQiLz48dGV4dCB4PSI2MCIgeT0iLTI4MCIgZHk9Ii40ZW0iIGNsYXNzPSJwb2ludExhYmVsIiB0ZXh0LWFuY2hvcj0iZW5kIj5QMjwvdGV4dD48cGF0aCBkPSJNMCAwYzI0MC00MCA4MC0yODAgNDAwLTQwMCIgc3R5bGU9ImZpbGw6bm9uZTtzdHJva2U6IzAwZjtzdHJva2Utd2lkdGg6NztzdHJva2UtbGluZWNhcDpyb3VuZCIvPjxjaXJjbGUgcj0iMTAiIGNsYXNzPSJjb250cm9sUG9pbnQiLz48dGV4dCB4PSItMTAiIHk9Ii0yMCIgZHk9Ii40ZW0iIGNsYXNzPSJwb2ludExhYmVsIiB0ZXh0LWFuY2hvcj0iZW5kIj5QMDwvdGV4dD48Y2lyY2xlIGN4PSI0MDAiIGN5PSItNDAwIiByPSIxMCIgY2xhc3M9ImNvbnRyb2xQb2ludCIvPjx0ZXh0IHg9IjM5NSIgeT0iLTM3NSIgZHk9Ii40ZW0iIGNsYXNzPSJwb2ludExhYmVsIiB0ZXh0LWFuY2hvcj0iZW5kIj5QMzwvdGV4dD48L2c+PC9zdmc+" alt="A diagram showing the points of a cubic bezier timing function." width="535" height="510" />  
Specifies [a cubic Bézier timing function](https://w3c.github.io/web-animations/#cubic-bzier-timing-function). The four numbers specify points P1 and P2 of the curve as (x1, y1, x2, y2). Both x values must be in the range \[0, 1\] or the definition is invalid.

`ease`  
A decelerated rate of change, going from fast to slow. Equivalent to `cubic-bezier(0.25, 0.1, 0.25, 1)`.

`ease-in`  
An accelerated rate of change, going from slow to fast. Equivalent to `cubic-bezier(0.42, 0, 1, 1)`.

`ease-out`  
Another decelerated rate of change, going from fast to slow. Equivalent to `cubic-bezier(0, 0, 0.58, 1)`.

`ease-in-out`  
This rate of change speeds up in the middle. Equivalent to `cubic-bezier(0.42, 0, 0.58, 1)`.

`steps(<integer>[, [ start | end ] ]?)`  
<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB2aWV3Qm94PSIwIDAgMzEwIDM4MCIgc3R5bGU9ImZvbnQtc2l6ZToxNXB4O2ZvbnQtZmFtaWx5OnNhbnMtc2VyaWYiPjxkZWZzPjxzdHlsZT4uYXhpcywudGlja01hcmt7c3Ryb2tlOiMwMDA7c3Ryb2tlLXdpZHRoOjEuMjtmaWxsOm5vbmU7c3Ryb2tlLWxpbmVjYXA6c3F1YXJlfS5jdXJ2ZSwuZG90dGVke2ZpbGw6bm9uZTtzdHJva2U6IzAwZjtzdHJva2Utd2lkdGg6MztzdHJva2UtbGluZWNhcDpyb3VuZH0uZG90dGVke3N0cm9rZS13aWR0aDoxLjU7c3Ryb2tlLWRhc2hhcnJheToyIDZ9LmZpbGxlZEVuZFBvaW50e2ZpbGw6IzAwZjtzdHJva2U6bm9uZX0ub3BlbkVuZFBvaW50e2ZpbGw6bm9uZTtzdHJva2U6IzAwZjtzdHJva2Utd2lkdGg6MS41fS5saW5lS25vY2tvdXR7ZmlsbDpub25lO3N0cm9rZTojNTU1O3N0cm9rZS13aWR0aDoyfS5jaXJjbGVLbm9ja291dHtmaWxsOiM1NTU7c3Ryb2tlOm5vbmV9LmF4aXNWYWx1ZXtmaWxsOmdyYXl9LmF4aXNWYWx1ZS52ZXJ0e3RleHQtYW5jaG9yOmVuZH0uYXhpc1ZhbHVlLmhvcnosLnBhcmFtTGFiZWx7dGV4dC1hbmNob3I6bWlkZGxlfS5wYXJhbUxhYmVse2ZvbnQtc2l6ZToxNXB4fTwvc3R5bGU+PGcgaWQ9ImdyYXBoIiBzdHlsZT0iZm9udC1zaXplOjEwcHgiPjxwYXRoIHN0eWxlPSJzdHJva2U6bm9uZTtmaWxsOiNmZmYiIGQ9Ik0wLTEwMGgxMDBWMEgweiIvPjxwYXRoIGNsYXNzPSJheGlzIiBkPSJNMCAwdi0xMDAiLz48cGF0aCBjbGFzcz0idGlja01hcmsiIGQ9Ik0wLTUwaC01bTUtNTBoLTUiLz48dGV4dCB4PSItOSIgeT0iLTUwIiBkeT0iLjNlbSIgY2xhc3M9ImF4aXNWYWx1ZSB2ZXJ0Ij4wLjU8L3RleHQ+PHRleHQgeD0iLTkiIHk9Ii0xMDAiIGR5PSIuM2VtIiBjbGFzcz0iYXhpc1ZhbHVlIHZlcnQiPjE8L3RleHQ+PHBhdGggY2xhc3M9ImF4aXMiIGQ9Ik0wIDBoMTAwIi8+PHBhdGggY2xhc3M9InRpY2tNYXJrIiBkPSJNNTAgMHY1bTUwLTV2NSIvPjx0ZXh0IHg9IjUwIiB5PSI3LjUiIGR5PSIxLjFlbSIgY2xhc3M9ImF4aXNWYWx1ZSBob3J6Ij4wLjU8L3RleHQ+PHRleHQgeD0iMTAwIiB5PSI3LjUiIGR5PSIxLjFlbSIgY2xhc3M9ImF4aXNWYWx1ZSBob3J6Ij4xPC90ZXh0Pjx0ZXh0IHg9Ii0uNWVtIiB5PSIxZW0iIGNsYXNzPSJheGlzVmFsdWUiIHRleHQtYW5jaG9yPSJlbmQiPjA8L3RleHQ+PC9nPjwvZGVmcz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzMCAxMTApIj48ZGVmcz48bWFzayBpZD0ic3RlcDFTdGFydEdyaWRNYXNrIiBtYXNrVW5pdHM9InVzZXJTcGFjZU9uVXNlIiB4PSItMzAiIHk9Ii0xMTAiIHdpZHRoPSIxMzUiIGhlaWdodD0iMTM1Ij48cmVjdCB4PSItMzAiIHk9Ii0xMTAiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9IiNmZmYiLz48cGF0aCBkPSJNMCAwdi0xMDAiIGNsYXNzPSJsaW5lS25vY2tvdXQiLz48Y2lyY2xlIHI9IjMiIGNsYXNzPSJjaXJjbGVLbm9ja291dCIvPjwvbWFzaz48bWFzayBpZD0ic3RlcDFTdGFydExpbmVNYXNrIj48cGF0aCBmaWxsPSIjZmZmIiBkPSJNLTUtMTA1aDExMFY1SC01eiIvPjxjaXJjbGUgcj0iMyIvPjwvbWFzaz48L2RlZnM+PHVzZSB4bGluazpocmVmPSIjZ3JhcGgiIG1hc2s9InVybCgjc3RlcDFTdGFydEdyaWRNYXNrKSIvPjxnIG1hc2s9InVybCgjc3RlcDFTdGFydExpbmVNYXNrKSI+PHBhdGggZD0iTTAtMTAwaDEwMCIgY2xhc3M9ImN1cnZlIi8+PHBhdGggZD0iTTAgMHYtMTAwIiBjbGFzcz0iZG90dGVkIi8+PC9nPjxjaXJjbGUgcj0iMyIgY2xhc3M9Im9wZW5FbmRQb2ludCIvPjxjaXJjbGUgY3k9Ii0xMDAiIHI9IjMuNSIgY2xhc3M9ImZpbGxlZEVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iMTAwIiBjeT0iLTEwMCIgcj0iMy41IiBjbGFzcz0iZmlsbGVkRW5kUG9pbnQiLz48dGV4dCB4PSI1MCIgeT0iNDAiIGNsYXNzPSJwYXJhbUxhYmVsIj5zdGVwczogMTx0c3BhbiB4PSI1MCIgZHk9IjFlbSI+cG9zaXRpb246IHN0YXJ0PC90c3Bhbj48L3RleHQ+PC9nPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIwMCAxMTApIj48ZGVmcz48bWFzayBpZD0ic3RlcDFFbmRHcmlkTWFzayIgbWFza1VuaXRzPSJ1c2VyU3BhY2VPblVzZSIgeD0iLTMwIiB5PSItMTEwIiB3aWR0aD0iMTM1IiBoZWlnaHQ9IjEzNSI+PHJlY3QgeD0iLTMwIiB5PSItMTEwIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjZmZmIi8+PGNpcmNsZSBjeD0iMTAwIiByPSIzIiBjbGFzcz0iY2lyY2xlS25vY2tvdXQiLz48L21hc2s+PG1hc2sgaWQ9InN0ZXAxRW5kTGluZU1hc2siPjxwYXRoIGZpbGw9IiNmZmYiIGQ9Ik0tNS0xMDVoMTEwVjVILTV6Ii8+PGNpcmNsZSBjeD0iMTAwIiByPSIzIi8+PC9tYXNrPjwvZGVmcz48dXNlIHhsaW5rOmhyZWY9IiNncmFwaCIgbWFzaz0idXJsKCNzdGVwMUVuZEdyaWRNYXNrKSIvPjxnIG1hc2s9InVybCgjc3RlcDFFbmRMaW5lTWFzaykiPjxwYXRoIGQ9Ik0wIDBoMTAwIiBjbGFzcz0iY3VydmUiLz48cGF0aCBkPSJNMTAwIDB2LTEwMCIgY2xhc3M9ImRvdHRlZCIvPjwvZz48Y2lyY2xlIHI9IjMuNSIgY2xhc3M9ImZpbGxlZEVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iMTAwIiByPSIzIiBjbGFzcz0ib3BlbkVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iMTAwIiBjeT0iLTEwMCIgcj0iMy41IiBjbGFzcz0iZmlsbGVkRW5kUG9pbnQiLz48dGV4dCB4PSI1MCIgeT0iNDAiIGNsYXNzPSJwYXJhbUxhYmVsIj5zdGVwczogMTx0c3BhbiB4PSI1MCIgZHk9IjFlbSI+cG9zaXRpb246IGVuZDwvdHNwYW4+PC90ZXh0PjwvZz48ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzMCAzMjApIj48ZGVmcz48bWFzayBpZD0ic3RlcDNTdGFydEdyaWRNYXNrIiBtYXNrVW5pdHM9InVzZXJTcGFjZU9uVXNlIiB4PSItMzAiIHk9Ii0xMTAiIHdpZHRoPSIxMzUiIGhlaWdodD0iMTM1Ij48cmVjdCB4PSItMzAiIHk9Ii0xMTAiIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9IiNmZmYiLz48cGF0aCBkPSJNMCAwdi0zMy4zIiBjbGFzcz0ibGluZUtub2Nrb3V0Ii8+PGNpcmNsZSByPSIzIiBjbGFzcz0iY2lyY2xlS25vY2tvdXQiLz48L21hc2s+PG1hc2sgaWQ9InN0ZXAzU3RhcnRMaW5lTWFzayI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTS01LTEwNWgxMTBWNUgtNXoiLz48Y2lyY2xlIHI9IjMiLz48Y2lyY2xlIGN4PSIzMy4zIiBjeT0iLTMzLjMiIHI9IjMiLz48Y2lyY2xlIGN4PSI2Ni42IiBjeT0iLTY2LjYiIHI9IjMiLz48L21hc2s+PC9kZWZzPjx1c2UgeGxpbms6aHJlZj0iI2dyYXBoIiBtYXNrPSJ1cmwoI3N0ZXAzU3RhcnRHcmlkTWFzaykiLz48ZyBtYXNrPSJ1cmwoI3N0ZXAzU3RhcnRMaW5lTWFzaykiPjxwYXRoIGQ9Ik0wLTMzLjNoMzMuM20wLTMzLjNoMzMuM20wLTMzLjRIMTAwIiBjbGFzcz0iY3VydmUiLz48cGF0aCBkPSJNMCAwdi0zMy4zbTMzLjMgMHYtMzMuM20zMy4zIDBWLTEwMCIgY2xhc3M9ImRvdHRlZCIvPjwvZz48Y2lyY2xlIHI9IjMiIGNsYXNzPSJvcGVuRW5kUG9pbnQiLz48Y2lyY2xlIGN5PSItMzMuMyIgcj0iMy41IiBjbGFzcz0iZmlsbGVkRW5kUG9pbnQiLz48Y2lyY2xlIGN4PSIzMy4zIiBjeT0iLTMzLjMiIHI9IjMiIGNsYXNzPSJvcGVuRW5kUG9pbnQiLz48Y2lyY2xlIGN4PSIzMy4zIiBjeT0iLTY2LjYiIHI9IjMuNSIgY2xhc3M9ImZpbGxlZEVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iNjYuNiIgY3k9Ii02Ni42IiByPSIzIiBjbGFzcz0ib3BlbkVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iNjYuNiIgY3k9Ii0xMDAiIHI9IjMuNSIgY2xhc3M9ImZpbGxlZEVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iMTAwIiBjeT0iLTEwMCIgcj0iMy41IiBjbGFzcz0iZmlsbGVkRW5kUG9pbnQiLz48dGV4dCB4PSI1MCIgeT0iNDAiIGNsYXNzPSJwYXJhbUxhYmVsIj5zdGVwczogMzx0c3BhbiB4PSI1MCIgZHk9IjFlbSI+cG9zaXRpb246IHN0YXJ0PC90c3Bhbj48L3RleHQ+PC9nPjxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIwMCAzMjApIj48ZGVmcz48bWFzayBpZD0ic3RlcDNFbmRHcmlkTWFzayIgbWFza1VuaXRzPSJ1c2VyU3BhY2VPblVzZSIgeD0iLTMwIiB5PSItMTEwIiB3aWR0aD0iMTM1IiBoZWlnaHQ9IjEzNSI+PHJlY3QgeD0iLTMwIiB5PSItMTEwIiB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjZmZmIi8+PGNpcmNsZSBjeD0iMzMuMyIgcj0iMyIgY2xhc3M9ImNpcmNsZUtub2Nrb3V0Ii8+PC9tYXNrPjxtYXNrIGlkPSJzdGVwM0VuZExpbmVNYXNrIj48cGF0aCBmaWxsPSIjZmZmIiBkPSJNLTUtMTA1aDExMFY1SC01eiIvPjxjaXJjbGUgY3g9IjMzLjMiIHI9IjMiLz48Y2lyY2xlIGN4PSI2Ni42IiBjeT0iLTMzLjMiIHI9IjMiLz48Y2lyY2xlIGN4PSIxMDAiIGN5PSItNjYuNiIgcj0iMyIvPjwvbWFzaz48L2RlZnM+PHVzZSB4bGluazpocmVmPSIjZ3JhcGgiIG1hc2s9InVybCgjc3RlcDNFbmRHcmlkTWFzaykiLz48ZyBtYXNrPSJ1cmwoI3N0ZXAzRW5kTGluZU1hc2spIj48cGF0aCBkPSJNMCAwaDMzLjNtMC0zMy4zaDMzLjNtMC0zMy4zSDEwMCIgY2xhc3M9ImN1cnZlIi8+PHBhdGggZD0iTTMzLjMgMHYtMzMuM2gzMy4zdi0zMy4zbTMzLjQgMFYtMTAwIiBjbGFzcz0iZG90dGVkIi8+PC9nPjxjaXJjbGUgcj0iMy41IiBjbGFzcz0iZmlsbGVkRW5kUG9pbnQiLz48Y2lyY2xlIGN4PSIzMy4zIiByPSIzIiBjbGFzcz0ib3BlbkVuZFBvaW50Ii8+PGNpcmNsZSBjeD0iMzMuMyIgY3k9Ii0zMy4zIiByPSIzLjUiIGNsYXNzPSJmaWxsZWRFbmRQb2ludCIvPjxjaXJjbGUgY3g9IjY2LjYiIGN5PSItMzMuMyIgcj0iMyIgY2xhc3M9Im9wZW5FbmRQb2ludCIvPjxjaXJjbGUgY3g9IjY2LjYiIGN5PSItNjYuNiIgcj0iMy41IiBjbGFzcz0iZmlsbGVkRW5kUG9pbnQiLz48Y2lyY2xlIGN4PSIxMDAiIGN5PSItNjYuNiIgcj0iMyIgY2xhc3M9Im9wZW5FbmRQb2ludCIvPjxjaXJjbGUgY3g9IjEwMCIgY3k9Ii0xMDAiIHI9IjMuNSIgY2xhc3M9ImZpbGxlZEVuZFBvaW50Ii8+PHRleHQgeD0iNTAiIHk9IjQwIiBjbGFzcz0icGFyYW1MYWJlbCI+c3RlcHM6IDM8dHNwYW4geD0iNTAiIGR5PSIxZW0iPnBvc2l0aW9uOiBlbmQ8L3RzcGFuPjwvdGV4dD48L2c+PC9zdmc+" alt="A diagram of the various steps timing functions." width="310" height="380" />  
Specifies [a step timing function](https://w3c.github.io/web-animations/#step-timing-function), which breaks the animation down into a number of equal time intervals. The browser flips to a different static frame when each interval is reached, rather than animating smoothly. The first parameter specifies the number of intervals in the function. It must be a positive integer (greater than 0). The second parameter, which is optional, specifies the point at which the change of values occur within the interval. If the second parameter is omitted, it is given the value end.

`step-start`  
Equivalent to `steps(1, start)`

`step-end`  
Equivalent to `steps(1, end)`.

## Examples

In the [Red Queen's Race](https://codepen.io/rachelnabors/pen/PNGGaV?editors=0010) example, we animate Alice and the Red Queen by passing an easing `of steps(7, end)` to `animate()`:

    // Define the key frames
    var spriteFrames = [
      { transform: 'translateY(0)' },
      { transform: 'translateY(-100%)' }
    ];

    // Get the element that represents Alice and the Red Queen
    var redQueen_alice_sprite = document.getElementById('red-queen_and_alice_sprite');

    // Animate Alice and the Red Queen using steps()
    var redQueen_alice = redQueen_alice_sprite.animate(
    spriteFrames, {
      easing: 'steps(7, end)',
      direction: "reverse",
      duration: 600,
      playbackRate: 1,
      iterations: Infinity
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#time-transformations">Web Animations<br />
<span class="small">The definition of 'easing' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`easing`

52

≤79

63

No

Yes

No

52

52

63

Yes

No

6.0

`jump`

52

≤79

65

No

No

No

52

52

65

55

No

12.0

## See also

- [Web Animations API](../web_animations_api)
- [`Element.animate()`](../element/animate), [`KeyframeEffect()`](../keyframeeffect/keyframeeffect), and [`AnimationEffect.updateTiming()`](../animationeffect/updatetiming) all accept an object of timing properties including this one.
- The value of this property corresponds to the one in [`EffectTiming`](../effecttiming) (which is returned from [`AnimationEffect.getTiming()`](../animationeffect/gettiming) and [`AnimationEffect.getComputedTiming()`](../animationeffect/getcomputedtiming)).
- CSS's `animation-timing-function` and `transition-timing-function`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/easing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/easing</a>
