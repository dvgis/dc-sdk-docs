---
sidebar: auto
---

# Overlays 🌎

An important part of the 3D scene, digitally representing an entity in the three scenes and recording its real-time state

## Overlay

> base class

:::warning
The class cannot be instantiated
:::

### properties

- `{String} overlayId` **_`readonly`_**
- `{String} id`
- `{Boolean} show`
- `{Object} attr`
- `{Array} contextMenu`
- `{String} state` **_`readonly`_**
- `{String} type` **_`readonly`_**
- `{Boolean} allowDrillPicking`：Default is false, if true, the overlay selects all the overlays behind it for penetration and triggers a mouse thing for all the overlays behind it 件

### methods

- **_addTo(layer)_**

  - Parameters
    - `{Layer} layer`
  - returns `this`

- **_remove()_**

  - returns `this`

- **_setLabel(text, textStyle)_**

  - Parameters
    - `{String} text`
    - `{String} textStyle` [DC.Label](#dc-label)
  - returns `this`

- **_on(type, callback, context)_**

  Event Subscription

  - Parameters
    - `{Object} type`
    - `{Function} callback`
    - `{Object} context`
  - returns `this`

- **_off(type, callback, context)_**

  Event Unsubscribe

  - Parameters
    - `{Object} type`
    - `{Function} callback`
    - `{Object} context`
  - returns `this`

- **_fire(type,params)_**

  - Parameters
    - `{Object} type`
    - `{Object} params`
  - returns `this`

### static methods

- **_registerType(type)_**

  - Parameters
    - `{String} type`

- **_getOverlayType(type)_**

  - Parameters
    - `{String} type`
  - returns `string`

## DC.Point

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let point = new DC.Point(position)
point.setStyle({
  pixelSize: 10,
})
```

### creation

- **_constructor(position)_**

  - Parameters
    - `{Position} position`
  - returns `point`

### properties

- `{Position} position`

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style` [PointGraphics](http://resource.dvgis.cn/cesium-docs/PointGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "pixelSize": 1,
  "heightReference": 0,
  "color": DC.Color.WHITE,
  "outlineColor": DC.Color.WHITE,
  "outlineWidth": 0,
  "scaleByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "translucencyByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "disableDepthTestDistance": 0
}
```

- **_fromEntity(entity)_**

  - Parameters
    - `{Object} entity`
  - returns `point`

## DC.Polyline

> Inherited from [Overlay](#overlay)

### example

```js
let polyline = new DC.Polyline('120,20;120,30')
polyline.setStyle({
  width: 10,
})
```

### creation

- **_constructor(positions)_**

  - Parameters
    - `{String|Array<Position|Number|String>} positions`
  - returns `polyline`

### properties

- `{String|Array<Position|Number|String>} positions`
- `{DC.Position} center` **_`readonly`_**
- `{Number} distance` **_`readonly`_**

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [PolylineGraphics](http://resource.dvgis.cn/cesium-docs/PolylineGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "width": 1,
  "material": DC.Color.WHITE,
  "clampToGround": false,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "classificationType": 2,
  "zIndex": 0
}
```

- **_fromEntity(entity)_**

  - Parameters
    - `{Object} entity`
  - returns `polyline`

## DC.Polygon

> Inherited from [Overlay](#overlay)

### example

```js
let polygon = new DC.Polygon('120,20;120,30;122,30')
polygon.setStyle({
  height: 10,
})
```

### creation

- **_constructor(positions)_**

  - Parameters
    - `{String|Array<Position|Number|String>} positions`
  - returns `polygon`

### properties

- `{String|Array<Position|Number|String>} positions`
- `{String|Array<Position|Number|String>} holes`
- `{DC.Position} center` **_`readonly`_**
- `{Number} area` **_`readonly`_**

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [PolygonGraphics](http://resource.dvgis.cn/cesium-docs/PolygonGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "height": 1,
  "heightReference": 0,
  "extrudedHeight": 0,
  "stRotation": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "closeTop": true,
  "closeBottom": true,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "classificationType": 2,
  "zIndex": 0
}
```

- **_fromEntity(entity)_**

  - Parameters
    - `{Object} entity`
  - returns `polygon`

## DC.Billboard

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let billboard = new DC.Billboard(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  - Parameters
    - `{Position} position`
    - `{String} icon`
  - returns `billboard`

### properties

- `{Position} position`
- `{String} icon`
- `{Array<Number>} size`: [width,height]

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [BillboardGraphics](http://resource.dvgis.cn/cesium-docs/BillboardGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "heightReference": 0,
  "scale": 1,
  "pixelOffset": { "x": 0, "y": 0 },
  "rotation": 0,
  "translucencyByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "scaleByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "disableDepthTestDistance": 0
}
```

- **_fromEntity(entity)_**

  - Parameters
    - `{Object} entity`：
  - returns `billboard`

## DC.Label

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let Label = new DC.Label(position, 'test')
```

### creation

- **_constructor(position,text)_**

  - Parameters
    - `{Position} position`
    - `{String} text`
  - returns `label`

### properties

- `{Position} position`
- `{String} text`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [LabelGraphics](http://resource.dvgis.cn/cesium-docs/LabelGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "font": "30px sans-serif",
  "scale": 1,
  "pixelOffset": { "x": 0, "y": 0 },
  "heightReference": 0,
  "showBackground": false,
  "backgroundColor": DC.Color.BLACK,
  "backgroundPadding": { "x": 0, "y": 0 },
  "fillColor": DC.Color.BLACK,
  "outlineColor": DC.Color.WHITE,
  "outlineWidth": 0,
  "scaleByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "translucencyByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "disableDepthTestDistance": 0
}
```

- **_fromEntity(entity,text)_**

  - Parameters
    - `{Object} entity`
    - `{String} text`
  - returns `label`

## DC.Circle

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let circle = new DC.Circle(position, 200)
```

### creation

- **_constructor(center, radius)_**

  - Parameters
    - `{Position} center`
    - `{String} radius`
  - returns `billboard`

### properties

- `{Position} center`
- `{String} radius`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [EllipseGraphics](http://resource.dvgis.cn/cesium-docs/EllipseGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "height": 1,
  "heightReference": 0,
  "extrudedHeight": 0,
  "rotation": 0,
  "stRotation": 0,
  "fill": true, s
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "classificationType": 2,
  "zIndex": 0
}
```

## DC.Rectangle

> 矩形要素，继承于[Overlay](#overlay)

### example

```js
let rectangle = new DC.Rectangle('-90.0,32.0;-94.0,36.0;')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `rectangle`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[RectangleGraphics](http://resource.dvgis.cn/cesium-docs/RectangleGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "height": 1, //高度
  "heightReference": 0, //高度参照，0：位置无参照，位置是绝对的，1：位置固定在地形上 2：位置高度是指地形上方的高度。
  "extrudedHeight": 0, //拉升高度
  "rotation": 0, //顺时针旋转角度
  "stRotation": 0, //逆时针旋转角度
  "fill": true, //是否用提供的材料填充多边形。
  "material": DC.Color.WHITE, //材质
  "outline": false, //是否显示边框
  "outlineColor": DC.Color.BLACK, //边框颜色
  "outlineWidth": 0, //边框宽度
  "shadows": 0, //阴影类型，0：禁用、1：启用 、2：投射、3：接受
  "distanceDisplayCondition": {
    "near": 0, //最近距离
    "far": Number.MAX_VALUE //最远距离
  }, //根据距离设置可见
  "classificationType": 2, //分类 是否影响地形，3D切片或同时影响这两者。0:地形、1:3D切片、2：两者
  "zIndex": 0 //层级
}
```

## DC.Wall

> 墙体要素，继承于[Overlay](#overlay)

### example

```js
let wall = new DC.Wall('-90.0,32.0,1000;-94.0,36.0,1000;')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `wall`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[WallGraphics](http://resource.dvgis.cn/cesium-docs/WallGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "fill": true, //是否用提供的材料填充多边形。
  "material": DC.Color.WHITE, //材质
  "outline": false, //是否显示边框
  "outlineColor": DC.Color.BLACK, //边框颜色
  "outlineWidth": 0, //边框宽度
  "shadows": 0, //阴影类型，0：禁用、1：启用 、2：投射、3：接受
  "distanceDisplayCondition": {
    "near": 0, //最近距离
    "far": Number.MAX_VALUE //最远距离
  }, //根据距离设置可见
  "classificationType": 2 //分类 是否影响地形，3D切片或同时影响这两者。0:地形、1:3D切片、2：两者
}
```

- **_fromEntity(entity)_**

  Entity 转换为 Overlay

  - Parameters
    - `{Object} entity`：Cesium 覆盖物
  - returns `wall`

## DC.Model

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let model = new DC.Model(position, '**/**.glb')
```

### creation

- **_constructor(position, modelUrl)_**

  - Parameters
    - `{Position|String|Array} position`
    - `{String} modelUrl`
  - returns `model`

### properties

- `{Position} position`
- `{String} modelUrl`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [ModelGraphics](http://resource.dvgis.cn/cesium-docs/ModelGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "scale": 1,
  "minimumPixelSize": 0,
  "maximumScale": 0,
  "heightReference": 0,
  "shadows": 0,
  "silhouetteColor": DC.Color.RED,
  "silhouetteSize": 0,
  "lightColor": DC.Color.RED,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

- **_fromEntity(entity,modelUrl)_**

  - Parameters
    - `{Object} entity`
    - `{String} modelUrl`
  - returns `model`

## DC.Tileset

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let tileset = new DC.Tileset('**/tileset.json')
tileset.setPosition(position)
```

### creation

- **_constructor(url,[options])_**

  - Parameters
    - `{String} url`
    - `{Object} options` [Tileset](http://resource.dvgis.cn/cesium-docs/Cesium3DTileset.html)
  - returns `tileset`

### properties

-`{Promise} readyPromise`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [TileStyle](https://github.com/CesiumGS/3d-tiles/tree/master/specification/Styling)
  - returns `this`

  ```js
  let style = new DC.TilesetStyle({
    color: {
      conditions: [
        ['${Height} >= 100', 'color("purple", 0.5)'],
        ['${Height} >= 50', 'color("red")'],
        ['true', 'color("blue")'],
      ],
    },
    show: '${Height} > 0',
  })
  ```

- **_setPosition(position)_**

  - Parameters
    - `{Position|Array|String} position`
  - returns `this`

- **_setHeight(height,isAbsolute)_**

  - Parameters
    - `{Number} height`
    - `{Boolean} isAbsolute`
  - returns `this`

- **_setCustomShader(customShader)_**

  - Parameters
    - `{String} customShader`
  - returns `this`

- **_setProperties(properties)_**

  - Parameters
    - `{Array<Object>} properties`
  - returns `this`

```json
{
  "key": "name",
  "keyValue": "1",
  "propertyName": "highlight",
  "propertyValue": true
}
```

## DC.DivIcon

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let divIcon = new DC.DivIcon(position, '<div></div>')
```

### creation

- **_constructor(position, content)_**

  - Parameters
    - `{Position|String|Array} position`
    - `{String|Element} content`
  - returns `divIcon`

### properties

- `{Position|String|Array} position`
- `{String|Element} content` **_`writeonly`_**

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style`
  - returns `this`

```json
// style(optional)
{
  "className": "test",
  "scaleByDistance": {
    "near": 0,
    "nearValue": 0,
    "far": 1,
    "farValue": 0
  },
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

- **_fromEntity(entity,content)_**

  - Parameters
    - `{Object} entity`
    - `{String|Element} content`
  - returns `divIcon`

## DC.Box

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let box = new DC.Box(position, 20, 30, 40)
```

### creation

- **_constructor(position, length, width, height)_**

  - Parameters
    - `{Position} position`
    - `{Number} length`
    - `{Number} width`
    - `{Number} height`
  - returns `box`

### properties

- `{Position} position`
- `{Number} length`
- `{Number} width`
- `{Number} height`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [BoxGraphics](http://resource.dvgis.cn/cesium-docs/BoxGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "heightReference": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

## DC.Corridor

> Inherited from [Overlay](#overlay)

### example

```js
let corridor = new DC.Corridor('120,20;120,30')
corridor.setStyle({
  width: 10,
})
```

### creation

- **_constructor(positions)_**

  - Parameters
    - `{String|Array<Position|Number|String>} positions`
  - returns `corridor`

### properties

- `{String|Array<Position|Number|String>} positions`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [CorridorGraphics](http://resource.dvgis.cn/cesium-docs/CorridorGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "width": 1,
  "height": 0,
  "heightReference": 0,
  "cornerType": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "classificationType": 2,
  "zIndex": 0
}
```

- **_fromEntity(entity)_**

  - Parameters
    - `{Object} entity`
  - returns `corridor`

## DC.Cylinder

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let cylinder = new DC.Cylinder(position, 20, 30, 40)
```

### creation

- **_constructor(position, length, topRadius, bottomRadius)_**

  - Parameters
    - `{Position} position`
    - `{Number} length`
    - `{Number} topRadius`
    - `{Number} bottomRadius`
  - returns `cylinder`

### properties

- `{Position} position`
- `{Number} length`
- `{Number} topRadius`
- `{Number} bottomRadius`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [CylinderGraphics](http://resource.dvgis.cn/cesium-docs/CylinderGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "heightReference": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

## DC.Ellipse

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let ellipse = new DC.Ellipse(position, 20, 30)
```

### creation

- **_constructor(position, semiMajorAxis, semiMinorAxis)_**

  - Parameters
    - `{Position} position`
    - `{Number} semiMajorAxis`
    - `{Number} semiMinorAxis`
  - returns `ellipse`

### properties

-`{Position} position`

- `{Number} semiMajorAxis`
- `{Number} semiMinorAxis`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [EllipseGraphics](http://resource.dvgis.cn/cesium-docs/EllipseGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "height": 1,
  "heightReference": 0,
  "extrudedHeight": 0,
  "rotation": 0,
  "stRotation": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  },
  "classificationType": 2,
  "zIndex": 0
}
```

## DC.Ellipsoid

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let ellipsoid = new DC.Ellipsoid(position, { x: 30, y: 30, z: 30 })
```

### creation

- **_constructor(position, radius)_**

  - Parameters
    - `{Position} position`
    - `{Object} radius`：{x: 30, y: 30, z: 30}
  - returns `ellipsoid`

### properties

-`{Position} position`

- `{Object} radius`：{x: 30, y: 30, z: 30}

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [EllipsoidGraphics](http://resource.dvgis.cn/cesium-docs/EllipsoidGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "heightReference": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

## DC.Plane

> Inherited from [Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let plane = new DC.Plane(position, 20, 30, { normal: 'x' })
```

### creation

- **_constructor(position, width, height, direction)_**

  - Parameters
    - `{Position} position`
    - `{Number} width`
    - `{Number} height`
    - `{Object} plane`
  - returns `plane`

```json
// plane
{
  "normal": "x",
  "distance": 0
}
```

### properties

- `{Position} position`
- `{Number} width`
- `{Number} height`
- `{Number} distance`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [PlaneGraphics](http://resource.dvgis.cn/cesium-docs/PlaneGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

## DC.PolylineVolume

> Inherited from [Overlay](#overlay)

### example

```js
function computeCircle(radius) {
  var positions = []
  for (var i = 0; i < 360; i++) {
    var radians = DC.Math.toRadians(i)
    positions.push({
      x: radius * Math.cos(radians),
      y: radius * Math.sin(radians),
    })
  }
  return positions
}

let polylineVolume = new DC.PolylineVolume(
  '-90.0,32.0,0.0;-90.0,36.0,100000.0;-94.0,36.0,0.0;',
  computeCircle(60000)
)
```

### creation

- **_constructor(positions, shape)_**

  - Parameters
    - `{String|Array<Position|Number|String>} positions`
    - `{Array} shape`
  - returns `polylineVolume`

### properties

- `{String|Array<Position|Number|String>} positions`
- `{Array} shape`

### methods

- **_setStyle(style)_**

  - Parameters
    - `{Object} style` [PolylineVolumeGraphics](http://resource.dvgis.cn/cesium-docs/PolylineVolumeGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "cornerType": 0,
  "fill": true,
  "material": DC.Color.WHITE,
  "outline": false,
  "outlineColor": DC.Color.BLACK,
  "outlineWidth": 0,
  "shadows": 0,
  "distanceDisplayCondition": {
    "near": 0,
    "far": Number.MAX_VALUE
  }
}
```

- **_fromEntity(entity)_**

  - Parameters
    - `{Object} entity`
  - returns `polylineVolume`

## DC.AttackArrow

> 攻击箭头要素，继承于[Overlay](#overlay)

### example

```js
let attackArrow = new DC.AttackArrow('-90.0,32.0;-94.0,36.0;-94.0,38.0')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `attackArrow`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[Polygon](../dc-sdk/#dc-polygon)
  - returns `this`

## DC.DoubleArrow

> 双箭头要素，继承于[Overlay](#overlay)

### example

```js
let doubleArrow = new DC.DoubleArrow('-90.0,32.0;-94.0,36.0;-94.0,38.0')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `doubleArrow`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[Polygon](../dc-sdk/#dc-polygon)
  - returns `this`

## DC.FineArrow

> 直箭头要素，继承于[Overlay](#overlay)

### example

```js
let fineArrow = new DC.FineArrow('-90.0,32.0;-94.0,36.0')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `fineArrow`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[Polygon](../dc-sdk/#dc-polygon)
  - returns `this`

## DC.GatheringPlace

> 聚集地要素，继承于[Overlay](#overlay)

### example

```js
let gatheringPlace = new DC.GatheringPlace('-90.0,32.0;-94.0,36.0')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `gatheringPlace`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[Polygon](../dc-sdk/#dc-polygon)
  - returns `this`

## DC.TailedAttackArrow

> 聚集地要素，继承于[Overlay](#overlay)

### example

```js
let tailedAttackArrow = new DC.TailedAttackArrow('-90.0,32.0;-94.0,36.0')
```

### creation

- **_constructor(positions)_**

  构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `tailedAttackArrow`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[Polygon](../dc-sdk/#dc-polygon)
  - returns `this`

## DC.ElecEllipsoidPrimitive

> 电弧球图元，继承于[Overlay](#overlay)

### example

```js
let elecEllipsoid = new DC.ElecEllipsoidPrimitive('120,20',{x:2000,y:2000:z:2000})
```

### creation

- **_constructor(center,radius)_**

  DC.WaterPrimitive 构造函数

  - Parameters
    - `{String|Position|Array} center`：中心点
    - `{Object} radius`:球半径
  - returns `elecEllipsoidPrimitive`

### properties

- `{String|Position|Array} center`：中心点,
- `{Object} radius`:球半径

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式
  - returns `this`

```json
// style(optional)
{
  "speed": 5, //速度
  "color": DC.Color.WHITE //颜色
}
```

## DC.FlowLinePrimitive

> 流动线图元，继承于[Overlay](#overlay)

### example

```js
let flowLinePrimitive = new DC.FlowLinePrimitive('120,20;120,30;122,30')
```

### creation

- **_constructor(positions,[asynchronous])_**

  DC.FlowLinePrimitive 构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `flowLinePrimitive`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式
  - returns `this`

```json
// style(optional)
{
  "speed": 5, //速度
  "color": DC.Color.WHITE, //颜色
  "percent": 0.3, // 比例
  "gradient": 0.1 // 透明程度
}
```

## DC.ScanCirclePrimitive

> 扫描圆图元，继承于[Overlay](#overlay)

### example

```js
let scanCirclePrimitive = new DC.ScanCirclePrimitive('120,20', 1000)
```

### creation

- **_constructor(position,radius)_**

  DC.ScanCirclePrimitive 构造函数

  - Parameters
    - `{String|Position|Array} position`：圆心
    - `{Number} radius`：半径
  - returns `scanCirclePrimitive`

### properties

- `{String|Position|Array} position`：圆心
- `{Number} radius`：半径

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式
  - returns `this`

```json
// style(optional)
{
  "speed": 5, //速度
  "color": DC.Color.WHITE //颜色
}
```

## DC.TrailLinePrimitive

> 轨迹线图元，继承于[Overlay](#overlay)

### example

```js
let trailLinePrimitive = new DC.TrailLinePrimitive('120,20;120,30;122,30')
```

### creation

- **_constructor(positions,[asynchronous])_**

  DC.TrailLinePrimitive 构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `trailLinePrimitive`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式
  - returns `this`

```json
// style(optional)
{
  "speed": 5, //速度
  "color": DC.Color.WHITE //颜色
}
```

## DC.WaterPrimitive

> 水面图元，继承于[Overlay](#overlay)

### example

```js
let waterPrimitive = new DC.WaterPrimitive('120,20;120,30;122,30')
water.setStyle({
  baseWaterColor: DC.Color.AQUA.withAlpha(0.3),
  normalMap: 'examples/images/icon/waterNormalsSmall.jpg',
  frequency: 1000.0,
  animationSpeed: 0.01,
  amplitude: 10,
  specularIntensity: 10,
})
```

### creation

- **_constructor(positions,[asynchronous])_**

  DC.WaterPrimitive 构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
    - `{Boolean} asynchronous`:异步创建，默认值：true
  - returns `waterPrimitive`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setStyle(style)_**

  设置样式

  - Parameters
    - `{Object} style`：样式，详情参考：[PolygonGraphics](http://resource.dvgis.cn/cesium-docs/PolygonGraphics.html)
  - returns `this`

```json
// style(optional)
{
  "height": 1, //高度
  "extrudedHeight": 0, //拉升高度
  "stRotation": 0, //旋转角度
  "outline": false, //是否显示边框
  "closeTop": true, //顶面是否闭合
  "closeBottom": true, //底面是否闭合
  "classificationType": 2, //分类 是否影响地形，3D切片或同时影响这两者。0:地形、1:3D切片、2：两者
  "baseWaterColor": DC.Color.WHITE, // 水体颜色
  "blendColor": DC.Color.WHITE, // 混合颜色
  "specularMap": "", // 镜面图
  "normalMap": "", // 法线图
  "frequency": 1000, //波纹数量
  "animationSpeed": 0.03, // 动画速度
  "amplitude": 10, //水波振幅
  "specularIntensity": 10 //镜面反射强度
}
```

## DC.VideoPrimitive

> 视频图元，继承于[Overlay](#overlay)

### example

```js
let videoEl = new document.getElementById('video')
let waterPrimitive = new DC.VideoPrimitive('120,20;120,30;122,30', videoEl)
```

### creation

- **_constructor(positions,video)_**

  DC.WaterPrimitive 构造函数

  - Parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
    - `{Element} video`：视频节点
  - returns `polygon`

### properties

- `{String|Array<Position|Number|String>} positions`：坐标串
- `{Element} video`：视频节点
