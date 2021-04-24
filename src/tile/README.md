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

  - parameters
    - `{Object} options`
  - returns `baseLayer`

- **_createBaiduImageryLayer(options)_**

  - parameters
    - `{Object} options`
  - returns `baseLayer`

- **_createGoogleImageryLayer(options)_**

  - parameters
    - `{Object} options`
  - returns `baseLayer`

- **_createTdtImageryLayer(options)_**

  - parameters
    - `{Object} options`
  - returns `baseLayer`

- **_createTencentImageryLayer(options)_**

  - parameters
    - `{Object} options`
  - returns `baseLayer`

- **_createArcGisImageryLayer(options)_**

  - parameters
    - `{Object} options` [ArcGis](https://cesium.com/docs/cesiumjs-ref-doc/ArcGisMapServerImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createSingleTileImageryLayer(options)_**

  - parameters
    - `{Object} options` [Single](https://cesium.com/docs/cesiumjs-ref-doc/SingleTileImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createWMSImageryLayer(options)_**

  - parameters
    - `{Object} options` [WMS](https://cesium.com/docs/cesiumjs-ref-doc/WebMapServiceImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createWMTSImageryLayer(options)_**

  - parameters
    - `{Object} options` [WMTS](https://cesium.com/docs/cesiumjs-ref-doc/WebMapTileServiceImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createXYZImageryLayer(options)_**

  - parameters
    - `{Object} options` [X/Y/Z](https://cesium.com/docs/cesiumjs-ref-doc/UrlTemplateImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createCoordImageryLayer(options)_**

  - parameters
    - `{Object} options`
  - returns `baseLayer`

- **_createGridImageryLayer(options)_**

  - parameters
    - `{Object} options` [Grid](http://resource.dvgis.cn/cesium-docs/GridImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createMapboxImageryLayer(options)_**

  - parameters
    - `{Object} options` [Mapbox](http://resource.dvgis.cn/cesium-docs/MapboxImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createMapboxStyleImageryLayer(options)_**

  - parameters
    - `{Object} options` [Mapbox Style](http://resource.dvgis.cn/cesium-docs/MapboxStyleImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createTMSImageryLayer(options)_**

  - parameters
    - `{Object} options` [TMS](http://resource.dvgis.cn/cesium-docs/TileMapServiceImageryProvider.html#.ConstructorOptions)
  - returns `baseLayer`

- **_createImageryLayer(type, options)_**

  - parameters
    - `{String} type`，DC.ImageryType
    - `{Object} options`
  - returns `baseLayer`

```json
//options(optional)
{
  "url": "",
  "style": "img", //img、elec、ter。baidu：normal、middlenight、dark，tencent：img,1、4
  "key": "", //Valid only for TDT
  "subdomains": [],
  "crs":"WGS84",// WGS84 、BD09 、GCJ02
  "tilingScheme":null, // GeographicTilingScheme , WebMercatorTilingScheme
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

  - returns `terrain`

- **_createUrlTerrain(options)_**

  - parameters
    - `{Object} options`
  - returns `terrain`

- **_createGoogleTerrain(options)_**

  - parameters
    - `{Object} options`
  - returns `terrain`

- **_createArcgisTerrain(options)_**

  - parameters
    - `{Object} options`
  - returns `terrain`

- **_createVRTerrain(options)_**

  - parameters
    - `{Object} options`
  - returns `terrain`

- **_createTerrain(type，options)_**

  - parameters
    - `{String} type`: DC.TerrainType
    - `{Object} options`
  - returns `terrain`

```json
//options（optional）
{
  "url": ""
}
```
