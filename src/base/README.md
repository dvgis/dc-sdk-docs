---
sidebar: auto
---

# Base 🌎

## Namespace

**`DC`**

DC is the default namespace for the framework.When developing with this framework, you need to start with `DC.`

:::danger
Try not to use DC as variable names or namespaces when developing to avoid the framework not working properly.
:::

**`Cesium`**

[Cesium](https://cesium.com/cesiumjs/) is a world-class ES6 open source product for 3D GIS. The product is convenient for individuals or teams to quickly build a plug-in-free 3D GIS web application, in terms of performance, accuracy, rendering quality, cross-platform are very good guarantee. If you need Cesium's internal interface during development, you can get Cesium through **`const { Cesium } = DC.Namespace`**.

**`mapv`**

[Mapv](https://mapv.baidu.com/) is a geographic information visualization open source library , can be used to display a large amount of geographic information data , point , line , surface data , each data also has different types of display , such as direct hit points , heat map , grid , aggregation and other ways to display data . If you need Mapv's internal interface during development, you can get Mapv through **`const { mapv } = DC.Namespace`**.

**`turf`**

[Turf](https://mapv.baidu.com/) is a JavaScript library for spatial analysis. It includes traditional spatial operations, helper functions for creating GeoJSON data, and data classification and statistics tools. Turf can be added to your website as a client-side plugin, or you can run Turf server-side with Node.js . If you need Turf's internal interface during development, you can get Turf through **`const { turf } = DC.Namespace`**.

## Global

### accessToken

> Used to load advanced features such as: location editor, analysis module

```js
DC.accessToken = '<your access token>'
```

### use

> Using third-party modules or frameworks in DC frameworks

```js
let plugin = {
  install: (DC) => {},
}
DC.use(plugin)
```

### mixin

> Adding additional properties or functions to the DC

```js
let comp = {
  a: 'b',
}
DC.mixin(comp)
DC.a // b
```

### init

> This function is used to initialize Cesium, the default Cesium is the latest version, if you use a custom version of Cesium, you can modify the reference to Cesium before the DC loads other modules, thus replacing Cesium in the entire DC system **_`(use with caution)`_**

```js
DC.init(() => {
  DC.Namespace['Cesium'] = '<自定义Cesium>'
  DC.use(DcCore)
})
```

### ready

> The main entrance to the framework, you must start with this when using the framework, otherwise you cannot build 3D scenes

```js
global.DC = DC
DC.use(DcCore)
DC.ready(() => {
  let viewer = new DC.Viewer(divId)
})
```

## Constants

> Framework internal default constants

::: warning
Please use the default constants for development
:::

### MouseEventType

**_`DC.MouseEventType.CLICK`_**

**_`DC.MouseEventType.RIGHT_CLICK`_**

**_`DC.MouseEventType.DB_CLICK`_**

**_`DC.MouseEventType.MOUSE_MOVE`_**

**_`DC.MouseEventType.WHEEL`_**

**_`DC.MouseEventType.MOUSE_OVER`_**

**_`DC.MouseEventType.MOUSE_OUT`_**

### SceneEventType

**_`DC.SceneEventType.CAMERA_MOVE_END`_**

**_`DC.SceneEventType.CAMERA_CHANGED`_**

**_`DC.SceneEventType.PRE_UPDATE`_**

**_`DC.SceneEventType.POST_UPDATE`_**

**_`DC.SceneEventType.PRE_RENDER`_**

**_`DC.SceneEventType.POST_RENDER`_**

**_`DC.SceneEventType.MORPH_COMPLETE`_**

**_`DC.SceneEventType.CLOCK_TICK`_**

### MouseMode

**_`DC.MouseMode.LEFT_MIDDLE`_**

**_`DC.MouseMode.LEFT_RIGHT`_**

### ImageryType

**_`DC.ImageryType.ARCGIS`_**

**_`DC.ImageryType.SINGLE_TILE`_**

**_`DC.ImageryType.WMS`_**

**_`DC.ImageryType.WMTS`_**

**_`DC.ImageryType.XYZ`_**

**_`DC.ImageryType.COORD`_**

**_`DC.ImageryType.AMAP`_**

**_`DC.ImageryType.BAIDU`_**

**_`DC.ImageryType.GOOGLE`_**

**_`DC.ImageryType.TDT`_**

**_`DC.ImageryType.TENCENT`_**

### TerrainType

**_`DC.TerrainType.NONE`_**

**_`DC.TerrainType.XYZ`_**

**_`DC.TerrainType.GOOGLE`_**

**_`DC.TerrainType.ARCGIS`_**

**_`DC.TerrainType.VR`_**

### LayerType

**_`DC.LayerType.VECTOR`_**

**_`DC.LayerType.PRIMITIVE`_**

**_`DC.LayerType.TILESET`_**

**_`DC.LayerType.HTML`_**

**_`DC.LayerType.GEOJSON`_**

**_`DC.LayerType.CLUSTER`_**

**_`DC.LayerType.VIDEO`_**

**_`DC.LayerType.KML`_**

**_`DC.LayerType.CZML`_**

**_`DC.LayerType.HEAT`_**

**_`DC.LayerType.MAPV`_**

**_`DC.LayerType.CHART`_**

### OverlayType

**_`DC.OverlayType.POINT`_**

**_`DC.OverlayType.POLYLINE`_**

**_`DC.OverlayType.POLYGON`_**

**_`DC.OverlayType.MODEL`_**

**_`DC.OverlayType.BILLBOARD`_**

**_`DC.OverlayType.RECTANGLE`_**

**_`DC.OverlayType.CIRCLE`_**

**_`DC.OverlayType.LABEL`_**

**_`DC.OverlayType.PLANE`_**

**_`DC.OverlayType.TILESET`_**

**_`DC.OverlayType.WALL`_**

**_`DC.OverlayType.BOX`_**

**_`DC.OverlayType.CORRIDOR`_**

**_`DC.OverlayType.CYLINDER`_**

**_`DC.OverlayType.CUSTOM_BILLBOARD`_**

**_`DC.OverlayType.CUSTOM_LABEL`_**

**_`DC.OverlayType.ATTACK_ARROW`_**

**_`DC.OverlayType.DOUBLE_ARROW`_**

**_`DC.OverlayType.FINE_ARROW`_**

**_`DC.OverlayType.GATHERING_PLACE`_**

**_`DC.OverlayType.TAILED_ATTACK_ARROW`_**

**_`DC.OverlayType.WATER_PRIMITIVE`_**

**_`DC.OverlayType.VIDEO_PRIMITIVE`_**

**_`DC.OverlayType.CAMERA_VIDEO`_**

**_`DC.OverlayType.PLAN_VIDEO`_**

### RoamingViewMode

**_`DC.RoamingViewMode.FREE`_**

**_`DC.RoamingViewMode.FP`_**

**_`DC.RoamingViewMode.TP`_**

**_`DC.RoamingViewMode.TRACKED`_**

## DC.Viewer

> 3D scene primary interface to build 3D scenes in a given DivId, also available as DC.World

### example

```html
<div id="viewer-container"></div>
```

```js
let viewer = DC.Viewer('viewer-container')
global.viewer = viewer
```

:::warning
If you are using a MVVM framework like Vue, do not add viewer, layer, or overlay to the data model. Since the 3D scene will keep refreshing each frame, adding data to the data model will cause the browser to crash if it takes a long time.
:::

### creation

- **_constructor(id,[options])_**

  - parameters
    - `{String} id`：divId
    - `{Object} options`
  - returns `viewer`

```json
//options（optional）
{
  "contextOptions": {
    "webgl": {
      "alpha": false,
      "depth": true,
      "stencil": false,
      "antialias": true,
      "powerPreference": "high-performance",
      "premultipliedAlpha": true,
      "preserveDrawingBuffer": false,
      "failIfMajorPerformanceCaveat": false
    },
    "allowTextureFilterAnisotropic": true
  },
  "sceneMode": 3 //1: 2.5D，2: 2D，3: 3D
}
```

### properties

- `{Element} dcContainer`：custom container **_`readonly`_**
- `{Object} scene` **_`readonly`_**[Scene](https://cesium.com/docs/cesiumjs-ref-doc/Scene.html)
- `{Object} camera`**_`readonly`_**[Camera](https://cesium.com/docs/cesiumjs-ref-doc/Scene.html)
- `{Element} canvas`**_`readonly`_**
- `{Object} clock`[Clock](https://cesium.com/docs/cesiumjs-ref-doc/Clock.html)
- `{Object} dataSources`[DataSourceCollection](https://cesium.com/docs/cesiumjs-ref-doc/DataSourceCollection.html)
- `{Object} imageryLayers`[ImageryLayerCollection](https://cesium.com/docs/cesiumjs-ref-doc/ImageryLayerCollection.html)
- `{Object} entities`[EntityCollection](https://cesium.com/docs/cesiumjs-ref-doc/EntityCollection.html)
- [`{Popup} popup`](#popup)**_`readonly`_**
- [`{ContextMenu} contextMenu`](#contextmenu)**_`readonly`_**
- [`{Tooltip} tooltip`](#tooltip)**_`readonly`_**
- [`{MapSplit} mapSplit`](#mapsplit)**_`readonly`_**
- [`{Compass} compass`](#compass)**_`readonly`_**
- [`{ZoomController} zoomController`](#zoomcontroller)**_`readonly`_**
- [`{LocationBar} locationBar`](#locationbar)**_`readonly`_**
- [`{DistanceLegend} distanceLegend`](#distancelegend)**_`readonly`_**
- [`{LoadingMask} loadingMask`](#loadingmask)**_`readonly`_**
- `{Position} cameraPosition`**_`readonly`_**

### methods

- **_setOptions(options)_**

  - parameters
    - `{Object} options`：属性对象
  - returns `this`

```json
// options(optional)
{
  "shadows": false,
  "resolutionScale": 1,
  "showAtmosphere": true,
  "showSun": true,
  "showMoon": true,
  "enableFxaa": true,
  "cameraController": {
    "enableRotate": true,
    "enableTilt": true,
    "enableTranslate": true,
    "enableZoom": true,
    "enableCollisionDetection": true,
    "minimumZoomDistance": 1.0,
    "maximumZoomDistance": 40489014.0
  },
  "globe": {
    "show": true,
    "showGroundAtmosphere": true,
    "enableLighting": false,
    "depthTestAgainstTerrain": false,
    "tileCacheSize": 100,
    "preloadSiblings": false,
    "baseColor": new DC.Color(0, 0, 0.5, 1),
    "translucency": {
      "enabled": false,
      "backFaceAlpha": 1,
      "backFaceAlphaByDistance": null,
      "frontFaceAlpha": 1,
      "frontFaceAlphaByDistance": null
    }
  },
  "skyBox": {
    "sources": {},
    "show": true,
    "offsetAngle": 0
  }
}
```

- **_setPitchRange(min,max)_**

  - parameters
    - `{Number} min`：min angel
    - `{Number} max`：max angel
  - returns `this`

- **_limitCameraToGround()_**

  - returns `this`

- **_changeSceneMode(sceneMode, [duration])_**

  - parameters
    - `{Number} sceneMode`: 2：2D，3：3D，2.5：2.5D
    - `{Number} duration`
  - returns `this`

- **_changeMouseMode(mouseMode)_**

  - parameters
    - `{Number} mouseMode`, Refer to：`DC.MouseMode`
  - returns `this`

- **_addBaseLayer(baseLayers,[options])_**

  - parameters
    - `{baseLayer|Array<baseLayer>} baseLayers`
    - `{Object} options`
  - returns `this`

```json
//options
{
  "name": "map",
  "iconUrl": "../preview.png"
}
```

- **_changeBaseLayer(index)_**

  - parameters
    - `{Number} index`
  - returns `this`

- **_addTerrain(terrain)_**

  - parameters
    - `{Terrain} terrain`
  - returns `this`

- **_changeTerrain(index)_**

  - parameters
    - `{Number} index`
  - returns `this`

- **_removeTerrain()_**

  - returns `this`

- **_addLayerGroup(layerGroup)_**

  - parameters
    - `{LayerGroup} layerGroup`
  - returns `this`

- **_removeLayerGroup(layerGroup)_**

  - parameters
    - `{LayerGroup} layerGroup`
  - returns `this`

- **_addLayer(layer)_**

  - parameters
    - `{Layer} layer`
  - returns `this`

- **_removeLayer(layer)_**

  - parameters
    - `{Layer} layer`
  - returns `this`

- **_getLayer(id)_**

  - parameters
    - `{String} id`:layer id
  - returns `layer`

- **_getLayers()_**

  - returns `layer`

- **_eachLayer(callback, context)_**

  - parameters
    - `{Function} callback`
    - `{Object} context`
  - returns `this`

  ```js
  viewer.eachLayer((layer) => {})
  ```

- **_flyTo(target,[duration])_**

  - parameters
    - `{VectorLayer|Overlay} target`
    - `{Number} duration`
  - returns `this`

- **_zoomTo(target)_**

  - parameters
    - `{VectorLayer|Overlay} target`
  - returns `this`

- **_flyToPosition(position, [completeCallback], [duration])_**

  - parameters
    - `{Position} position`
    - `{Function} completeCallback`
    - `{Number} duration`
  - returns `this`

- **_zoomToPosition(position, [completeCallback])_**

  - parameters
    - `{DC.Position} position`
    - `{Function} completeCallback`
  - returns `this`

- **_on(type, callback, [context])_**

  - parameters
    - `{Object} type`
    - `{Function} callback`
    - `{Object} context`
  - returns `this`

- **_once(type, callback, [context])_**

  - parameters
    - `{Object} type`
    - `{Function} callback`
    - `{Object} context`
  - returns `this`

- **_off(type, callback, [context])_**

  - parameters
    - `{Object} type`
    - `{Function} callback`
    - `{Object} context`
  - returns `this`

- **_destroy()_**

  - returns `this`

- **_exportScene([name])_**

  - parameters
    - `{String} name`
  - returns `this`

- **_use(plugin)_**

  - parameters
    - `{Object} plugin`
  - returns `this`

  ```js
  let plugin = {
    install: (viewer) => {},
  }
  viewer.use(plugin)
  ```

## Popup

### example

```js
let popup = viewer.popup
popup.setContent('<div></div>')
```

### properties

- `{String} state`**_`readonly`_**
- `{Object} config`**_`writeOnly`_**

```json
{
  "position": "center", // center，left ，right
  "customClass": "custom" // Add a custom Css class name to the popup, separating multiple names with spaces
}
```

### methods

- **_setPosition(position)_**

  - parameters
    - `{Cartesian3} position`: World Coordinates
  - returns `this`

- **_setContent(content)_**

  - parameters
    - `{String|Element} content`
  - returns `this`

- **_setWrapper(wrapper)_**

  - parameters
    - `{Element} wrapper`**_`(Templates for MVVM frameworks in general)`_**
  - returns `this`

- **_showAt(position, content)_**

  - parameters
    - `{Cartesian3} position`
    - `{String|Element} content`
  - returns `this`

- **_hide()_**

  - returns `this`

## ContextMenu

### example

```js
let contextMenu = viewer.contextMenu
contextMenu.enable = true
contextMenu.DEFAULT_MENU = [
  {
    label: '测试',
    callback: (e) => {}, // e: windowPosition,position,surfacePosition,overlay
    context: this,
  },
] // Setting the default ContextMenu affects the global ContextMenu (use with caution).
```

### properties

- `{Boolean} enable`
- `{String} state`**_`readonly`_**
- `{Array} DEFAULT_MENU`：**_`writeOnly`_**

## Tooltip

### example

```js
let tooltip = viewer.tooltip
tooltip.enable = true
tooltip.showAt({ x: 100, y: 100 }, 'test')
```

### properties

- `{Boolean} enable`
- `{String} state` **_`readonly`_**

### methods

- **_showAt(position,content)_**

  - parameters
    - `{Cartesian2} position`: Screen Coordinates
    - `{String|Element} content`
  - returns `this`

## MapSplit

### examples

```js
let baseLayer_elc = DC.ImageryLayerFactory.createGoogleImageryLayer()
viewer.mapSplit.enable = true
viewer.mapSplit.addBaseLayer(baseLayer_elc, -1)
```

### properties

- `{Boolean} enable`
- `{String} state`**_`readonly`_**

### methods

- **_addBaseLayer(baseLayer,splitDirection)_**

  - parameters
    - `{BaseLayer} baseLayer`
    - `{Number} splitDirection`,-1：left，0：none，1：right
  - returns `this`

## Compass

### examples

```js
viewer.compass.enable = true
```

### properties

- `{Boolean} enable`
- `{String} state` **_`readonly`_**

## ZoomController

### examples

```js
viewer.zoomController.enable = true
```

### properties

- `{Boolean} enable`
- `{String} state`**_`readonly`_**

## LocationBar

### examples

```js
viewer.locationBar.enable = true
```

### properties

- `{Boolean} enable`
- `{String} state` **_`readonly`_**

## DistanceLegend

### examples

```js
viewer.distanceLegend.enable = true
```

### properties

- `{Boolean} enable`
- `{String} state`,**_`readonly`_**

## LoadingMask

### examples

```js
viewer.loadingMask.enable = true
```

### properties

- `{Boolean} enable`
- `{String} state`**_`readonly`_**

## DC.SkyBox

### example

```js
scene.skyBox = new DC.SkyBox({
  sources: {
    positiveX: 'skybox_px.png',
    negativeX: 'skybox_nx.png',
    positiveY: 'skybox_py.png',
    negativeY: 'skybox_ny.png',
    positiveZ: 'skybox_pz.png',
    negativeZ: 'skybox_nz.png',
  },
})
```

### creation

- **_constructor(id)_**

  - parameters
    - `{Object} options`
  - returns `skyBox`

```json
//options(optional)
{
  "sources": {},
  "show": true,
  "offsetAngle": 0
}
```

### properties

- `{Object} sources`
- `{Boolean} show`
- `{Number} offsetAngle`

## DC.Position

### example

```js
let position = new DC.Position(120, 22, 102)

let position1 = DC.Position.fromCoordString('120,22,102')

let position2 = DC.Position.fromCoordArray([120, 22, 102])
```

### creation

- **_constructor(lng,lat,[alt],[heading],[pitch],[roll])_**

  - parameters
    - `{Number} lng`
    - `{Number} lat`
    - `{Number} alt`
    - `{Number} heading`
    - `{Number} pitch`
    - `{Number} roll`
  - returns `position`

### properties

- `{Number} lng`
- `{Number} lat`
- `{Number} alt`
- `{Number} heading`
- `{Number} pitch`
- `{Number} roll`

### methods

- **_serialize()_**

  - returns `string`

- **_copy()_**

  - returns `position`

- **_toString()_**

  - returns `string`

- **_toArray()_**

  - returns `array`

- **_toObject()_**

  - returns `Object`

### static methods

- **_fromString(str)_**

  - parameters
    - `{String} str`
  - returns `position`

- **_fromArray(array)_**

  - parameters
    - `{Array} array`
  - returns `position`

- **_fromObject(obj)_**

  - parameters
    - `{Object} obj`
  - returns `position`

- **_deserialize(valStr)_**

  - parameters
    - `{String} valStr`
  - returns `position`

## DC.Color

### example

```js
let red = DC.Color.RED
```

### properties

- `{Color} RED`
- `{Color} YELLOW`
- `{Color} WHITE`
- `{Color} GREEN`

  [others](https://cesium.com/docs/cesiumjs-ref-doc/Color.html)

## DC.TilesetStyle

### example

```js
let style = new DC.TilesetStyle()
style.color = {
  conditions: [
    ['${floor} >= 5', 'rgb(198, 106, 11)'],
    ['true', 'rgb(127, 59, 8)'],
  ],
}
```

[Cesium3DTileStyle](https://cesium.com/docs/cesiumjs-ref-doc/Cesium3DTileStyle.html)

## DC.JulianDate

```js
let date = DC.JulianDate.now()
```

### static methods

- **_now()_**

  - returns `date`

- **_fromDate(date)_**

  - parameters
    - `{Date} date`
  - returns `date`

[JulianDate](https://cesium.com/docs/cesiumjs-ref-doc/JulianDate.html)

## DC.Rect

### example

```js
let r = DC.Rect.fromDegrees(10, 20, 12, 31)
```

[Rectangle](https://cesium.com/docs/cesiumjs-ref-doc/Rectangle.html)

## DC.CallbackProperty

```js
let position = new DC.Position(120, 20)
let point = new DC.Point(position)
let size = 0
point.setStyle({
  pixelSize: new DC.CallbackProperty((time) => {
    size += 1
    if (size == 10) {
      size = 0
    }
    return size
  }),
})
```

[CallbackProperty](https://cesium.com/docs/cesiumjs-ref-doc/CallbackProperty.html)

## DC.Parse

> Coordinate resolution tool class, can be abbreviated as DC.P

```js
let position = DC.P.parsePosition('123,32,0')
```

### static methods

- **_parsePosition(position)_**

  - parameters
    - `{String|Array|Position} position`
  - returns `position`

- **_parsePositions(positions)_**

  - parameters
    - `{String|Array} positions`
  - returns `array`

- **_parsePointCoordToArray(position)_**

  - parameters
    - `{String|Position} position`
  - returns `array`

- **_parsePolylineCoordToArray(positions)_**

  - parameters
    - `{String|Array} positions`
  - returns `array`

- **_parsePolygonCoordToArray(positions)_**

  - parameters
    - `{String|Array} positions`
  - returns `array`

## DC.Transform

> Coordinate conversion tool class , can be abbreviated DC.T

```js
let cartesian3 = DC.T.transformWGS84ToCartesian(new DC.Position(120, 20))
```

### static methods

- **_transformCartesianToWGS84(cartesian)_**

  - parameters
    - `{Cartesian3} cartesian`
  - returns `position`

- **_transformWGS84ToCartesian(position)_**

  - parameters
    - `{Position} position`
  - returns `cartesian`

- **_transformWGS84ToCartographic(position)_**

  - parameters
    - `{Position} position`
  - returns `cartographic`

- **_transformCartesianArrayToWGS84Array(cartesianArr)_**

  - parameters
    - `{Array<cartesian3>} cartesianArr`
  - returns `array`

- **_transformWGS84ArrayToCartesianArray(WGS84Arr)_**

  - parameters
    - `{Array<cartesian3>} WGS84Arr`
  - returns `array`

- **_transformWGS84ToMercator(position)_**

  - parameters
    - `{Position} position`
  - returns `position`

- **_transformMercatorToWGS84(position)_**

  - parameters
    - `{Position} position`
  - returns `position`

- **_transformWindowToWGS84(position,viewer)_**

  - parameters
    - `{Object} position`,format:`{x:1,y:1}`
    - `{Viewer} viewer`
  - returns `position`

- **_transformWGS84ToWindow(position,viewer)_**

  - parameters
    - `{Position} position`
    - `{Viewer} viewer`
  - returns `Object`

## DC.CoordTransform

> China Coordinate Conversion Tool

```js
let point = DC.CoordTransform.BD09ToGCJ02(120, 20)
```

### static methods

- **_BD09ToGCJ02(lng, lat)_**

  - parameters
    - `{Number} lng`
    - `{Number} lat`
  - returns `[]`

- **_GCJ02ToBD09(lng, lat)_**

  - parameters
    - `{Number} lng`
    - `{Number} lat`
  - returns `[]`

- **_WGS84ToGCJ02(lng, lat)_**

  - parameters
    - `{Number} lng`
    - `{Number} lat`
  - returns `[]`

- **_GCJ02ToWGS84(lng, lat)_**

  - parameters
    - `{Number} lng`
    - `{Number} lat`
  - returns `[]`

## DC.Math

### static methods

- **_area(positions)_**

  - parameters
    - `{Array<Position>} positions`
  - returns `number`

- **_bounds(positions , expand)_**

  - parameters
    - `{Array<Position>} positions`
    - `{Number}} expand`:0~1
  - returns `object`

- **_mid(startPosition , endPosition)_**

  - parameters
    - `{Position} startPosition`
    - `{Position} endPosition`
  - returns `position`

- **_center(positions)_**

  - parameters
    - `{Array<Position>} positions`
  - returns `position`

- **_distance(positions)_**

  - parameters
    - `{Array<Position>} positions`
  - returns `number`

- **_heading(startPosition, endPosition)_**

  - parameters
    - `{Position} startPosition`
    - `{Position} endPosition`
  - returns `number`

- **_parabola(startPosition, endPosition,height,count)_**

  - parameters
    - `{Position} startPosition`
    - `{Position} endPosition`
    - `{Number} height`
    - `{Number} count`
  - returns `Array`

> [more](https://cesium.com/docs/cesiumjs-ref-doc/Math.html)

## DC.Util

### static methods

- **_uuid([prefix])_**

  - parameters
    - `{String} prefix`
  - returns `string`

- **_merge(dest, ...sources)_**

  - parameters
    - `{Object} dest`
    - `{Object|Array} sources`
  - returns `object`

- **_emptyImageUrl()_**

- **_debounce(fn,delay)_**

- **_throttle(fn,delay)_**

## DC.DomUtil

### static methods

- **_get(id)_**

  - parameters
    - `{String} id`
  - returns `Element`

- **_create(tagName, className, [container])_**

  - parameters
    - `{String} tagName`
    - `{String} className`
    - `{Element} [container]`
  - returns `Element`

- **_addClass(el, name)_**

  - parameters
    - `{Element} el`
    - `{String} className`

- **_removeClass(el, name)_**

  - parameters
    - `{Element} el`
    - `{String} className`

- **_addClass(el, name)_**

  - parameters
    - `{Element} el`
    - `{String} className`

- **_createSvg(width, height, path, [container])_**

  - parameters
    - `{Number} width`
    - `{Number} height`
    - `{String} path`
    - `{Element} [container]`
  - returns `svg`

- **_parseDom(domStr, [withWrapper], [className])_**

  - parameters
    - `{String} domStr`
    - `{Boolean} withWrapper`
    - `{String} className`
  - returns `Element | Nodes`

- **_enterFullscreen(el)_**

  - parameters
    - `{Element} el`

- **_exitFullscreen()_**

- **_createVideo(url, className, [container])_**

  - parameters
    - `{String} url`
    - `{String} className`
    - `{Element} [container]`
  - returns `Element | Nodes`
