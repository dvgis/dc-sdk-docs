---
sidebar: auto
---

# 业务图层 🌎

将具有相同业务逻辑或属性的覆盖元素进行分类，以便于同一管理

## Layer

> 图层的基类，其子类是实例化后需添加到三维场景中方可展示各类三维数据

:::warning
该基本类无法实例化
:::

### properties

- `{String} id`：唯一标识 **_`readonly`_**
- `{Boolean} show`：是否显示
- `{Object} attr`：业务属性
- `{String} state`：图层状态 **_`readonly`_**
- `{String} type`：图层类型 **_`readonly`_**

### methods

- **_addOverlay(overlay)_**

  添加覆盖物

  - 参数
    - `{Overlay} overlay`：覆盖物
  - 返回值 `this`

- **_addOverlays(overlays)_**

  添加覆盖物数组

  - 参数
    - `{Array<Overlay>} overlays`：覆盖物数组
  - 返回值 `this`

- **_removeOverlay(overlay)_**

  删除覆盖物

  - 参数
    - `{Overlay} overlay`：覆盖物
  - 返回值 `this`

- **_getOverlay(overlayId)_**

  根据 Id 获取覆盖物`(不推荐用)`

  - 参数
    - `{String} overlayId`：覆盖物唯一标识(默认产生)
  - 返回值 `overlay`

- **_getOverlayById(Id)_**

  根据业务 Id 获取覆盖物`(推荐用)`

  - 参数
    - `{String} Id`：覆盖物业务唯一标识
  - 返回值 `overlay`

- **_getOverlaysByAttr(attrName, attrVal)_**

  根据覆盖物属性获取覆盖物

  - 参数
    - `{String} attrName`：属性名称
    - `{Object} attrVal`：属性值
  - 返回值 `array`

  ```js
  overlay.attr.name = 'test' //设置覆盖物的属性
  let arr = layer.getOverlaysByAttr('name', 'test') //根据属性获取覆盖物
  ```

- **_getOverlays()_**

  获取所有覆盖物

  - 返回值 `array`

- **_eachOverlay(method, context)_**

  遍历覆盖物

  - 参数
    - `{Function} method`：回调函数，参数为每一个覆盖物
    - `{Object} context`：上下文
  - 返回值 `this`

  ```js
  layer.eachOverlay((item) => {})
  ```

- **_clear()_**

  清空图层

  - 返回值 `this`

- **_remove()_**

  删除图层

  - 返回值 `this`

- **_addTo(viewer)_**

  添加图层到场景

  - 参数
    - `{Viewer|World} viewer`：场景
  - 返回值 `this`

### static methods

- **_registerType(type)_**

  注册图层类型

  - 参数
    - `{String} type`：图层类型

- **_getLayerType()_**

  获取图层类型

  - 返回值 `string`

## DC.LayerGroup

> 图层组，将图层按一定的逻辑分组，方便统一管理

### example

```js
let layerGroup = new DC.LayerGroup('id')
viewer.addLayerGroup(layerGroup)
let layer = new DC.VectorLayer('layer')
layerGroup.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.LayerGroup 构造函数

  - 参数
    - `{String} id`：图层组唯一标识
  - 返回值 `layerGroup`

### properties

- `{String} id`：唯一标识 **_`readonly`_**
- `{Boolean} show`：是否显示
- `{String} type`：图层类型 **_`readonly`_**

### methods

- **_addLayer(layer)_**

  添加图层

  - 参数
    - `{Layer} layer`：图层
  - 返回值 `this`

- **_removeLayer(layer)_**

  删除图层

  - 参数
    - `{Layer} layer`：图层
  - 返回值 `this`

- **_getLayer(id)_**

  获取图层

  - 参数
    - `{String} id`：图层 ID
  - 返回值 `layer`

- **_getLayers()_**

  获取所有图层，不包括地图

  - 返回值 `layer`

- **_remove()_**

  删除图层组

  - 返回值 `this`

- **_addTo(viewer)_**

  添加图层到场景

  - 参数
    - `{Viewer|World} viewer`：场景
  - 返回值 `this`

## DC.VectorLayer

> 矢量图层，用于添加各类矢量数据（点、线、面等），将矢量数据按一定的逻辑分组，方便统一管理，继承于[Layer](#layer)

### example

```js
let layer = new DC.VectorLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.VectorLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `vectorLayer`

