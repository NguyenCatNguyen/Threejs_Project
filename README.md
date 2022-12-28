# Threejs_Project
 Document learning process with threejs

# Index
- [WebGL](#webgl)
- [Part 1 Basic scene](#part-1-basic-scene)


## WebGL
    - JavaScript API for rendering 3D graphics in a web browser.
    - Can create 2D and 3D graphics, and interactive 3D applications.

## Part 1 Basic scene
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