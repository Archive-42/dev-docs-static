# CanvasRenderingContext2D.createPattern()

The ` CanvasRenderingContext2D``.createPattern() ` method of the Canvas 2D API creates a pattern using the specified image and repetition. This method returns a [`CanvasPattern`](../canvaspattern).

This method doesn't draw anything to the canvas directly. The pattern it creates must be assigned to the [`CanvasRenderingContext2D.fillStyle`](fillstyle) or [`CanvasRenderingContext2D.strokeStyle`](strokestyle) properties, after which it is applied to any subsequent drawing.

## Syntax

    CanvasPattern ctx.createPattern(image, repetition);

### Parameters

`image`  
A [`CanvasImageSource`](../canvasimagesource) to be used as the pattern's image. It can be any of the following:

- [`HTMLImageElement`](../htmlimageelement) ([`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img))
- [`SVGImageElement`](../svgimageelement) ([`<image>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image))
- [`HTMLVideoElement`](../htmlvideoelement) ([`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), by using the capture of the video)
- [`HTMLCanvasElement`](../htmlcanvaselement) ([`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas))
- [`ImageBitmap`](../imagebitmap)
- [`OffscreenCanvas`](../offscreencanvas)

`repetition`  
A [`DOMString`](../domstring) indicating how to repeat the pattern's image. Possible values are:

- `"repeat"` (both directions)
- `"repeat-x"` (horizontal only)
- `"repeat-y"` (vertical only)
- `"no-repeat"` (neither direction)

If `repetition` is specified as an empty string (`""`) or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) (but not [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)), a value of `"repeat"` will be used.

### Return value

[`CanvasPattern`](../canvaspattern)  
An opaque object describing a pattern.

## Examples

### Creating a pattern from an image

This example uses the `createPattern()` method to create a [`CanvasPattern`](../canvaspattern) with a repeating source image. Once created, the pattern is assigned to the canvas context's fill style and applied to a rectangle.

