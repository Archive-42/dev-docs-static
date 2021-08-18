# Applying styles and colors

- <a href="drawing_shapes" class="button minimal">« Previous</a>
- <a href="drawing_text" class="button minimal">Next »</a>

In the chapter about [drawing shapes](drawing_shapes), we used only the default line and fill styles. Here we will explore the canvas options we have at our disposal to make our drawings a little more attractive. You will learn how to add different colors, line styles, gradients, patterns and shadows to your drawings.

## Colors

Up until now we have only seen methods of the drawing context. If we want to apply colors to a shape, there are two important properties we can use: `fillStyle` and `strokeStyle`.

[`fillStyle = color`](../../canvasrenderingcontext2d/fillstyle)  
Sets the style used when filling shapes.

[`strokeStyle = color`](../../canvasrenderingcontext2d/strokestyle)  
Sets the style for shapes' outlines.

`color` is a string representing a CSS [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value), a gradient object, or a pattern object. We'll look at gradient and pattern objects later. By default, the stroke and fill color are set to black (CSS color value `#000000`).

**Note:** When you set the `strokeStyle` and/or `fillStyle` property, the new value becomes the default for all shapes being drawn from then on. For every shape you want in a different color, you will need to reassign the `fillStyle` or `strokeStyle` property.

The valid strings you can enter should, according to the specification, be CSS [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) values. Each of the following examples describe the same color.

    // these all set the fillStyle to 'orange'

    ctx.fillStyle = 'orange';
    ctx.fillStyle = '#FFA500';
    ctx.fillStyle = 'rgb(255, 165, 0)';
    ctx.fillStyle = 'rgba(255, 165, 0, 1)';

### A `fillStyle` example

In this example, we once again use two `for` loops to draw a grid of rectangles, each in a different color. The resulting image should look something like the screenshot. There is nothing too spectacular happening here. We use the two variables `i` and `j` to generate a unique RGB color for each square, and only modify the red and green values. The blue channel has a fixed value. By modifying the channels, you can generate all kinds of palettes. By increasing the steps, you can achieve something that looks like the color palettes Photoshop uses.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      for (var i = 0; i < 6; i++) {
        for (var j = 0; j < 6; j++) {
          ctx.fillStyle = 'rgb(' + Math.floor(255 - 42.5 * i) + ', ' +
                           Math.floor(255 - 42.5 * j) + ', 0)';
          ctx.fillRect(j * 25, i * 25, 25, 25);
        }
      }
    }

The result looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAHtQTFRF////VP8AVKkA/ykAKX4AKdQAKVQA9/f3+/v7zMzM1CkAfikAftQAqX4A1H4A1KkAVCkAqVQAKSkAVH4Afn4AqSkAVNQA/1QAqakAVFQAKakA/6kAKf8A1FQAfv8AflQA1NQA//8A/34A1P8Aqf8A/9QAqdQAfqkA4uLihhE7PAAAAoZJREFUeNrt3cly2zAQhGFkxSirs+9xEmfh+z9hbBLUwaUGlFQl6qH/tlTlgw6f2oOh5AtLIYQQQsgJUqdpZ55pio5+qua5Ikp9TRDlz6G/8m+Rv6tJsoMPH/5B/leVHyofVL6pvFG5owIfPnz48OHDhw8fPnz48OHDhw//hvEvVL6oPFV5ovJJ5YEKfG9+zA9bfuN12w/z9qPbfk3dfti3X3O3H7lnv9t+VDYPm4fNw+Zh87B52Dz/YfaX0Q9XfrSfHj/gw4eflf9d5afKW5XHKs9UXqnAhw8fPnz4G+LHGk/+nqf5dX7Y8hee4tflFa78lddtP7zbv3xK/vzHqbb8Vn/eo1t7R7e2/o1nf9R+dW+/dtpfpsu5/e7mWV7i3H5veNrR9m6/brT99Wgz+6fZPP7t13H7n1UeqfxSealyrvJQZXjVXePLD/jw4cOHDx8+fPjw4f8tv8wPW37j9dsv3u2XTbdfvGe/9Gc/vNsfbJ7i3X7Zdvvh3n5/88xv8JbKa5XbKi9U3qmcqRzdviv/yM3j2345ZvM4tz+46prPftn07GfePKUNvym/tB/NL85Hd8Rfzkbm9uHDhw8fPnz48OHD/3f8/W+e/APQ6/z5+0r5qHJP5b3KXZX7Ks9V9jzFj+UVrvyV122/eLd/+ZT89v5c+Y3XObph3f7g6Nq3H93hcZ/90dFd3qHx5hkeXev2o3/ZWoYr6+YJ68vWEe2Xknf2w33vx/hDg/lVt98+m4fN0/vEmXbzrB8Ksm6eSP5lcfSJ033zHDH78OHfXP71xGmiOH/KNwt8Q37k0B/+B3momza76au6u3GO9oWz5vB3b+0d9pOjZzzFbeFznFBCCCFkc/kN0Ay+rk8fjJ0AAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

### A `strokeStyle` example

This example is similar to the one above, but uses the `strokeStyle` property to change the colors of the shapes' outlines. We use the `arc()` method to draw circles instead of squares.

      function draw() {
        var ctx = document.getElementById('canvas').getContext('2d');
        for (var i = 0; i < 6; i++) {
          for (var j = 0; j < 6; j++) {
            ctx.strokeStyle = 'rgb(0, ' + Math.floor(255 - 42.5 * i) + ', ' +
                             Math.floor(255 - 42.5 * j) + ')';
            ctx.beginPath();
            ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
            ctx.stroke();
          }
        }
      }

