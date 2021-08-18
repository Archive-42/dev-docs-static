# &lt;ratio&gt;

The `<ratio>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types), used for describing [aspect ratios](@media/aspect-ratio) in [media queries](media_queries), denotes the proportion between two unitless values.

## Syntax

In Media Queries Level 3, the `<ratio>` data type consisted of a strictly positive [`<integer>`](integer) followed by a forward slash ('/', Unicode `U+002F SOLIDUS`) and a second strictly positive [`<integer>`](integer). Spaces before and after the slash are optional. The first number represents the width, while the second represents the height.

In Media Queries Level 4, the &lt;ratio&gt; date type is updated to consist of a strictly positive [`<number>`](number) followed by a forward slash ('/', Unicode `U+002F SOLIDUS`) and a second strictly positive [`<number>`](number). In addition a single [`<number>`](number) as a value is allowable.

## Examples

### Use in a media query

    @media screen and (min-aspect-ratio: 16/9) { ... }

### Common aspect ratios

<table><thead><tr class="header"><th></th><th>Ratio</th><th>Usage</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAO0AAADHCAMAAADCpCTtAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAADnUExURf///zs8O1BQUff39/r6+qysrPX//5nL+wAAAKrU/E5OTpubmwsLCx1DlP//71AOCvH+/0ELB/zxzv//+YVGE/740mZmZiRQmCcHBaJvMLzf9/z+/xk8jVeJw+jUrP7744ux2Hal066MZrW1r4V2YSwsLMieY6fR78DAwNjV0uTl3QAIQ/fhtQAFLJvC5Kmin5KfuFllZmKRyTFIWmRcVgAObKe30Bk4WbbU7nSBjNOuebSDSOPFkmUhDVVlcyAgIJ6KiYZdM0xBD9rIs97x/uT6/trx/mlPMQANYj0uC7ulhcugbMnp/Y2a6RoAAAJ3SURBVHja7d1rT9pgFMDxAoWdzQltNyajCHIdCOhcvN/m7tfv/3n2tFAHZHEvlizpOf//i2o0JvxypH2eJlrPe7Dy05WGG9+U3PUwNh4X0iQ9Fje1j/LV479o711//ipatGjRokWLFi1atGjRokWLFi1atGjRokWLFi1atGjRokWLFi1atGjRokWLFi1atGjRokWLVpm2VCpZ0Va/fxORs9eBBW10s/zDmZPP+rXV5w560R+4YytQr70WmZ67j+2GyCvt2mcvRXbTz65Euuq1vcJypKOMrfuc7N8Pec/K6qLac6eppglt527gzlHro9WrjcLkejv9aERbK74XaczPzewK2m6+J5/M7IFm7q17YEabXILeaF9dTPrZ5mekX1sPs8tsMtuucm2yBVosGNuyvi1Q+b69TJYV8eKcvLbl07u/Pbv44o5zAyvHzrvlvYuvTRNrqQ+DYWF4e1oxcs8x5n4yWrRo0aJFixYtWrRo0aJFixYtWrRo0aJFixYtWrRo0aJFixYtWrRo0aJFixYtWrRo0aJFixatcu3+Vpqkx7JybXy4+hzkt+pnW16pv6lV9txqIiIiIiIiypqM8/Rq4/Hkn37+ifg50pakiBYtWrSqtfmK2aJFi1aztmhKS0SUFYWyU7GCTf737XZgRfvDLeC3rcx2Joa0nRtL2iuR29CK9lqktV8zoo1qMm/Wjcx28eSAyMhsL0V2Aq9uQztryPSnZ0SbLKL2vFSrf+UYj9zvccX3Y7dObgW+gdGu1DWl3VV++ekdvUg7dtaj4wMj+4LkLBXb2c3XDO1vbVyBfs823Hggre4t7uHWqZ33LRERERER/c9+AYA7uIt1HP27AAAAAElFTkSuQmCC" class="default internal" width="237" height="199" /></td><td><code>4/3</code></td><td>Traditional TV format in the 20<sup>th</sup> century.</td></tr><tr class="even"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAASgAAADHCAMAAACdvD7IAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAFNUExURemYZUtKTMrKynx9e2KRyfv7+6Ghof///wAAAPbZxrKysuvSnvf/////8wAFLKWmp///+f/+6P331uX7/5uamsukb8WZXomJi5OTk1AOCgAIRBQwgj0KB/nnvejLlicHBfLy8sDc9Mnp/O/+/1svDraVav336kd7uINEE5K/5tTl9v//7wANZNvb29fx/s23n1KHwVmRyQAPeJ2/3fbz8yRBWm1qZ7aFSGgRDX2Qn5NdGN7BkHehzydXlA4lfmqYy7La9fzv07GfhCJLe2BgYKp3NrnM4PTcqykpKf3//7q6ujA3QEhIQW4xDzUuHtHR0bzS5kROYoaz3Ulhf+zcwptnGp55TayGWpaCbXB+kDUtCpirydGrdYxRFkxBIENwoXSYv3xmUdzNs5lxRuLi4vbbyTNws5NnNR1DlGtcQx5ATqKYmGtdeKixsaCRe8cqrcsAAAOsSURBVHja7d3pU9pAGMdxj2qeWkBQWysqoLS2atW23tfUW1E7OlYdj9r7vv7/l81miQQhG6adMsV8fy8CAq8+s9l9djPjU2eZ0+DNhPebjxKiWFZdAFTRzxu839yUutCkAqhGHXGuH4AKipR+BBRQQAEFFFBAAQUUUEABBRRQQAEFFFBAAQUUUEABBRRQQAEFFFBAAQUUUEABBRRQQAEFFFBAAQUUUEABBRRQQAEFFFBAAQUUUEABBRRQljWRaQIqECq6ciYik+cRoIxQy8/z/zPjUT9QBqiEclr9+Sst0p0Fyh/qpe20oAbWPf0KVHmo6EORB867TfvmawfKD6qtS5J6bhq2yZaAMkDF8pP4usgBUL5QMyIaKn4k8gQo04jq08ufTXYDKD+o+IXIYtZd/oDyLw/mVRk1ZA3cF6CMUNEjJRTTxTlQhi3M8LFGWlxhMjdvinOHJ2trpxvWHZFBoEzHLDk9si4oOA1Qufmpel0e9KbZwphG1LTIM6dOWHc3fUCVhUqJJPftxc8uD2L9QBnOo+y9sLxo7JH8yALKbzJXB1FO3kSAMq560bGvO7v1s0M8XKisPOApTCAUz/WAAgoooIACCiiggAIKKKCAAgoooIACCiiggAIKKKCAAgoooIACCiiggAIKKKCAAgoooIACCiiggAIKKKCAAgoooIACCiiggAIKKJ0BCVGCoep1xLmOWOFNEFSRawNQvmnyJgcUAQoooIACCigCFFBAAXWtoXItW62hUdpe2/vzEdUsHaGBuistQAEFFFDXFaoZqMqgwpS/ggpPHdUJFFBAAXVdoUaaw/OEfXtqj2OWf33MAhSpWah4xtt8ZSKTyQFVLtG5Qgu7+JjqXBObbQeqNLcLTRETn/Nbr2QfUGWcXKjhOdUyquXEvj5tB6ooiWNPm03Vo3Tcfr2VvtInMfRQ8bEeTz9Se7LKNx+bFnkMlCcpNXO/cqEK7REPO1v7gCqGWu3fdKFSV9sjAuWm98eGPSO5UKqDa2LFHmCT5xGgSuOBis3qOUtWR4EyQYmcybcphdWdBcoXSlVUsXHdo1QOgDJCDbrlwZcIUIZbT99xud6eqpfmNQb1SX/U1iXJUaAMt95iBKhgqM3LvbBdo1d72aslqMSMyILzbr36NXotQTnLnl0exFV5sASUP5TTwnyyUR1yVvvwoBagUgWWxPv8CefrLFAlWf7esXH5x7u3Wzu7p/ucHlQUnsL8xwEKKKCAAgoooAhQQAEFVA3lN+r3On9GdaSCAAAAAElFTkSuQmCC" width="296" height="199" /></td><td><code>16/9</code></td><td>Modern "widescreen" TV format.</td></tr><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAATAAAADHCAMAAACpxf/UAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAEsUExURf///+vSnaampvv7+//+4mKRyaGhof7+zAAAAP/+601MS8zMy3t8fP//+dXy/unMlQAKTPn+/0QMCAAFLHBwb+7u8O/9/5zH6v331/Pz8zQuNZFbF9va2f/951iOx/fmwPvv2bCysrvL4aGYmCcHBcro+089DlQOCgAMXnAxD9/f4AAIP9Pn96B8R/3zzdq3gbHU7vTgtuT5/sabVPLap8qlbIipzlFjgs+zkkVTW/774f//89bBoXKayMundSFMmGlddd7y/SRPgbmNUcXFxYN6bEtBL5NnJ7yfeGx+naaVfMfc8VSCuXxrS5WiuOTVui1Pbr+6snhDEjNwrSQkJGFhZgAPdWsSDaPC4DgKB+3o4/ny6xg5fsOZYv7/7WlQXF5lXJ2rsC5mp/Hu7nhEOwcAAAOLSURBVHja7d1XVxNBGMbxASG+lKUkgqSRkEIJgpTQez8gRVRUEKzf/zs4syUsbDTZ45Xs/7lYtt3wOzOz7wycM0r9PV3+JP1PvkoUoxrlwdv7/icd8jxyaWsM1u1E7GMFMNVk6rwIGGCAAQYYYIABBhhggAEGGGCAAQYYYIABBhhggAEGGGCAAQYYYIABBhhggAEGGGCAAQYYYIABBhhggAEGGGCAAQYYYIABBhhggAEGGGCA/X9gVrIfsBBga2kZBiwE2IJIO2DNg20KYCHAslMCWPNg1npcAAsB1quxEqOAhQHbLVcBaxost11QqgWwcGUFYIABBhhggAEGGGCAAQYYYGYGzhJ1GLB8sVgALAQYf2YDDDDAAAMMMMAAAwwwwAADDDDAAAMMMMAAAwwwwAADDDDAAAMMMMAAAwwwwAADDDDAAAMMMMAAAwwwwAADDDDAAAMMMMAAAwwwwAAD7KmBWRLFNJTqdCL2MaNIw6blzz4eDfPMHzgIIYQQQgghhPxTRj6M8DuHSUxaIwfWKjHAAAMMMMAAawosiqGF0SUBAwwwwJpJJlaJHFglxn9LEEJCxEr2B28mk0lk6mctHdxiaXnUbBV9vONczV69cLP9Bi+1ENjEK5t2J3WJGfv69f007yVem8E92vf0rbcjJ/o43uNdA+Y2pqngpvbTcZEN/TMXd57oPpuY+TVgJ+rD/XpcgmAtIh8H3a74Xn8PhsZkfI6uaNJrxqnRP4JVRbb0yWxJtvrBcsF2y9XHYFVv7LoTOXXe2lA3mcoAYLntQp2tLrOftOOOspbdQX5epM+UGbL0CjJVb2/QWTOyrRijU90VrfT9R/IzXHU3U513ffrMWL86YaqMH5dnZsAr4xUEs6YkJYmrQ5HSuO6E09cii+b+ekl/NfEKgpnCfkN/HS/GRG4HlXWTKdRq3L4ewB6DtU14N3LXD0t7XdECFgQzLOXaHMk/L1/Vn88ZwB6DDU3IpNuO7syjL12X7hqFLvlpYfVbWE/ta9luDm6hr0t+wIJgHbUxTLcoPYbpQn/S7qJrRyI/mSP5wHLfvi/N2Qtksqhh8u/0HGnHZrvV5UWHWdhgCPOD9TplQ1ZDyWT3mbf+Za8fLh2UggtnkZ2BD9fO7OF+9chbcXWmQsvezGgRLZ18sVjwzmLn9rqOujhIraRWzr1VsPxJZ+owdczcmxBCCCGEEEIIeSr5DWyk0S7T0KN+AAAAAElFTkSuQmCC" alt="Ratio1_1.85.png" width="304" height="199" /></td><td><code>185/100</code> = <code>91/50</code></td><td>The most common movie format since the 1960s.</td></tr><tr class="even"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAXYAAADHCAMAAAA6YYgzAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAFHUExURf///5+fn0tMTXx8fNL9/mGRyfv7+8v9/gAAAOz+////+aGhoevSnfX09cvLzP//7kREREELB+nNl9Xx/gAKTPX7//r///Piwf752//85oFEEycHBQAFLMqhZaenp3up1dLS0r7j+6bP7fzwzJuamsmod/D9/1AOCp9tNQAIPwAMYOT4/pG42VSIw5ZiIOHe3bevoi8rK9zBmJzH69Pr/FJkgXKfzubSrbXU7wAObsrh9Pbfstv0/peisfHZqGAQDKp8P39tXMbGxJJ/a7CytRc1XaablB9HklF8sD9zt/PlzZuYn4xRFtzNvtnX1ZGKhrzZ76CGba6OZWJ0k3syETpAOGxPMY2rzdq9ikIuC6i6zruliGdcSfzw2WtbYUxBD11gXNi0erjL4SBIfmkiDi5mp2hheHmRo2iJulJcb5ClwG5CEhQwfluXAhYAAAQjSURBVHja7dpZV9pAGIDhoNV+LlSlCghY617ADZe6Wxe07npsra11q7Z2/f/XnZkQBddTEmPP8X0vogS4eTJMJgHLur1n+QXzn6kQKjbrrgpePVfI/pSK6snd7KV2YrZ9sPvE7gz6q7tghx12gh12gh122GGHHXbYYYedYIedYIedYIcddthhhx122GEn2GEn2GEn2GGHHXbYYYcddtgJdtgJdthhhx122GGHHXbYYYedYIedYIcddthhhx122GGH/b7YK4MNsPvOXtMrZbD7zt4ksPvP3iGw+87eOCOw+81eOVAnsPvOHlLkiSPY/Wc/HZ+G3Wf2yNmJZVXD/hALSNhhhx122GEn2GEn2GGHHXbYHzl7SKQHdt/ZDxbbT2D3nZ0fbMAOO+yww06ww06www477LDDDjvssMMOO+wEO+wEO+ywww477LDDDjvssMNOsMNOsMMOO+ywww477LDDDjvsBDvsBDvssMMOO+ywww477LDDTrDDTrDDDvu/soeFiu1O7xI7MdsNi/yp4CDN4eFT5fnBQURERERERET0wGUzL0AoqtIqF28OSDuCRSW1Lt5cBTvssNP9sgcQhP3RsFORuWNn3V5U5bA/REHYYYcd9v+XvS/QB2FRp9TaUhCIiG4/QQWDDdfuLthbHgzyw1nPqvn8SV9sD29dt3vhlyMfmdWvejcOmCdFupy7HD/Cebvb3uT2jk2axx3Oq15D5kGNX/VIzy7WqT/NeWM9pod2dl5t33aqxx+1+Pf+D2rbDZr7vogkWrXzK5FU+nz3gEhyVP0diYuop6Nq7I8N2YM+NYma2yp7nWkjqiab0fPd6iD0mP9mzIegWh2cFueJZthcn0/fi7TY0mtmXOfYt3dyD5qMv9ou2c+ERL6FcXNb31y24nw2b81fLp4P+24H35xq62SsAjbPUvNIcujKh2FbzKdBsS/beyZE6p+j5VX6pGnWLHmLnM3ZeG7lotnDzikYdu/WkTFxJvmLpbteVEq9XrhMq38GnaMDu2fqa3J1hdLWVXIkEk+M2mde2W2wInqVD7tXM0zspsvPETXix9L2cFeHwGxh9/D+wA2r8Ym4Pb2MmBlHElO/YfemAbnlkr9SXS+VmXmo//D4bCodrZM/LCA9SN9uSY5e2rneP5Vb1jTl2C0ul7we66nLC3Y1pp2LV3M3IDq/vxR2bhZwD9KDeV3N3afpK5dJMeeyVJ9LW/Va0iwk9VSfaEHNbfpWmHRvvDQ9U/NK5PB4OG3fXt8N22dSdRWlD8NSp33yXUbNdRMFP+ccNHO3XqmY++0Lm/r+emLLntIlWbqvJyTWMe4LXcOe1LCNvbl9KftrPOfbpQW+1fOgldXARavqzHqwGDBrmLC1PpvZyfzcc75LXZnPlNQO77GKISIiIiIiIiIi8ru/ox/iqwnS8/UAAAAASUVORK5CYII=" alt="Ratio1_2.39.png" width="374" height="199" /></td><td><code>239/100</code><br />
</td><td>"Widescreen," anamorphic movie format.</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-4/#values">Media Queries Level 4<br />
<span class="small">The definition of '&lt;ratio&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/mediaqueries-3/#values">Media Queries<br />
<span class="small">The definition of '&lt;ratio&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ratio`

3

12

3.5

9

9.5

5

≤37

18

4

14

4.2

1.0

`number_value`

No

No

70

No

No

No

No

No

No

No

No

No

## See also

- `aspect-ratio` media feature

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/ratio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/ratio</a>
