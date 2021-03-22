---
sidebar: auto
---

# 效果动画 🌎

在三维场景中添加动态要素，让场景能够动起来，更加贴近真实世界的运行

## DC.Weather

> 天气效果

### example

```js
let weather = new DC.Weather()
viewer.use(weather)
```

### creation

- **_constructor()_**

  DC.Weather 构造函数

  - 返回值 `weather`

### properties

- [`{Rain} rain`](#rain)：雨天 **_`readonly`_**
- [`{Snow} snow`](#snow)：雪天 **_`readonly`_**
- [`{Fog} snow`](#fog)：雾天 **_`readonly`_**
- [`{Cloud} cloud`](#cloud)：云 **_`readonly`_**

## Rain

> 雨天效果

### example

```js
viewer.weather.rain.enable = true
viewer.weather.rain.speed = 2
```

### properties

- `{Boolean} enable`：是否启用
- `{Number} speed`：速度

## Snow

> 雪天效果

### example

```js
viewer.weather.snow.enable = true
viewer.weather.snow.speed = 2
```

### properties

- `{Boolean} enable`：是否启用
- `{Number} speed`：速度

## Fog

> 雾天效果

### example

```js
viewer.weather.fog.enable = true
viewer.weather.fog.fogColor = DC.Color.BLACK
```

### properties

- `{Boolean} enable`：是否启用
- `{Color} fogColor`：颜色，
- `{Object} fogByDistance`：距离可见，默认： { near: 10, nearValue: 0, far: 2000, farValue: 1.0 }

## Cloud

> 云效果

### example

```js
viewer.weather.cloud.enable = true
viewer.weather.cloud.rotateAmount = 0.02
```

### properties

- `{Boolean} enable`：是否启用
- `{Number} rotateAmount`：移动增量，可为负数

## DC.Effect

> 效果类

### example

```js
let effect = new DC.Effect()
viewer.use(effect)
```

### creation

- **_constructor()_**

  DC.Effect 效果函数

  - 返回值 `effect`

### properties

- [`{BlackAndWhite} blackAndWhite`](#blackandwhite)：黑白 **_`readonly`_**
- [`{Bloom} bloom`](#bloom)：泛光 **_`readonly`_**
- [`{Brightness} brightness`](#brightness)：明亮 **_`readonly`_**
- [`{DepthOfField} depthOfField`](#depthoffield)：景深 **_`readonly`_**
- [`{LensFlare} lensFlare`](#lensflare)：镜头耀斑 **_`readonly`_**
- [`{Night} night`](#night)：夜视 **_`readonly`_**
- [`{Silhouette} silhouette`](#silhouette)：描边 **_`readonly`_**

## BlackAndWhite

> 黑白效果

### example

```js
viewer.effect.blackAndWhite.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Number} gradations`：强度
- `{Array} selected`：设置后期作用的覆盖物

## Bloom

> 泛光效果

### example

```js
viewer.effect.bloom.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Number} contrast`：对比度
- `{Number} brightness`：亮度
- `{Number} glowOnly`：只发光
- `{Number} delta`：Delta
- `{Number} sigma`：Sigma
- `{Number} stepSize`：StepSize
- `{Array} selected`：设置后期作用的覆盖物

## Brightness

> 明亮效果

### example

```js
viewer.effect.brightness.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Number} intensity`：强度
- `{Array} selected`：设置后期作用的覆盖物

## DepthOfField

> 景深效果

### example

```js
viewer.effect.depthOfField.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Number}} focalDistance`：焦距
- `{Number} delta`：Delta
- `{Number} sigma`：Sigma
- `{Number} stepSize`：StepSize
- `{Array} selected`：设置后期作用的覆盖物

## LensFlare

> 镜头耀斑效果

### example

```js
viewer.effect.lensFlare.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Number}} intensity`：强度
- `{Number} distortion`：扭曲度
- `{Number} dirtAmount`：分散度
- `{Number} haloWidth`：光圈宽度
- `{Array} selected`：设置后期作用的覆盖物

## Night

> 夜视效果

### example

```js
viewer.effect.night.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Array} selected`：设置后期作用的覆盖物

## Silhouette

> 描边效果

### example

```js
viewer.effect.silhouette.enable = true
```

### properties

- `{Boolean} enable`：是否启用
- `{Color} color`：颜色
- `{Number} length`：长度
- `{Array} selected`：设置后期作用的覆盖物

## Animation

> 场景动画基类

:::warning
该类无法实例化
:::

### methods

- **_start()_**

  开始动画

  - 返回值 `this`

- **_stop()_**

  停止动画

  - 返回值 `this`

## DC.AroundPoint

> 点位环绕,继承于[Animation](#animation)

### example

```js
let aroundPoint = new DC.AroundPoint(viewer, '120.121, 31.12')
aroundPoint.start()
```

### creation

- **_constructor(viewer,position,[options])_**

  DC.AroundPoint 构造函数

  - 参数
    - `{Viewer} viewer`：3D 场景
    - `{Position|String|Array} position`：点位
    - `{Object} options`：options
  - 返回值 `aroundPoint`

```json
//options（optional）
{
  "heading": 0, //偏移角度
  "pitch": 0, //翻转角度
  "range": 0, //距离
  "duration": 0, //间隔，单位：秒,当此值大于0时，callback才会生效
  "callback": null, //完成回调函数
  "context": null //回调函数执行上下文
}
```

## DC.AroundView

> 相机环绕，继承于[Animation](#animation)

### example

```js
let aroundView = new DC.AroundView(viewer)
aroundView.start()
```

### creation

- **_constructor(viewer,[options])_**

  DC.AroundView 构造函数

  - 参数
    - `{Viewer} viewer`：3D 场景
    - `{Object} options`：options
  - 返回值 `aroundView`

```json
//options（optional）
{
  "heading": 0, //偏移角度
  "duration": 0, //间隔，单位：秒，当此值大于0时，callback才会生效
  "callback": null, //完成回调函数
  "context": null //回调函数执行上下文
}
```

## DC.CircleScan

> 扫描圈，继承于[Animation](#animation)

### example

```js
let circleScan = new DC.CircleScan(viewer, '120, 20', 200)
circleScan.start()
```

### creation

- **_constructor(viewer,position,radius,options)_**

  DC.CircleScan 构造函数

  - 参数
    - `{Viewer} viewer`：场景
    - `{DC.Position} position`：位置
    - `{Number} radius`：半径
    - `{Object} options`：属性
  - 返回值 `circleScan`

```json
// 属性参数（optional）
{
  "color": DC.Color.BLUE, // 颜色
  "speed": 5 // 速度
}
```

## DC.Flying

> 定点巡航，继承于[Animation](#animation)

### example

```js
let flying = new DC.Flying(viewer)
flying.positions = ['121.234,21.212,0,-29', '121.435,21.212,0,-29']
circleScan.start()
```

### creation

- **_constructor(viewer,[options])_**

  DC.Flying 构造函数

  - 参数
    - `{Viewer} viewer`：场景
    - `{Object} options`：options
  - 返回值 `flying`

```json
// 属性参数（optional）
{
  "loop": false, //是否循环,
  "dwellTime": 3, //驻留时间
  "callback": null //回调函数
}
```

### properties

- `{Array} positions`：点位
- `{Array} durations`：每个点位的飞行间隔时间，当数组长度为 1 时，每个间隔时间相同，如果不为 1 时，长度必须和点位长度相等

### methods

- **_start()_**

  开始动画

  - 返回值 `this`

- **_pause()_**

  暂停

  - 返回值 `this`

- **_restore()_**

  继续

  - 返回值 `this`

## DC.GlobeRotate

> 地球自转，继承于[Animation](#animation)

### example

```js
let globeRotate = new DC.GlobeRotate(viewer, {
  duration: 5,
  speed: 1000,
  callback: () => {},
})
globeRotate.start()
```

### creation

- **_constructor(viewer,[options])_**

  DC.GlobeRotate 构造函数

  - 参数
    - `{DC.Viewer} viewer`：3D 场景
    - `{Object} options`：options
  - 返回值 `globeRotate`

```json
//options（optional）
{
  "speed": 12 * 1000, //速度
  "duration": 0, //持续时间,当此值大于0时，callback才会生效
  "callback": null, //执行完成的回调函数
  "context": null //回调函数执行上下文
}
```

## DC.RadarScan

> 雷达扫描，继承于[Animation](#animation)

### example

```js
let radarScan = new DC.RadarScan(viewer, '120, 20', 200)
radarScan.start()
```

### creation

- **_constructor(viewer,position,radius,options)_**

  DC.RadarScan 构造函数

  - 参数
    - `{Viewer} viewer`：场景
    - `{DC.Position} position`：位置
    - `{Number} radius`：半径
    - `{Object} options`：属性
  - 返回值 `radarScan`

```json
// 属性参数（optional）
{
  "color": DC.Color.BLUE, // 颜色
  "speed": 5 // 速度
}
```

## DC.RoamingController

> 漫游控制

### example

```js
let rc = new DC.RoamingController(viewer)
```

### creation

- **_constructor(viewer)_**

  DC.RoamingController 构造函数

  - 参数
    - `{Viewer} viewer`：3D 场景
  - 返回值 `roamingController`

### properties

- `{JulianDate} startTime`：开始时间 **_`readonly`_**
- `{Object} roamingLayer`：漫游图层 **_`readonly`_**

### methods

- **_setStartTime(startTime)_**

  设置开始时间

  - 参数
    - `{Date} startTime`：开始时间
  - 返回值 `this`

- **_play()_**

  播放所有路径

  - 返回值 `this`

- **_pause()_**

  暂停所有路径

  - 返回值 `this`

- **_restore()_**

  继续播放所有路径

  - 返回值 `this`

- **_changeSpeed(speed)_**

  改变播放速度

  - 参数
    - `{Number} speed`：速度
  - 返回值 `this`

- **_addPath(path)_**

  添加路径

  - 参数
    - `{DC.RoamingPath} path`：路径
  - 返回值 `this`

- **_getPath(id)_**

  根据唯一标识获取路径

  - 参数
    - `{String} id`：唯一标识
  - 返回值 `path`

- **_removePath(path)_**

  移除路径

  - 参数
    - `{RoamingPath} path`：路径
  - 返回值 `path`

- **_clearPath()_**

  移除所有路径

  - 返回值 `this`

- **_trackedPath(path, viewMode, viewOption)_**

  跟踪某一条路径

  - 参数
    - `{RoamingPath} path`：路径
    - `{String} viewMode`：相机模式：FP:第一视角，TP：第三视角，TRACKED：跟踪视角，FREE：自由视角
    - `{String} viewOption`：配置信息
  - 返回值 `this`

```json
// 属性参数（optional）
{
  "alt": 0, // 高度
  "pitch": 0, // 俯仰角，第一视角有效
  "range": 1000 // 距离
}
```

- **_releasePath(path)_**

  取消跟踪某一条路径

  - 参数
    - `{RoamingPath} path`：路径
  - 返回值 `this`

- **_releaseCamera()_**

  释放相机

  - 返回值 `this`

## DC.RoamingPath

> 漫游路径

### example

```js
let path = new DC.RoamingPath('path1', 20， (position,isLast) => {}, {
  showPath: true,
})
```

### creation

- **_constructor(id, duration, [callback], [options])_**

  DC.RoamingPath 构造函数

  - 参数
    - `{String} id`：唯一标识
    - `{Number} duration`：间隔时间，单位：秒
    - `{Function} callback`：每一个点位到达回调函数，参数有：position(位置信息),isLast(是否为最后的点位)
    - `{Object} options`：options
  - 返回值 `roamingPath`

```json
//options（optional）
{
  "showPath": false, //显示路径
  "pathWidth": 1, //路径宽度
  "pathMaterial": DC.Color.ORANGE.withAlpha(0.8), //路径材质
  "pathLeadTime": 1 // 路径提前时间
}
```

### properties

- `{String} id`：唯一标识 **_`readonly`_**
- `{String} state`：状态 **_`readonly`_**
- `{Date} startTime`：开始时间，设置后会独立于控制器的开始时间
- `{String|Array<Position|Number|String>} positions`：坐标串

### methods

- **_setMode(mode)_**

  设置路径模式

  - 参数
    - `{String} mode`：模式，speed:匀速，distance:根据距离设置时间
  - 返回值 `this`

- **_setModel(modelUrl,style)_**

  设置模型

  - 参数
    - `{String} modelPath`：模型路径
    - `{Object} style`：样式，详情参考：[DC.Model](../dc-sdk/#dc-model)
  - 返回值 `this`

- **_setBillboard(icon,style)_**

  设置图标

  - 参数
    - `{String} icon`：图标路径
    - `{Object} style`：样式，参考：[DC.Billboard](../dc-sdk/#dc-billboard)
  - 返回值 `this`

- **_setLabel(text,style)_**

  设置文本

  - 参数
    - `{String} text`：文本
    - `{Object} style`：样式，参考：[DC.label](../dc-sdk/#dc-label)
  - 返回值 `this`

- **_setPositions(positions)_** `deprecated`

  设置坐标串

  - 参数
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - 返回值 `this`