The result looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAwBQTFRF+vr6+fn5/Pz8/////v7+9vb2/f39+Pj49/f3+/v7zMzM+f//+f78+fz+3eXo6Ozs5/Xv5/3v5/373fb5xdvlxeDx3fzp5/X71vTt9v373fDn5+315+392Nzcxfrrwv/c2er09vj93OX9F///F//YF7FjF/9jF9ixF9g8F9iKF4qKF4rYF2P/F2PYF2NjF4r/1PTfxfXdxfX6xev6xf/6xevcFzyKFzxjxdjTwd/Vxc7mxc7TvvTRwt7/t8nJgL62fr6ZGf8+GbI+GdhlGbKLGf+LGdj/g/+7GWWLGYtlGWWyhMHRhKr/GT6yGT7YGT7/1+L03f/5FLDXFP+wFNfXFGE6FDo6xNH1xNH/1PX61Onigv+kgtXAgv/qgurqgurVgur/guqrgv/Vgv//S/+5gsD/gqikS33hwP/O1+3/t+/7t+vrt8v7t8frgOq+E7CwgKnqgKm+FrH/gJSlgJT/Sp501Nz81v/fxevr1uHhxerOOlmMfdTpfb3pff+SfemSfdSSfajUfaiSfdTUfdSofNT/fZLUfZKSfZK9fZLpR+B1R/91R+CUR8F1R6KiF4qxR3X/R3Wi1P/71P/te5r0eceZ1N3qvdzwU/HiU8a3U8bx9vv2U4ybU6nxt+3DjfX1t//5t+fVjLept9vtt9vJi567t8nb8/PzK/TpOntlF4o9QnbAHbOzS3OH9v/4VITGU3hui9jYjNKzjL7rjLPSEa+TIe59Ot69Or3eOt7/Opz/Or29Opy9Or3/Olm9OpxZOt7eOpzeOv//OXrNOs29Ov/eOr1ZOv9ZOlneOln/Ov+cece8ebzegdT/H9nZH45DH7T/H460H/+0H2lDH0NDU/+MU+LGU8aMU+KpU+L/U///U4z/U6nGU6mMt//Di9j/i9iet//ni+uejfXFi9jrFIk7i57ri57YBIAtBNVXBFeABP+ABNX/BFerBKuABP8tBC2rBC3VBKstBICrBIBXBC3/BKv/O95bOVhYO76cOd1YOb2bO1tbIbXZHbTZFImxDwDbKQAAFQ5JREFUeNrsl1tMVEcfwM/Jl/3m4O6GWwWWlkWzd31wuT2Y0MjeIMaXz4UXZLljwiWBhMRACAIJ8MLFJvrCJRJ4ImlIE3hRa02tiZqYYK2JoqYVUB5qNJr4fbFpG5vvzJzbXM7WPehX3H7Mw8yc+TGzvx1m/+c/3D+SunC7+rv6u/q7+rv6u/pJqs+n5u35yEteKh9PfzEvL3XR9FGXxdS8vEV9fT4v1fTxFyE1j9fVT80zJUXJS9XVT4rNF0tqnq7+nsXk0F/co69vSpKyq7+rv6v/t9Y/23zN4XBcaz7LgNrrTqfzei0DzjW1VFZWtjSdY0DFrcjzyK0KBvTUjLvd7vGaHgYM3Ay8Ctwc6Nmm/vFHjubiDHNGcbPj0XECTDlrEah1TpGg5W6TPcOSYW+620KArJZIRX66JT2/ItKSRYB77hoEatz3cCD0jAcGWkXQOhAY79mO/ryj2Sx3zc2OeQw4a21y11brxMBmZZMKmio3NZAfqfhK7n5VEcnXQKsbA+5WDTwO1KigJvDYuP68oxjbjGLNf96JAVOx5r9ZadcmCHbVf3ETMxaEfO2p1Y19FVO+5v84gH0VUyvlH0dfwMpxRzH+KPofl4GTAk4FVNoJYK+UQVYknwD5kSwZuCngVkCglQCtgSz8MQH9R83EAgJofiS1U7XEuAnUTkmgpYmcwTe1SJ2Wp9RST2Vwr4IEQsU9qR2voWbUjBvTP+swU0ubHWcRcDLAicC5uxYa3D2HQIQGlggCPW4GuHsQCDAg0GNIv5nafHWotpYB0lBTEwOkoYoKBqAhUFPDAGloYIABxNC79a8VMysUX4P1dR1wHR0ROwPs6JDcymdA/i10RHQAOiQ3WxnQetOQviODXgBkOGDjZICQ4YR1JQNmMyphE0lnlkqPwMbNACHdDeuADggY0zczK5glfR0g6VsYYEH6z3XAc6SvA5D+Kx3w6i/ffWHndj/Jz76ByGNCQyY28pj+PPIIbOQxoSHw/pHnQ8R9y87FfZDoW1dQ3rp8wm/dWfmtC+K9dcF7v3WTPecB84S/mHEq53Me94cZp9LfJPzFjFP5m3zcH2hPMOMk7BVpmHES9o8Fg/qCAPN95Xg3q/bIv9Ym92G+r82A+b4CmlR7ccammO/LfZjvCybNHwOivQIEmO8roIayT0x/P3HbwuMDcdsiThx+28ImkLctAuC3LXwp4rYlbEMfhhnlrkv99gT1riv2iSOn3nXpkKjedenPUO+61K9VUO+6Yn97+nGLiWopYjIyI86gKf6M99bf2bKr/xHqA7pUN1wqf1F+qaGaAXVXq6qqrtYxIKf+gsfjuVCfQ40LOZ0TPp9vopMGwN84FnoWGmv0M2DwN6/X+9sgA0Bi+pkPyxsKxfhY2FD+MJMAU7frEKi7PUWC+556FDjrPfcJkPXA11kghsGCTt+DLAJMhBoRaAxNkGDMO1gqgtJB71jWNvT59vIGq7x11obydhXMtlfV2YCAwpmtrgoDHZ56mxTkgK3e06GC/aW+Tpvct3X6SrX/SWmoUZwB0FKNIQ2AOe+TWTQsLvvEO2dcv728EHsq1Pzbqwig+Xd47Biwa/6lvgJsWwo0/9IQBkCB5j/nxb4KKKX8363PZxL2gC8sl09DJmEPhMIqBRD2QLB7ZJCF2yN/6TQIWYQ9EApCCiDsAV/qzTK4+w8bqAPX8FBqp+ooUDcltffrKVB/X2ofPKXA0wdSO9FIgcYJqR17QoEnY4b0+epyM7kAby5HYab6Ng2styHgczwWCvzTg8JMjo8CwOKDgPeHmBkhPwJeZobXb2j3GxqYcCUN1dUxQBqqr2eANNTZyQBpqLGRAdLQ4CADiKF3618qZFYovATrqwwQCq/C5oKdAfYL6IgUMEsVoEMyxoJSdEh+KWXBL4b0yzOYFTLKYV2lA6pg7dEBHlj70hmQ7oN1SAeEYO3VAV5D+i/MzArmF3BHq3QA1Bfoow9PLNQXfCywIf1nOjOewRleFnzl/X/a/f/p2d8f7+wLBR/o7Cd35GHjPogX94EZxX3AxH3x6BuM+8DyoeJ+cr91mZwHxMt5QLycB8TLeYCS8wAq5wFKzgO2l/PwWOHEjBN7FDNOpStmnDioUoGYcWJAzDiV7oKvAANixql0xYwTByEFwIwTA2LGyQPsOQF96N9glfsw31cByvflPsz31Qko31dAvWbPW2G+r4BOzV7K9xXQGNKUOZjvK58n5vuEWUL6PE/ctgiA37YIgN+2sPH9xG0LA+RtC99i4rbFb0Of43n1rksS7K5LAV696xL/bZGod116hnrXJWbA+KPcdamlEt39PymAahObAZAWQwCvO66uz6D31t/ZsqufDPptq1e633RfWW2jQXX/xWg0erG/mgY5w5eXupYuD+cwIPZ7+GX49xgD/COTLpdrcsTPgKEbwdfBG0P+7elzbTN3RouyrdlFo3dm8DAIMmf+6Eeg/w8KTC8N92ZbsnuHl6aJiJo7HY6VpFnSSmLhaeIL5K65RhAYca3lEmAyONQngr6h4GTudvTbu9etUvzkrevd2muL74hu2eRIYtuKdmCga9kGR0VmW+7CwEI4ZpOjiC0WXsCAa8WGoo641IoLA3PBjVkeJQz87EbQ+GsLtHcXYY9Fmn9HlACqP+jo6sVAr+a/EC7B/qklqj9YcGGAL1H9wVywDwN9lH8C+pmEPfSXT0NmlAJRBRD20F8GObg91AzL5yfXRQGXfExyCXvon2tMn5tZp34J6zPSxsxsUS+WLQlw08vUjOVpqTMdI8e5mAzWVqhDvbIm/cXkBgU2Jo3pt92xUitY76D4U/2WBpa3KP7kLFlosJQjbT4DpO33uxjgQmHGH2RA0G9If3WUCVejq7Du72eANDQ8zABpKBZjgDQ0MsIAaWhoiAHEUBx9TitXiji6FF2B9UUdcBHWl3sZ0HsZ1r+WMKDkV1hP6oBJWN/oY0DfDezh3frd2fQCKdndsIkygMuOwrqLAXx2F2zCacxSaWHYuBjApblgHWQAnxY0pP/GyixtfYP0dYCkb2GABem/1AEvkb4OQPqvdcDrv3z3uZ3b/SQ/+6ujzAqjq7Du72eANDQ8zABpKBZj9lIaGhlhZqChlKEhBhBD79YX4z59wu+0wUaM+zR4Ww0bMe7T53UpB4EwA8II+JnDL8Z9BIIMCPoN6afMrFPndX1G2rmZLWrpLQmkTC9TM5an0QRumtr+lNi01K6tUGBlTWonNyiwMckZ0ufEnIc84N2ZMohSIKqALvL0izmP1MkNk4e8RNp8Ebgo4MqVQZA8/WLOY0w/ZX874S9mnEq3g/AXM07lRHcQ/mLGqay1QPiLGacyY4HwFzNOBcwR/mLGyRncfY6D+b5yvNc1e+i/ZZO7MN/XfpEw31fAcpcGOJjvKyCm2iP/FRWsuDAA8325D/N9zrh+CnHbwgMHcdvCxnnitoUvRdy28A8hblv4ZxC3LW4b+lxKinrX5Yhwg911OUAATr3rwgec+JW7LjkuhhnlrkvHSvWuy0TRxPTjF55XffVoIjOJP+aNfcb76u9w+XvqpyRJSVCfazv59aFDh74+2UaTfae/O3jw4Hen99HgX8e++eLfX3xzjAEnjpw5cODAmSMnWHDq6H+OnmIAd6Ls2y9//vLbshPb1G87f+jk559ZP/v85KHzxBfYd/7g6b1i4Nx7+uB5wnPfjz8c2/up9dO9x374kQC5Zw4c+UQMg58cOXAmlwA/HS07nJaSdrjs6E8kOPV92eFULvVw2ff/be9cQuLIujheqapcU3xWO4uW4fMBdi+1u911q42ty7afbroV93YTUFB8gJFZ6MLHxsfGjWbjK6iIEl0NQ4bZJasQkl2S5SRDIJAwX2AWA/nuo6ruq4xdRkkk3mHuvX1/fW796+b0qXNCoCbqLiD/VmfrYACOKvw/MNjaSclWy0kAnw8EJy1b9Ly2ltMBtGooSiC9TEGgvTldhb9vGFXp5na61XZPVxWZmVVdPdt0q+397nVrq/Xu/W3v8juhYtX+oHZS/VsttczXaqn+rWUGqLVUf3uzn2jHyvxU/3YPcytGO9W/vd/OXPyeoL8C+XfZ88b6if+oTZx6KLOlyQKfWaAYtZ8t/2mC6plW7W+2vKGOU6+C9h4ClLo/73E/g3t/1nmUf39QcLjB+xY4EcCJBV6lBZB+RcYlCSyR8fVDesT4Bh6+JpOJTcFic8Kb/LutJr+B+h9y/E0tAjCq8fErTc9EC/MZAtW+5mrBQm3G0WSgRww2Rg8BTxXxGk8HPMkfHJTCFVn65RcJkKV0WgJkqatLAmSpq1sC3Rh0u4BuT/J/7ZR26PwV9X/USqD2D9T/JgGl9jfUL/lFUO1H3qNMtIvAbMdO8rsElPbfPclv/VlS+XMr6ltcQAvql13AMuqbf5LAT82o73EB2J/2XcC+F/mK6ProaJB8pcUFYPl/S0Ax/0a95PqG8V8s/38u+QBe+0uR1pW/fqDTv1rfV7DvG7LvG5fl+9cx8qhOQ3Ff5ZvZehcNMO6LoKUJWcC4L4JnCJgw7ougeQANMO4LoLqHgKeKAJSnA8ync+Wr6v1BYYfB+xY4EcCJBV6lBZB+RcYlCSyR8fVDATx8TcaJTQFsTqie5Osw52EtQCc5fBXAnIcDtfjwEfjMARXmPGSrumY/B2DOQyYw5+G2gjkPmcCch7OAOY83+Ugvq59+AlucfphxOmCZA8s2UNs5/TDjtKfbnH6YcTpgnwP726pH+UYA5fvWB5Tv0xtD+b4NThz1KsqY0w5IU/UmzvetD+tpql4FKN+35ijfp1uhfN+26BbUVyIf/XzZaktlfmZctcVacNUW+1vlqi2V+Y1z1Ra7FVdtqReQrwLTqXVVwN+ZU+sKJrTWFbYCTq0rGKhOrSusG06tqxoXko/+EPmRHie+gjXhQp9hGcgWBv7PlK9huBqoyllbVSz/O2038q+D/MnMSigUWslMiqB3pBwOh8sjvRKYOUi9Tx3MSGBtdDX5Lrk6uiaCqdJeJBLZK02JoHF2r1Ao7M02XlB+8GUo0w8DZ38m9DLIhpGmcnikD4K+kXCZBWrTUWrGDwOnfyZ1xEfUjeSov96o948mN3ws8G1ESm0wPraVIhwAA8fPZzGYfX7su4j8oVAmYD/CMqEhBoRHnKfTSJgBw6lTB5ymhinYTY5WqeRvvKpGk7sUJCKbzmNrM5JgQKG0jgOeYayXCgnP8sFQiHnQqp2OfmMo3MeAWqp/OMXkBqaf6t9N+hkLv6MfJCJtjEUb1Z8oMEBtE/RXID8Y4lI2qN9yk2BYyMzCFmhKCZlZyvIfX1IAScsbfKx6eDdtERtw6pF+XwXyAW36ywzgmp55ScbyCQ/ASZmAo1PB4vSIjBsCUE83yGRjU7DYJAAmzILF5gT78Xz5wZApqDRDQTT0hiUQ7sUgJYEUBmtJQwBKcg0NUxFFBJEpDJ6L4NbzKU/yM8LhO0sjIxIgSzMzEiBLo6MSwEt6qSSukyV9dlay4JbOl7/SL+3Qv4L6cp8E+rD3HPgl4D9A/aoLWEX9YZsE2g5Rv+cC9jzJDzVIJ9MQQkNYAqAhjPpUvQTqU6hPSkCtT6IhUiNZ1ERQX5CAWlPwJt+UtjaJfBeA5b93Ae9R/86QgPEOy1ckoBD5LqDwlacPLu/0AT59VT59/azTBx5P/3r7frUceVS8pF5G5FHJkhx5rCU58qgeI8+Vxn3Dc9xXPMZ9ID51Neupq3l+6mqen7rgq5+68Pg7uR06yeFDEK7lAMx5yATmPLyDp5oskBRA0kcmMOfhHTxig4IACj6P8vUhTj/MOO0pzDiZr/WFHTDM6YcZpz3dZfWjjNM2TrD6dZhx2vMEpx9mnMCjfKQ/E7DmKN+n1x+G+b4NRqh6pP/UAadUPdI/WmVNUb5Pr4HyfRvAfB/oVH9p3ZqifB94lg90rtpi1jWu2mJNuGqLA2y1xWwFuGqL9fY6ttoCF5APm1PrCjemO7WuaOHUuiJwal16wlgmrXWBygHg1LqSrErlg2rAb8pcFpC/PZOW7avLJu7Lpq7DZd3t0sLkPPn6NWk38q+D/MnxJ/lP+Sfjk8I6mFx8nPuYe7woAn1t7lH2Q/bR3JoEFqaj0ej0ggQax6Zjsdj0WKN4jcb5f4rF4j/zjReUH1zJj+PAOZ5fCbKgt5xbxIFzMVfu5cBBdq4DBs6OuewBB3yr0YWOeqW+YyG66uPAYWwsDuNjfCx2yIGp4xfzGMy/OJ66iPyh/HhAB+gc9MB4foiC4dybAIkUeuBNbpie13D2bQB/X9cDb7MM2I3u3NFRmIcWO9FdulUiBgH+in5nJ5agFoni2G1iAW6PFRPe5Q/l+3XN/qD1U/3DuT7ma31U/3C2gwEdVP9ulANUfyIWxzdLJMep/kQxzsoV9FcgPwjVs60/T/wHBDn1SL/lWL2cel3ryFr+4+PUI/2Wm/hicc4iHiMA+Dj1uh4v+jzKX8kIDpdZIWP5jQDelMl49FYAb4/IuLojgJ1VMh4KQNs5JJPjkmBROvYkX5vMm8IOZh6Hmd6cBHIIgN6sBPDxa2tRRVBpRnH8mYoJQDdi+Ffa+EIEyotGT6c/Pi6FK7K0uCgBsjQ3JwGytLAgAbI0NiYBsjQ/LwFu6Xz5T/rFDUD/EzQ87pNA32M0POqQrtnxCJ31tAuYRv10XAJxDP6VAIj/60l+vkHauiGP+pwLyKE+Wy+B+izqoy4givpYjQRqYqgvuoCiJ/mfTGkH8xPqP0oAmB/R8MHF4gPCouvDdgvJBzEXgOSDogyqij/S6V+p7wPs++AKff96Rx7vcV+vPO7rJO5rZ8V97evj/jd56uqX9dTVtcvLebSzch7tCnMenHGy6i+ecWpfzDgZkWdlnPHKMk7u7Z0437fmKN+nBOX7NoD5vrOO830bwHzf2UlH+b714Q7M9+lWKN+3prdhvu9Y4HzfBjDf518sWol8ja+2WBJkqy3Wgqu2WMBVW+xWXLXFWnDVlqZ7lw+bU+vy9wWLYLvWFS2cWlcCdq3Lb6Xpa3atKxjoTq0ryapU/plNF0ZvVuJhoLv4wjX0S5f/bduN/Bv5N/L5f79/PdSf8e/3uZc2f79Nf+D+euAa3/U4fZ/7y5lvsS9t/n7bWa/G1h40+h585/5vPPCd9WJyTau61q+F95zEfJNfrvYF+det3ci/kX8j/0b+jfwfS/7/ARqgd3o3bDAiAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