The original image looks like this:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFYAAAB1CAMAAADjsOZdAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAeZQTFRF+Pr20s+w1dO39ffx6enZuK+I4N/JoqV64+TRsqqC2te/p6qC7O3g+/z6wryYx8GfsaR9wLiTycOjzsqq29zDu7WP7fDlxr6craJ58fLozManyM6xu7+c/f79kplu9/n1+Pr2+vv49ffy4uDMw72Z9vjz9PbwtamCsaR8vLONx76c1NK18fLpxLuYrqF53dvEtquF+Pr32da86urb5eTSwriV4+LOsqZ/5+jX5ubU4N/J1tG39PXuwLmU8vPrycSk393H5OTRyMKgzMeo2ti/y8amysWlurGM9vn1zciquK6I09Gz6uvd7+/k1tS3tq6G+/z619O5z8usuK2G0M6u0cyxuq+KuLCK/P383t3Fxb2byL+fvreS3NnCvLSP4eLMvLGMycKi1M+10s6wwbqX2da+wLaT7/Hm7e7ivrWR0Mut7O3gzcmoxsGezsms7e3gvrSQ////xb+eqZlx3dzFtLKJx8Sh2di919W529rAxsus5ObU6ejYvLaQsamAtKyDrZ522NS8oqV6wsanqqd709a7082zrKB3xL+b0dO419i9rJx0rKp/zdCzvrqT2dvDwMKfrq6G3d/Iu76b2tfBnp9xys6wmqF3zMyro6BzpqJ21NjArKR6lZtv4eTPtruYsbaRrqd973/engAAAB90Uk5T8PDx8PDw8fDw8O778PDw8PDv8PDw8PDw8PDw8PDw8DKH1SQAAB+/SURBVGjeTJX5W9pqFsdj+1RLn2nVdqbtc+fOZUkgCZAEgbCEHSIIKMguiyBGQRARLYuKirK4W9SWulzbTv/TwY3O+2vO+bzn/Z5zvgGGB5/98+2bD8MsVj/wHPjH26GhfuD9e+DhPO9/w+p79SdrsO/l6+f9L5+/73/3b9afL/tYgy9fA0/nP69YL/qfA6/7h4eGB//4413fu2EW0F+rLfmZXAHZE5uqEwHYBhP8sTH245lUhA7WTk9bs3IuaGfG9fJZ4rBFQJGqeOQphCMIILjEpNWn9TF4lUmac3HdM+BZDHZYRyEYJ8Zz9mKZ9LqLfM5Typh+Hp6jicZGVsVx6Q6ohWr2bONIhMaKi9welsO4MdsVsb45VcYzFiGWCRpeAX+adTDsgwwa+eit8rNFKtKNjz1hOfzi0idyHWxs+De50maJWFRc/dygRRKl2TTVu3vlq27UuYXC1mqV1KGwEpnJPgPeQDloHxGZBCb3LeyeLZZz7B51RHt0cExW6NaRS81J1M9/pAlRq1UsBhEI5PaEmjLNxS4gN26zCubzoeOdkM7yDmAtUQvtip43NW+eNseYvRit7dWhz9F5OAk6qbZTSs1/+XJUdB1dEO026aYqFVVPK3EApV1QJFKr8tgJi3PCBb0APiod3kRiPZEmNONenSUPOUSP8dwJCsZxt+7AL/r5szJdVCjWw6aNDdEaE0EQPELxHsPE2WDG64QYT6wytqBOi9fJIAsYgByfcAQxggy9CS1VwD13taetVnd8vIPXih6CuvgBlr2g+oIiiq7k8Q6yn594CpvShEbDBtQbtoyOBxCJRKnb6mLjpA3/ZANF9jBoIEAGsot72rKNDhw2MwopeNpoU1DSVGwcrhtpBsXxuELQ01YFxcJGb54yQgkGOcZtUGkAGLgNBXYDAafVYDcnvwbKVwtp9gjngTzCEZWZHyaTCWycHeVLJVHr7IpWgJW2GZrmcx+mi8MVLFbMuWnPgZey+EV2ayAZbP4FDDT3A1qxCBo12NwxHepXCRRanoD3UC4PpBOJNUpFiSrE1uUlJHWtteXgWmK9on5UlsdjLyYSIDSXzMQtrjJzIVsQ4td/AR+vbwJyDRyLoWgBCxaM2rDduWQg7rM4vAtn1uWMknZF2Nu87IToKljW5cOegBS8XzPuBJhf84yGBUwNTUl8M8LYqkwQu7keAFiI0khs+5KYTxKMkEHYpoPdkHHxaXjVRsJbOIbXqxV3/eazijcPIxGNYlrLvx9bjnY564B92KpEQmI+30yUxEcX879+dT3BrJPOp1Aheqv0kUFbAYXdjoD+d9e0RXO07ATDa2W8xhQr8uyBQUMJOL0AAeTYlvgkcIr0SbYjGGJOrGawt0Cf1SpXmGcwd/MXMmObi+h8Osecauqpzdy0y7A7TRCUgnZHFJQrQcxLKzT/97UqNG5zFDDU5lM265GUkhE7IWsfwCozJnopkzmp3+7cNks6DNWJ8hS/h132ZEEZOLq77KmRCqOBUamNtJTXw/IIv8GWEa6Wmvv7199LGcfsRJuxDgNDmLdliGGFZgfHrzudUhQNLo7LxL+rNUoJGUha5RiOBGYLUVWCJsK/sXz1wh6cMm/Vr/eR2+8nsYKh6NREPgJvECSZ+1yIn1zjO/vdcoU+u4DdK/Zu45e1bPmMMnOg0MSViFXP02oF//eZz1UXgsKTJoLjO53zOLrqh2DJv4BBB3KMGizx7X0cP74+X43OEFMrPTNlj3CNhooLOlZCerF+XfnJ5ySkfkWvY92AFf2qIwqVtvGdY1wSExm2lXBhEPigC/rQLWguhO/v79+4uzPm0lD6J+6IXvWV8TsPkKhRvzyhFsIhj4ZZo2S/LZlnnI44yKVSDcF3kAKU1NV8KPYBeIFmhGRw62AOvv5e7zQLJFkOxYrixzxumgIVWZVKCurVJrUM9IgmKL9UnngSl8OntyAMzaDNk5PmLZqEbJk5DJvrtmy7FsNICIqQ5/U7bASzKCh1+gHL4fC1i9XNSS3obHyZNn5rqQl9GqT1Ys6jDBw+CHrIVKR207k8R6Pe1ThmJks1FjBUOnGTKaiMYaT7pBnCsBknd4U78gC9W/m0jDsJZs/ql7vS/zYUWbVWr2KPdU3j8R85uaKKFaLo9s3NVjTKWOKpaKjZHAI+np+jaJBR220YhkUiQgxd1z49UJtYl+6OswXyvb2/G1+o+avipsZr4vJkhGZ+vDctafvMXSJJCqOVCuTQuS+72IF6s7vPmZa/5jCjGBl0bEFe9f2STSWgVaM8PG0y7WlON5yzy6bpbz+le9KFEVq+SS+VeSP3d5sYrOBLmaMZt4+U5uIp8le93vXby+tfpNBRruwFwKijMAd5cltrdx3hsHe7rn/UAk101nV6tpTXqmavGi0nY0pTR4fzhvgEp2s3HL3fwIyGUJ8tb9nKOQ8ykdTN5R22Xj9PkQ6Naly8IvtqrKp4i7NdK+kOgQqSeA7PvslkxHTjzBpPcqoRL9E4cyZUssb5oSbkvL9c7KfF4xRh3ROLEz/oCBolbzp32M65LjNjJ/aShEws5k1Ncrjs+zZPym1I4OLvb21Vq71RJiV2ripesG+cNg6r7dNWIi9ZEozcvWlCwOVOTWnHtIqvgdlcoYC5O50B4GPnPILa6HIcmZMq2uP/47pKnxLH0zAztb1V82G3dueo2d0vOUmChAQCSAhXQghnuEEwyKGAcojKIdqAomV7tG7bjvbO9JQzTs9/ukGxnRoqRRUp6smPl+d9DtMTA2aUbVv7frN5NFo8eff+zEhE4Mk6EY4Jd3cPo7dus0JVn8gLzd5hzGmXdMaahBp3Vmawf98xKIZhpBLfrXk6K3r352wFJIq6sP/47aWd9itWb0YYnTJDNLC6ucz++I5ulUrsS04JPjRLqyK6G0elZriwonul+V4dd2eA2Gy7ruHei3I9aik5pZYUsWXFKUm4PLk7Gd1uB47SC35xIW0LsfCLMABw1BxDdbuHQ/vWYaVi/Vrz3VZ9y+rndFOX12U9ll9EBoC6iUigUtLp1ksKcz+6GY1G9w+peDhsXDfY0sva/Mt3gwDJ11wXu4ehsncqSco/Na+iXZ462iwfS+LQVkOebSGRz8tFRJ7Y6z0rbdken/w2ur+/P72XB0V/SbLwZdbCbyQSpmfBYXS2odhJHqP4TttZf6X5KruN2Po9yJSMtBEhCs0XbIy0mTjeK3LcgG/Abvn2/nZslsdjEsAm/B5toRfSrrHdPo+5oJY75vbRIlQmKAO2GFIzGOVrWCkR7nJIN5+AnogAwhH0Uh/o96e6Tl1VLrkdJc3tdjQqu4EN1pIKoIGrvoJsptj5IMB8votc2PNCGve7Vw7/ofkPLpHbRREDtc++p3o1CFiMVFiHhz1rNBNbcww23DJrt7MTmRwwMT3zIaXghNVo683S8zy7g1pMmyijPETi0+813+aIMzCIPbN15qUNDArKpX4/rtAnp7d3P7AxkXGaJhZLFNLWM8jg5Ef25q1DObpKO9SjJEhyPjk1Y2nV46GU8q3mmw5ah00vXAFJZo81JczX+M5Q5E4zmzcH2bshY97YtrDRqLkofvRf31RH7/eGtXSg6sxD2zyCvRQJE0B6FPELzSuJJ7E/oGoRR9aBsOWqxFyKSCx1bEH8/x3SmdCibF7Wx2j0OsMXtzq+9yfLsdA+27A7kkn7H8gOO9lU5zvNV8piF3zZAJUqCHcmRYq3b99HOlyHwboJ7sB/ioYj5CTl+aivbTa6CaGUZTxImVOvSBbhORh4gYCAC3XLXokC9LmzzPZwXJxYOO4tkvqIxtHYBAK0mOB58+nCi3Gd4W+7sQmgBTFBmjaZjOWWRhA7S09UXXiJT85Y7V+abzyRz2UIGzdAQPYhAivcfPQnV89xEgDt+2Na8p9GVoABWr/tpAa83gzkPxDEcvb4Y2TRLAvLUQget7VzQsBF/9bXmi/dsHbeASZrK1USAsnXdHGfW6yhvZpNwDj8KHxwfZM564G8wry/jueI/jXWLU7jPQOP0HU+iWCQmsSsdTL/9OewsPCF5q9PyjZzjzX/UkfukojqYLyFQ8OG1krZ+eGc8jhGn+78m6CgtE7vMllVHrEurYTCOo61cAxDP5AJ2hYQ+e0Z84NBMmH/UvNvIDg/7JrBmzZmWSntUUI0HZGMxk0hCh6f4/T2w8lByQ46U2jm1GzOhnPOxMalRMUj6milnitdnShHaSWLPC2UyUT+RaN5nnQ74hUrNp2fUIuPUm2lWjrqAE50PxC2Y8HuWw/Apm69InIWQUyvOMEuPT3KSSmmqBBH/WbLSFVWHcIzUU1/e4aFZCbl8bWaR1RFMRLK3oI/pbvCLWqM9xI7Bmt6yYtBeX5K7DTV+sloTUCqrxZctGpZOg8sBHBCl1JDlP4ZV/MMmxhL1T1fJCaiCIJTW2zgMOdqxrMwmECUuJFo2gEt6QTk4tSGT3VuE9Tu2Fy5JSLbKFwZ2KQrldlfZqpidC7tL7B2D0fGiQsR5WgKR4BOn5IGVbNKR2eDtdBjCCJDPgyCb8tC+VadIfSQmZSuqA/Q3pFi9vUyOcJhbhWcfz6tifSltnLGwFLaH7L1GgDaJ0o9RU2GQS3mJttuCObCBTZoim6Q0UZQve27DhlV2K6Mr+/7VbGzKY5qUfsnWBDsygf964sdgnJdhMUNU9JIHfUJVo1wJshkgoIWx7ot7RWc6ifocaey/T5FNdm8rNOJrit85+B3nR577onPsDAGsK7zg5uLJUISw9dloOFV4+pUnkmdWmsgp2MJd1XijoZKn1neA7pJSm3DWdLJhFf0ClXrHLzZiWDauTg8woLwRtUb4dHzNz/9EMDj/rDNWMPcvVqWg01w2dNza8Hg2nRpYR13uNX8v9jyRQHIvF/QydpByYgrHSO++9OvP9di9PEZ8pgkH2Ehds1QSC6nFOLNLzZ8c3/BYPBumDAMDgIJQRrWchk7vJZuFgzTrYb7spOurKrJQ525HMwveg2GFmPAf/nfz7kIR6+tFizgHBbaDrn8ligfqlqnh6uL5tcdxWGBwZnYA3neG4vZ+jqfx2YtFJYM+zHbVUBsqR6lvoJqBzBvXlSFQQs/nErV0HaUVzyzdjWDTUw8iuPdgDs7ayXXzpJFJhIRyJmFzMIoh7aYQp/yKkZvstpsihd9fMuxuvrIexUZdiOZGM+0QnV9NVKV7+ns7JfMYEETX2gJn2726kwbdAp1ZtDYgCEAe/SMxLhpiNHr6XhuqW5Z9FQMgVxqWV/ZmjdtrQq8bd/bpxvdIBLzIXeni6JHbQAzWPi44GDvTiJJGoDc7QY7BmeatqFmBtX/zM0dPZ31HMR1NI9srS/UQr7Xm4/WCIKPTwbz5DLyfyas/SttbI1m7jhtp6tr7rqzpuuu+8sIJJAECCABQgIBEl4FRJ6ChIdAShCkqFRULBBF1OKordVqdWo785/eiK/Jzyc7Oec73/723tKcn+tq1j0fd011dXdSgv1RXuV9tvMPLl/OO96aUjmmyTPRJr9JjQxB92xoZqPZQoNBLhmqVKQehd03IYVWcqrRG6WkuHllDqTNndXRbrn06ZXsR+C5XQ7WN06PZrJYUnHzD7Lb/a0h8KxVoZCtioS34Y27oYK+8Zo3BuJ1QdeSqD9seS3St9pq/EqUzBk0nc3z9eSCrPoE+G8SJxuhA48GjWsfB92UCirQqH8h8E7p1DXKcTahS/555E+YvXtNP2F6xXpiKFdC83OPI1e+p2Mp8EOojOOefwP/obSkb2fTo0mnZh+l5ZSi4fc602d+XmUjaEFIIUTldJNDYLRWEINV3ACVcrbSe+oRNmpd1nHM6s4XG651/QL8rLVTtt1NV6WoO3bIH3MCvDfr4nOG9BmuL6cIA8Y22x+bXA0RuQq11IL7kAZsgOHHpDF6hmwtmzLnux7ryvxL4OkibqQWKdAloKEl1UP+IJ2ClwJRyMBVV+xfem+MNj9NBzwbfhacm6NgyO+0eOLhx+0pHWBtv8AwpOUMnPz0Evitsu0JbVZmjC1/LsIyc/fiZKZH2yioY3tDRVVaaUdsQjQI+emqY0GrDHjJZADkoS/vovfLN6C0Hw548qMjjdG4/gR4wnSto4+hmdcIsfUWdd3BTtkjBDfrTOtdXle0/r7hhJHgsE9IJXO/sUy1tvHZnK9B98t3RZap3hBvCVFoxEI7512QmQB+MHXB3d1Yxvn1j7dwfuleryrK/RJ1Bs1IDlKaZrAEKA4Oi8E+DKdWte8ZU9PZMZq94L3MVLiyWzoiEfN4dkcUST0HXoLU5gg0UXqvAV6XR2/vivSo4k0Xnnd68vFyKAEXWHZ4MeipoYSh5anEyb2mnuQD2puV93brTcLMg4ypc76Jx6SSuWdGRsoFUsZ4Y2yJZJOORXzRAYZxm3ePxkoNd9MGghz8eTDoY0lmnfd63c5aK9Aw4uSSo7rouOUHGdXQMJ2MpRMa5T8+BX7vlRlK7zZ5vHyMUY5hlzJ8pxtQrFREmi4aWslCXkum9y+Gw2GQVYHsspMOBgtob3GyUbGCniX7bVsyIY1xg6+YGEuz/TvwFKImYygc1yRD4N2Yl+vTEQ6lMhiCqdXFIobqnCR0OdTphtC6C4YFLIWxLAonyRxmFnPdW4c4Fd6I63kzsRd2+ETJnH45wGMRJFsHF8MPgpRM/oGgBoTguCKCZrktweK9FHNoHzJWENSnTsGCepkg/BEErS88NEQVx5voWx9pcbYlc6rXM1SzZCszCvtDiM60DGLfkCpiQmLYPsa2uC4vQvG1XhPUI0U13UdSZkwoiqKhqA7fC1uJ0smYl9smV9edPwG/4mQs/w5kYnnVY5wUg9gEas6ypzAxHLQxJLBEJdfMmK9DgoZi4fDiKyIes6VlmIZyHeUDbDiUp0zznrw28wvwkzGPBRYWLRTzkFdOhU1kElZne+2Tfd1wcKJOtTrrkm4h3ms26rDQu7z+igyHbY5DzBkT8wCrCuczpKOyzJN7kshnfYmAXfbtneqRNlRK+QFsxvrXl2+39j8PuGXa7cPgmiHljh8jQu/ztQ7ZvxwcY/uvJR/xSI2yhW/T0W0E2uN+Bl5IypDLOOapxX8Ybmnm+AWsfbivkwCuIIhlE0ithBEwXaex9PCrTqe7vD7GxG3ZP2NDZVi6x24CKdSfARNamy5Sqvt4fdfxwJ1VRuMlirQkMAmdTvRJ2tAfZLPZ5WCtUPNBfUT62N89rrhWX59/tCIKh2Wv7IO3ItPV/wHPtGSzDIbi2+uZJeV9h59B7Joh6G/32n0ETufQotlcYzE1h2FCEILS8P7w6qq/XGRZCDPd5XsyGb6qlzRuOWtzOF4ATw6+gXgUr+ut01rZfQLIc9KQrf09GFwMpE5DDeYSVogUi2lztpTIcbRwdX39+Urk/FBWiN1x7ivZEtONeRx2prs6/wx4/v1Ib6OUzLS9ulC9xZXZw9olQc2lpXYVMTXGpwTsZHBFEFcirTY4A341OhweRnLZYLm6uHDrpCX1p7XLyLCWqmT++vgc+Nf3EdP0qebkCyD1zn7LnzJ5VAX5MaxQM6uzGKT3F4ShdKmQ4Qkq9Ju8n1Mv+3tY1pxzrUTvbLRKscCQquiKNTn74eT7D8BvZ52DUBycxI2rYJkF726Znff6BY7LFtCUec2D5paHnweHJ20RloR/Jp6Q+q+UVdOQ03R3sI6Wz+PKryomLbzmwOV5DkzMnv41yqut1Or8JzDtHQ89eVgvGqEEnDC4nRH3t4Lad3OaFxeD/ldzFvVSwZwXKqKRQhx9Pc6zZcoDcc2C453uxqzrz1N3bAKYyLZ2zjU8aDEdfQe5Fhkd5+yZJg5uOyGIsW5T0xHMh11JqBeDkz7GJZrTNoq0YVzARtq84/RdpkjS9fMjkrHqZ8/PN2legkUxzdHmeWie2Ty1uAuVufGeFhzyuakwjs85qO0ZJ1qjDyUWv7hoH5tTXGx1HV9xkFatfU6F4zfVmLKb1bGjnZE1c3C+sxMwBCaAF8VUaffo+84H/QFpyhpsK7c1mxobduUk+L7W2y6Ixfbgcng16L0pRmaNHM3bleM1ko+4HagpwYbv7oCjnc1RUoD/36W5P6WtbmE4XtrxdGx7dtvdPd2dDoFAEiAmkACBhPvVQJCLXARBhEChAiIXFdQKbk+9brW1nY4zzjnt+U9P0Grp+Q0YvjXJl5W13uddX/QlMFVfUnKRj2cnW8cUq1HmRnVKQNzDpffKvNqSyPRDoX6yZXu7V0hnzpcOnHVyRAPBaXRGd/bp+GJrK67X+Nhp4PXZxUp/V1XYI1fyfmV21F6jTgKBxdD6+yLjSczMpPOL6Rm93hTtr6+/E7hYZ8S1A/l3/kWS6GUDM4nk3Nnxa+D11vU2F9IgmuV5lFbzTe2IQTLrOMrIM5puEwpZbCKizswk5VKdkj7P2KI7IxcgCmKj7dBvUSbmaRVh/PzxNfDi61bOFImrllps4UuwWi3fy0YtZkzvFj02jiy1kqyOTTiZXs0fZ2utI1tini3fDQlE0AxWZMZ4vBBS5uNM9fjb/mvg1cX1NmyGG9BlBQsSeU9OIruv5pDeq85HsN6gvVRtknimYr0ctFs8fzS3qo/zd4VJIaXm0qwJq/B7hopMZr7e+jAFADkeq1jFOrCd03V32/pLa/BGjg+zEXNUHMVSE8LbRR4u4vgXzI63XbDCQlZyuvsJjNWsc52eiimuw7SgVBRs15cTwEsjZZWIWjQg5PUI/nZuc0k+tLVu7nBWAVYcZdCA+k0GC/0WSegkHpyDZ3OU4hYFhhSFnbzn3OcomvHUsoS9IZE1KGoamAyayyk1yQROOlerLlUIpUUgBhXVH1pFjD/Lp3hQQGeMAh0PmpkcJp291fUShYg6Em01jSO+Re7qxPiV7EUICq5Q4usgNadq+/u9Ysi11TneT6I4pxClWI25K89D+yVs2rB167WN93UZOLQgf7g726SpCS5AfRxp7R+fxDzr6rPvcpaSYmJYPke4v65HV20fPxqPz+Jx/aYVruiiXevPoRgoDdpLNUuRKzGKn8MnUMawpR1F0yhPH0Q+fjhxOm1R+XoA6jSwV8CkULs6i53lquXeVW+u674QdWSKVDNdasQml4QxyLe+y5mb4KjvRzBZFtoxpYhL0vuh59Y1dEL9+IOXgyaAqTz3bd1mboYXyrl6QXB5HUxhJeCmehQm/Xll0oY79GnXO8IKQzLtGHdKMTXp6FzlowKBNcPNsvrz98+ZiFgTVMKxS7CaRWyAV9GMEOO2CB1PQXMwOCu7v+UwU3fJW3UofI8sCoW4CYyJpy6+XkXUddSXCw9tVvv557N04aEYNrIdO4r5fKK+h/Ckre4SSANl6lEiwAU6ZsUPzU9uBCN2oXSfrNXepkxiNUE8ZScDBeF8sGwKw6w8wtkYo014AUxaClvfNzKJQcus2PBlkqhrh9jM2iFpeCHST68w8N1Q25wsyO5eQNggrFlk0qbVHtmLOBzO5EYoAZV7ODr/bv2TQSVMAS+Lq2dbHfcincYkXa5I41GHzi2wQikY9B6uLcYaCz+6pox13JEC6IjnE34etmcjgTmDzp5GijanoyrgSm9k/5t7hnwFTNj0zo6J8SY4WIulim16T8S8d8satJ7200WvK4vJJCNG7M2QoaG22ZbxOjeESi/Eqr00rb60VklUH9lJqdNOwxtgIppIFCJOvZ8FtQriXVvTWWS99ABFD09pJadmBYP116hDQ7p7UNDj+GG7PRjoA614nD61mZqYDln2EkRBw20/BiYodYimNeiaKQzCHv8pEl3eIeYHrr10KOElSHKFGB3I3OZrhBXsBSXui9XmB+lO2ulB8SViuBxFEn4kSVQeA9MKLZNZzif3xCwt1znbOo1sV1yHXCPbVcfkc6S3QCnAX8PCnNCtBVLRAAzN491UemDxWBBOTPOGz69JWqoK2QTwzCwFYVhmHvoZsl5Av4v3rU23CMz6tWSftoibW5X8f1ih5vRpMm/lmy6axsqudnKj5jFIxW5iDFZ5MUF0z4EHxI5MqgW12hu7XYWgAw3cNEblc/P0/NpSSMkGzeAvYUGtBLIokz4lkvTILasKMN6mk8tDWgZBqwwWHzxV+A14gAyVjKjMxNWyyFobR+NVKpI/7yKIPn/+N5LVymDJL5XADPP+XRFUaCTmPIoZww7foN0uQgvgrFkLis/drlr+B/B7u9gIa2cVfFUMm2rhuJLPqUPtc5JOHMk/9X1kMNgY9f8lGN9wLPU/fXcmQ8SKvy9YgyvoKdoyLEhgHhbvWkH6kQfAE/SoCsJGrzM2xGgsIDeabUrE5/Ei/X/9+69Qy90rOEvUz8MTTDy/yhb/+/dff/URLmZBEq5tq1Dcq5jDxjlXTCdWY3tC+QR4giw5DHX01LbyZbg7YrWQndQWveR2rt5uH6oCEGR3qmpU+EeLZxZnYp2s8H5XpAqWz63kve6GVAErxLIxZ2FpPM0vCEr9H8BTxBfhdumisHErv8RHxzOufIGp7OnTtoBQMpnYtMouu+1t1sLiKmPqRGu2oi+9Y0y5VCxv1Q4XScsxy16GpllTOmR5BowvJ4qatjMVsWRvw0rBsMxElNRZsT0b7V0m9+HiYLFwM28DzY38AXO9Band0PZ/OlC3FCk0pOKSG0aMJQOb9VM649fbxoEXqqJcPhNwr9y4TyCM7YhFFlSUO6QdE4mH/JIKXEMH3I1/IW10vJDj67dezNSQLFQIUoeJPVwbDA5bdXiPLhLqonJJqRIeAo+ePns+9mh8/M8Hj94AAPBqcnzi5gTd5PRL8cPk2J8Pp6amxp5ODs/WPRa/Tk29GB/749XwL9MPp29+nbo5ePfm0T8fjI+PPX/2+29jj/4HTsxuuPHTHJUAAAAASUVORK5CYII=" alt="A flowery pattern" width="86" height="117" />

