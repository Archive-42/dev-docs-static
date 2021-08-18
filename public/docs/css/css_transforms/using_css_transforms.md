# Using CSS transforms

By modifying the coordinate space, **CSS transforms** change the shape and position of the affected content without disrupting the normal document flow. This guide provides an introduction to using transforms.

CSS transforms are implemented using a set of CSS properties that let you apply affine linear transformations to HTML elements. These transformations include rotation, skewing, scaling, and translation both in the plane and in the 3D space.

Only elements positioned by the [box model](../css_box_model) can be `transform`ed. As a rule of thumb, an element is positioned by the box model if it has `display: block`.

## CSS transforms properties

Two major properties are used to define CSS transforms: [`transform`](../transform) and [`transform-origin`](../transform-origin)

[`transform-origin`](../transform-origin)  
Specifies the position of the origin. By default, it is at the center of the element and can be moved. It is used by several transforms, like rotations, scaling or skewing, that need a specific point as a parameter.

[`transform`](../transform)  
Specifies the transforms to apply to the element. It is a space-separated list of transforms, which are applied one after the other, as requested by the composition operation. Composite transforms are effectively applied in order from right to left.

## Examples

Here is an unaltered image of the MDN logo:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAG4AAABqCAMAAABqFJTfAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAFxUExURfLy8uLm6OTo6uHl5+Pn6eXp6+js7ubq7Ofr7f///wBysAB2sxqg3gBvrgB0shh6w+nt8ACJwACMwgCSxgCPxBh9xRmU1QCOwwCQxRiFywB4tBuj3xqf3QB5tQCUxwBsrBmZ2Bui3gB8txl/xxmb2Rqk4ACDvABtrQCVyBqc2xmIzhh2wRmMzwBwrwB7thmX2AB+uRiCyRmAyBmO0QCFvRh7xRR2vwCIv+ru8Bmh3RmHzBh4wRqR0+3x8xyo4xum4f7+/gGXywCAuvv7/Bh5wxl6wwCCu2m54xOY1Ges2hSg2mel1L/c69bk602dzAqb0Giy3YW+2xF/wwN3uSye0X+z1/T6/JvO5q7Y7jGGwmWh0OHr8BiKzl654USRx33E40uy3gWRyzeu497v+dfo8bXT5cjh763O4sjc6Dan2RJ0vJi/2qDJ4TCTxIjK6ValzuPp7Git0Vut1Onz+SV+xOTq7na64yJ9uRR3tSup4hqPwoCyQWYAAA7BSURBVGjenJqJUxPLFod7lsxMXCAYNkUoRaGixRIU2YoAiSWBsCsC93EVBMRrPXCtZ9W9f/07v3O6ZyZJ49WcGskkc7q/OUuf7ulRRVGY8TyfJAoiOlw3kwlZ6EoUBLjq+EHg+hn6xfU9L5Px/TD0fcfJZKBLjYKAeomiDP0Lwwz/HAU5+hGCvh2HGpOiCkgJOM+jRtTM9+NOoEBNYhx15jPOdQWHrkUTPUf6nwC5vca5LhnDoqiVg5+Ay9ENOQ6A1C6YyZGWm8uxXig2Q0e+omuI5wAm3dPNRb6DmwpDx5ff2dBArvi+crw0Lgodh93JbJc0TPeM45uw4tAnGwRMhq3HVWmVm2G/AScOgsG4CfzETgnQCPfmuugg5KjAqXC3RMm4k7sNEaqMyzGCKRwG9ExhcEulHAyk249x4g6fbOObDpAW4nngIo6Kj2thgvM8Hb2IvR8hKUzUEZgEJzeQcRXFh5ODgdoV0tz3yQnsRgm72A2bgJPslFZIHejjdnC7HEaYF0IPPuEsQmYaHCJWj3PdmRgnrtE4dq5kp6+Hh1xxM3LOPcOl5B3KRD+JtUJyEMZh//NIkVjMzMAdAUdIUl1HKeO7NBpDXOVUiLRIQ+PcjDHR8cyQgG4TToYqsinHdEkI3Z841TWxiX/jy3JVbiDkv4zjzJXhTziic4glRSQWvisD1/d1fSF9GigSlEjqDwaQ50iKu3FNMmnmePBPpKsTDBEd5TiCM5HBZcQA9wm74vHlaRqiQwyqNRQV8YE4HM4wnqXaw+42eRvjcMl0KgM5oCGEdAlDqY9yxfFnZjA2c1RFIx5DjHblxsxQcLmdVFPdYygZG3IuK8QtwXFGcfnCdzRLcLkc7k9wxka+KjjuXkKC20wKvePISEWgFJoiTSVq3ECHPCm9usZHsXUceK6KQRIhCYiJIZwNbMRTgDEqhZOUQInl7nQVNBXe4AKd1IgsOk9wYkUDjtNUcLBXiX/lguPkclx2eE6Q+WH/+M259IdBj6wlpzpmZLk6KnxDztHJpy/JsGeEvmnkB6BKvG5wyDgUapk2oo03W+WthYWT/S/UGpVPYigQGTimoGXWj7fKtYWFN+sah8D4UpFSOCm8En4uTRw4OCbc/1guFIAjeXMeoULwXGiyOJRUwtmXo91yoQzcwuLJJ8fnUcruxaCCN4BzHIWiJBVf7lM+HYcMKxCtUBAcmfjpfw5PVEmKA4cUWD8us2qhtrDIusfvE5wrNYurp6NM+mZMBDiX2DBIubA1NLQ4tAghR7FLAplAtStdGCaq5ZrWXVj8+8hDEZf5IpORCZxTJYhxnHEhIlYYKBjZWqQeTDcnnwQn45JwZFghkVpa9/i94MwEp3E+BrAjw4Dyf/9joTDAAuYArEsLcgEzAkqWc7RbpzpQS2sukomHOplMIVAwNpdzPMGRYQP5gTrZ6usb6huiQz6pG4oiJiAybKBBao26C8cHThTFkxKtxFyJO0wmwwwsP5BnGcgTrkmGjtdhWL5BFbhGzb6/j86wfIL7sRLzkyKWrxd0lx8o9/Xd77vPQicsdFKzqeZrVt0q43hhoTC8Qz0A8jbZSrpISc2qW7PqVk1yhRjmerzRT/ne3nxvno7ks7e3PDt7f/Y+HbOzN2Zv0DELqdlUe2tW3aqelOlDmUkRQ7HXJuUbsaC57qZm1a1ZdauyrtY4mfKB60wadvZ2iqRxd2/cZaGTmkW1s3PFqqtxyH1llqpI006blJOmKVmx6q5YdauyDkWWKHl0kNKrG/V09tBhPst3LXJjxabauWLTvVsVVzJOz1k8ver2RqSfd+mWH/fXT09PD05gXbNqzxU4s5gQXMYsyXua5VbPu0eP7j4S1sHeUpZlae9g16J6ayXWZaEvkKpeKlGS0LiboWkTq8YousVtYunh7+90s5MzzWJeVpXWj/bPSkqps29G9dZKjGABmv5UZRGicZilPcHZ5J20XE/BIColO0Z35VGTPHz00OAiThV53IBv7biHJG/2stmrcWrT4B42CfGqJjeoZsrSweVHR27SYcEdLGV/iju8GkdSxZiTJyauKmZW0I06bnWwgNxBuI/fs9mf49Quq3Zo3L2H91joBOdV8+SAnYcUrsMm76pL2X/FfWPV6RXBjN8bp+OekarexCCUQgQdT4qYFbdvpTXgNkV3PkYwEkIn1dS+iuBkp2CabrBjmoVO5IbPVfYXcKVNbroyHou2DqdVl7d84EBeGskDYximcFr+OVS/hFPqA+5wZTy2any8mw/gsM70+DmSY+fo54LpBpncxTD+NZwq7UyTdfe6GdTdzShGd2scZyavmX0pY424b9zPL+IIuL/bHYsYx5/b5imYcfLohAXEZL1t29LJ0q/ilHp++qO7WbblyVjjgnjrjHCT05MsdLJDqPOdz6Xsb+Cy2ecHu004iRsyRCU7c4RLyfTm+uvLycmd33Am46h8n+9acNj1Y5wkC6omUYYnh+mIoe/V7+MIWE3B5ru3ZZ8MG3V1uGERgxvGMGgFl12qs2+bn/J4N1UZT8LU4USWh5eXeRi0hMv+mIeQZdqZ9MzLWyLKbB6iYi8nKPqzCdp5qSXcp/mUaBzcqWTJIpPfcqWyXFlmqSxf0ryy889Za9YdzD+df0qH4KQiYwEW47DcrACjkcO5jc/LlzMtOvOcURq5bfZfGMe7YtgFCyopubysVD63HLvTpylZNZt3vBLzPLNzrEnFSpGOSoVqWOlDriXcXh1OP81jrWK2eVHMiolxxNukqlvcaM26JeaMPB2h4+m22eaKcbKJXayTw4tKcb1FZ+6NQAgF5Krep/DZmdhZkR28etxysXjRauwORlKyLVvIEe+J8caTxg0OFgeLdOhPpMrhxVILVWU+jVsVHHY3lckZpMtgvRRL6vBrJdeCdWcjdbhk70bXTCljDbiL0uvBwb9acea3kZE/R/40sprsnins7GEPDA/MhBgbHKNDcF/pH01Av+/Mvcd1siobkJiCGBfx7pbrjgnKIOnPZ1X67+/hlr7vfV9twEXx9qqSFwy8axQRpkFK68V/i11pY+MwwT3/8bhJVqV3XwaCvGqCf8f6+8f6E1b/2OXr/h219/wnuNxXVt38wMi9g8dzJI/nhDPH3+ZWZVFLjEDJY57DG4L9Fvnr9cHVi/bSTkrz8uvXOZHbc7dZ6IRxEjuPRMlDLIpYGNpwg59Pr8RtLKc17/SPvUxwQGlsPc68KguiOyLUkA5zvnl6VewOG1X7X962iR53YCa7RiR3mqX/7dXj7m2T9k9wQlABb7zLekU3un7nOgud0PHhKtxZk+p1O25NXkiGvGsU46Louk2K61fgdpp1X07Uye2J23RMrLou3ujyfJe8OmnCtV1vo6M4cW7H/dGkCpxGpGU1yMlrYFSVBBe0JUJtdT+vJiZsQ0GVmlXbCPdk4gkLnbDQyRreUmtc6sV81GaTV9R2x7IVsGHRffnEJmuuvLwI+H8FyA47hoMd9+DBkwebzRsdFzYcdJ/QkXySrOmXiYEUMf3i1HOuJdJ2rY0OfL7iJg8aH9HV22ZV4IykcVH84lLpVyy8o3nNJoLr6pp7XwfM2XRTuC5qomUtikXRwwhvSmOSvQonTR907aTqmboCl8KkcPLKOghiHH7SjUavjdJhPl/VNf3Pxdn3vedLS0ulP5pVr0112WQNSSLvzBQKJ+ZzbDM2t4d11i6mbKo/w+mFn6NxsHHUJm3t7c/anz3reiZt6YS+tk9ZdaesumvmtXiE/4QQ8sMkPXJlbo6O3hy9Gcsof2978aL9RXujTNlUb05ZddcQKtkOUAB5/PLLd5N2qY7IOuqjsZspi+r/2zR3nlZiIArvOvFDSIvyDyi3QLQrpIguqQLpUmyKdBERoaAAcX/+9ZkzY29ILEArNPbxY+yd9XxdN9y0xb4zOYN28Fbv+r7rWbEvz/erq7JerYdbpt1w03ajAIZD4Gdy2XF61kXp9PnucNyN69VyuVqy+pLPw7Vpf7993Xwvr203xrJkOYV6ZCv0f0r3u/sBO3Xaf0tVFDSV/3z8tX0az3IMvx/Wf233jNRx394Y0wDPfLgoT9tTMlZn/nlYPU7Lx4Vp/2//Jil8jONrN17aTuUYZ/LmCBUf+vyTtcYzE7TEe7xvZ7vxUs5MH54OR7oCiYIc4J2264ktN4IktoscSult7qzXi7ki10b/Wlspo+t/dy5p0MqTn0n88zgZnd41VLmAqdBJRGeTgWxJ5fgWdrmVYXgcTO5ue1JSApsJ7AZQJp75b5vvQWz3YOkkfIi2dgEEGDv7kzTpq0QO07TFodiKyI1nvkvITLlc9EvRLvXeD7lzg8opQMJ0OyTQWXyeaKAb8ktfX/t4389aHHY42HMrH5jwLOExBQItRIZ3pFzIciCrnld8X7meIpfN47m1XD/lyK4YKQRAJir28rV7TyA28mjyFLSzqRzq59iOZFoe1enIOFbkyHIZIIP3A1rHPEs4mJ6f3byScUloPEf8TBEoZJAMFamAgoJ9ic4TFWtr7PqtxPF6ncRJATHk5ryr1hLqf7RV6SRXeCqnEcOEgcly00S2sZZcLVaHE5AU86T9otFZSAfYZqmkh8k5KTytMATvrvLmds1pwRL3G+SiLDuqEfsEGyXJDsUNL8ESozKNiiPfSbk2Rv6Sz6yAkh09ZekFMmQnCpoWbLwVYSLqw28qdkisxP0aY04ol/Sj3aIzZvbE26JhI/bFFG/K5TVvBf10iofO9WKYciRJ5vPqxnQxXXDhEi3GJ/1XQwG6GBkpQ7WSnE8kcQNZVdKMXuNMHEAcuk6sALyXcoswQfkY6LSEsbznrvWFT10It2oocIpTILGhkPFPlpIVQtYtFt4J4qmuE5J5LgFZjorPemuYG395IbLWzow/JoMF24ZThdta4TLVv9B357mhmcLnNuZJEwqwa3I4nlvFuXAw8DZDUdiwKCdT47XXpMJkIrVh6YY4xUxdnqNDX0OgG9XzKOleVTerIKKipHx7NjFVOJVytu0Y+1JONjT3ZJCVLHK16alcJRnRTFQgOKX/wold/R4h3bAAAAAASUVORK5CYII=" alt="MDN Logo" width="110" height="106" />

