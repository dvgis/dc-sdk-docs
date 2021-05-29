---
sidebar: auto
---

# 场景分析 🌎

## DC.Analysis

> 三维场景分析

### example

```js
viewer.use(new DC.Analysis())
```

### creation

- **_constructor()_**

  构造函数

  - 返回值 `analysis`

### methods

- **_contourLine(lineColor, lineWidth, lineSpacing)_**

  等高线

  - 参数
    - `{Color} lineColor`：颜色
    - `{Number} lineWidth`：宽度
    - `{Number} lineSpacing`：间隔
  - 返回值 `this`

- **_shadows(startTime, multiplier)_**

  日照分析

  - 参数
    - `{Date} startTime`：日期
    - `{Number} multiplier`：倍率
  - 返回值 `this`

- **_sightLine(startPosition, endPosition, excludes, lerpNum)_**

  通视分析(线)

  - 参数
    - `{Position|Array|String|Object} startPosition`：起点
    - `{Position|Array|String|Object} endPosition`：终点
    - `{Array<Overlay>} excludes`：非包含覆盖物
    - `{Number} lerpNum`：插值数量，默认：10，数量越大越准确，同时计算量也会增加
  - 返回值 `this`

- **_sightCircle(center, radius, excludes, lerpNum)_**

  通视分析(圆)

  - 参数
    - `{Position|Array|String|Object} center`：圆心
    - `{Number} radius`：半径
    - `{Array<Overlay>} excludes`：非包含覆盖物
    - `{Number} lerpNum`：插值数量，默认：10，数量越大越准确，同时计算量也会增加
  - 返回值 `this`

- **_viewshed(position, radius, fov, aspectRatio, options)_**

  可视域分析

  - 参数
    - `{Position|Array|String|Object} position`：视点
    - `{Number} radius`：半径
    - `{Number} fov`：横向视角
    - `{Number} aspectRatio`：横纵比例
    - `{Object} options`：属性设置
  - 返回值 `this`

```json
//属性参数
{
  "visibleColor"：DC.Color.GREEN,//可见颜色
  "disVisibleColor"：DC.Color.RED,//不可见颜色
  "showHelp": false, //显示辅助覆盖物
  "gridColor": DC.Color.YELLOW, //辅助覆盖物格子颜色
  "lineColor": DC.Color.YELLOW.withAlpha(0.3) //辅助覆盖物边线颜色
}
```

## DC.CameraVideoLayer