## DC.PrimitiveLayer

> 图元图层，用于添加各类图元数据，将图元数据按一定的逻辑分组，方便统一管理，继承于[Layer](#layer)

### example

```js
let layer = new DC.PrimitiveLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.PrimitiveLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `primitiveLayer`

## DC.TilesetLayer

> 3dTiles 图层，用于添加 3dTiles 模型数据， 继承于[Layer](#layer)

### example

```js
let layer = new DC.TilesetLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.TilesetLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `tilesetLayer`

## DC.GeoJsonLayer

> GeoJson 图层，用于加载 GeoJson 格式数据，继承于[Layer](#layer)，

### example

```js
let layer = new DC.GeoJsonLayer('id', '**/**.geojson')
layer.eachOverlay((item) => {
  // item 为一个entity,
  if (item.polyline) {
    //todo
    let polyline = DC.Polyline.fromEntity(item)
  }
  if (item.polygon) {
    //todo
    let polygon = DC.Polygon.fromEntity(item)
  }
  if (item.billboard) {
    //todo
    let point = DC.Point.fromEntity(item)
    let divIcon = DC.DivIcon.fromEntity(item)
    let billboard = DC.Billboard.fromEntity(item)
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.GeoJsonLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{String} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[GeoJsonDataSource](https://cesium.com/docs/cesiumjs-ref-doc/GeoJsonDataSource.html)
  - 返回值 `geoJsonLayer`

### methods

- **_toVectorLayer()_**

  转换为矢量图层

  - 返回值 `vectorLayer`

- **_toModelLayer(modelUrl)_**

  转换为模型图层

  - 参数
    - `{String} modelUrl`：模型地址
  - 返回值 `vectorLayer`

## DC.TopoJsonLayer

> TopoJson 图层，用于加载 TopoJson 格式数据，继承于[Layer](#layer)，

### example

```js
let layer = new DC.GeoJsonLayer('id', '**/**.geojson')
layer.eachOverlay((item) => {
  // item 为一个entity,
  if (item.polyline) {
    //todo
    let polyline = DC.Polyline.fromEntity(item)
  }
  if (item.polygon) {
    //todo
    let polygon = DC.Polygon.fromEntity(item)
  }
  if (item.billboard) {
    //todo
    let point = DC.Point.fromEntity(item)
    let divIcon = DC.DivIcon.fromEntity(item)
    let billboard = DC.Billboard.fromEntity(item)
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.TopoJsonLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{String} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[GeoJsonDataSource](https://cesium.com/docs/cesiumjs-ref-doc/GeoJsonDataSource.html)
      - 返回值 `topoJsonLayer`

### methods

- **_toVectorLayer()_**

  转换为矢量图层

  - 返回值 `vectorLayer`

- **_toModelLayer(modelUrl)_**

  转换为模型图层

  - 参数
    - `{String} modelUrl`：模型地址
  - 返回值 `vectorLayer`

## DC.HtmlLayer

> Html 图层，用于加载 DivIcon 节点，继承于[Layer](#layer)，

### example

```js
let layer = new DC.HtmlLayer('dom')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  DC.HtmlLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `htmlLayer`

## DC.CzmlLayer

> Czml 图层，用于加载 Czml 数据，继承于[Layer](#layer)

### example

```js
let layer = new DC.CzmlLayer('id', '**/**.czml')
layer.eachOverlay((item) => {
  if (item.polyline) {
    //todo
  }
  if (item.polygon) {
    //todo
  }
  if (item.billboard) {
    //todo
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.CzmlLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{String} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[CzmlDataSource](https://cesium.com/docs/cesiumjs-ref-doc/CzmlDataSource.html)
  - 返回值 `czmlLayer`

## DC.KmlLayer

> Kml 图层，用于加载 Kml 数据，继承于[Layer](#layer)

### example

```js
let layer = new DC.KmlLayer('id', '**/**.kml')
layer.eachOverlay((item) => {
  if (item.polyline) {
    //todo
  }
  if (item.polygon) {
    //todo
  }
  if (item.billboard) {
    //todo
  }
})
```

### creation

- **_constructor(id,url,[options])_**

  DC.KmlLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{String} url`：数据地址
    - `{Object} options`：属性配置，详情参考：[KmlDataSource](https://cesium.com/docs/cesiumjs-ref-doc/KmlDataSource.html)
  - 返回值 `kmlLayer`

## DC.ClusterLayer

> 聚合图层，继承于[Layer](../dc-sdk/#layer)

### example

```js
let layer = new DC.ClusterLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id,[options])_**

  DC.ClusterLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{Object} options`：属性配置
  - 返回值 `clusterLayer`

```json
// 属性参数(可选)
{
  "size": 48, //聚合的尺寸
  "pixelRange": 40, //像素范围
  "gradient": {
    "0.0001": DC.Color.DEEPSKYBLUE,
    "0.001": DC.Color.GREEN,
    "0.01": DC.Color.ORANGE,
    "0.1": DC.Color.RED
  }, // 幅度颜色设置
  "style": "circle", // circle 和 clustering
  "fontSize": 12, // 字体大小
  "fontColor": DC.Color.BLACK // 字体颜色
}
```

## DC.HeatLayer

> 热区图层，继承于[Layer](../dc-sdk/#layer)

### example

```js
let bounds = [new DC.Position(100, 20), new DC.Position(150, 26)]
let layer = new DC.HeatLayer('id', bound)
viewer.addLayer(layer)
```

### creation

- **_constructor(id,bounds,[options])_**

  DC.HeatLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{Array<DC.Position>} bounds`：热区范围，有长度为 2 的数组组成，第一个为西南坐标，第二个为东北坐标
    - `{Object} options`：属性配置
  - 返回值 `heatLayer`

```json
//属性参数(可选)
{
  "maxOpacity": 0.8, // 最大透明度
  "minOpacity": 0.1, // 最小透明度
  "blur": 0.85, // 模糊度
  "gradient": {
    "0.5": "blue",
    "0.8": "red",
    "0.95": "white",
    "0.6": "yellow",
    "0.5": "green"
  }, //颜色设置
  "distanceDisplayCondition": {
    "near": 0, //最近距离
    "far": Number.MAX_VALUE //最远距离
  } //根据距离设置可见
}
```

### methods

- **_setPositions(positions)_**

  设置点位

  - 参数
    - `{Array<Object>} positions`：点位信息
  - 返回值 `heatLayer`

```json
//点位信息参数
{
  "lng": "", //经度
  "lat": "", //纬度
  "value": 10 //强度
}
```

## DC.WindLayer

> 风向图层，继承于[Layer](../dc-sdk/#layer)

### example

```js
let layer = new DC.WindLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id,[options])_**

  DC.WindLayer 构造函数

  - 参数
    - `{String} id`：图层唯一标识
    - `{Object} options`：属性配置
  - 返回值 `windLayer`

```json
//属性参数(可选)
{
  "globalAlpha": 0.9, //透明度
  "lineWidth": 1, // 线宽
  "colorScale": "#fff", //颜色
  "velocityScale": 1 / 25,
  "maxAge": 90,
  "paths": 800, // 路径数
  "frameRate": 20,
  "useCoordsDraw": true,
  "gpet": true
}
```

### methods

- **_setData(data,[options])_**

  设置风向数据

  - 参数
    - `{Object} data`：风向数据
    - `{Object} options`：配置信息，参考构造函数的配置信息
  - 返回值 `windLayer`

- **_setOptions(options)_**

  设置风向数据

  - 参数
    - `{Object} options`：配置信息，参考构造函数的配置信息
  - 返回值 `windLayer`
