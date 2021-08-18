WebGL tutorial
==============

[WebGL](https://www.khronos.org/webgl/) enables web content to use an API based on [OpenGL ES](https://www.khronos.org/opengles/) 2.0 to perform 3D rendering in an HTML [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) in browsers that support it without the use of plug-ins. WebGL programs consist of control code written in JavaScript and special effects code (shader code) that is executed on a computer's Graphics Processing Unit (GPU). WebGL elements can be mixed with other HTML elements and composited with other parts of the page or page background.

This tutorial describes how to use the `<canvas>` element to draw WebGL graphics, starting with the basics. The examples provided should give you some clear ideas of what you can do with WebGL and will provide code snippets that may get you started in building your own content.

Before you start
----------------

Using the `<canvas>` element is not very difficult, but you do need a basic understanding of [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) and [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript). The `<canvas>` element and WebGL are not supported in some older browsers, but are supported in recent versions of all major browsers. In order to draw graphics on the canvas we use a JavaScript context object, which creates graphics on the fly.

In this tutorial
----------------

[Getting started with WebGL](tutorial/getting_started_with_webgl)  
How to set up a WebGL context.

[Adding 2D content to a WebGL context](tutorial/adding_2d_content_to_a_webgl_context)  
How to render simple flat shapes using WebGL.

[Using shaders to apply color in WebGL](tutorial/using_shaders_to_apply_color_in_webgl)  
Demonstrates how to add color to shapes using shaders.

[Animating objects with WebGL](tutorial/animating_objects_with_webgl)  
Shows how to rotate and translate objects to create simple animations.

[Creating 3D objects using WebGL](tutorial/creating_3d_objects_using_webgl)  
Shows how to create and animate a 3D object (in this case, a cube).

[Using textures in WebGL](tutorial/using_textures_in_webgl)  
Demonstrates how to map textures onto the faces of an object.

[Lighting in WebGL](tutorial/lighting_in_webgl)  
How to simulate lighting effects in your WebGL context.

[Animating textures in WebGL](tutorial/animating_textures_in_webgl)  
Shows how to animate textures; in this case, by mapping an Ogg video onto the faces of a rotating cube.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial</a>