> 视频图层，继承于[Layer](../layer/#layer)

### example

```js
let layer = new DC.CameraVideoLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `videoLayer`

### methods

- **_showHelp(show, videoOverlay, color)_**

  是否显示辅助视锥

  - 参数
    - `{Boolean} show`：是否显示
    - `{Overlay} videoOverlay`：视频覆盖物
    - `{Color} color`：边线颜色
  - 返回值 `this`

## DC.CameraVideo

> 视频融合要素，继承于[Overlay](../overlay/#overlay)

### example

```js
let position = new DC.Position(120, 20, 200, -20, 19)
let videoEl = new document.getElementById('video')
let cameraVideo = new DC.CameraVideo(position, videoEl)
layer.addOverlay(cameraVideo)
```

### creation

- **_constructor(position, video,[maskUrl])_**

  构造函数

  - 参数
    - `{Position} position`：坐标
    - `{Element} video`：视频节点
    - `{String} [maskUrl]`: 羽化图片地址
  - 返回值 `cameraVideo`

### properties

- `{Position} position`：坐标
- `{Element} video`：视频节点
- `{String} maskUrl`: 羽化图片地址

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式
  - 返回值 `this`

```json
// 样式参数(可选)
{
  "fov": 60, //视场角
  "near": 1, //近平面的距离
  "far": 5000, //远平面的距离
  "aspectRatio": 1, //视锥的宽度与高度的纵横比
  "alpha": 1, //透明度
  "clearBlack": true, //清除空白
  "disViewColor": DC.Color.WHITE //设置视频不可见颜色
}
```

## DC.PlaneVideoLayer

> 平面视频图层，继承于[Layer](../layer/#layer)

### example

```js
let layer = new DC.PlaneVideoLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `videoLayer`

### methods

- **_showHelp(show, videoOverlay, color)_**

  是否显示辅助视锥

  - 参数
    - `{Boolean} show`：是否显示
    - `{Overlay} videoOverlay`：视频覆盖物
    - `{Color} color`：边线颜色
  - 返回值 `this`

## DC.PlaneVideo

> 平面视频要素，继承于[Overlay](../overlay/#overlay)

### example

```js
let position = new DC.Position(120, 20, 200, -20, 19)
let videoEl = new document.getElementById('video')
let cameraVideo = new DC.PlaneVideo(position, videoEl)
layer.addOverlay(cameraVideo)
```

### creation

- **_constructor(position, video)_**

  构造函数

  - 参数
    - `{Position} position`：坐标
    - `{Element} video`：视频节点
  - 返回值 `cameraVideo`

### properties

- `{Position} position`：坐标
- `{Element} video`：视频节点

### methods

- **_setStyle(style)_**

  设置样式

  - 参数
    - `{Object} style`：样式
  - 返回值 `this`

```json
// 样式参数(可选)
{
  "fov": 60, //视场角
  "near": 1, //近平面的距离
  "far": 5000, //远平面的距离
  "aspectRatio": 1 //视锥的宽度与高度的纵横比
}
```

## DC.GeoTools

> 要素工具

### example

```js
let coords = DC.GeoTools.pointBuffer(
  '120.71259021075333,31.22148081085083',
  100
)

let coords1 = DC.GeoTools.polygonBuffer(
  '120.71259021075333,31.22148081085083;120.71611354431036,31.221447256684566;120.7140691869497,31.21875584696343',
  150
)
```

### static methods

- **_pointBuffer(position, radius, steps)_**

  点缓冲

  - 参数
    - `{Array|String|Position} position`：坐标
    - `{Number} radius`：半径
    - `{Number} steps`：步数，默认：8
  - 返回值 `array`

- **_polylineBuffer(positions, radius, steps)_**

  线缓冲

  - 参数
    - `{Array|String|Array<Position>} positions`：坐标串
    - `{Number} radius`：半径
    - `{Number} steps`：步数，默认：8
  - 返回值 `array`

- **_polygonBuffer(positions, radius, steps)_**

  面缓冲

  - 参数
    - `{Array|String|Array<Position>} positions`：坐标串
    - `{Number} radius`：半径
    - `{Number} steps`：步数，默认：8
  - 返回值 `array`

- **_transformPolylineScale(positions, factor)_**

  线比例

  - 参数
    - `{Array|String|Array<Position>} positions`：坐标串
    - `{Number} factor`：比例
  - 返回值 `array`

- **_transformPolygonScale(positions, factor)_**

  面比例

  - 参数
    - `{Array|String|Array<Position>} positions`：坐标串
    - `{Number} factor`：比例
  - 返回值 `array`

## DC.GlobClipping

> 地球裁剪

### example

```js
let globClipping = new DC.GlobClipping(viewer)
```

### creation

- **_constructor(viewer,[options])_**

  构造函数

  - 参数
    - `{Viewer} viewer`：场景
    - `{Object} options`：属性
  - 返回值 `globClipping`

```json
// 属性参数(可选)
{
  "edgeWidth": 0, // 边缘宽度
  "edgeColor": DC.Color.WHITE // 边缘颜色
}
```

### properties

- `{Array<Position>} positions`：坐标串
- `{Number} distance`: 距离
- `{Boolean} enable`: 是否启用
- `{String} state`: 状态 **_`readonly`_**

## DC.TerrainClipping

> 地形裁剪

### example

```js
let terrainClipping = new DC.TerrainClipping(viewer)
```

### creation

- **_constructor(viewer,[options])_**

  构造函数

  - 参数
    - `{Viewer} viewer`：场景
    - `{Object} options`：属性
  - 返回值 `terrainClipping`

```json
// 属性参数(可选)
{
  "edgeWidth": 0, // 边缘宽度
  "edgeColor": DC.Color.WHITE, // 边缘颜色
  "lerpInterval": 50, // 插值数量
  "bottomImage": "", // 底部图片
  "sideImage": "" // 侧边图片
}
```

### properties

- `{Array<Position>} positions`：坐标串
- `{Number} height`: 高度
- `{Boolean} enable`: 是否启用
- `{String} state`: 状态 **_`readonly`_**
