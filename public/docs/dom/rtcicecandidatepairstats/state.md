RTCIceCandidatePairStats.state
==============================

The `state` property in an [`RTCIceCandidatePairStats`](../rtcicecandidatepairstats) object indicates the state of the check list of which the candidate pair is a member.

Syntax
------

    state = rtcIceCandidatePairStats.state;

### Value

A [`DOMString`](../domstring) whose value is one of those found in the [`RTCStatsIceCandidatePairState`](../rtcstatsicecandidatepairstate) enumerated type.

ICE check lists
---------------

During ICE negotiation, the ICE layer builds up a **check list**, which is a list of potential pairings of ICE candidates. Each pair has a state, whose value is represented by `RTCStatsIceCandidatePairState`.

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjM2Ny41IDEyNy41IDU2MSAzMjEiIHdpZHRoPSI1NjEiIGhlaWdodD0iMzIxIj48ZGVmcz48bWFya2VyIG9yaWVudD0iYXV0byIgb3ZlcmZsb3c9InZpc2libGUiIG1hcmtlclVuaXRzPSJzdHJva2VXaWR0aCIgaWQ9ImEiIHN0cm9rZS1saW5lam9pbj0ibWl0ZXIiIHN0cm9rZS1taXRlcmxpbWl0PSIxMCIgdmlld0JveD0iLTEgLTQgMTAgOCIgbWFya2VyV2lkdGg9IjEwIiBtYXJrZXJIZWlnaHQ9IjgiIGNvbG9yPSIjMDAwIj48cGF0aCBkPSJNOCAwIDAtM3Y2eiIgZmlsbD0iY3VycmVudENvbG9yIiBzdHJva2U9ImN1cnJlbnRDb2xvciIvPjwvbWFya2VyPjwvZGVmcz48ZyBmaWxsPSJub25lIj48dGV4dCB0cmFuc2Zvcm09InJvdGF0ZSgtNDUgNzAxLjUyNyAtNzU4LjkzMykiIGZpbGw9IiMwMDAiPgogICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTMiPmZhaWx1cmU8L3RzcGFuPgogICAgICAgIDwvdGV4dD48cGF0aCBmaWxsPSIjZWRlZGZmIiBkPSJNMzY4IDEyOGgxMjh2NDhIMzY4eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMzY4IDEyOGgxMjh2NDhIMzY4eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDM3MyAxNDIuNSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IkNvdXJpZXIgTmV3IiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNDAwIiB4PSIzMC4xOTUiIHk9IjEzIj5mcm96ZW48L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik0zNjggMjY0aDEyOHY0OEgzNjh6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik0zNjggMjY0aDEyOHY0OEgzNjh6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMzczIDI3OC41KSIgZmlsbD0iIzAwMCI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjI1LjM5NSIgeT0iMTMiPndhaXRpbmc8L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik01ODQgMjY0aDEyOHY0OEg1ODR6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik01ODQgMjY0aDEyOHY0OEg1ODR6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNTg5IDI3OC41KSIgZmlsbD0iIzAwMCI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjYuMTkxIiB5PSIxMyI+aW4tcHJvZ3Jlc3M8L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIGZpbGw9IiNlZGVkZmYiIGQ9Ik04MDAgMjY0aDEyOHY0OEg4MDB6Ii8+PHBhdGggc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiIGQ9Ik04MDAgMjY0aDEyOHY0OEg4MDB6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODA1IDI3OC41KSIgZmlsbD0iIzAwMCI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iQ291cmllciBOZXciIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjMwLjE5NSIgeT0iMTMiPmZhaWxlZDwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHBhdGggZmlsbD0iI2VkZWRmZiIgZD0iTTU4NCA0MDBoMTI4djQ4SDU4NHoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTU4NCA0MDBoMTI4djQ4SDU4NHoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg1ODkgNDE0LjUpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJDb3VyaWVyIE5ldyIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMTUuNzkzIiB5PSIxMyI+c3VjY2VlZGVkPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTQzMiAxNzZ2NzguMW02NCAzMy45aDc4LjFtMTM3LjkgMGg3OC4xTTY0OCAzMTJ2NzguMSIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ0MC42MDYgMjA4LjkyMykiIGZpbGw9IiMwMDAiPgogICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTMiPnVuZnJlZXplPC90c3Bhbj4KICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJyb3RhdGUoLTQ1IDU5NC4wNyAtNDk3Ljk1MykiIGZpbGw9IiMwMDAiPgogICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJBcmlhbCIgZm9udC1zaXplPSIxNCIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTMiPmNoZWNrIHBhaXI8L3RzcGFuPgogICAgICAgIDwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2NTUuNTE1IDM0NS44NjkpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iQXJpYWwiIGZvbnQtc2l6ZT0iMTQiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjAiIHk9IjEzIj5zdWNjZXNzPC90c3Bhbj4KICAgICAgICA8L3RleHQ+PC9nPjwvc3ZnPg==" alt="A diagram showing how ICE candidate pairs change state as the check list is analyed" width="561" height="321" />

When a candidate pair is added to the check list, it begins in the `frozen` state. As soon as there are no checks ongoing which block the pair from being analyzed, it is unfrozen and moves into the `waiting` state. This may happen immediately upon being added to the check list.

Each time a candidate pair is done being checked, the next-highest priority candidate pair remaining on the check list moves from the `waiting` state to the `in-progress` state, and its check begins. If the check fails for any reason, the pair moves into its final state, `failed`. If the check succeeds, the pair ends up in the `succeeded` state.

The ICE check list state for any given pair of ICE candidates can be found in the corresponding the `state` property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatepairstats-state">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidatePairStats.state' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`state`

No

No

29

No

?

?

No

No

29

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidatePairStats/state</a>