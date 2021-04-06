---
sidebar: auto
---

# 场景分析 🌎

## DC.VideoLayer

> 视频图层，继承于[Layer](../layer/#layer)

### example

```js
let layer = new DC.VideoLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  构造函数

  - 参数
    - `{String} id`：图层唯一标识
  - 返回值 `videoLayer`

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

- **_showHelp(show)_**

  是否显示视锥

  - 参数
    - `{Boolean} show`：样式
  - 返回值 `this`

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