## Transparency

In addition to drawing opaque shapes to the canvas, we can also draw semi-transparent (or translucent) shapes. This is done by either setting the `globalAlpha` property or by assigning a semi-transparent color to the stroke and/or fill style.

[`globalAlpha = transparencyValue`](../../canvasrenderingcontext2d/globalalpha)  
Applies the specified transparency value to all future shapes drawn on the canvas. The value must be between 0.0 (fully transparent) to 1.0 (fully opaque). This value is 1.0 (fully opaque) by default.

The `globalAlpha` property can be useful if you want to draw a lot of shapes on the canvas with similar transparency, but otherwise it's generally more useful to set the transparency on individual shapes when setting their colors.

Because the `strokeStyle` and `fillStyle` properties accept CSS rgba color values, we can use the following notation to assign a transparent color to them.

    // Assigning transparent colors to stroke and fill style

    ctx.strokeStyle = 'rgba(255, 0, 0, 0.5)';
    ctx.fillStyle = 'rgba(255, 0, 0, 0.5)';

The `rgba()` function is similar to the `rgb()` function but it has one extra parameter. The last parameter sets the transparency value of this particular color. The valid range is again between 0.0 (fully transparent) and 1.0 (fully opaque).

### A `globalAlpha` example

In this example, we'll draw a background of four different colored squares. On top of these, we'll draw a set of semi-transparent circles. The `globalAlpha` property is set at `0.2` which will be used for all shapes from that point on. Every step in the `for` loop draws a set of circles with an increasing radius. The final result is a radial gradient. By overlaying ever more circles on top of each other, we effectively reduce the transparency of the circles that have already been drawn. By increasing the step count and in effect drawing more circles, the background would completely disappear from the center of the image.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      // draw background
      ctx.fillStyle = '#FD0';
      ctx.fillRect(0, 0, 75, 75);
      ctx.fillStyle = '#6C0';
      ctx.fillRect(75, 0, 75, 75);
      ctx.fillStyle = '#09F';
      ctx.fillRect(0, 75, 75, 75);
      ctx.fillStyle = '#F30';
      ctx.fillRect(75, 75, 75, 75);
      ctx.fillStyle = '#FFF';

      // set transparency value
      ctx.globalAlpha = 0.2;

      // Draw semi transparent circles
      for (var i = 0; i < 7; i++) {
        ctx.beginPath();
        ctx.arc(75, 75, 10 + 10 * i, 0, Math.PI * 2, true);
        ctx.fill();
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

### An example using `rgba()`

In this second example, we do something similar to the one above, but instead of drawing circles on top of each other, I've drawn small rectangles with increasing opacity. Using `rgba()` gives you a little more control and flexibility because we can set the fill and stroke style individually.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // Draw background
      ctx.fillStyle = 'rgb(255, 221, 0)';
      ctx.fillRect(0, 0, 150, 37.5);
      ctx.fillStyle = 'rgb(102, 204, 0)';
      ctx.fillRect(0, 37.5, 150, 37.5);
      ctx.fillStyle = 'rgb(0, 153, 255)';
      ctx.fillRect(0, 75, 150, 37.5);
      ctx.fillStyle = 'rgb(255, 51, 0)';
      ctx.fillRect(0, 112.5, 150, 37.5);

      // Draw semi transparent rectangles
      for (var i = 0; i < 10; i++) {
        ctx.fillStyle = 'rgba(255, 255, 255, ' + (i + 1) / 10 + ')';
        for (var j = 0; j < 4; j++) {
          ctx.fillRect(5 + i * 14, 5 + j * 37.5, 14, 27.5);
        }
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAALFQTFRF////+fn5zMzM+/v7AJj/9/f3/v7+/90AZcwA/zIA/f39/+dMf8z//+5//+QyhNYyddEZMqz//4RlouBlTLj//1sy/0cZ/+tlsuZ//5h/GaL/k9tMZcL//+AZ/+rl//GY//jM4PXM/3BM5fX/suD//6yY7/rl//WywuuYmNb///zl0fCyzOv//8Gy/9bMuN0+tYGH/2I76urq3d3dbMX/l91SGqP//3RS/08j/zwL/+xsBWCVNQAAAl9JREFUeNrt3WlT01AYhuGkJUErIIu4gOzgjug5bvD/f5ilbWKekBNDJfY9cN9Jywww0yvPlC8MTJKEiIiIFlDq/MB43qUBfJ557zLjOe+zwPb28dMLaN7f+SyKvGvkxzH+9fyN/MHsq9OHzXPyGLTx7Xdv+Y71+/257cBfNlnn9eEviO9Yv0e+68zfk9akJ9ILaVU6kN5Kh9IHSWlzrA8fPnz48OHDhw8fPnz48OHDh/9P/HR2GOUXPNZn/X7XX96rHrWLmR7Fh9qlXV9d8Wi70CtptaU51o/vN8y6vjk+68ew/oXJOq//yGSd1zfKZ/141l8fH+VTrafV80a7f56079LW1vgsH9pLaY71a171SW0v/E76KB1Jb6R8VCnvtH5aZICvtAmo5MGHDx8+fPjw4cOHD//h8Yezwyi/4LE+67M+67M+699Y31y3W98en/VZv/f1l0z2t/WHRTb5JQ8+/H75O9KG9Ex6La1I76VT6ZN0IikNPnz48OHDhw//Dvmj2WGUX/BYn/VZn/VZn/VZn/VZn/UXsn759/LT3ynuVI8f2kb1qF9a9Wy70G/SSksTT8nrxrcWfPj987+YrDP/scngw/9P/EvpufRL2pa+asfjyqef0uZm9dReSXPwFazEY6nthc+kc+mztC/pP/1Fx1cafPjwW/h5kU1+yYMPHz58+PDhw4cPHz58+PAfCF+/21wNUPjw4Yc+azD48O+aP4xD3/z3PHnops3GGmXNtwcO3DXYXIGbM6eBzxsrdGvsJPM+M/7+H2bBG5MnedS3hZ9cgfW3Tp4nREREkfYbS+lztTpXkG4AAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

## Line styles

There are several properties which allow us to style lines.

[`lineWidth = value`](../../canvasrenderingcontext2d/linewidth)  
Sets the width of lines drawn in the future.

[`lineCap = type`](../../canvasrenderingcontext2d/linecap)  
Sets the appearance of the ends of lines.

[`lineJoin = type`](../../canvasrenderingcontext2d/linejoin)  
Sets the appearance of the "corners" where lines meet.

[`miterLimit = value`](../../canvasrenderingcontext2d/miterlimit)  
Establishes a limit on the miter when two lines join at a sharp angle, to let you control how thick the junction becomes.

[`getLineDash()`](../../canvasrenderingcontext2d/getlinedash)  
Returns the current line dash pattern array containing an even number of non-negative numbers.

[`setLineDash(segments)`](../../canvasrenderingcontext2d/setlinedash)  
Sets the current line dash pattern.

[`lineDashOffset = value`](../../canvasrenderingcontext2d/linedashoffset)  
Specifies where to start a dash array on a line.

You'll get a better understanding of what these do by looking at the examples below.

### A `lineWidth` example

This property sets the current line thickness. Values must be positive numbers. By default this value is set to 1.0 units.

The line width is the thickness of the stroke centered on the given path. In other words, the area that's drawn extends to half the line width on either side of the path. Because canvas coordinates do not directly reference pixels, special care must be taken to obtain crisp horizontal and vertical lines.

In the example below, 10 straight lines are drawn with increasing line widths. The line on the far left is 1.0 units wide. However, the leftmost and all other odd-integer-width thickness lines do not appear crisp, because of the path's positioning.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      for (var i = 0; i < 10; i++) {
        ctx.lineWidth = 1 + i;
        ctx.beginPath();
        ctx.moveTo(5 + i * 14, 5);
        ctx.lineTo(5 + i * 14, 140);
        ctx.stroke();
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+BAMAAAB5WqiuAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAACFQTFRF+Pj4/////v7+/Pz89/f3AAAA+vr6d3d3hoaGzMzM4eHhvQFXNQAAAhtJREFUeNrtnE1LG1EYhbNJSLOrummXpoJuUzKky0IUm5VUj7MdSCOxq2Ak/2D2/RBBVxaC4PzK3vPOROZClveKH+cQchYPPDlkOfBO433cNOSXX/7Y/s7DTdjc3tf9n4rlMGxGxdeavxNa737gruYvhuFTPKH/KoL/m/zPyj8aDpeBvvjR/y//y/MfXlrtn1jlqRVgCCDcBwhzIDVEeMi6JCqh/PLLL7/88r8K/69GlfbMqnlkladWgCGAsAkQ0m+IsM2aEZXQ8k5++eWXX375Y/tbVdozq+ZRxjg/CzDkFEROQUQ/EaHnX6k8f/a4P/P2t/z9mbe/tXZ/pv3ar/3a/4b2X59VmS6sJqdWeWoFGAIIJwAh/YYIp6wFUQkt5/LLL7/88ss/rjJdWE1OE8b5WYAhpyByCiL6iQg9/0rl+ZPH/Ym3f+zvT7z947X7E+3Xfu3X/me0/+/nKoO5Vf/YKk+tAEMAYR8gpN8Q4YA1Jyqh5Yv88ssvv/zyd6sM5lb9Y6s87bk4CYt+Iqcgcn5DhJ5/pdpbs79X7u95+7v1/T1vf1f7tV/7tV/7o+7/s11l98Jq57tVnloBhgDCHYCQfkOEu6wLohJa9uSXX3755Zf/tfgD5in9vyNcnn6QX375y+f/Efy15/+by/D6zVH9fjnC/vr9cudfcP3H+n33VnEQWP/Du0/f/hn8vv4u7vsBNvT+BPnlj+7/D9e99Fyq0bz2AAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

Obtaining crisp lines requires understanding how paths are stroked. In the images below, the grid represents the canvas coordinate grid. The squares between gridlines are actual on-screen pixels. In the first grid image below, a rectangle from (2,1) to (5,5) is filled. The entire area between them (light red) falls on pixel boundaries, so the resulting filled rectangle will have crisp edges.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAc8AAACYCAMAAAC1WpLiAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAYdEVYdFNvZnR3YXJlAFBhaW50Lk5FVCB2My4xMHKyJZIAAAD5UExURQAAABQAAAAMU3+k/kFn/r3i/v8AAP/r6////1hw/v88PAAlQQAmvQAYpiWRMP8kJYXBizydRjw8PP+Fhc3mzwB/Dv/Z2SUlJf/MzJPJmL3dwIWFhTxZ/yVF//9jY2NjY1GnWszLzWOwa/j39xyMJ4WX//+/v1FRUczT//+jo8C+wKHPpv9RUWuB/9nr2/+UlNnZ2ZSUlBEWEv/m5qm1/9ne/9kAAXS5e7/I//+xsZcABr4AAABqCv90dAAFKDwAAFFq/wAggKOjo+Lr43R0dLGxsen06iYAAJSj/3AAANp8jAAm/+bp/+dPWQAey86lugBKB+0AAAwAADUGzsQAAAfSSURBVHja7d0NV9rIGgfwrL2yz83uJkDY8JZEBUFQEKuAvIjQ2ta3vu39/h/mziSTcbF211ojT/Q/p8XxoZ7z7/yYmSRnztEgtOfUDAwBPNHYexZ3l+uv80wCcg3GNJfyrG4Qva2+VtGq74nyb1nk4xqMay7lmd+larGafyf7O/lq8T1Vd1h4cg3GNZfyLG5Rvkq7RdV/l6ctHusH12Bcc914Fqu0JeMdGFtUzdMuG0+Wwbjmitfbt7SR39rYoY0Nym9siY+e3CA4rGtMg3HNpTxfi8V/o7hzQMXXdLBT3Ag3CA6NazCuueL7lfz78Mtu8ewmL48JyjQY01yx58FB+OVdvAkccLlB5hqMaa6l50MGh3ZnSqbB+OWC57P2/LcZ/IS1NATjlwue8IQnPOEJT3jCE57whOdz9Gyer9LTdR8nFzx5zE+7+b1/15sm5jkYLNf66fJUc0DX2nw8nYDGjuOGtZ7j9FT5yKkTTdtJefqj5Vq3mypPNQd0zRyz8TSbFDiBfSRrtmkGUTWwMyWiy05Cno0uDRqNflQbNYjq/scUecZzIKy1xRQYm2w87VL0auh+uHXWZX9uJuTpjWjR7V4PZM3zfVm5SJFnPAfkyju05SDZLidPJzBlrZTp9JbqiXn6LZJzsiVro5b0bDRS5BnPAfmfOHfkIJklNuut2CM7plhvO27dceyAArnkuiW77dJlkKSnt4hqoWc3bZ5yDoQ1Zp69cI80HeEpdwaTbDlHA1NupdNmUuttn0beojWgxRq1+n6rLispWm/VHKBOm+YzaRmuvTzuV8yxWxrbbUNOypLZad5ES+5+5WJBXc/zuq3rU1qIzsVHP03Xt/EcKGVcdyo++W5bzFGXiafrBrY9k7WebXdodrNnusk9H1LTsevH9yuNVN2vqDkws+P7leYLf96nnid4XVUbpe15QjgHzJmqNenZe96zDTMPb8MfPj30oHM6p2txm+je6SMfa/q580OPk/BRnt9mfv22/XLPWibR+bket1f/iVtG917pdzk8v137b9wyurf2pOstPOEJT3jCE57whCc84QlPeMITnvCEJzzhCU94whOe8IQnPOEJT3jCE57whOfPex7e79BK5peHt8yDzg/dM5jxW9ze/B63jO690e8+2vmhw4efH1r7I24Z3VvD+SHMT3jCE57whCc84QlPeMITnvCEJzzhCU94whOe8IQnPOEJT3jCE57whCc84QnPFXoaXM8PGUzPDxk4P4T5ifUWnvCEJzzhCU94whOe8IQnPOEJT3jCE57whCc84QlPeMITnvCEJzzhCU94Ph9PnB/C+SHMT6y38IQnPOEJT3jCE57whCc84QlPeMITnvB8TE/Xvftn2/C8w3Nra9mzzc7Tbt79s8EMnt962l+WPc0xM08noLHjRHO05ziXYcdxnGbdPoLnbc+rT+tfri6j0WqKUaKxyczTbFLgBJGdbZqTcAnOmGaPxB943vI0v6x/uppEo9WxzY4YM5eXp11aeg1/tmRHkxSetz3tXXk9FI2WGY6PWeLn6QThqlHKdHrhzzp2IPb5GTzv9LyaRGusbTpH/DxNIdcxxQrSceuOY08oCMTOMMu0w3fgeWu9vVpf/zSVo9UW65cpYNVVBhvPXketHR25EThTsntR4cjG9e1d10NivTWdUsaN9qU2t+shccXtlsa2nItuqWROm+ID1xSFXuD8qOc9fx3XX5mHt78S/f1lup2uxW2oe6fhO9P5+Xw+vJwMjf/N5+J1Ol/N7y/7fsLz88lwOJG9y+FwakymhhEW5kmdH3qKWmLBXDewhzMyZ+Tattg7myt6npDIgL1Az0cMBs8n9jxTtQ91rp5n6rsoITz/qba3XVO18na5ztEzSkg6Ybo8B4PlWj9Rz73tXEXXCptLojw844SkE6bL0x8t17x+cp5n23/ebtsVXp53JDxMk2ejK/423khUGjUaDep7Cc7Ps5qakcbSbGXkqRPerCepmp/eiAbX3ucL2V/43kJM2EGS+6dYwfZUrbKkyWb/VAlJJ0yVp9+ilq9qXiN8bSV7fVuoqNp+hen1bSEOtl9J3fWt8Gz43eiRlu81PibvifvPRNfbvtg2u9d9WvTFPuqJzdP/CM/0el4s5OvnRutabpti6U30euj7tc2srIlX2awCQ88om0p4UuB6v+L1R63+54uuT/VWS7x6o5V47tdlLZcNLVl67oeXvSohX8/BoOv7b8jr0sD3xd45Svj5UCWr7tuzZTlI4rvsPpUr5QoZ2Wwum7WOy2RVwjdX5BklJJ3Q0AlJJzzRCV/4876cZYW1rJXNHRN9sPYr1jFZe+Jzf1ITxcgzdyyKK/JUCUknNHTCnE54ohO+cM9KIfIUo1OxwvXreDMnarls4eTv6202typPlZB0wq86ofX39VYlfOGepDytbNTby1kVq1Zj5KkSkk54ohPC89vnQ3tWob6/adRyhdpmOGzik/9nRYzTh5NyQYyhVS6s1lMlJJ3wRCe0dEJ4xvcluVyuLDypZm3uy4L45JfFsNXKdCi2zbLYtnIk3inXVuWpEpJO+FUn3NMJv+qEP+658va9ceMZjF8unDfB8yF4whOe8IQnPOEJT3jCE57w5Ov5M8cKD5P0fOJg/HL9uyeHxjUYv1zwfMaeaKlv8IQnGjzR4IkGT3iiPaf2f+HuS/dgEX3OAAAAAElFTkSuQmCC" class="internal" width="463" height="152" />

If you consider a path from (3,1) to (3,5) with a line thickness of `1.0`, you end up with the situation in the second image. The actual area to be filled (dark blue) only extends halfway into the pixels on either side of the path. An approximation of this has to be rendered, which means that those pixels being only partially shaded, and results in the entire area (the light blue and dark blue) being filled in with a color only half as dark as the actual stroke color. This is what happens with the `1.0` width line in the previous example code.

To fix this, you have to be very precise in your path creation. Knowing that a `1.0` width line will extend half a unit to either side of the path, creating the path from (3.5,1) to (3.5,5) results in the situation in the third image—the `1.0` line width ends up completely and precisely filling a single pixel vertical line.

**Note:** Be aware that in our vertical line example, the Y position still referenced an integer gridline position—if it hadn't, we would see pixels with half coverage at the endpoints (but note also that this behavior depends on the current `lineCap` style whose default value is `butt`; you may want to compute consistent strokes with half-pixel coordinates for odd-width lines, by setting the `lineCap` style to `square`, so that the outer border of the stroke around the endpoint will be automatically extended to cover the whole pixel exactly).

Note also that only start and final endpoints of a path are affected: if a path is closed with `closePath()`, there's no start and final endpoint; instead, all endpoints in the path are connected to their attached previous and next segment using the current setting of the `lineJoin` style, whose default value is `miter`, with the effect of automatically extending the outer borders of the connected segments to their intersection point, so that the rendered stroke will exactly cover full pixels centered at each endpoint if those connected segments are horizontal and/or vertical). See the next two sections for demonstrations of these additional line styles.

For even-width lines, each half ends up being an integer amount of pixels, so you want a path that is between pixels (that is, (3,1) to (3,5)), instead of down the middle of pixels.

While slightly painful when initially working with scalable 2D graphics, paying attention to the pixel grid and the position of paths ensures that your drawings will look correct regardless of scaling or any other transformations involved. A 1.0-width vertical line drawn at the correct position will become a crisp 2-pixel line when scaled up by 2, and will appear at the correct position.

### A `lineCap` example

The `lineCap` property determines how the end points of every line are drawn. There are three possible values for this property and those are: `butt`, `round` and `square`. By default this property is set to `butt`.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAD9QTFRF9/f3////zMzMhoaG+fn5/f39AAAA+/v7/Pz8/v7+d3d3h87/dsn/7Ozs3t7eQWiCdnZ2vLy8IiIiCwsLlJSUioh4IQAAAmBJREFUeNrt3WFzojAQxnFC01I8NwXt9/+sZ8+7UVJyIZBItv6XcdoXbubn48IrZ7YxqquBDx8+fPjwlfKtuLbycmID/L5xTprKS5xr5vm2fvz1A9g5fi+uUVFOZtP/G37NX4Fc45/lt94bpb4/V1kb5Nf/BVyqjacPv9TsR/i3AdpxyGdesiB9+QnDI1XPj6rZl3W3rmx/yfj5OcrC09qXSY3TZ/39o///z/1ckyPD+e1S52HZgS9vkzrs/OB0p3+Sk9PHl9ONchJ1/MNCS518Od9bzqKMP04x4z78X2vrY4r5WN2xiX+8ln/0MVrZOnIMj/fFDsmjkLVjK/+Qc5IfcOvChw8fPnz48OHDh5+FbwPX96Nt5CrakZi+Tc6ybAfpkz7pkz7pkz7pkz7pk/4u6dtg+UfbaJXsgA8fPnz48OHDhw8f/hPyu8D1/egucpXsCPG7xcl0yVlm7CB90id90id90id90id9rel3wfKP7qJVsgM+fPjw4cOHDx8+/F3478Hyj36PVskO+PDhw4cPHz58+PDhp/Nfg+Uf/Rqtkh3w4cOHDx8+fPjw4cN/On4fLP/oPlolO+DDhw8fPnz48OHDh5+Fn3uXQXrHJv5xbWXbfpBjeJLL+KszkodnyDj76eUvLtn11l1Rh8Q7dzs/6/bP6dKeBQ0+P/zOR/DN/coko49vbgurjEb+5QP8WRe28M3jMKlxf/6W6nXzDXz4j+N3OvSB3+870cEPrAcWp4M/v5y5tzriD6zGvvzvnFQ+/114MbnpG81r4b8+QF/97EyFjVFd8OHDhw//ufi/AcbfGEtcUO62AAAAAElFTkSuQmCC" width="190" height="190" />

`butt`  
The ends of lines are squared off at the endpoints.

`round`  
The ends of lines are rounded.

`square`  
The ends of lines are squared off by adding a box with an equal width and half the height of the line's thickness.

In this example, we'll draw three lines, each with a different value for the `lineCap` property. I also added two guides to see the exact differences between the three. Each of these lines starts and ends exactly on these guides.

The line on the left uses the default `butt` option. You'll notice that it's drawn completely flush with the guides. The second is set to use the `round` option. This adds a semicircle to the end that has a radius half the width of the line. The line on the right uses the `square` option. This adds a box with an equal width and half the height of the line thickness.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      var lineCap = ['butt', 'round', 'square'];

      // Draw guides
      ctx.strokeStyle = '#09f';
      ctx.beginPath();
      ctx.moveTo(10, 10);
      ctx.lineTo(140, 10);
      ctx.moveTo(10, 140);
      ctx.lineTo(140, 140);
      ctx.stroke();

      // Draw lines
      ctx.strokeStyle = 'black';
      for (var i = 0; i < lineCap.length; i++) {
        ctx.lineWidth = 15;
        ctx.lineCap = lineCap[i];
        ctx.beginPath();
        ctx.moveTo(25 + i * 50, 10);
        ctx.lineTo(25 + i * 50, 140);
        ctx.stroke();
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAD9QTFRF9/f3////zMzMhoaG+vr6+Pj4AAAA/f39/Pz8/v7+d3d3h87/dsn/7Ozs3d3dQWiDdnZ2vLy8IiIiCwsLlJSUdGB7kwAAAn9JREFUeNrt3eFSqzAQhuGkgkLtRmi9/2s9PVXHEtkmKYEm03cZRxnZ+PAR9I8za2zVZeDDhw8fPvxK+a24XeHlpFX4vXFOTOElzpl5fls+/usG2jl+L85UUU5m07+EX/jH5ZOb5e/qCF/Mrma+uc0vdesYCfOl9I0TTL9kuInhXz0qKeHcv4/I9KWUc5meh/e+5EOkrmeC37+dvsQsEjj/fvTj5+coJm693cukxtkGSXp15fZT1M6/T4bT67lOg0Td9MvrpPb6k4njL9yq7vgjOTrvepk7n+PP/6gtfnHK8ZdyjPlzcotvNufvIy1l8uV0bTlJZfxxihkfw3+/tz6mmI+7OxbxD1/lL30IVraOHJvHe7BD8lbI2rGUv8+5kzd4deHDhw8fPnz48OEXwm/V8pdug7VmB3z48OHDhw8fPnz48OHXxm+U4+/STeBYs0PjN9HJNMlZZuwgfdInfdInfdInfdIn/VrTb9Tyl26CtWYHfPjw4cOHDx8+fPjwn5DfKcffpbvAsWaHxu+ik+mSs8zYQfqkT/qkT/qkT/qk/8Tpd2r5S3fBWrMDPnz48OHDhw8fPnz46fw3tfyl34K1Zgd8+PDhw4cPHz58+PCfjt+r5S/dB2vNDvjw4cOHDx8+fPjw4Wfh555lkN6xiH+4t7JNP8ixeZLL+qMzkjfPkHHvp5c/uOShr+4dtU98c5fzs07/nA7tiWjw+fqVW/Dt9cgkWx/f/g6ssjXyzzdwGRcWefE4TGp8PH9J9XXzLXz42/GbOvTK/+87qYOvjAcWVwdfGc7c1hG/Mhr7/LVzUvj+b/TB5Laveiz8/xvoi987U6GxVRd8+PDhw38u/j9+9zvAu5qbDwAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

### A `lineJoin` example

The `lineJoin` property determines how two connecting segments (of lines, arcs or curves) with non-zero lengths in a shape are joined together (degenerate segments with zero lengths, whose specified endpoints and control points are exactly at the same position, are skipped).

There are three possible values for this property: `round`, `bevel` and `miter`. By default this property is set to `miter`. Note that the `lineJoin` setting has no effect if the two connected segments have the same direction, because no joining area will be added in this case.

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAADxQTFRF9vb2/f39+Pj4+vr6////+fn5/Pz8AAAA/v7+9/f3+/v7bW1tzMzMfHx83d3d6urqbGxsGBgYS0tLw8PDLa0lCgAABTdJREFUeNrt3Y1u2zgQBGC5MR2eFMv9ef93vUvTuJZNcmd2p6yF4wIFCmM5+8WQHYUSoOm465oGf/AHf/AHf/B3yk+X9e3Ja72kCj9P63qZnrwu6zqV+en58R8/QCryL+u0i1ovRf4+3vz3t7/If5t2Um+DP/iDP/iDP/iD/3f5/+ykBh+qH9+/ffv+Y6f8w/n1Z51zZ75kXl5ef9WiyYP5inm/9Rp/XmC+YN6t/lWTh/PD87Z6TR7BD86710vyGH5o3qNekUfxA/NKekEex3fPK+vjeSTfOa+mD+exfNe8uj6aR/Md8+70X78G/Td5PJ+ed6df8sML/jwHn5xXwIb8m8UePjWvSA34t0tdfGJeBer23y3Ezzhd86rMrMnDz/c98xqLxHkV/pdrPSz9YlZziTbP5PPzjAXSPJvPzjPblXkAn5sHNAvzED4zD2rV5UF8fB7YKMvD+N1ZaBvI731QoE0ov/NHEm2B+X2/ENE8nN/11xGaR/B7ngygeQy/FenQK/Iofj3UpRfkcfxarFMfzyP55WC3PpzH8kvRAX00r8JP9bI3QBJVoTyen6ztp5RCfirPwU/tzb+Ugn4mz8NPra3XlJR+K8/FT/WN75SUfjPPx0+1yw7l7pfj+Xxe/vt3zpI8nM/MW+zmRZMH84l5UKsmD+bj88BGSR7O78pC2wh+z4MCbWL4HT+SaB7Fb4Rdb3TRfCGieRy/8QX8cZuR7tcRlkfyu58MGHksv/epmJFn8V8+62beC1nWiXAg7/oazKfn2X+G+PMcfHJeARvybxZ7+NS8IjXg3y518Yl5Fajbf7cQ5vvmVZlZkwfzXfMai8R5Ft8zr7lEm2fy+XnGAmmezWfnme3KPIDPzQOahXkIn5kHteryID4+D2yU5WH87iy0DeT3PijQJpTf+SOJtlT482M9hNENfyAP51txpF6TR/DbgbReksfwW5EOvSKP4tdDXXpBHsevxTr18TySXw5268N5LL8UHdBH82j+bG+AzHPIz+Tx/Nnafqoty9o8L39ub/5VFy1Zmefnz62t18YSh986El38ub7x3VxA+83PkY8/1y47GO2k3/4WsPjMPAC3aPIs/umzlnwqV+mSG9Cqybv+1+Lj88BGSR7O78pC2wh+z4MCbWL4yDxCr8ij+I2w8687XY6EXpDH8avzjsfTy+k0H46Z0cfzSH79/WpW62QglMfyXfPap2KRPJrvmGedCAfyeD49z/4zxJ/n4JPzCtiQf7PYw6fmFakB/3api0/Mq0Dd/ruFMN83r8rMmjyY75rXWCTOq/AP13pYejCruUSbZ/L5ecYCaZ7NZ+eZ7co8gM/NA5qFeQifmQe16vIgPj4PbJTlYfzuLLQN5Pc+KNAmlN/5I4m2wPy+X4hoHs7v+usIzSP4PU8G0DyG34p06BV5FL8e6tIL8jh+Ldapj+eR/HKwWx/OY/ml6IA+mlfh50aZGyBkRfIcfGv7Kcf8VJ6H3978y1E/k+fit7Zes9Rv5fn49Y3vLPWbeU5+7bJDlvrtPC+/fNEnS/1AnptfuuSWpX4kz89/vOCZpX4oL8C/vw6bpX4sL8LfXofNUj+YF+LfXofNUj+aF+P/vtElS/1wXpD/eZtRlvrxvCj/4yavLPUTeWH++y120qLy4vy/WoM/+IO/4e/lwaKDP/iDP/iDP/jv9+/vQ1++fz+v+3jK92EqPx749qnBz1yVhzOn29eft2qPxj5O6zo9+fE/T9UHkx/zrh8L//MnePZDJ2+F+/i2qdbgD/7gD/7g/7/4/wIhdQJGjM27PwAAAABJRU5ErkJggg==" width="190" height="190" />

`round`  
Rounds off the corners of a shape by filling an additional sector of disc centered at the common endpoint of connected segments. The radius for these rounded corners is equal to half the line width.

`bevel`  
Fills an additional triangular area between the common endpoint of connected segments, and the separate outside rectangular corners of each segment.

`miter`  
Connected segments are joined by extending their outside edges to connect at a single point, with the effect of filling an additional lozenge-shaped area. This setting is effected by the `miterLimit` property which is explained below.

The example below draws three different paths, demonstrating each of these three `lineJoin` property settings; the output is shown above.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      var lineJoin = ['round', 'bevel', 'miter'];
      ctx.lineWidth = 10;
      for (var i = 0; i < lineJoin.length; i++) {
        ctx.lineJoin = lineJoin[i];
        ctx.beginPath();
        ctx.moveTo(-5, 5 + i * 40);
        ctx.lineTo(35, 45 + i * 40);
        ctx.lineTo(75, 5 + i * 40);
        ctx.lineTo(115, 45 + i * 40);
        ctx.lineTo(155, 5 + i * 40);
        ctx.stroke();
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

### A demo of the `miterLimit` property

As you've seen in the previous example, when joining two lines with the `miter` option, the outside edges of the two joining lines are extended up to the point where they meet. For lines which are at large angles with each other, this point is not far from the inside connection point. However, as the angles between each line decreases, the distance (miter length) between these points increases exponentially.

The `miterLimit` property determines how far the outside connection point can be placed from the inside connection point. If two lines exceed this value, a bevel join gets drawn instead. Note that the maximum miter length is the product of the line width measured in the current coordinate system, by the value of this `miterLimit` property (whose default value is 10.0 in the HTML [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)), so the `miterLimit` can be set independently from the current display scale or any affine transforms of paths: it only influences the effectively rendered shape of line edges.

More exactly, the miter limit is the maximum allowed ratio of the extension length (in the HTML canvas, it is measured between the outside corner of the joined edges of the line and the common endpoint of connecting segments specified in the path) to half the line width. It can equivalently be defined as the maximum allowed ratio of the distance between the inside and outside points of jonction of edges, to the total line width. It is then equal to the cosecant of half the minimum inner angle of connecting segments below which no miter join will be rendered, but only a bevel join:

- `miterLimit` = **max** `miterLength` / `lineWidth` = 1 / **sin** ( **min** _θ_ / 2 )
- The default miter limit of 10.0 will strip all miters for sharp angles below about 11 degrees.
- A miter limit equal to √2 ≈ 1.4142136 (rounded up) will strip miters for all acute angles, keeping miter joins only for obtuse or right angles.
- A miter limit equal to 1.0 is valid but will disable all miters.
- Values below 1.0 are invalid for the miter limit.

Here's a little demo in which you can set `miterLimit` dynamically and see how this effects the shapes on the canvas. The blue lines show where the start and endpoints for each of the lines in the zig-zag pattern are.

If you specify a `miterLimit` value below 4.2 in this demo, none of the visible corners will join with a miter extension, but only with a small bevel near the blue lines; with a `miterLimit` above 10, most corners in this demo should join with a miter far away from the blue lines, and whose height is decreasing between corners from left to right because they connect with growing angles; with intermediate values, the corners on the left side will only join with a bevel near the blue lines, and the corners on the right side with a miter extension (also with a decreasing height).

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // Clear canvas
      ctx.clearRect(0, 0, 150, 150);

      // Draw guides
      ctx.strokeStyle = '#09f';
      ctx.lineWidth   = 2;
      ctx.strokeRect(-5, 50, 160, 50);

      // Set line styles
      ctx.strokeStyle = '#000';
      ctx.lineWidth = 10;

      // check input
      if (document.getElementById('miterLimit').value.match(/\d+(\.\d+)?/)) {
        ctx.miterLimit = parseFloat(document.getElementById('miterLimit').value);
      } else {
        alert('Value must be a positive number');
      }

      // Draw lines
      ctx.beginPath();
      ctx.moveTo(0, 100);
      for (i = 0; i < 24 ; i++) {
        var dy = i % 2 == 0 ? 25 : -25;
        ctx.lineTo(Math.pow(i, 1.5) * 2, 75 + dy);
      }
      ctx.stroke();
      return false;
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

### Using line dashes

The `setLineDash` method and the `lineDashOffset` property specify the dash pattern for lines. The `setLineDash` method accepts a list of numbers that specifies distances to alternately draw a line and a gap and the `lineDashOffset` property sets an offset where to start the pattern.

In this example we are creating a marching ants effect. It is an animation technique often found in selection tools of computer graphics programs. It helps the user to distinguish the selection border from the image background by animating the border. In a later part of this tutorial, you can learn how to do this and other [basic animations](basic_animations).

    var ctx = document.getElementById('canvas').getContext('2d');
    var offset = 0;

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.setLineDash([4, 2]);
      ctx.lineDashOffset = -offset;
      ctx.strokeRect(10, 10, 100, 100);
    }

    function march() {
      offset++;
      if (offset > 16) {
        offset = 0;
      }
      draw();
      setTimeout(march, 20);
    }

    march();

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHEAAAB4BAMAAAA3XwArAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAA9QTFRF////d3d3iIiIPz8/ODg4Tz+BIgAAAFhJREFUWMPt2LENgDAMRcEfJiCwQSZh/6nShAEsChTpntxasq50In2v9fTirI6RUZzVVb7y3HLzj9iyZcuWLVu2bNmyZcuWLVu2bNmyZct2N9u7/KZ+Ir1N/7QRzgRV1aUAAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

## Gradients

Just like any normal drawing program, we can fill and stroke shapes using linear, radial and conic gradients. We create a [`CanvasGradient`](../../canvasgradient) object by using one of the following methods. We can then assign this object to the `fillStyle` or `strokeStyle` properties.

[`createLinearGradient(x1, y1, x2, y2)`](../../canvasrenderingcontext2d/createlineargradient)  
Creates a linear gradient object with a starting point of (`x1`, `y1`) and an end point of (`x2`, `y2`).

[`createRadialGradient(x1, y1, r1, x2, y2, r2)`](../../canvasrenderingcontext2d/createradialgradient)  
Creates a radial gradient. The parameters represent two circles, one with its center at (`x1`, `y1`) and a radius of `r1`, and the other with its center at (`x2`, `y2`) with a radius of `r2`.

[`createConicGradient(angle, x, y)`](../../canvasrenderingcontext2d/createconicgradient)  
Creates a conic gradient object with a starting angle of `angle` in radians, at the position (`x`, `y`).

For example:

    var lineargradient = ctx.createLinearGradient(0, 0, 150, 150);
    var radialgradient = ctx.createRadialGradient(75, 75, 0, 75, 75, 100);

Once we've created a `CanvasGradient` object we can assign colors to it by using the `addColorStop()` method.

[`gradient.addColorStop(position, color)`](../../canvasgradient/addcolorstop)  
Creates a new color stop on the `gradient` object. The `position` is a number between 0.0 and 1.0 and defines the relative position of the color in the gradient, and the `color` argument must be a string representing a CSS [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value), indicating the color the gradient should reach at that offset into the transition.

You can add as many color stops to a gradient as you need. Below is a very simple linear gradient from white to black.

    var lineargradient = ctx.createLinearGradient(0, 0, 150, 150);
    lineargradient.addColorStop(0, 'white');
    lineargradient.addColorStop(1, 'black');

### A `createLinearGradient` example

In this example, we'll create two different gradients. As you can see here, both the `strokeStyle` and `fillStyle` properties can accept a `canvasGradient` object as valid input.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // Create gradients
      var lingrad = ctx.createLinearGradient(0, 0, 0, 150);
      lingrad.addColorStop(0, '#00ABEB');
      lingrad.addColorStop(0.5, '#fff');
      lingrad.addColorStop(0.5, '#26C000');
      lingrad.addColorStop(1, '#fff');

      var lingrad2 = ctx.createLinearGradient(0, 50, 0, 95);
      lingrad2.addColorStop(0.5, '#000');
      lingrad2.addColorStop(1, 'rgba(0, 0, 0, 0)');

      // assign gradients to fill and stroke styles
      ctx.fillStyle = lingrad;
      ctx.strokeStyle = lingrad2;

      // draw shapes
      ctx.fillRect(10, 10, 130, 130);
      ctx.strokeRect(50, 50, 50, 50);

    }

The first is a background gradient. As you can see, we assigned two colors at the same position. You do this to make very sharp color transitions—in this case from white to green. Normally, it doesn't matter in what order you define the color stops, but in this special case, it does significantly. If you keep the assignments in the order you want them to appear, this won't be a problem.

In the second gradient, we didn't assign the starting color (at position 0.0) since it wasn't strictly necessary, because it will automatically assume the color of the next color stop. Therefore, assigning the black color at position 0.5 automatically makes the gradient, from the start to this stop, black.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

### A `createRadialGradient` example

In this example, we'll define four different radial gradients. Because we have control over the start and closing points of the gradient, we can achieve more complex effects than we would normally have in the "classic" radial gradients we see in, for instance, Photoshop (that is, a gradient with a single center point where the gradient expands outward in a circular shape).

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // Create gradients
      var radgrad = ctx.createRadialGradient(45, 45, 10, 52, 50, 30);
      radgrad.addColorStop(0, '#A7D30C');
      radgrad.addColorStop(0.9, '#019F62');
      radgrad.addColorStop(1, 'rgba(1, 159, 98, 0)');

      var radgrad2 = ctx.createRadialGradient(105, 105, 20, 112, 120, 50);
      radgrad2.addColorStop(0, '#FF5F98');
      radgrad2.addColorStop(0.75, '#FF0188');
      radgrad2.addColorStop(1, 'rgba(255, 1, 136, 0)');

      var radgrad3 = ctx.createRadialGradient(95, 15, 15, 102, 20, 40);
      radgrad3.addColorStop(0, '#00C9FF');
      radgrad3.addColorStop(0.8, '#00B5E2');
      radgrad3.addColorStop(1, 'rgba(0, 201, 255, 0)');

      var radgrad4 = ctx.createRadialGradient(0, 150, 50, 0, 140, 90);
      radgrad4.addColorStop(0, '#F4F201');
      radgrad4.addColorStop(0.8, '#E4C700');
      radgrad4.addColorStop(1, 'rgba(228, 199, 0, 0)');

      // draw shapes
      ctx.fillStyle = radgrad4;
      ctx.fillRect(0, 0, 150, 150);
      ctx.fillStyle = radgrad3;
      ctx.fillRect(0, 0, 150, 150);
      ctx.fillStyle = radgrad2;
      ctx.fillRect(0, 0, 150, 150);
      ctx.fillStyle = radgrad;
      ctx.fillRect(0, 0, 150, 150);
    }

In this case, we've offset the starting point slightly from the end point to achieve a spherical 3D effect. It's best to try to avoid letting the inside and outside circles overlap because this results in strange effects which are hard to predict.

The last color stop in each of the four gradients uses a fully transparent color. If you want to have a nice transition from this to the previous color stop, both colors should be equal. This isn't very obvious from the code because it uses two different CSS color methods as a demonstration, but in the first gradient `#019F62 = rgba(1,159,98,1)`.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

### A `createConicGradient` example

In this example, we'll define two different conic gradients. A conic gradient differs from a radial gradient as, instead of creating circles, it circles around a point.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // Create gradients
      var conicGrad1 = ctx.createConicGradient(2, 62, 75);
      conicGrad1.addColorStop(0, '#A7D30C');
      conicGrad1.addColorStop(1, '#fff');

      var conicGrad2 = ctx.createConicGradient(0, 187, 75);
      // we multiple our values by Math.PI/180 to convert degrees to radians
      conicGrad2.addColorStop(0, 'black');
      conicGrad2.addColorStop(0.25, 'black');
      conicGrad2.addColorStop(0.25, 'white');
      conicGrad2.addColorStop(0.5, 'white');
      conicGrad2.addColorStop(0.5, 'black');
      conicGrad2.addColorStop(0.75, 'black');
      conicGrad2.addColorStop(0.75, 'white');
      conicGrad2.addColorStop(1, 'white');

      // draw shapes
      ctx.fillStyle = conicGrad1;
      ctx.fillRect(12, 25, 100, 100);
      ctx.fillStyle = conicGrad2;
      ctx.fillRect(137, 25, 100, 100);
    }