### Rotating

Here is the MDN logo rotated 90 degrees from its bottom-left corner.

    <img style="transform: rotate(90deg);
                transform-origin: bottom left;"
         src="screen_shot_2016-02-16_at_15.53.54.png">

### Skewing and translating

Here is the MDN logo, skewed by 10 degrees and translated by 150 pixels on the X-axis.

    <img style="transform: skewx(10deg) translatex(150px);
                transform-origin: bottom left;"
         src="screen_shot_2016-02-16_at_15.53.54.png">

## 3D specific CSS properties

Performing CSS transformations in 3D space is a bit more complex. You have to start by configuring the 3D space by giving it a perspective, then you have to configure how your 2D elements will behave in that space.

### Perspective

The first element to set is the [`perspective`](../perspective). The perspective is what gives us the 3D impression. The farther from the viewer the elements are, the smaller they are.

#### Setting perspective

This example shows a cube with the perspective set at different positions. How quick the cube shrinks is defined by the [`perspective`](../perspective) property. The smaller its value is, the deeper the perspective is.

##### HTML

The HTML below creates four copies of the same box, with the perspective set at different values.

    <table>
      <tbody>
        <tr>
          <th><code>perspective: 250px;</code>
          </th>
          <th><code>perspective: 350px;</code>
          </th>
        </tr>
        <tr>
          <td>
            <div class="container">
              <div class="cube pers250">
                <div class="face front">1</div>
                <div class="face back">2</div>
                <div class="face right">3</div>
                <div class="face left">4</div>
                <div class="face top">5</div>
                <div class="face bottom">6</div>
              </div>
            </div>
          </td>
          <td>
            <div class="container">
              <div class="cube pers350">
                <div class="face front">1</div>
                <div class="face back">2</div>
                <div class="face right">3</div>
                <div class="face left">4</div>
                <div class="face top">5</div>
                <div class="face bottom">6</div>
              </div>
            </div>
          </td>
        </tr>
        <tr>
          <th><code>perspective: 500px;</code>
          </th>
          <th><code>perspective: 650px;</code>
          </th>
        </tr>
        <tr>
          <td>
            <div class="container">
              <div class="cube pers500">
                <div class="face front">1</div>
                <div class="face back">2</div>
                <div class="face right">3</div>
                <div class="face left">4</div>
                <div class="face top">5</div>
                <div class="face bottom">6</div>
              </div>
            </div>
          </td>
          <td>
            <div class="container">
              <div class="cube pers650">
                <div class="face front">1</div>
                <div class="face back">2</div>
                <div class="face right">3</div>
                <div class="face left">4</div>
                <div class="face top">5</div>
                <div class="face bottom">6</div>
              </div>
            </div>
          </td>
        </tr>
      </tbody>
    </table>

