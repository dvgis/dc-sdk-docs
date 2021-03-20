---
sidebar: auto
---

# Map 🌎

Construct topography and pictures of the earth's surface to show the real state of the earth's surface

## DC.ImageryLayerFactory

> For creating all kinds of map tiles

### example

```js
let baseLayer = DC.ImageryLayerFactory.createAmapImageryLayer({
  style: 'img',
})
viewer.addBaseLayer(baseLayer, {
  name: 'map',
  iconUrl: '../preview.png',
})
```

### static methods

- **_createAmapImageryLayer(options)_**

  - Parameters
    - `{Object} options`
  - Returns `baseLayer`

- **_createBaiduImageryLayer(options)_**

  - Parameters
    - `{Object} options`
  - Returns `baseLayer`

- **_createGoogleImageryLayer(options)_**

  - Parameters
    - `{Object} options`
  - Returns `baseLayer`

- **_createTdtImageryLayer(options)_**

  - Parameters
    - `{Object} options`
  - Returns `baseLayer`

- **_createTencentImageryLayer(options)_**

  - Parameters
    - `{Object} options`
  - Returns `baseLayer`

- **_createArcGisImageryLayer(options)_**

  - Parameters
    - `{Object} options` [ArcGis](https://cesium.com/docs/cesiumjs-ref-doc/ArcGisMapServerImageryProvider.html#.ConstructorOptions)
  - Returns `baseLayer`

- **_createSingleTileImageryLayer(options)_**

  - Parameters
    - `{Object} options` [Single](https://cesium.com/docs/cesiumjs-ref-doc/SingleTileImageryProvider.html#.ConstructorOptions)
  - Returns `baseLayer`

- **_createWMSImageryLayer(options)_**

  - Parameters
    - `{Object} options` [WMS](https://cesium.com/docs/cesiumjs-ref-doc/WebMapServiceImageryProvider.html#.ConstructorOptions)
  - Returns `baseLayer`

- **_createWMTSImageryLayer(options)_**

  - Parameters
    - `{Object} options` [WMTS](https://cesium.com/docs/cesiumjs-ref-doc/WebMapTileServiceImageryProvider.html#.ConstructorOptions)
  - Returns `baseLayer`

- **_createXYZImageryLayer(options)_**

  - Parameters
    - `{Object} options` [X/Y/Z](https://cesium.com/docs/cesiumjs-ref-doc/UrlTemplateImageryProvider.html#.ConstructorOptions)
  - Returns `baseLayer`

- **_createCoordImageryLayer(options)_**

  - Parameters
    - `{Object} options`
  - Returns `baseLayer`

- **_createImageryLayer(type, options)_**

  - Parameters
    - `{String} type`，DC.ImageryType
    - `{Object} options`
  - Returns `baseLayer`

```json
//options(optional)
{
  "url": "",
  "style": "img", //img、elec、ter。baidu：normal、middlenight、dark，tencent：img,1、4
  "key": "", //Valid only for TDT
  "subdomains": [],
  "crs":"WGS84",// WGS84 、BD09 、GCJ02
  "rectangle": {
    "west": 0,
    "south": 0,
    "east": 0,
    "north":
  }
}
```

## DC.TerrainFactory

> For creating terrain

### example

```js
let terrain = DC.ImageryLayerFactory.createUrlTerrain({
  url: '****/***',
})
viewer.addTerrain(terrain)
```

### static methods

- **_createEllipsoidTerrain()_**

  - Returns `terrain`

- **_createUrlTerrain(options)_**

  - Parameters
    - `{Object} options`
  - Returns `terrain`

- **_createGoogleTerrain(options)_**

  - Parameters
    - `{Object} options`
  - Returns `terrain`

- **_createArcgisTerrain(options)_**

  - Parameters
    - `{Object} options`
  - Returns `terrain`

- **_createVRTerrain(options)_**

  - Parameters
    - `{Object} options`
  - Returns `terrain`

- **_createTerrain(type，options)_**

  - Parameters
    - `{String} type`: DC.TerrainType
    - `{Object} options`
  - Returns `terrain`

```json
//options（optional）
{
  "url": ""
}
```
