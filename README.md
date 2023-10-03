# GrafKom-Assignment-3
- Farhan Dwi Putra (5025211093)
- GrafKom A

---

## The RGB Triangle to Rectangel in WebGL
![Screenshot (72)](https://github.com/farhandp93/GrafKom-Assignment-3/assets/128909158/997031c7-0616-48e8-b541-55a06211c4c6)

Code :
```js
function draw() {
        gl.clearColor(0, 0, 0, 1); 
        gl.clear(gl.COLOR_BUFFER_BIT); 


        let coordsTriangle1 = new Float32Array([-0.5, -0.5, 0.5, 0.5, -0.5, 0.5]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
        gl.bufferData(gl.ARRAY_BUFFER, coordsTriangle1, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeCoords);

        let colorTriangle1 = new Float32Array([0, 1, 0, 1, 0, 0, 0, 0, 1]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
        gl.bufferData(gl.ARRAY_BUFFER, colorTriangle1, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeColor);

        gl.drawArrays(gl.TRIANGLES, 0, 3);

        let coordsTriangle2 = new Float32Array([-0.5, -0.5, 0.5, 0.5, 0.5, -0.5]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferCoords);
        gl.bufferData(gl.ARRAY_BUFFER, coordsTriangle2, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeCoords, 2, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeCoords);

        let colorTriangle2 = new Float32Array([0, 1, 0, 1, 0, 0, 1, 1, 1]);

        gl.bindBuffer(gl.ARRAY_BUFFER, bufferColor);
        gl.bufferData(gl.ARRAY_BUFFER, colorTriangle2, gl.STREAM_DRAW);
        gl.vertexAttribPointer(attributeColor, 3, gl.FLOAT, false, 0, 0);
        gl.enableVertexAttribArray(attributeColor);

        gl.drawArrays(gl.TRIANGLES, 0, 3);
```

## Cube made with WebGL and glMatrix
![Screenshot (71)](https://github.com/farhandp93/GrafKom-Assignment-3/assets/128909158/ab76cf3e-817f-4d1d-b0e9-ab5b97c8fbd3)

Without front side

![Screenshot (73)](https://github.com/farhandp93/GrafKom-Assignment-3/assets/128909158/5d7811c0-6120-438b-a221-e266ec81bab4)

Without upper side

![Screenshot (74)](https://github.com/farhandp93/GrafKom-Assignment-3/assets/128909158/87e03b06-33f0-403c-b9f7-3a5f92d04673)

Without right side

![Screenshot (75)](https://github.com/farhandp93/GrafKom-Assignment-3/assets/128909158/182e1888-b1e1-4263-9559-38a598b0210e)

Code :
```js
gl.clearColor(0,0,0,1);
    gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);
    //Front
    drawPrimitive( gl.TRIANGLE_FAN, [0,1,0,1], [-0.5,-0.5,-0.5, -0.5,0.5,-0.5, 0.5,0.5,-0.5, 0.5,-0.5,-0.5]);
    //Upper
    drawPrimitive( gl.TRIANGLE_FAN, [1,1,0,1], [0.5,0.5,-0.5, -0.5,0.5,-0.5, -0.2,0.7,0.5, 0.8, 0.7, 0.5]);
    //Rear
    drawPrimitive( gl.TRIANGLE_FAN, [0,0,1,1], [-0.2,-0.3,0.5, -0.2,0.7,0.5, 0.8,0.7,0.5, 0.8,-0.3,0.5]);
    //Left
    drawPrimitive( gl.TRIANGLE_FAN, [1,1,1,1], [-0.5,0.5,-0.5, -0.5,-0.5,-0.5, -0.2,-0.3,0.5, -0.2,0.7,0.5]);
     //Right
    drawPrimitive( gl.TRIANGLE_FAN, [1,0,0,1], [0.5,0.5,-0.5, 0.5,-0.5,-0.5, 0.8,-0.3,0.5, 0.8,0.7,0.5]);
    //Bottom
    drawPrimitive( gl.TRIANGLE_FAN, [0,1,1,1], [-0.5,-0.5,-0.5, -0.2,-0.3,0.5, 0.8,-0.3,0.5, 0.5,-0.5,-0.5]);
```