##### CSS

The CSS establishes classes that can be used to set the perspective to different distances. It also includes classes for the container box and the cube itself, as well as each of its faces.

    /* Shorthand classes for different perspective values */
    .pers250 {
      perspective: 250px;
    }

    .pers350 {
      perspective: 350px;
    }

    .pers500 {
      perspective: 500px;
    }

    .pers650 {
      perspective: 650px;
    }

    /* Define the container div, the cube div, and a generic face */
    .container {
      width: 200px;
      height: 200px;
      margin: 75px 0 0 75px;
      border: none;
    }

    .cube {
      width: 100%;
      height: 100%;
      backface-visibility: visible;
      perspective-origin: 150% 150%;
      transform-style: preserve-3d;
    }

    .face {
      display: block;
      position: absolute;
      width: 100px;
      height: 100px;
      border: none;
      line-height: 100px;
      font-family: sans-serif;
      font-size: 60px;
      color: white;
      text-align: center;
    }

    /* Define each face based on direction */
    .front {
      background: rgba(0, 0, 0, 0.3);
      transform: translateZ(50px);
    }

    .back {
      background: rgba(0, 255, 0, 1);
      color: black;
      transform: rotateY(180deg) translateZ(50px);
    }

    .right {
      background: rgba(196, 0, 0, 0.7);
      transform: rotateY(90deg) translateZ(50px);
    }

    .left {
      background: rgba(0, 0, 196, 0.7);
      transform: rotateY(-90deg) translateZ(50px);
    }

    .top {
      background: rgba(196, 196, 0, 0.7);
      transform: rotateX(90deg) translateZ(50px);
    }

    .bottom {
      background: rgba(196, 0, 196, 0.7);
      transform: rotateX(-90deg) translateZ(50px);
    }

    /* Make the table a little nicer */
    th, p, td {
      background-color: #EEEEEE;
      padding: 10px;
      font-family: sans-serif;
      text-align: left;
    }

