WebGLRenderingContext.getUniformLocation()
==========================================

Part of the [WebGL API](../webgl_api), the [`WebGLRenderingContext`](../webglrenderingcontext) method `getUniformLocation()` returns the location of a specific **uniform** variable which is part of a given [`WebGLProgram`](../webglprogram). The uniform variable is returned as a [`WebGLUniformLocation`](../webgluniformlocation) object, which is an opaque identifier used to specify where in the GPU's memory that uniform variable is located.

Once you have the uniform's location, you can access the uniform itself using one of the other uniform access methods, passing in the uniform location as one of the inputs:

[`getUniform()`](getuniform)  
Returns the value of the uniform at the given location.

[`uniform[1234][fi][v]()`](uniform)  
Sets the uniform's value to the specified value, which may be a single floating point or integer number, or a 2-4 component vector specified either as a list of values or as a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) or [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array).

 [`uniformMatrix[234][fv]()`](uniformmatrix)   
Sets the uniform's value to the specified matrix, possibly with transposition. The value is represented as a sequence of `GLfloat` values or as a `Float32Array`.

The uniform itself is declared in the shader program using GLSL.

Syntax
------

    WebGLUniformLocation = WebGLRenderingContext.getUniformLocation(program, name);

### Parameters

`program`  
The [`WebGLProgram`](../webglprogram) in which to locate the specified uniform variable.

`name`  
A [`DOMString`](../domstring) specifying the name of the uniform variable whose location is to be returned. The name can't have any whitespace in it, and you can't use this function to get the location of any uniforms starting with the reserved string `"gl_"`, since those are internal to the WebGL layer.  
  
The possible values correspond to the uniform names returned by [`getActiveUniform`](getactiveuniform); see that function for specifics on how declared uniforms map to uniform location names.  
  
Additionally, for uniforms declared as arrays, the following names are also valid:  

-   The uniform name without the `[0]` suffix. E.g. the location returned for `arrayUniform` is equivalent to the one for `arrayUniform[0]`.
-   The uniform name indexed with an integer. E.g. the location returned for `arrayUniform[2]` would point directly to the third entry of the `arrayUniform` uniform.

### Return value

A [`WebGLUniformLocation`](../webgluniformlocation) value indicating the location of the named variable, if it exists. If the specified variable doesn't exist, [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) is returned instead.

The `WebGLUniformLocation` is an opaque value used to uniquely identify the location in the GPU's memory at which the uniform variable is located. With this value in hand, you can call other WebGL methods to access the value of the uniform variable.

The `WebGLUniformLocation` type is compatible with the `GLint` type when specifying the index or location of a uniform attribute.

### Errors

The following errors may occur; to check for errors after `getUniformLocation()` returns, call [`getError()`](geterror).

`GL_INVALID_VALUE`  
The `program` parameter is not a value or object generated by WebGL.

`GL_INVALID_OPERATION`  
The `program` parameter doesn't correspond to a GLSL program generated by WebGL, or the specified program hasn't been linked successfully.

Example
-------

In this example, taken from the `animateScene()` method in the article [A basic 2D WebGL animation example](../webgl_api/basic_2d_animation_example#drawing_and_animating_the_scene), obtains the locations of three uniforms from the shading program, then sets the value of each of the three uniforms.

    gl.useProgram(shaderProgram);

    uScalingFactor =
        gl.getUniformLocation(shaderProgram, "uScalingFactor");
    uGlobalColor =
        gl.getUniformLocation(shaderProgram, "uGlobalColor");
    uRotationVector =
        gl.getUniformLocation(shaderProgram, "uRotationVector")

    gl.uniform2fv(uScalingFactor, currentScale);
    gl.uniform2fv(uRotationVector, currentRotation);
    gl.uniform4fv(uGlobalColor, [0.1, 0.7, 0.2, 1.0]);

### Note

This code snippet is taken from [the function `animateScene()`](../webgl_api/basic_2d_animation_example#drawing_and_animating_the_scene) in "A basic 2D WebGL animation example." See that article for the full sample and to see the resulting animation in action.

After setting the current shading program to `shaderProgram`, this code fetches the three uniforms `"uScalingFactor"`, `"uGlobalColor"`, and `"uRotationVector"`, calling `getUniformLocation()` once for each uniform.

Then the three uniforms' values are set:

-   The `uScalingFactor` uniform ??? a 2-component vertex ??? receives the horizontal and vertical scaling factors from the variable `currentScale`.
-   The uniform `uRotationVector` is set to the contents of the variable `currentRotation`. This, too, is a 2-component vertex.
-   Finally, the uniform `uGlobalColor` is set to the color `[0.1, 0.7, 0.2, 1.0]`, the components in this 4-component vector represent the values of red, green, blue, and alpha, respectively.

Having done this, the next time the shading functions are called, their own variables named `uScalingFactor`, `uGlobalColor`, and `uRotationVector` will all have the values provided by the JavaScript code.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.10">WebGL 1.0<br />
<span class="small">The definition of 'getUniformLocation' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man/xhtml/glGetUniformLocation.xml">OpenGL ES 2.0<br />
<span class="small">The definition of 'glGetUniformLocation' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the OpenGL API.</td></tr></tbody></table>

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

`getUniformLocation`

9

12

4

11

12

5.1

???37

25

Yes

12

8

1.5

See also
--------

-   [`WebGLRenderingContext.getAttribLocation()`](getattriblocation)
-   [`WebGLRenderingContext.getActiveUniform()`](getactiveuniform)
-   [`WebGLUniformLocation`](../webgluniformlocation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getUniformLocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getUniformLocation</a>
