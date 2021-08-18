Data in WebGL
=============

**Draft**

This page is not complete.

Shader programs have access to three kinds of data storage, each of which has a specific use case. Each kind of variable is accessible by one or both types of shader program (depending on the data store type) and possibly by the site's JavaScript code, depending on the specific type of variable.

GLSL data types
---------------

&lt;&lt;document the basic types, vectors, etc; see [Data Type (GLSL)](https://www.khronos.org/opengl/wiki/Data_Type_(GLSL)) on the Khronos WebGL wiki&gt;&gt;

GLSL variables
--------------

There are three kinds of "variable" or data storage available in GLSL, each of which with its own purpose and use cases: **[attributes](#attributes)**, **[varyings](#varyings)**, and **[uniforms](#uniforms)**.

### Attributes

**Attributes** are GLSL variables which are only available to the vertex shader (as variables) and the JavaScript code. Attributes are typically used to store color information, texture coordinates, and any other data calculated or retrieved that needs to be shared between the JavaScript code and the vertex shader.

    //init colors
        var vertexColors = [
            vec4( 0.0, 0.0, 0.0, 1.0 ),  // black
            vec4( 1.0, 0.0, 0.0, 1.0 ),  // red
            vec4( 1.0, 1.0, 0.0, 1.0 ),  // yellow
            vec4( 0.0, 1.0, 0.0, 1.0 ),  // green
            vec4( 0.0, 0.0, 0.0, 1.0 ),  // black
            vec4( 1.0, 0.0, 0.0, 1.0 ),  // red
            vec4( 1.0, 1.0, 0.0, 1.0 ),  // yellow
            vec4( 0.0, 1.0, 0.0, 1.0 ),  // green
        ];
        var cBuffer = gl.createBuffer();

    //continued
    //create buffer to store colors and reference it to "vColor" which is in GLSL
        gl.bindBuffer( gl.ARRAY_BUFFER, cBuffer );
        gl.bufferData( gl.ARRAY_BUFFER, flatten(vertexColors), gl.STATIC_DRAW );

        var vColor = gl.getAttribLocation( program, "vColor" );
        gl.vertexAttribPointer( vColor, 4, gl.FLOAT, false, 0, 0 );
        gl.enableVertexAttribArray( vColor );

    //glsl
    attribute  vec4 vColor;

    void main()
    {

    fColor = vColor;
    }

### Varyings

**Varyings** are variables that are declared by the vertex shader and used to pass data from the vertex shader to the fragment shader. This is commonly used to share a vertex's [normal vector](https://en.wikipedia.org/wiki/Normal_(geometry)) after it has been computed by the vertex shader.

&lt;&lt;how to use&gt;&gt;

### Uniforms

**Uniforms** are set by the JavaScript code and are available to both the vertex and fragment shaders. They're used to provide values that will be the same for everything drawn in the frame, such as lighting positions and magnitudes, global transformation and perspective details, and so forth.

&lt;&lt;add details&gt;&gt;

Buffers
-------

&lt;&lt;add information&gt;&gt;

Textures
--------

&lt;&lt;add information&gt;&gt;

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Data</a>