##### Result

The second element to configure is the position of the viewer, with the [`perspective-origin`](../perspective-origin) property. By default the perspective is centered on the viewer, which is not always adequate.

#### Changing the perspective origin

This example shows cubes with popular `perspective-origin` values.

##### HTML

    <section>

    <figure>
      <figcaption><code>perspective-origin: top left;</code></figcaption>
        <div class="container">
         <div class="cube potl">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
         </div>
        </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: top;</code></figcaption>
       <div class="container">
        <div class="cube potm">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: top right;</code></figcaption>
      <div class="container">
        <div class="cube potr">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: left;</code></figcaption>
      <div class="container">
        <div class="cube poml">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: 50% 50%;</code></figcaption>
      <div class="container">
        <div class="cube pomm">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: right;</code></figcaption>
      <div class="container">
        <div class="cube pomr">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: bottom left;</code></figcaption>
      <div class="container">
        <div class="cube pobl">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: bottom;</code></figcaption>
      <div class="container">
        <div class="cube pobm">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: bottom right;</code></figcaption>
      <div class="container">
        <div class="cube pobr">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: -200% -200%;</code></figcaption>
      <div class="container">
        <div class="cube po200200neg">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: 200% 200%;</code></figcaption>
      <div class="container">
        <div class="cube po200200pos">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    <figure>
      <figcaption><code>perspective-origin: 200% -200%;</code></figcaption>
      <div class="container">
        <div class="cube po200200">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
    </figure>

    </section>

