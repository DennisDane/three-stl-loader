## three-stl-loader

@aleeper's [THREE.STLLoader](http://threejs.org/examples/js/loaders/STLLoader.js) repackaged as a node module

## Automatically rotated
The models are being rotated at the import level such that the model is imported in the correct orientation.

## Speed improvement
The importing speeds have been increased.

## install

`npm i --save three`

`npm i --save three-stl-loader`

## usage

```js

var THREE = require('three')
var STLLoader = require('three-stl-loader')(THREE)

var loader = new STLLoader()

loader.load('./path/to/daaaamn.stl', function (geometry) {
  var material = new THREE.MeshNormalMaterial()
  var mesh = new THREE.Mesh(geometry, material)
  scene.add(mesh)
})

```

## Usage with bufferArray:
```js
import * as Three from 'three'
const STLLoader = require('three-stl-loader')(Three)

export async function convertSTL(file){
  const loader = new STLLoader()
  const arrayBuf = await file.arrayBuffer()
  const geometry = loader.parse(arrayBuf)
  return geometry
}

```
