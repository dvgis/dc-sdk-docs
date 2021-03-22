---
sidebar: auto
---

# Effects 🌎

Add dynamic elements to the 3D scene to allow the scene to move and run more closely to the real world

## DC.Weather

### example

```js
let weather = new DC.Weather()
viewer.use(weather)
```

### creation

- **_constructor()_**

  - Returns `weather`

### properties

- [`{Rain} rain`](#rain)**_`readonly`_**
- [`{Snow} snow`](#snow) **_`readonly`_**
- [`{Fog} snow`](#fog) **_`readonly`_**
- [`{Cloud} cloud`](#cloud) **_`readonly`_**

## Rain

### example

```js
viewer.weather.rain.enable = true
viewer.weather.rain.speed = 2
```

### properties

- `{Boolean} enable`
- `{Number} speed`

## Snow

### example

```js
viewer.weather.snow.enable = true
viewer.weather.snow.speed = 2
```

### properties

- `{Boolean} enable`
- `{Number} speed`

## Fog

### example

```js
viewer.weather.fog.enable = true
viewer.weather.fog.fogColor = DC.Color.BLACK
```

### properties

- `{Boolean} enable`
- `{Color} fogColor
- `{Object} fogByDistance`: { near: 10, nearValue: 0, far: 2000, farValue: 1.0 }

## Cloud

### example

```js
viewer.weather.cloud.enable = true
viewer.weather.cloud.rotateAmount = 0.02
```

### properties

- `{Boolean} enable`
- `{Number} rotateAmount`

## DC.Effect

### example

```js
let effect = new DC.Effect()
viewer.use(effect)
```

### creation

- **_constructor()_**

  - Returns `effect`

### properties

- [`{BlackAndWhite} blackAndWhite`](#blackandwhite) **_`readonly`_**
- [`{Bloom} bloom`](#bloom) **_`readonly`_**
- [`{Brightness} brightness`](#brightness)**_`readonly`_**
- [`{DepthOfField} depthOfField`](#depthoffield) **_`readonly`_**
- [`{LensFlare} lensFlare`](#lensflare) **_`readonly`_**
- [`{Night} night`](#night) **_`readonly`_**
- [`{Silhouette} silhouette`](#silhouette) **_`readonly`_**

## BlackAndWhite

### example

```js
viewer.effect.blackAndWhite.enable = true
```

### properties

- `{Boolean} enable`
- `{Number} gradations`
- `{Array} selected`

## Bloom

### example

```js
viewer.effect.bloom.enable = true
```

### properties

- `{Boolean} enable`
- `{Number} contrast`
- `{Number} brightness`
- `{Number} glowOnly`
- `{Number} delta`
- `{Number} sigma`
- `{Number} stepSize`
- `{Array} selected`

## Brightness

### example

```js
viewer.effect.brightness.enable = true
```

### properties

- `{Boolean} enable`
- `{Number} intensity`
- `{Array} selected`

## DepthOfField

### example

```js
viewer.effect.depthOfField.enable = true
```

### properties

- `{Boolean} enable`
- `{Number}} focalDistance`
- `{Number} delta`
- `{Number} sigma`
- `{Number} stepSize`
- `{Array} selected`

## LensFlare

### example

```js
viewer.effect.lensFlare.enable = true
```

### properties

- `{Boolean} enable`
- `{Number}} intensity`
- `{Number} distortion`
- `{Number} dirtAmount`
- `{Number} haloWidth`
- `{Array} selected`

## Night

### example

```js
viewer.effect.night.enable = true
```

### properties

- `{Boolean} enable`
- `{Array} selected`

## Silhouette

### example

```js
viewer.effect.silhouette.enable = true
```

### properties

- `{Boolean} enable`
- `{Color} color`
- `{Number} length`
- `{Array} selected`

## Animation

> Animation base class

:::warning
The class cannot be instantiated
:::

### methods

- **_start()_**

  - returns `this`

- **_stop()_**

  - returns `this`

## DC.AroundPoint

> Inherited from [Animation](#animation)

### example

```js
let aroundPoint = new DC.AroundPoint(viewer, '120.121, 31.12')
aroundPoint.start()
```

### creation

- **_constructor(viewer,position,[options])_**

  - parameters
    - `{Viewer} viewer`
    - `{Position|String|Array} position`
    - `{Object} options`
  - returns `aroundPoint`

```json
//options(optional)
{
  "heading": 0,
  "pitch": 0,
  "range": 0,
  "duration": 0,
  "callback": null,
  "context": null
}
```

## DC.AroundView

> Inherited from [Animation](#animation)

### example

```js
let aroundView = new DC.AroundView(viewer)
aroundView.start()
```

### creation

- **_constructor(viewer,options)_**

  - parameters
    - `{Viewer} viewer`
    - `{Object} options`
  - returns `aroundView`

```json
//options(optional)
{
  "heading": 0,
  "duration": 0,
  "callback": null,
  "context": null
}
```

## DC.CircleScan

> Inherited from [Animation](#animation)

### example

```js
let circleScan = new DC.CircleScan(viewer, '120, 20', 200)
circleScan.start()
```

### creation

- **_constructor(viewer,position,radius,[options])_**

  - parameters
    - `{Viewer} viewer`：场景
    - `{DC.Position} position`：位置
    - `{Number} radius`：半径
    - `{Object} options`：属性
  - returns `circleScan`

```json
//options(optional)
{
  "color": DC.Color.BLUE,
  "speed": 5
}
```

## DC.Flying

> Inherited from [Animation](#animation)

### example

```js
let flying = new DC.Flying(viewer)
flying.positions = ['121.234,21.212,0,-29', '121.435,21.212,0,-29']
circleScan.start()
```

### creation

- **_constructor(viewer,options)_**

  - parameters
    - `{Viewer} viewer`：场景
    - `{Object} options`：options
  - returns `flying`

```json
//options(optional)
{
  "loop": false,
  "dwellTime": 3,
  "callback": null
}
```

### properties

- `{Array} positions`
- `{Array} durations`: The flight interval of each point, when the length of the array is 1, each interval is the same, if not 1, the length must be equal to the length of the point

### methods

- **_start()_**

  - returns `this`

- **_pause()_**

  - returns `this`

- **_restore()_**

  - returns `this`

## DC.GlobeRotate

> Inherited from [Animation](#animation)

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

  - parameters
    - `{DC.Viewer} viewer`
    - `{Object} options`
  - returns `globeRotate`

```json
//options（optional）
{
  "speed": 12 * 1000,
  "duration": 0,
  "callback": null,
  "context": null
}
```

## DC.RadarScan

> Inherited from [Animation](#animation)

### example

```js
let radarScan = new DC.RadarScan(viewer, '120, 20', 200)
radarScan.start()
```

### creation

- **_constructor(viewer,position,radius,options)_**

  - parameters
    - `{Viewer} viewer`
    - `{DC.Position} position`
    - `{Number} radius`
    - `{Object} options`
  - returns `radarScan`

```json
//options(optional)
{
  "color": DC.Color.BLUE,
  "speed": 5
}
```

## DC.RoamingController

### example

```js
let rc = new DC.RoamingController(viewer)
```

### creation

- **_constructor(viewer)_**

  - parameters
    - `{Viewer} viewer`：3D 场景
  - returns `roamingController`

### properties

- `{JulianDate} startTime` **_`readonly`_**
- `{Object} roamingLayer` **_`readonly`_**

### methods

- **_setStartTime(startTime)_**

  - parameters
    - `{Date} startTime`
  - returns `this`

- **_play()_**

  - returns `this`

- **_pause()_**

  - returns `this`

- **_restore()_**

  - returns `this`

- **_changeSpeed(speed)_**

  - parameters
    - `{Number} speed`：速度
  - returns `this`

- **_addPath(path)_**

  - parameters
    - `{DC.RoamingPath} path`：路径
  - returns `this`

- **_getPath(id)_**

  - parameters
    - `{String} id`：唯一标识
  - returns `path`

- **_removePath(path)_**

  - parameters
    - `{RoamingPath} path`：路径
  - returns `path`

- **_clearPath()_**

  - returns `this`

- **_trackedPath(path, viewMode, viewOption)_**

  - parameters
    - `{RoamingPath} path`
    - `{String} viewMode`: FP: first view, TP: third view, TRACKED: tracking view, FREE: free view
    - `{String} viewOption`
  - returns `this`

```json
//options(optional)
{
  "alt": 0,
  "pitch": 0,
  "range": 1000
}
```

- **_releasePath(path)_**

  - parameters
    - `{RoamingPath} path`
  - returns `this`

- **_releaseCamera()_**

  - returns `this`

## DC.RoamingPath

### example

```js
let path = new DC.RoamingPath('path1', 20， (position,isLast) => {}, {
  showPath: true,
})
```

### creation

- **_constructor(id, duration, callback, [options])_**

  - parameters
    - `{String} id`
    - `{Number} duration`
    - `{Function} callback`
    - `{Object} options`
  - Returns `roamingPath`

```json
//options(optional)
{
  "showPath": false,
  "pathWidth": 1,
  "pathMaterial": DC.Color.ORANGE.withAlpha(0.8),
  "pathLeadTime": 1
}
```

### properties

- `{String} id` **_`readonly`_**
- `{String} state` **_`readonly`_**
- `{Date} startTime`
- `{String|Array<Position|Number|String>} positions`

### methods

- **_setMode(mode)_**

  - parameters
    - `{String} mode`：speed，distance
  - returns `this`

- **_setModel(modelUrl,style)_**

  - parameters
    - `{String} modelPath`
    - `{Object} style` [DC.Model](../overlay/#dc-model)
  - returns `this`

- **_setBillboard(icon,style)_**

  - parameters
    - `{String} icon`
    - `{Object} style` [DC.Billboard](../overlay#dc-billboard)
  - returns `this`

- **_setLabel(text,style)_**

  - parameters
    - `{String} text`
    - `{Object} style` [DC.label](../overlay/#dc-label)
  - returns `this`

- **_setPositions(positions)_** `deprecated`

  - parameters
    - `{String|Array<Position|Number|String>} positions`：坐标串
  - returns `this`
