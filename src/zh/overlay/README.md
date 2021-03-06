---
sidebar: auto
---

# è¦çåç´  ð

ä¸ç»´åºæ¯éè¦ç»æé¨åï¼ ç¨æ°å­åè¡¨ç¤ºä¸åºæ¯ä¸­çä¸ä¸ªå®ä½åè®°å½å¶å®æ¶ç¶æ

## Overlay

> è¦çç©åºç±»

:::warning
è¯¥ç±»æ æ³å®ä¾å
:::

### properties

- `{String} overlayId`ï¼å¯ä¸æ è¯ **_`readonly`_**
- `{String} id`ï¼ä¸å¡å¯ä¸æ è¯
- `{Boolean} show`ï¼æ¯å¦æ¾ç¤º
- `{Object} attr`ï¼ä¸å¡å±æ§
- `{Array} contextMenu`ï¼è®¾ç½®å³å»èåï¼èåçåè°å½æ°åæ°ä¸º viewer,overlay
- `{String} state`ï¼è¦çç©ç¶æ **_`readonly`_**
- `{String} type`ï¼è¦çç©ç±»å **_`readonly`_**
- `{Boolean} allowDrillPicking`ï¼æ¯å¦å¯ä»¥ç©¿ééæ©ï¼é»è®¤ä¸º falseï¼å¦æä¸º true æ¶ï¼è¦çç©ä¸ºç©¿ééæ©å¶åé¢çææè¦çç©ï¼å¹¶è§¦åå¶åé¢çææè¦çç©çé¼ æ äºä»¶

### methods

- **_addTo(layer)_**

  æ·»å å°å¾å±

  - åæ°
    - `{Layer} layer` ï¼å¾å±
  - è¿åå¼ `this`

- **_remove()_**

  å é¤

  - è¿åå¼ `this`

- **_setLabel(text, textStyle)_**

  è®¾ç½®æ ç­¾

  - åæ°
    - `{String} text`ï¼ææ¬
    - `{String} textStyle`ï¼ææ¬æ ·å¼ï¼è¯¦æåèï¼[DC.Label](#dc-label)
  - è¿åå¼ `this`

- **_on(type, callback, context)_**

  äºä»¶è®¢é

  - åæ°
    - `{Object} type` ï¼è®¢éç±»å
    - `{Function} callback` ï¼è®¢éåè°
    - `{Object} context` ï¼ä¸ä¸æ
  - è¿åå¼ `this`

- **_off(type, callback, context)_**

  åæ¶äºä»¶è®¢é

  - åæ°
    - `{Object} type` ï¼è®¢éç±»å
    - `{Function} callback` ï¼è®¢éåè°
    - `{Object} context` ï¼ä¸ä¸æ
  - è¿åå¼ `this`

- **_fire(type,params)_**

  è§¦åäºä»¶

  - åæ°
    - `{Object} type` ï¼è®¢éç±»å
    - `{Object} params` ï¼åæ°
  - è¿åå¼ `this`

### static methods

- **_registerType(type)_**

  æ³¨åè¦çç©ç±»å

  - åæ°
    - `{String} type`ï¼è¦çç©ç±»å

- **_getOverlayType(type)_**

  è·åè¦çç©ç±»å

  - åæ°
    - `{String} type`ï¼è¦çç©ç±»å
  - è¿åå¼ `string`

## DC.Point

> ç¹ä½è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

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

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
  - è¿åå¼ `point`

### properties

- `{Position|String|Array|Object} position`ï¼åæ 

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PointGraphics](http://resource.dvgis.cn/cesium-docs/PointGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "pixelSize": 1, //åç´ å¤§å°
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "color": DC.Color.WHITE, //é¢è²
  "outlineColor": DC.Color.WHITE, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å¤§å°ï¼
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `point`

## DC.Polyline

> çº¿è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let polyline = new DC.Polyline('120,20;120,30')
polyline.setStyle({
  width: 10,
})
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `polyline`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
- `{DC.Position} center`ï¼ä¸­å¿ç¹ **_`readonly`_**
- `{Number} distance`ï¼è·ç¦»,åä½ï¼ç±³ **_`readonly`_**

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PolylineGraphics](http://resource.dvgis.cn/cesium-docs/PolylineGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "width": 1, //çº¿å®½
  "material": DC.Color.WHITE, //æè´¨
  "clampToGround": false, //æ¯å¦è´´å°
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `polyline`

## DC.Polygon

> é¢è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let polygon = new DC.Polygon('120,20;120,30;122,30')
polygon.setStyle({
  height: 10,
})
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object} positions`ï¼åæ ä¸²
  - è¿åå¼ `polygon`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
- `{String|Array<Position|Number|String|Object>} holes`ï¼æ´åæ ä¸²
- `{DC.Position} center`ï¼ä¸­å¿ç¹ **_`readonly`_**
- `{Number} area`ï¼è·ç¦»ï¼åä½ï¼å¹³æ¹ç±³ **_`readonly`_**

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PolygonGraphics](http://resource.dvgis.cn/cesium-docs/PolygonGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "height": 1, //é«åº¦
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "extrudedHeight": 0, //æåé«åº¦
  "stRotation": 0, //æè½¬è§åº¦
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "closeTop": true, //é¡¶é¢æ¯å¦é­å
  "closeBottom": true, //åºé¢æ¯å¦é­å
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `polygon`

## DC.Billboard

> å¾æ è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let billboard = new DC.Billboard(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String} icon`ï¼å¾æ å°å
  - è¿åå¼ `billboard`