#### HTML

    <canvas id="canvas" width="300" height="300"></canvas>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    var img = new Image();
    img.src = 'https://mdn.mozillademos.org/files/222/Canvas_createpattern.png';
    img.onload = function() {
      var pattern = ctx.createPattern(img, 'repeat');
      ctx.fillStyle = pattern;
      ctx.fillRect(0, 0, 300, 300);
    };

### Creating a pattern from a canvas

In this example we create a pattern from the contents of an offscreen canvas. We then apply it to the fill style of our primary canvas, and fill that canvas with the pattern.

#### JavaScript

    // Create a pattern, offscreen
    const patternCanvas = document.createElement('canvas');
    const patternContext = patternCanvas.getContext('2d');

    // Give the pattern a width and height of 50
    patternCanvas.width = 50;
    patternCanvas.height = 50;

    // Give the pattern a background color and draw an arc
    patternContext.fillStyle = '#fec';
    patternContext.fillRect(0, 0, patternCanvas.width, patternCanvas.height);
    patternContext.arc(0, 0, 50, 0, .5 * Math.PI);
    patternContext.stroke();

    // Create our primary canvas and fill it with the pattern
    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const pattern = ctx.createPattern(patternCanvas, 'repeat');
    ctx.fillStyle = pattern;
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Add our primary canvas to the webpage
    document.body.appendChild(canvas);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-createpattern">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.createPattern' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createPattern`

1

12

1.5

9

≤12.1

2

1

18

4

≤12.1

1

1.0

### Gecko-specific notes

- Starting with Gecko 5.0 (Firefox 5.0 / Thunderbird 5.0 / SeaMonkey 2.2), specifying a `null` or `undefined` image correctly throws a `TYPE_MISMATCH_ERR` exception.
- Starting with Gecko 16.0 (Firefox 16.0 / Thunderbird 16.0 / SeaMonkey 2.13), specifying `null` for the `repetition` parameter is now allowed and results in the repetition being set to `"repeat"` ([bug 762657](https://bugzilla.mozilla.org/show_bug.cgi?id=762657)).

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasPattern`](../canvaspattern)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createPattern" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createPattern</a>