The first gradient is positioned in the center of the first rectangle and moves a green color stop at the start, to a white one at the end. The angle starts at 2 radians, which is noticeable because of the beginning/end line pointing south east.

The second gradient is also positioned at the center of it's second rectangle. This one has multiple colour stops, alternating from black to white at each quarter of the rotation. This gives us the checkered effect.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" width="305" height="150" /></td><td></td></tr></tbody></table>

## Patterns

In one of the examples on the previous page, we used a series of loops to create a pattern of images. There is, however, a much simpler method: the `createPattern()` method.

[`createPattern(image, type)`](../../canvasrenderingcontext2d/createpattern)  
Creates and returns a new canvas pattern object. `image` is a [`CanvasImageSource`](../../canvasimagesource) (that is, an [`HTMLImageElement`](../../htmlimageelement), another canvas, a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, or the like. `type` is a string indicating how to use the image.

The type specifies how to use the image in order to create the pattern, and must be one of the following string values:

`repeat`  
Tiles the image in both vertical and horizontal directions.

`repeat-x`  
Tiles the image horizontally but not vertically.

`repeat-y`  
Tiles the image vertically but not horizontally.

`no-repeat`  
Doesn't tile the image. It's used only once.

We use this method to create a [`CanvasPattern`](../../canvaspattern) object which is very similar to the gradient methods we've seen above. Once we've created a pattern, we can assign it to the `fillStyle` or `strokeStyle` properties. For example:

    var img = new Image();
    img.src = 'someimage.png';
    var ptrn = ctx.createPattern(img, 'repeat');

**Note:** Like with the `drawImage()` method, you must make sure the image you use is loaded before calling this method or the pattern may be drawn incorrectly.

### A `createPattern` example

In this last example, we'll create a pattern to assign to the `fillStyle` property. The only thing worth noting is the use of the image's `onload` handler. This is to make sure the image is loaded before it is assigned to the pattern.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // create new image object to use as pattern
      var img = new Image();
      img.src = 'https://mdn.mozillademos.org/files/222/Canvas_createpattern.png';
      img.onload = function() {

        // create pattern
        var ptrn = ctx.createPattern(img, 'repeat');
        ctx.fillStyle = ptrn;
        ctx.fillRect(0, 0, 150, 150);

      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Shadows

Using shadows involves just four properties:

[`shadowOffsetX = float`](../../canvasrenderingcontext2d/shadowoffsetx)  
Indicates the horizontal distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.

[`shadowOffsetY = float`](../../canvasrenderingcontext2d/shadowoffsety)  
Indicates the vertical distance the shadow should extend from the object. This value isn't affected by the transformation matrix. The default is 0.

[`shadowBlur = float`](../../canvasrenderingcontext2d/shadowblur)  
Indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.

[`shadowColor = color`](../../canvasrenderingcontext2d/shadowcolor)  
A standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

The properties `shadowOffsetX` and `shadowOffsetY` indicate how far the shadow should extend from the object in the X and Y directions; these values aren't affected by the current transformation matrix. Use negative values to cause the shadow to extend up or to the left, and positive values to cause the shadow to extend down or to the right. These are both 0 by default.

The `shadowBlur` property indicates the size of the blurring effect; this value doesn't correspond to a number of pixels and is not affected by the current transformation matrix. The default value is 0.

The `shadowColor` property is a standard CSS color value indicating the color of the shadow effect; by default, it is fully-transparent black.

**Note:** Shadows are only drawn for `source-over` [compositing operations](compositing).

### A shadowed text example

This example draws a text string with a shadowing effect.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      ctx.shadowOffsetX = 2;
      ctx.shadowOffsetY = 2;
      ctx.shadowBlur = 2;
      ctx.shadowColor = 'rgba(0, 0, 0, 0.5)';

      ctx.font = '20px Times New Roman';
      ctx.fillStyle = 'Black';
      ctx.fillText('Sample String', 5, 30);
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFYAAAB1CAMAAADjsOZdAAAACXBIWXMAAAsTAAALEwEAmpwYAAAA4VBMVEX////T09Pn5+fQ0NDz8/MAAADMzMz+/v77+/v4+PhQUFDk5OTp6en19fXt7e2Li4v9/f3W1tbb29vx8fHd3d3i4uIfHx+AgIDHx8eurq7r6+soKCjg4OBeXl6EhISlpaVVVVXAwMAvLy/6+vpbW1vY2NgKCgqenp739/exsbGWlpbe3t7ExMRkZGRvb2+Pj49YWFiZmZkkJCQ3NzdISEg9PT2oqKgsLCxoaGhAQEC4uLjJyckTExMzMzM6Ojq0tLRycnK8vLwYGBihoaGIiIh6enp9fX1NTU1hYWFERER3d3esfWM1AAADPElEQVRo3u3V6Y6ySBQG4KKgSkARKRoQEQTEhU1Rcd937fu/oLG7k2+SGSZt5nc9CaGWkzeVExYAKIqi/qE6GmFYtMEMK3/GJDr/XWSufk9t37PBxgSlf+/0EO7zP0PFvwabFaj9THO3VPstdjVvwEWkFsRWl6um8DNsTTkyaQlh/XtWIZD/NdZKtFakSd4HAJxQJaCiAKDyTAP08xkrrMlX0XnCNKMhyVrtvkrafUVt9DXttZ4o/xWLu5bXwExgb9et6dPXjflpFe3yzUQT8hZ7u+u9V4NMtGM/8BBtr8+pni6dcOeOLQXI6dKOimP5B9JNAZ8+sgO7Pc38zWy+WHUtBxnVPBxNO8FcrQF1guaswOSfpn+yL/5A0cetbivesENkqsUNaYgIzZqp9xShvdDcHAZ2rF+Y5UR5hsZpsdvWXw2Ol0jH7UBmRJFV7nZlZyi643XxvpsQqTC1ES/QVgqnlsgEDya7s06ALRl/jr1laAySxKtXAccRER3UTFZcO+mIGdkZiW7su/vzZs8UxppHQbP1/Xhl5Dh7EFtk5Ed9PFQu/nEaGj6OzaMK9gkfT+esGzWzx7oRBGTnYN/BouUPE6WwCTNXALJ+2yr5M8kWWirGTorHw3iRJtO9jG51uyyAngxAmnv3TzZzmf4jiCeO4svHybCHWa3wGTbRYOYfemiro4U1WW31/dza67lzSkbdNLQQGkgCOHfl0amXiMidj4+duRVu7q2uayLUtcLCHgByPhwinMi3mTEyrj35OrpcZ2NxYWo92fBWgwOr9QHpDQ4zBXu33uU2S4bXSDbkizNaOgPR5YqfBI40y0ysKmyHrRBGilmuuR6PcLNTqcUYduprrQ1An8RlhgiQUeEagu8ytSHaEJ8DrfC4JQmWtTInQA3CKoRqpaw2vM2g3qxIQgVyVRJ/vdj9ryKVV2G1oan977KqlKL0c3LuqIWnrfGCJNRKvMB/a/N8LRLdpNp+rfGvTaH2p+h1+yqofa2/LmhPl+fyB/f2x7LGYPWNMl5hCKm0346V4vidMwiwQ6BUejuW57h3zlBqc5zwfioovdD/JkVRFEVRFEVRFEVRFEVRFEVRFEVR1P/3FyjjZOD9ze91AAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

We will look at the `font` property and `fillText` method in the next chapter about [drawing text](drawing_text).

## Canvas fill rules

When using `fill` (or [`clip`](../../canvasrenderingcontext2d/clip) and [`isPointInPath`](../../canvasrenderingcontext2d/ispointinpath)) you can optionally provide a fill rule algorithm by which to determine if a point is inside or outside a path and thus if it gets filled or not. This is useful when a path intersects itself or is nested.

Two values are possible:

- `"nonzero`": The [non-zero winding rule](https://en.wikipedia.org/wiki/Nonzero-rule), which is the default rule.
- `"evenodd"`: The [even-odd winding rule](https://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

In this example we are using the `evenodd` rule.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      ctx.beginPath();
      ctx.arc(50, 50, 30, 0, Math.PI * 2, true);
      ctx.arc(50, 50, 15, 0, Math.PI * 2, true);
      ctx.fill('evenodd');
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGQAAABrCAMAAAC2atezAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAHtQTFRFAAAA6+vrenp6l5eX9fX1/Pz8NjY2////BgYGSkpKEBAQRUVF5+fnYGBg7+/vKioqDAwM1tbWIyMjqqqqjIyM3d3dbGxsvLy8PT09GhoaU1NTW1tbk5OT0dHRxMTEzMzMuLi4h4eHsbGxycnJc3NzoaGhWFhYzc3NZmZmjdqSCgAAAb1JREFUaN7t2dmWgjAMANAgFMsiKIuAOi7jbP//heOjtgUTwJw5c5Ln6pUuIY2wZAgQRBBBBBFEEEEE+S9I0FSrsOjiuCvan+qo5kfSqtXwEOvEz2ZFmghcoXen2ZBzCL0Rfc+C1BEMxiqdjvgansS6nIgEe0DEVk1BvBBQEQXjkboAZITeWMRDGzclGIcEId4AHalRyBeQYjEG8YEYDR3ZaCrSZWQkAXJsqci7c3WTwzXNsvR4aZ3KlYao3JE+LnfzkX44pjOiIaX9Dfv0eeJ8IyHWEdEH+2kXdkamIBvLOLuGfVozGhAQ6zf6S9y4koDkuGlYKnOj7/CIZ3w07s2x5rzGCo2Ye6vqT0srY+gJjRhTrQfS+AazeE5khztjruXbopEctbWcT52gkRh1jp1JLkcjRloarBLqx+Xr0IixmMMFjbGHX4JkRmJ5yXQZe7j7WwvPsoVZDiNLWmFJkCypnuWlxfP6ZSkkWEoinuKOpUwdKLiVmqvg5rk68FyCWK5zPBdT2hUbRl6xWZoFPG0PngYOTyuKp6nG1B7kaXQytWyZms93bfRbCRu/qo0uf20IIogggggiiCCCTItfycP38nPQ9KoAAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

- <a href="drawing_shapes" class="button minimal">« Previous</a>
- <a href="drawing_text" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors</a>
