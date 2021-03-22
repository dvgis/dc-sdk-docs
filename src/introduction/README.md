---
sidebar: auto
---

# Tutorials 🌎

## Base

### What is DC-SDK

**_`DC-SDK`_** is based on the open source project **_`Cesium`_** for the second development of two three-dimensional **_`WebGis`_** application framework , the framework optimizes the use of **_`Cesium`_** and adds some additional features , designed for developers to quickly build **_`WebGis`_** application.

### Coordinate System

**`World Coordinates`**

Cartesian coordinates, the coordinates of a point in a right-angle coordinate system in space with the center of the ellipsoid as the origin.

**`Geographical Coordinates`**

Geographic coordinate system with the origin of coordinates at the center of mass of the ellipsoid.

Longitude: The two-sided angle between the geodetic meridian and the prime meridian at a point on the reference ellipsoid. East is positive and west is negative.

Latitude : The angle between the normal and the equatorial plane at a point on the reference ellipsoid. North positive and south negative.

**`Screen Coordinates`**

Browser window coordinates

### WebGL

WebGL is a JavaScript API for rendering interactive 2D and 3D graphics in any compatible web browser without the use of plug-ins. WebGL is fully integrated into all web standards of the browser and allows for the use of GPU acceleration of image processing and effects as part of the web Canvas. WebGL elements can be added to other HTML elements and blended with other parts of the web page or web page background. WebGL programs consist of handles written in JavaScript and shader code written in OpenGL Shading Language (**`GLSL`**).

### 3D Data Format

**`glb/gltf`**

GLTF stands for Graphics Language Transmission Format. This cross-platform format has become the standard for 3D objects on the Web. It was defined by Khronos, the 3D graphics standards organization behind OpenGL and Vulkan, making GLTF essentially a JPG format for 3D models: a common standard for Web exports.

**`3dtiles`**

3D Tiles is an open specification for streaming large scale heterogeneous 3D geospatial datasets. 3D Tiles data can be generated from shp, osgb (oblique photography), 3dmax, and other data.

**`geojson`**

GeoJSON is a format for encoding various geographic data structures, based on the Javascript object representation of geospatial information data interchange format.
GeoJSON objects can represent geometry, features or feature collections.GeoJSON supports the following geometry types: point, line, surface, multipoint, polyline, polysurface and geometry collections. A feature in GeoJSON contains a geometric object and other attributes, and a feature set represents a set of features.

**`kml/czml`**

KML/CZML is a JSON format data describing time-dynamic graphic scenes, which describes lines, points, billboards (markers), models, and other graphic primitives, and specifies how they change over time.

<img src="http://dc.dvgis.cn/examples/images/base/data_transform.png" style="width:100%;height:500px">

## Preparation

`Running Env`

DC-SDK is a development platform that relies on [`WebGL`](#webgl), which requires a `discrete graphics card` and a browser that supports `WebGL` on the development or running terminal. Recommended to use **_Chrome_**、**_Firefox_**

`Static File Server`

Static file servers are mainly used to publish map tiles, terrain, model data and other data services, such as: **_Apache Http Sever_**、**_Tomcat_** 、**_Nginx_**. Recommended to use **_Nginx_**

## Installation

`NPM / YARN` **_`(Recommend)`_**

Installing with NPM or YARN is recommended and it works seamlessly with webpack.

```node
   yarn add @dvgis/dc-sdk
   -------------------------
   npm install @dvgis/dc-sdk
```

```js
import DC from '@dvgis/dc-sdk/dist/dc.base.min'
import DcCore from '@dvgis/dc-sdk/dist/dc.core.min'
import DcChart from '@dvgis/dc-sdk/dist/dc.chart.min'
import DcMapv from '@dvgis/dc-sdk/dist/dc.mapv.min'
import '@dvgis/dc-sdk/dist/dc.core.min.css'
```

`NPM / YARN` **_`(On-demand)`_**

```node
   yarn add @dvgis/dc-base
   yarn add @dvgis/dc-core
   yarn add @dvgis/dc-chart
   yarn add @dvgis/dc-mapv
   -------------------------
   npm install @dvgis/dc-base
   npm install @dvgis/dc-core
   npm install @dvgis/dc-chart
   npm install @dvgis/dc-mapv
```

```js
import DC from '@dvgis/dc-base'
import DcCore from '@dvgis/dc-core'
import DcChart from '@dvgis/dc-chart'
import DcMapv from '@dvgis/dc-mapv'
import '@dvgis/dc-core/dist/dc.core.min.css'
```

`CDN`

[Resources 下载链接](https://github.com/dvgis/dc-sdk/tree/master/dist)

```html
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.base.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.core.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.chart.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.mapv.min.js"></script>
<link
  href="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.core.min.css"
  rel="stylesheet"
  type="text/css"
/>
```

::: danger
Please put the resources in the project root directory libs/dc-sdk, if you put it in other directory, the framework will not run properly.
:::

## Configuration

> The configuration is mainly used in the `NPM / YARN` way

Since the DC framework sets `CESIUM_BASE_URL` to `JSON.stringify('. /libs/dc-sdk/resources/')`, you need to copy `Cesium` static resource files: `Assets`, `Workers`, `ThirdParty` to the `libs/dc-sdk/resources` directory of the project to ensure that the 3D scene can be rendered properly.

`Webpack`

[Project Template](https://github.com/cavencj/dc-vue-app)

```js
// webpack.config.js
const path = require('path')
const CopywebpackPlugin = require('copy-webpack-plugin')
const dvgisDist = './node_modules/@dvgis'

module.exports = {
  plugins: [
    new CopyWebpackPlugin([
      {
        from: path.join(dvgisDist, 'dc-sdk/dist/resources'),
        to: 'libs/dc-sdk/resources',
      },
    ]),
  ],
}
```

`Vue2.x`

[Project Template](https://github.com/dvgis/dc-vue)

```js
// vue.config.js
const path = require('path')
const CopywebpackPlugin = require('copy-webpack-plugin')
const dvgisDist = './node_modules/@dvgis'
module.exports = {
  chainWebpack: (config) => {
    config.plugin('copy').use(CopywebpackPlugin, [
      [
        {
          from: path.join(dvgisDist, 'dc-sdk/dist/resources'),
          to: 'libs/dc-sdk/resources',
        },
      ],
    ])
  },
}
```

`Vue3.x`

[Project Template](https://github.com/dvgis/dc-vue-next)

```js
// vue.config.js
const path = require('path')
const CopywebpackPlugin = require('copy-webpack-plugin')
const dvgisDist = './node_modules/@dvgis'
module.exports = {
  chainWebpack: (config) => {
    config.plugin('copy').use(CopywebpackPlugin, [
      {
        patterns: [
          {
            from: path.join(dvgisDist, 'dc-sdk/dist/resources'),
            to: path.join(__dirname, 'dist', 'libs/dc-sdk/resources'),
          },
        ],
      },
    ])
  },
}
```

## Structure

> DC structure, it is recommended to be familiar with the overall structure diagram before use so that you can use it quickly.

<img src="http://dc.dvgis.cn/examples/images/base/SDK.png" style="width:100%;height:800px">

## Support

> If dc-sdk can bring you benefits, please support it!

<p>
<img src="http://dc.dvgis.cn/examples/images/base/sponsor.jpg?v=2" title="数字视觉"/>
</p>