### properties

- `{Position|String|Array|Object} position`ï¼åæ 
- `{String} icon`ï¼å¾æ å°å
- `{Array<Number>} size`ï¼å¾æ å¤§å°

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[BillboardGraphics](http://resource.dvgis.cn/cesium-docs/BillboardGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "rotation": 0, //æè½¬è§åº¦
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `billbard`

## DC.Label

> æ ç­¾è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let Label = new DC.Label(position, 'test')
```

### creation

- **_constructor(position,text)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String} text`ï¼ææ¬
  - è¿åå¼ `label`

### properties

- `{Position} position`ï¼åæ 
- `{String} text`ï¼ææ¬

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[LabelGraphics](http://resource.dvgis.cn/cesium-docs/LabelGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "font": "30px sans-serif", // CSS å­ä½è®¾ç½®
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "showBackground": false, //æ¯å¦æ¾ç¤ºèæ¯
  "backgroundColor": DC.Color.BLACK, //èæ¯é¢è²
  "backgroundPadding": { "x": 0, "y": 0 }, //èæ¯é´é
  "fillColor": DC.Color.BLACK, //æå­é¢è²
  "outlineColor": DC.Color.WHITE, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å¤§å°ï¼
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

- **_fromEntity(entity,text)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
    - `{String} text`ï¼ææ¬
  - è¿åå¼ `label`

## DC.Circle

> åè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let circle = new DC.Circle(position, 200)
```

### creation

- **_constructor(center, radius)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} center`ï¼åå¿
    - `{String} radius`ï¼åå¾
  - è¿åå¼ `billboard`

### properties

- `{Position} center`ï¼åå¿
- `{String} radius`ï¼åå¾

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[EllipseGraphics](http://resource.dvgis.cn/cesium-docs/EllipseGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "height": 1, //é«åº¦
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "extrudedHeight": 0, //æåé«åº¦
  "rotation": 0, //é¡ºæ¶éæè½¬è§åº¦
  "stRotation": 0, //éæ¶éæè½¬è§åº¦
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

## DC.Rectangle

> ç©å½¢è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let rectangle = new DC.Rectangle('-90.0,32.0;-94.0,36.0;')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String>} positions`ï¼åæ ä¸²
  - è¿åå¼ `rectangle`

### properties

- `{String|Array<Position|Number|String>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[RectangleGraphics](http://resource.dvgis.cn/cesium-docs/RectangleGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "height": 1, //é«åº¦
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "extrudedHeight": 0, //æåé«åº¦
  "rotation": 0, //é¡ºæ¶éæè½¬è§åº¦
  "stRotation": 0, //éæ¶éæè½¬è§åº¦
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

## DC.Wall

> å¢ä½è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let wall = new DC.Wall('-90.0,32.0,1000;-94.0,36.0,1000;')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String>} positions`ï¼åæ ä¸²
  - è¿åå¼ `wall`

### properties

- `{String|Array<Position|Number|String>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[WallGraphics](http://resource.dvgis.cn/cesium-docs/WallGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2 //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `wall`

## DC.Model

> æ¨¡åè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let model = new DC.Model(position, '**/**.glb')
```

### creation

- **_constructor(position, modelUrl)_**

  æé å½æ°

  - åæ°
    - ``{Position|String|Array|Object} position`ï¼åæ 
    - `{String} modelUrl`ï¼æ¨¡åå°å
  - è¿åå¼ `model`

### properties

- `{Position} position`ï¼åæ 
- `{String} modelUrl`ï¼æ¨¡åå°å

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[ModelGraphics](http://resource.dvgis.cn/cesium-docs/ModelGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "scale": 1, //æ¯ä¾
  "minimumPixelSize": 0, //æå®æ¨¡åçæå°åç´ å¤§å°ï¼èä¸èèç¼©æ¾
  "maximumScale": 0, //æå®æ¨¡åçæå¤§æ¯ä¾
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "silhouetteColor": DC.Color.RED, //è½®å»é¢è²
  "silhouetteSize": 0, //è½®å»å®½åº¦
  "lightColor": DC.Color.RED, //æ¨¡åçè²æ¶æå®ç¯åé¢è²
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

- **_fromEntity(entity,modelUrl)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
    - `{String} modelUrl`ï¼æ¨¡åå°å
  - è¿åå¼ `model`

## DC.Tileset

> 3Dtiles æ¨¡åè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let tileset = new DC.Tileset('**/tileset.json')
tileset.setPosition(position)
```

### creation

- **_constructor(url,[options])_**

  æé å½æ°

  - åæ°
    - `{String} url`ï¼æ¨¡åå°å
    - `{Object} options`ï¼è¯¦æåèï¼[Tileset](http://resource.dvgis.cn/cesium-docs/Cesium3DTileset.html)
  - è¿åå¼ `tileset`

### properties

- `{Promise} readyPromise`ï¼å è½½å®æåçå¼æ­¥å½æ° **_`readonly`_**

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[TileStyle](https://github.com/CesiumGS/3d-tiles/tree/master/specification/Styling)
  - è¿åå¼ `this`

  ```js
  let style = new DC.TilesetStyle({
    color: {
      conditions: [
        ['${Height} >= 100', 'color("purple", 0.5)'], //Height ä¸ºæ¨¡åè®¾ç½®çå±æ§
        ['${Height} >= 50', 'color("red")'],
        ['true', 'color("blue")'],
      ],
    },
    show: '${Height} > 0',
  })
  ```

- **_setPosition(position)_**

  è®¾ç½®ä½ç½®

  - åæ°
    - `{Position|String|Array|Object} position`ï¼ä½ç½®
  - è¿åå¼ `this`

- **_setHeadingPitchRoll(heading, pitch, roll)_**

  è®¾ç½®æ¹ä½è§

  - åæ°
    - `{Number} heading`ï¼åèªè§åº¦ï¼å¯è½å¶ä»æ¡æ¶ä½ yawï¼è¡¨ç¤ºç» Z è½´æè½¬ãé»è®¤ï¼0
    - `{Number} pitch`ï¼ä¿¯ä»°è§åº¦ï¼è¡¨ç¤ºç» Y è½´æè½¬ãé»è®¤ï¼0
    - `{Number} roll`ï¼ç¿»è½¬è§åº¦ï¼è¡¨ç¤ºç» X è½´æè½¬ãé»è®¤ï¼0
  - è¿åå¼ `this`

- **_setHeight(height,isAbsolute)_**

  è®¾ç½®é«åº¦

  - åæ°
    - `{Number} height`ï¼é«åº¦
    - `{Boolean} isAbsolute`ï¼æ¯å¦ä¸ºç»å¯¹é«åº¦ï¼å¦æä¸º trueï¼å°ä¸æ ¹æ®æ¨¡åä¸­å¿é«åº¦è®¡ç®
  - è¿åå¼ `this`

- **_setScale(scale)_**

  è®¾ç½®æ¯ä¾

  - åæ°
    - `{Number} scale`ï¼æ¯ä¾
  - è¿åå¼ `this`

- **_setCustomShader(customShader)_**

  è®¾ç½®èªå®ä¹çåçè²å¨

  - åæ°
    - `{String} customShader`ï¼çåçè²å¨
  - è¿åå¼ `this`

- **_setProperties(properties)_**

  æ ¹æ®ç°æçå±æ§æ·»å å±æ§

  - åæ°
    - `{Array<Object>} properties`: å±æ§
  - è¿åå¼ `this`

```json
//å±æ§åæ°
{
  "key": "name", //å·²æå±æ§åç§°
  "keyValue": "1", //å·²æå±æ§å¼
  "propertyName": "highlight", //æ°å¢å±æ§åç§°
  "propertyValue": true //æ°å¢å±æ§å¼
}
```

## DC.DivIcon

> DivIcon è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let divIcon = new DC.DivIcon(position, '<div></div>')
```

### creation

- **_constructor(position, content)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String|Element} content`ï¼åå®¹
  - è¿åå¼ `divIcon`

### properties

- `{Position|String|Array} position`ï¼åæ 
- `{String|Element} content`ï¼åå®¹ **_`writeonly`_**

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "className": "test", //æ ·å¼å
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

- **_fromEntity(entity,content)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
    - `{String|Element} content`ï¼åå®¹
  - è¿åå¼ `divIcon`

## DC.Box

> çè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let box = new DC.Box(position, 20, 30, 40)
```

### creation

- **_constructor(position, length, width, height)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{Number} length`ï¼é¿åº¦
    - `{Number} width`ï¼å®½åº¦
    - `{Number} height`ï¼é«åº¦
  - è¿åå¼ `box`

### properties

- `{Position} position`ï¼åæ 
- `{Number} length`ï¼é¿åº¦
- `{Number} width`ï¼å®½åº¦
- `{Number} height`ï¼é«åº¦

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[BoxGraphics](http://resource.dvgis.cn/cesium-docs/BoxGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.Corridor

> èµ°å»è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let corridor = new DC.Corridor('120,20;120,30')
corridor.setStyle({
  width: 10,
})
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `corridor`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[CorridorGraphics](http://resource.dvgis.cn/cesium-docs/CorridorGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "width": 1, //çº¿å®½
  "height": 0, //é«åº¦
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "cornerType": 0, //è½¬è§ç±»å«ï¼0ï¼åè§ã1ï¼ç´è§ã2ï¼æè§
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `corridor`

## DC.Cylinder

> åæ±è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let cylinder = new DC.Cylinder(position, 20, 30, 40)
```

### creation

- **_constructor(position, length, topRadius, bottomRadius)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{Number} length`ï¼é¿åº¦
    - `{Number} topRadius`ï¼ä¸åå¾
    - `{Number} bottomRadius`ï¼ä¸åå¾
  - è¿åå¼ `cylinder`

### properties

- `{Position} position`ï¼åæ 
- `{Number} length`ï¼é¿åº¦
- `{Number} topRadius`ï¼ä¸åå¾
- `{Number} bottomRadius`ï¼ä¸åå¾

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[CylinderGraphics](http://resource.dvgis.cn/cesium-docs/CylinderGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.Ellipse

> æ¤­åè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let ellipse = new DC.Ellipse(position, 20, 30)
```

### creation

- **_constructor(position, semiMajorAxis, semiMinorAxis)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{Number} semiMajorAxis`ï¼é¿åè½´
    - `{Number} semiMinorAxis`ï¼ç­åè½´
  - è¿åå¼ `ellipse`

### properties

- `{Position} position`ï¼åæ 
- `{Number} semiMajorAxis`ï¼é¿åè½´
- `{Number} semiMinorAxis`ï¼ç­åè½´

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[EllipseGraphics](http://resource.dvgis.cn/cesium-docs/EllipseGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "height": 1, //é«åº¦
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "extrudedHeight": 0, //æåé«åº¦
  "rotation": 0, //é¡ºæ¶éæè½¬è§åº¦
  "stRotation": 0, //éæ¶éæè½¬è§åº¦
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

## DC.Ellipsoid

> çä½è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let ellipsoid = new DC.Ellipsoid(position, { x: 30, y: 30, z: 30 })
```

### creation

- **_constructor(position, radius)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{Object} radius`ï¼åå¾ï¼æ ¼å¼æ¯ï¼{x: 30, y: 30, z: 30}
  - è¿åå¼ `ellipsoid`

### properties

- `{Position} position`ï¼åæ 
- `{Object} radius`ï¼åå¾ï¼æ ¼å¼æ¯ï¼{x: 30, y: 30, z: 30}

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[EllipsoidGraphics](http://resource.dvgis.cn/cesium-docs/EllipsoidGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.Plane

> å¹³é¢è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let plane = new DC.Plane(position, 20, 30, { normal: 'x' })
```

### creation

- **_constructor(position, width, height, direction)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{Number} width`ï¼å®½åº¦
    - `{Number} height`ï¼é«åº¦
    - `{Object} plane`ï¼é¢æ¿æ ¼å¼
  - è¿åå¼ `plane`

```json
// é¢æ¿åæ°(å¯é)
{
  "normal": "x", // æ³çº¿,x,y,zå¶ä¸­ä¸ä¸ª
  "distance": 0 // è·ç¦»
}
```

### properties

- `{Position} position`ï¼åæ 
- `{Number} width`ï¼å®½åº¦
- `{Number} height`ï¼é«åº¦
- `{Number} distance`ï¼è·ç¦»

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PlaneGraphics](http://resource.dvgis.cn/cesium-docs/PlaneGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.PolylineVolume

> ç®¡éè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

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

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
    - `{Array} shape`ï¼å½¢ç¶
  - è¿åå¼ `polylineVolume`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²
- `{Array} shape`ï¼å½¢ç¶

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PolylineVolumeGraphics](http://resource.dvgis.cn/cesium-docs/PolylineVolumeGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "cornerType": 0, //è½¬è§ç±»å«ï¼0ï¼åè§ã1ï¼ç´è§ã2ï¼æè§
  "fill": true, //æ¯å¦ç¨æä¾çææå¡«åå¤è¾¹å½¢ã
  "material": DC.Color.WHITE, //æè´¨
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "outlineColor": DC.Color.BLACK, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å®½åº¦
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

- **_fromEntity(entity)_**

  Entity è½¬æ¢ä¸º Overlay

  - åæ°
    - `{Object} entity`ï¼Cesium è¦çç©
  - è¿åå¼ `polylineVolume`

## DC.DynamicBillboard

> å¨æå¾æ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let billboard = new DC.DynamicBillboard(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String} icon`ï¼å¾æ å°å
  - è¿åå¼ `billboard`

### properties

- `{Position} position`ï¼åæ  **_`readonly`_**
- `{String} icon`ï¼å¾æ å°å
- `{Array<Number>} size`ï¼å¾æ å¤§å°

### methods

- **_addPosition(position,interval)_**

  æ·»å ç¹ä½

  - åæ°
    - `{Position|Array|String|Object} position`ï¼ç¹ä½
    - `{Number} interval`ï¼é´éï¼åä½ï¼ç§
  - è¿åå¼ `this`

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[BillboardGraphics](http://resource.dvgis.cn/cesium-docs/BillboardGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "rotation": 0, //æè½¬è§åº¦
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

## DC.DynamicModel

> å¨ææ¨¡åè¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let model = new DC.DynamicModel(position, '**/**.glb')
```

### creation

- **_constructor(position, modelUrl)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String} modelUrl`ï¼æ¨¡åå°å
  - è¿åå¼ `model`

### properties

- `{Position} position`ï¼åæ  **_`readonly`_**
- `{String} modelUrl`ï¼æ¨¡åå°å

### methods

- **_addPosition(position,interval)_**

  æ·»å ç¹ä½

  - åæ°
    - `{Position|Array|String|Object} position`ï¼ç¹ä½
    - `{Number} interval`ï¼é´éï¼åä½ï¼ç§
  - è¿åå¼ `this`

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[ModelGraphics](http://resource.dvgis.cn/cesium-docs/ModelGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "scale": 1, //æ¯ä¾
  "minimumPixelSize": 0, //æå®æ¨¡åçæå°åç´ å¤§å°ï¼èä¸èèç¼©æ¾
  "maximumScale": 0, //æå®æ¨¡åçæå¤§æ¯ä¾
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "silhouetteColor": DC.Color.RED, //è½®å»é¢è²
  "silhouetteSize": 0, //è½®å»å®½åº¦
  "lightColor": DC.Color.RED, //æ¨¡åçè²æ¶æå®ç¯åé¢è²
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.CustomBillboard

> èªå®ä¹å¾æ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let billboard = new DC.CustomBillboard(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String} icon`ï¼å¾æ å°å
  - è¿åå¼ `billboard`

### properties

- `{Position} position`ï¼åæ 
- `{String} icon`ï¼å¾æ å°å
- `{Array<Number>} size`ï¼å¾æ å¤§å°

### methods

- **_setVLine(style)_**

  è®¾ç½®åç´çº¿

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PolylineGraphics](http://resource.dvgis.cn/cesium-docs/PolylineGraphics.html)
  - è¿åå¼ `this`

- **_setBottomCircle(radius,style,rotateAmount)_**

  è®¾ç½®åºå

  - åæ°
    - `{Number} radius`ï¼åå¾
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[EllipseGraphics](http://resource.dvgis.cn/cesium-docs/EllipseGraphics.html)
    - `{Number} rotateAmount`ï¼æè½¬é
  - è¿åå¼ `this`

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[BillboardGraphics](http://resource.dvgis.cn/cesium-docs/BillboardGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "rotation": 0, //æè½¬è§åº¦
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

## DC.CustomLabel

> èªå®ä¹ææ¬ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let label = new DC.CustomLabel(position, 'test')
```

### creation

- **_constructor(position,text)_**

  æé å½æ°

  - åæ°
    - `{Position|String|Array|Object} position`ï¼åæ 
    - `{String} text`ï¼ææ¬
  - è¿åå¼ `label`

### properties

- `{Position} position`ï¼åæ 
- `{String} text`ï¼ææ¬

### methods

- **_setVLine(style)_**

  è®¾ç½®åç´çº¿

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PolylineGraphics](http://resource.dvgis.cn/cesium-docs/PolylineGraphics.html)
  - è¿åå¼ `this`

- **_setBottomCircle(radius,style,rotateAmount)_**

  è®¾ç½®åºå

  - åæ°
    - `{Number} radius`ï¼åå¾
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[EllipseGraphics](http://resource.dvgis.cn/cesium-docs/EllipseGraphics.html)
    - `{Number} rotateAmount`ï¼æè½¬é
  - è¿åå¼ `this`

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[LabelGraphics](http://resource.dvgis.cn/cesium-docs/LabelGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "rotation": 0, //æè½¬è§åº¦
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

## DC.AttackArrow

> æ»å»ç®­å¤´è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let attackArrow = new DC.AttackArrow('-90.0,32.0;-94.0,36.0;-94.0,38.0')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `attackArrow`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Polygon](#dc-polygon)
  - è¿åå¼ `this`

## DC.DoubleArrow

> åç®­å¤´è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let doubleArrow = new DC.DoubleArrow('-90.0,32.0;-94.0,36.0;-94.0,38.0')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `doubleArrow`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Polygon](#dc-polygon)
  - è¿åå¼ `this`

## DC.FineArrow

> ç´ç®­å¤´è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let fineArrow = new DC.FineArrow('-90.0,32.0;-94.0,36.0')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `fineArrow`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Polygon](#dc-polygon)
  - è¿åå¼ `this`

## DC.GatheringPlace

> èéå°è¦ç´ ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let gatheringPlace = new DC.GatheringPlace('-90.0,32.0;-94.0,36.0')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `gatheringPlace`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Polygon](#dc-polygon)
  - è¿åå¼ `this`

## DC.TailedAttackArrow

> èéå°ï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let tailedAttackArrow = new DC.TailedAttackArrow('-90.0,32.0;-94.0,36.0')
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `tailedAttackArrow`

### properties

- `{Array<Position>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Polygon](#dc-polygon)
  - è¿åå¼ `this`

## DC.BillboardPrimitive

> å¾æ å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let billboard = new DC.BillboardPrimitive(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{String} icon`ï¼å¾æ å°å
  - è¿åå¼ `billboard`

### properties

- `{Position} position`ï¼åæ 
- `{String} icon`ï¼å¾æ å°å
- `{Array<Number>} size`ï¼å¾æ å¤§å°

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Billboard](http://resource.dvgis.cn/cesium-docs/Billboard.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "rotation": 0, //æè½¬è§åº¦
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

## DC.BounceBillboardPrimitive

> è·³å¨å¾æ å¾åï¼ç»§æ¿äº[BillboardPrimitive](#dc-billboardprimitive)

### example

```js
let position = new DC.Position(120, 20)
let billboard = new DC.BounceBillboardPrimitive(position, '***/**.png')
billboard.size = [20, 20]
```

### creation

- **_constructor(position,icon)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{String} icon`ï¼å¾æ å°å
  - è¿åå¼ `billboard`

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Billboard](http://resource.dvgis.cn/cesium-docs/Billboard.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "maxOffsetY": 10, //åç´æ¹åæå¤§å¹³ç§»é
  "offsetAmount": 0.1 //åç´æ¹åæ¯å¸§å¹³ç§»é
  // å¶ä»æ ·å¼åè BillboardPrimitive æ ·å¼
}
```

## DC.DiffuseWallPrimitive

> æ©æ£å¢å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let wall = new DC.DiffuseWallPrimitive(position, 2000, 1000)
```

### creation

- **_constructor(center, radius, height)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} center`ï¼åå¿
    - `{Number} radius`ï¼åå¾
    - `{Number} height`ï¼é«åº¦
  - è¿åå¼ `wall`

### properties

- `{Position|Number|String|Object} center`ï¼åå¿
- `{Number} radius`ï¼åå¾
- `{Number} height`ï¼é«åº¦

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "minRadius": 10, // å¨ç»æå°åå¾
  "minHeight": 30, // å¨ç»æå°é«åº¦
  "color": DC.Color.RED, // å¢ä½é¢è²
  "slices": 128, //è¾¹æ°
  "speed": 10 //éåº¦
}
```

## DC.ElecEllipsoidPrimitive

> çµå¼§çå¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let elecEllipsoid = new DC.ElecEllipsoidPrimitive('120,20',{x:2000,y:2000:z:2000})
```

### creation

- **_constructor(center,radius)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} center`ï¼çå¿
    - `{Object} radius`:çåå¾
  - è¿åå¼ `elecEllipsoid`

### properties

- `{Position|Number|String|Object} center`ï¼çå¿
- `{Object} radius`:çåå¾

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "speed": 5, //éåº¦
  "color": DC.Color.WHITE //é¢è²
}
```

## DC.FlowLinePrimitive

> æµå¨çº¿å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let flowLinePrimitive = new DC.FlowLinePrimitive('120,20;120,30;122,30')
```

### creation

- **_constructor(positions,[asynchronous])_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `flowLine`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "speed": 5, //éåº¦
  "color": DC.Color.WHITE, //é¢è²
  "percent": 0.3, // æ¯ä¾
  "gradient": 0.1 // éæç¨åº¦
}
```

## DC.LabelPrimitive

> æ ç­¾å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let Label = new DC.LabelPrimitive(position, 'test')
```

### creation

- **_constructor(position,text)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{String} text`ï¼ææ¬
  - è¿åå¼ `label`

### properties

- `{Position|Number|String|Object} position`ï¼åæ 
- `{String} text`ï¼ææ¬

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Label](http://resource.dvgis.cn/cesium-docs/Label.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "font": "30px sans-serif", // CSS å­ä½è®¾ç½®
  "scale": 1, //æ¯ä¾
  "pixelOffset": { "x": 0, "y": 0 }, //åç§»åç´ 
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "showBackground": false, //æ¯å¦æ¾ç¤ºèæ¯
  "backgroundColor": DC.Color.BLACK, //èæ¯é¢è²
  "backgroundPadding": { "x": 0, "y": 0 }, //èæ¯é´é
  "fillColor": DC.Color.BLACK, //æå­é¢è²
  "outlineColor": DC.Color.WHITE, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å¤§å°ï¼
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

## DC.BounceLabelPrimitive

> è·³å¨ææ¬å¾åï¼ç»§æ¿äº[LabelPrimitive](#dc-labelprimitive)

### example

```js
let position = new DC.Position(120, 20)
let label = new DC.BounceLabelPrimitive(position, 'test')
```

### creation

- **_constructor(position,text)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{String} text`ï¼ææ¬
  - è¿åå¼ `label`

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Label](http://resource.dvgis.cn/cesium-docs/Label.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "maxOffsetY": 10, //åç´æ¹åæå¤§å¹³ç§»é
  "offsetAmount": 0.1 //åç´æ¹åæ¯å¸§å¹³ç§»é
  // å¶ä»æ ·å¼åè LabelPrimitive æ ·å¼
}
```

## DC.ModelPrimitive

> æ¨¡åå¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let model = new DC.ModelPrimitive(position, '**/**.glb')
```

### creation

- **_constructor(position, modelUrl)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
    - `{String} modelUrl`ï¼æ¨¡åå°å
  - è¿åå¼ `model`

### properties

- `{Position|Number|String|Object} position`ï¼åæ 
- `{String} modelUrl`ï¼æ¨¡åå°å
- `{Promise} readyPromise`ï¼å è½½å®æåçå¼æ­¥å½æ° **_`readonly`_**

### methods

- **_getMaterial(name)_**

  è®¾ç½®æè´¨

  - åæ°
    - `{String} name`ï¼èç¹åç§°
  - è¿åå¼ `modelMaterial`

- **_getMesh(name)_**

  è·åä¸è§ç½

  - åæ°
    - `{String} name`ï¼èç¹åç§°
  - è¿åå¼ `modelMesh`

- **_getNode(name)_**

  è·åèç¹

  - åæ°
    - `{String} name`ï¼èç¹åç§°
  - è¿åå¼ `modelNode`

- **_getNodes()_**

  è·åææèç¹

  - è¿åå¼ `array<ModelNode>`

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Model](http://resource.dvgis.cn/cesium-docs/Model.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "scale": 1, //æ¯ä¾
  "minimumPixelSize": 0, //æå®æ¨¡åçæå°åç´ å¤§å°ï¼èä¸èèç¼©æ¾
  "maximumScale": 0, //æå®æ¨¡åçæå¤§æ¯ä¾
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "silhouetteColor": DC.Color.RED, //è½®å»é¢è²
  "silhouetteSize": 0, //è½®å»å®½åº¦
  "lightColor": DC.Color.RED, //æ¨¡åçè²æ¶æå®ç¯åé¢è²
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.ModelCollectionPrimitive

> æ¨¡åç»åå¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let positions = '120,20;120,30;122,30'
let model = new DC.ModelCollectionPrimitive(positions, '**/**.glb')
```

### creation

- **_constructor(positions, modelUrl)_**

  æé å½æ°

  - åæ°
    - `{Array<Position|String|Object>} positions`ï¼åæ ä¸²
    - `{String} modelUrl`ï¼æ¨¡åå°å
  - è¿åå¼ `model`

### properties

- `{Array<Position|String|Object>} positions`ï¼åæ ä¸²
- `{String} modelUrl`ï¼æ¨¡åå°å
- `{Array<Object>} attrs`ï¼å±æ§éå
- `{Promise} readyPromise`ï¼å è½½å®æåçå¼æ­¥å½æ° **_`readonly`_**

### methods

- **_getModelInstance(instanceId)_**

  è·åæ¨¡åå®ä¾

  - åæ°
    - `{String} instanceId`ï¼å®ä¾ IDï¼é»è®¤ä¸ºå®ä¾ç indexï¼å¯éè¿é¼ æ äºä»¶è·å
  - è¿åå¼ `modelInstance`

- **_getAttrByInstanceId(instanceId)_**

  è·åå±æ§

  - åæ°
    - `{String} instanceId`ï¼å®ä¾ IDï¼é»è®¤ä¸ºå®ä¾ç indexï¼å¯éè¿é¼ æ äºä»¶è·å
  - è¿åå¼ `Object`

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Model](http://resource.dvgis.cn/cesium-docs/Model.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "scale": 1, //æ¯ä¾
  "minimumPixelSize": 0, //æå®æ¨¡åçæå°åç´ å¤§å°ï¼èä¸èèç¼©æ¾
  "maximumScale": 0, //æå®æ¨¡åçæå¤§æ¯ä¾
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "silhouetteColor": DC.Color.RED, //è½®å»é¢è²
  "silhouetteSize": 0, //è½®å»å®½åº¦
  "lightColor": DC.Color.RED, //æ¨¡åçè²æ¶æå®ç¯åé¢è²
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  } //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
}
```

## DC.PointPrimitive

> ç¹ä½å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let position = new DC.Position(120, 20)
let point = new DC.PointPrimitive(position)
point.setStyle({
  pixelSize: 10,
})
```

### creation

- **_constructor(position)_**

  æé å½æ°

  - åæ°
    - `{Position|Number|String|Object} position`ï¼åæ 
  - è¿åå¼ `point`

### properties

- `{Position|Number|String|Object} position`ï¼åæ 

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PointGraphics](http://resource.dvgis.cn/cesium-docs/PointGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "pixelSize": 1, //åç´ å¤§å°
  "heightReference": 0, //é«åº¦åç§ï¼0ï¼ä½ç½®æ åç§ï¼ä½ç½®æ¯ç»å¯¹çï¼1ï¼ä½ç½®åºå®å¨å°å½¢ä¸ 2ï¼ä½ç½®é«åº¦æ¯æå°å½¢ä¸æ¹çé«åº¦ã
  "color": DC.Color.WHITE, //é¢è²
  "outlineColor": DC.Color.WHITE, //è¾¹æ¡é¢è²
  "outlineWidth": 0, //è¾¹æ¡å¤§å°ï¼
  "scaleByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®æ¯ä¾
  "translucencyByDistance": {
    "near": 0, //æè¿è·ç¦»
    "nearValue": 0, //æè¿è·ç¦»å¼
    "far": 1, //æè¿è·ç¦»å¼
    "farValue": 0 //æè¿è·ç¦»å¼
  }, //æ ¹æ®è·ç¦»è®¾ç½®éæåº¦
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "disableDepthTestDistance": 0 // æ·±åº¦æ£æµè·ç¦»ï¼ç¨äºé²æ­¢åªåå°å½¢ï¼è®¾ç½®ä¸ºé¶æ¶ï¼å°å§ç»åºç¨æ·±åº¦æµè¯ãè®¾ç½®ä¸ºNumber.POSITIVE_INFINITYæ¶ï¼æ°¸è¿ä¸ä¼åºç¨æ·±åº¦æµè¯ã
}
```

## DC.PolylinePrimitive

> çº¿å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let polyline = new DC.PolylinePrimitive('120,20;120,30')
polyline.setStyle({
  width: 10,
})
```

### creation

- **_constructor(positions)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `polyline`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
- `{Position} center`ï¼ä¸­å¿ç¹ **_`readonly`_**
- `{Number} distance`ï¼è·ç¦»,åä½ï¼ç±³ **_`readonly`_**

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[Polyline](http://resource.dvgis.cn/cesium-docs/Polyline.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "width": 1, //çº¿å®½
  "material": DC.Color.WHITE, //æè´¨
  "clampToGround": false, //æ¯å¦è´´å°
  "shadows": 0, //é´å½±ç±»åï¼0ï¼ç¦ç¨ã1ï¼å¯ç¨ ã2ï¼æå°ã3ï¼æ¥å
  "distanceDisplayCondition": {
    "near": 0, //æè¿è·ç¦»
    "far": Number.MAX_VALUE //æè¿è·ç¦»
  }, //æ ¹æ®è·ç¦»è®¾ç½®å¯è§
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "zIndex": 0 //å±çº§
}
```

## DC.ScanCirclePrimitive

> æ«æåå¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let scanCirclePrimitive = new DC.ScanCirclePrimitive('120,20', 1000)
```

### creation

- **_constructor(position,radius)_**

  æé å½æ°

  - åæ°
    - `{String|Position|Array|Object} position`ï¼åå¿
    - `{Number} radius`ï¼åå¾
  - è¿åå¼ `scanCircle`

### properties

- `{String|Position|Array|Object} position`ï¼åå¿
- `{Number} radius`ï¼åå¾

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "speed": 5, //éåº¦
  "color": DC.Color.WHITE //é¢è²
}
```

## DC.TrailLinePrimitive

> è½¨è¿¹çº¿å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let trailLinePrimitive = new DC.TrailLinePrimitive('120,20;120,30;122,30')
```

### creation

- **_constructor(positions,[asynchronous])_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
  - è¿åå¼ `trailLine`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "speed": 5, //éåº¦
  "color": DC.Color.WHITE //é¢è²
}
```

## DC.WaterPrimitive

> æ°´é¢å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let water = new DC.WaterPrimitive('120,20;120,30;122,30')
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

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
    - `{Boolean} asynchronous`:å¼æ­¥åå»ºï¼é»è®¤å¼ï¼true
  - è¿åå¼ `water`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²

### methods

- **_setStyle(style)_**

  è®¾ç½®æ ·å¼

  - åæ°
    - `{Object} style`ï¼æ ·å¼ï¼è¯¦æåèï¼[PolygonGraphics](http://resource.dvgis.cn/cesium-docs/PolygonGraphics.html)
  - è¿åå¼ `this`

```json
// æ ·å¼åæ°(å¯é)
{
  "height": 1, //é«åº¦
  "extrudedHeight": 0, //æåé«åº¦
  "stRotation": 0, //æè½¬è§åº¦
  "outline": false, //æ¯å¦æ¾ç¤ºè¾¹æ¡
  "closeTop": true, //é¡¶é¢æ¯å¦é­å
  "closeBottom": true, //åºé¢æ¯å¦é­å
  "classificationType": 2, //åç±» æ¯å¦å½±åå°å½¢ï¼3Dåçæåæ¶å½±åè¿ä¸¤èã0:å°å½¢ã1:3Dåçã2ï¼ä¸¤è
  "baseWaterColor": DC.Color.WHITE, // æ°´ä½é¢è²
  "blendColor": DC.Color.WHITE, // æ··åé¢è²
  "specularMap": "", // éé¢å¾
  "normalMap": "", // æ³çº¿å¾
  "frequency": 1000, //æ³¢çº¹æ°é
  "animationSpeed": 0.03, // å¨ç»éåº¦
  "amplitude": 10, //æ°´æ³¢æ¯å¹
  "specularIntensity": 10 //éé¢åå°å¼ºåº¦
}
```

## DC.VideoPrimitive

> è§é¢å¾åï¼ç»§æ¿äº[Overlay](#overlay)

### example

```js
let videoEl = new document.getElementById('video')
let videoPrimitive = new DC.VideoPrimitive('120,20;120,30;122,30', videoEl)
```

### creation

- **_constructor(positions,video)_**

  æé å½æ°

  - åæ°
    - `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
    - `{Element} video`ï¼è§é¢èç¹
  - è¿åå¼ `videoPrimitive`

### properties

- `{String|Array<Position|Number|String|Object>} positions`ï¼åæ ä¸²
- `{Element} video`ï¼è§é¢èç¹
