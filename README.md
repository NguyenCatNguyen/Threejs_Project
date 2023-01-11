# Threejs_Project
 Document learning process with threejs

# Index
- [WebGL](#webgl)
- [Part 1 Basic scene](#part-1-basic-scene)
    - [Scene](#scene)
    - [Object](#object)
    - [Camera](#camera)
    - [Renderer](#renderer)


## WebGL
    - JavaScript API for rendering 3D graphics in a web browser.
    - Can create 2D and 3D graphics, and interactive 3D applications.
    - WebGL is fast because it uses the Graphic Processing Unit (GPU) of the visitor.


## PART 1 BASIC SCENE
- To get start we need 4 element
    ```
    - A scene that will contain objects 
    - Some objects
    - A Camera
    - A Renderer
    ```
### Scene
- `scene` is like a container. You place your objects, models, particles, lights, etc.
- Create a scene by use the `Scene` class:
```js
// Scene
const scene = new THREE.Scene();
```
### Object
- `Object` can be many things, such as a cube, a sphere, a plane, a particle system, a light, a camera, etc.
- There are many geometries and many materials.
- To create the geometry, we use the `BoxGeometry` class with the first 3 parameters that correspond to the box's size.
- To create the material, we use the `MeshBasicMaterial` class with one parameter: an object `{}` containing all the options. All we need is to specify its `color` property.
```js
// Object
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const mesh = new THREE.Mesh(geometry, material);
// Add mesh to scene by using add method
scene.add(mesh);
```
- `Mesh` is an object that takes a geometry, and applies a material to it, which we then can insert to our scene and move freely around.
### Camera
- `Camera` is a tool that allows us to see the scene. Camera is not visible it more like a theoretical point of view.
- To create the camera, we use the `PerspectiveCamera` class with 4 parameters: *field of view*, *aspect ratio*, *near* and *far*.
```js
// Sizes
const sizes = {
    width: 800,
    height: 600
}
const camera = new THREE.PerspectiveCamera(75, sizes.width / sizes.height);
scene.add(camera);
```
- `The field of view` is the angle of the camera's view. The higher the value, the more we see. The lower the value, the less we see.
- `The aspect ratio` is the width of the canvas divided by its height. It is the ratio between the width and the height of the camera. It is usually the same as the ratio of the screen.

### Renderer
- `Renderer` is a process used in web development that turns website codes into the interactive pages users see when they visit a website.
The term generally refers to the use of HTML, CSS, and JavaScript codes.
- We want the renderer to render our scene from the camera point of view, and the result will be drawn into a canvas.
#### First
- Create the `<canvas>` element before load the scripts and give it a class:
```javascript
<canvas class="webgl"></canvas>
```