##### CSS

    /* perspective-origin values (unique per example) */
    .potl {
      perspective-origin: top left;
    }
    .potm {
      perspective-origin: top;
    }
    .potr {
      perspective-origin: top right;
    }
    .poml {
      perspective-origin: left;
    }
    .pomm {
      perspective-origin: 50% 50%;
    }
    .pomr {
      perspective-origin: right;
    }
    .pobl {
      perspective-origin: bottom left;
    }
    .pobm {
      perspective-origin: bottom;
    }
    .pobr {
      perspective-origin: bottom right;
    }
    .po200200neg {
      perspective-origin: -200% -200%;
    }
    .po200200pos {
      perspective-origin: 200% 200%;
    }
    .po200200 {
      perspective-origin: 200% -200%;
    }

    /* Define the container div, the cube div, and a generic face */
    .container {
      width: 100px;
      height: 100px;
      margin: 24px;
      border: none;
    }

    .cube {
      width: 100%;
      height: 100%;
      backface-visibility: visible;
      perspective: 300px;
      transform-style: preserve-3d;
    }

    .face {
      display: block;
      position: absolute;
      width: 100px;
      height: 100px;
      border: none;
      line-height: 100px;
      font-family: sans-serif;
      font-size: 60px;
      color: white;
      text-align: center;
    }

    /* Define each face based on direction */
    .front {
      background: rgba(0, 0, 0, 0.3);
      transform: translateZ(50px);
    }
    .back {
      background: rgba(0, 255, 0, 1);
      color: black;
      transform: rotateY(180deg) translateZ(50px);
    }
    .right {
      background: rgba(196, 0, 0, 0.7);
      transform: rotateY(90deg) translateZ(50px);
    }
    .left {
      background: rgba(0, 0, 196, 0.7);
      transform: rotateY(-90deg) translateZ(50px);
    }
    .top {
      background: rgba(196, 196, 0, 0.7);
      transform: rotateX(90deg) translateZ(50px);
    }
    .bottom {
      background: rgba(196, 0, 196, 0.7);
      transform: rotateX(-90deg) translateZ(50px);
    }

    /* Make the layout a little nicer */
    section {
      background-color: #EEE;
      padding: 10px;
      font-family: sans-serif;
      text-align: left;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
    }

##### Result

Once you have done this, you can work on the element in the 3D space.

## See also

- [Using device orientation with 3D Transforms](https://developer.mozilla.org/en-US/docs/Web/Events/Using_device_orientation_with_3D_transforms)
- [Intro to CSS 3D transforms](https://desandro.github.com/3dtransforms/) (Blog post by David DeSandro)
- [CSS Transform Playground](https://css-transform.moro.es/) (Online tool to visualize CSS Transform functions)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms</a>
