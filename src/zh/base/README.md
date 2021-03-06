---
sidebar: auto
---

# åºç¡ææ ð

## å½åç©ºé´

**`DC`**

DC ä¸ºæ¡æ¶é»è®¤å½åç©ºé´ï¼ä½¿ç¨è¯¥æ¡æ¶å¼åæ¶é½éè¦ç»ä»¥ `DC.` å¼å§

:::danger
å¼åæ¶å°½éä¸è¦ä½¿ç¨ DC ä¸ºåéåæèå½åç©ºé´ï¼é¿åæ¡æ¶æ æ³æ­£å¸¸ä½¿ç¨ã
:::

**`Cesium`**

[Cesium](https://cesium.com/cesiumjs/) æ¯ä¸æ¬¾é¢åä¸ç»´ GIS çä¸ççº§ç ES6 çå¼æºäº§åãè¯¥äº§åæ¹ä¾¿ä¸ªäººæèå¢éå¿«éæ­å»ºä¸æ¬¾æ æä»¶çä¸ç»´ GIS ç Web åºç¨ï¼ å¨æ§è½ãç²¾åº¦ãæ¸²æè´¨éãè·¨å¹³å°ä¸é½æå¾å¥½çä¿è¯ãå¼åæ¶å¦æéè¦ Cesium çåé¨æ¥å£å¯ä»¥éè¿ **`const { Cesium } = DC.Namespace`** è·å Cesiumã

**`mapv`**

[Mapv](https://mapv.baidu.com/) æ¯ä¸æ¬¾å°çä¿¡æ¯å¯è§åå¼æºåºï¼å¯ä»¥ç¨æ¥å±ç¤ºå¤§éå°çä¿¡æ¯æ°æ®ï¼ç¹ãçº¿ãé¢çæ°æ®ï¼æ¯ç§æ°æ®ä¹æä¸åçå±ç¤ºç±»åï¼å¦ç´æ¥æç¹ãç­åå¾ãç½æ ¼ãèåç­æ¹å¼å±ç¤ºæ°æ®ãå¼åæ¶å¦æéè¦ Mapv çåé¨æ¥å£å¯ä»¥éè¿ **`const { mapv } = DC.Namespace`** è·å mapv

**`turf`**

[Turf](https://mapv.baidu.com/) æ¯ä¸ä¸ªç¨äºç©ºé´åæç JavaScript åºï¼å®åæ¬ä¼ ç»çç©ºé´æä½ãåå»º GeoJSON æ°æ®çç¸å³å½æ°ï¼ä»¥åæ°æ®åç±»åç»è®¡å·¥å·ãTurf å¯ä»¥ä½ä¸ºå®¢æ·ç«¯æä»¶æ·»å å°ä½ çç½ç«ä¸ï¼ä¹å¯ä»¥ä½¿ç¨ Node.js å¨æå¡å¨ç«¯è¿è¡ Turfãå¼åæ¶å¦æéè¦ Turf çåé¨æ¥å£å¯ä»¥éè¿ **`const { turf } = DC.Namespace`** è·å turf

## å¨å±å±æ§

### version

> æ¡æ¶çæ¬å·

### accessToken

> ç¨äºå»é¤ logo åæ§å¶ç«¯çè¾åºä¿¡æ¯ã`ä¸å½±åæ¡æ¶çä½¿ç¨`

```js
DC.accessToken = '<your access token>'
```

:::tip
Token ç³è¯·å¯éè¿ [http://dvgis.cn/#/price](http://dvgis.cn/#/price) è¿è¡ç³è¯·
:::

### baseUrl

> ç¨äºè®¾ç½® `Cesium` ç¸å³çéæèµæºæä»¶: `Assets`ã`Workers` ã`ThirdParty`ã`Widgets` çè·¯å¾

```js
DC.baseUrl = './libs/dc-sdk/resources/'
DC.ready(() => {})
```

:::warning
`baseUrl` çè®¾ç½®éè¦å¨ `ready` å½æ°ä¹åï¼å¦åå°ä½¿ç¨é»è®¤çè®¾ç½® `./libs/dc-sdk/resources/`
:::

### Namespace

> ç¬¬ä¸æ¹åºçå½åç©ºé´éå

## å¨å±å½æ°

### use

> å¨ DC ä¸­ä½¿ç¨ç¬¬ä¸æ¹æ¨¡åææ¡æ¶

```js
let plugin = {
  install: (DC) => {},
}
DC.use(plugin)
```

### mixin

> å¨ DC ä¸­æ·»å é¢å¤å±æ§æèå½æ°

```js
let comp = {
  a: 'b',
}
DC.mixin(comp)
DC.a // b
```

### init

> è¯¥å½æ°ä¸ºåå§å Cesium ä½¿ç¨ï¼é»è®¤ä½¿ç¨ç Cesium ä¸ºææ°ççæ¬ï¼å¦æä½¿ç¨èªå®ä¹ç Cesium çæ¬ï¼å¯å¨ DC å è½½å¶ä»æ¨¡ååä¿®æ¹ Cesium çå¼ç¨ï¼ä»èæ¿æ¢æ´ä¸ª DC ä½ç³»ä¸­ Cesium **_`(æç¨)`_**

```js
DC.init(() => {
  DC.Namespace['Cesium'] = '<èªå®ä¹Cesium>' // æ¿æ¢æ¡æ¶ä¸­çé»è®¤Cesiumå¼ç¨,éå¨DCå è½½å¶ä»æ¨¡ååä½¿ç¨
  DC.use(DcCore)
})
```

### ready

> æ¡æ¶ä¸»å¥å£ï¼ä½¿ç¨æ¡æ¶æ¶å¿é¡»ä»¥è¿ä¸ªå¼å§ï¼å¦åæ æ³æå»º 3D åºæ¯

```js
global.DC = DC //å° DC åéè®¾ç½®ä¸ºå¨å±ï¼æ¹ä¾¿å¨å·¥ç¨ä¸­ä½¿ç¨
DC.use(DcCore)
DC.ready(() => {
  let viewer = new DC.Viewer(divId)
})
```

## å¸¸é

> æ¡æ¶åé¨é»è®¤å¸¸é

::: warning
å¼åæ¶è¯·ä½¿ç¨é»è®¤å¸¸éè¿è¡å¼å
:::

### MouseEventType

**_`DC.MouseEventType.LEFT_DOWN`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ å·¦é®æä¸äºä»¶

**_`DC.MouseEventType.LEFT_UP`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ å·¦é®æ¬åäºä»¶

**_`DC.MouseEventType.CLICK`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ ç¹å»äºä»¶

**_`DC.MouseEventType.RIGHT_DOWN`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ å³é®æä¸äºä»¶

**_`DC.MouseEventType.RIGHT_UP`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ å³é®æä¸äºä»¶

**_`DC.MouseEventType.RIGHT_CLICK`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ å³å»äºä»¶

**_`DC.MouseEventType.DB_CLICK`_**: (åºæ¯ãå¾å±ãè¦çç©)é¼ æ åå»äºä»¶

**_`DC.MouseEventType.MOUSE_MOVE`_**: åºæ¯é¼ æ ç§»å¨äºä»¶

**_`DC.MouseEventType.WHEEL`_**: åºæ¯é¼ æ æ»è½®äºä»¶

**_`DC.MouseEventType.MOUSE_OVER`_**: è¦çç©é¼ æ ç§»å¥äºä»¶

**_`DC.MouseEventType.MOUSE_OUT`_**: è¦çç©é¼ æ ç§»åºäºä»¶

### SceneEventType

**_`DC.SceneEventType.CAMERA_MOVE_END`_**: ç¸æºç§»å¨å®æ

**_`DC.SceneEventType.CAMERA_CHANGED`_**: ç¸æºä½ç½®å®æ

**_`DC.SceneEventType.PRE_UPDATE`_**: åºæ¯æ´æ°å

**_`DC.SceneEventType.POST_UPDATE`_**: åºæ¯æ´æ°å

**_`DC.SceneEventType.PRE_RENDER`_**: åºæ¯æ¸²æå

**_`DC.SceneEventType.POST_RENDER`_**: åºæ¯æ¸²æå

**_`DC.SceneEventType.MORPH_COMPLETE`_**: åºæ¯æ¨¡å¼åæ¢å®æ

**_`DC.SceneEventType.CLOCK_TICK`_**: æ¶éè·³å¨

### MouseMode

**_`DC.MouseMode.LEFT_MIDDLE`_**: å·¦é®æå¨ï¼ä¸­é®ç¿»è½¬(é»è®¤)

**_`DC.MouseMode.LEFT_RIGHT`_**: å·¦é®æå¨ï¼å³é®ç¿»è½¬

### ImageryType

**_`DC.ImageryType.ARCGIS`_**: arcgis å°å¾

**_`DC.ImageryType.SINGLE_TILE`_**: åå¾çå°å¾

**_`DC.ImageryType.WMS`_**: WMS å°å¾

**_`DC.ImageryType.WMTS`_**: WMTS å°å¾

**_`DC.ImageryType.XYZ`_**: xyz æ ¼å¼å°å¾

**_`DC.ImageryType.COORD`_**: ç¦çåæ å°å¾

**_`DC.ImageryType.AMAP`_**: é«å¾·å°å¾

**_`DC.ImageryType.BAIDU`_**: ç¾åº¦å°å¾

**_`DC.ImageryType.GOOGLE`_**: è°·æ­å°å¾

**_`DC.ImageryType.TDT`_**: å¤©å°å¾

**_`DC.ImageryType.TENCENT`_**: è¾è®¯å°å¾

### TerrainType

**_`DC.TerrainType.NONE`_**: æ å°å½¢

**_`DC.TerrainType.XYZ`_**: xyz æ ¼å¼å°å½¢

**_`DC.TerrainType.GOOGLE`_**: è°·æ­å°å½¢

**_`DC.TerrainType.ARCGIS`_**: arcgis å°å½¢

**_`DC.TerrainType.VR`_**: VR å°å½¢

### LayerType

**_`DC.LayerType.VECTOR`_**: ç¢éå¾å±

**_`DC.LayerType.PRIMITIVE`_**: å¾åå¾å±

**_`DC.LayerType.TILESET`_**: 3dtiles å¾å±

**_`DC.LayerType.HTML`_**: html å¾å±

**_`DC.LayerType.GEOJSON`_**: GeoJson å¾å±

**_`DC.LayerType.CLUSTER`_**: èåå¾å±

**_`DC.LayerType.CAMERA_VIDEO`_**: ç¸æºè§é¢å¾å±

**_`DC.LayerType.PLANE_VIDEO`_**: å¹³é¢è§é¢å¾å±

**_`DC.LayerType.KML`_**: kml å¾å±

**_`DC.LayerType.CZML`_**: czml å¾å±

**_`DC.LayerType.HEAT`_**: ç­åºå¾å±

**_`DC.LayerType.MAPV`_**: Mapv å¾å±

**_`DC.LayerType.CHART`_**: echarts å¾å±

### OverlayType

**_`DC.OverlayType.POINT`_**: ç¹ **_`å¯æ ç»`_**

**_`DC.OverlayType.POLYLINE`_**: çº¿ **_`å¯æ ç»`_**

**_`DC.OverlayType.POLYGON`_**: é¢ **_`å¯æ ç»`_**

**_`DC.OverlayType.MODEL`_**: æ¨¡å

**_`DC.OverlayType.BILLBOARD`_**: å¾æ ç¹ **_`å¯æ ç»`_**

**_`DC.OverlayType.RECTANGLE`_**: ç©å½¢ **_`å¯æ ç»`_**

**_`DC.OverlayType.CIRCLE`_**: å **_`å¯æ ç»`_**

**_`DC.OverlayType.LABEL`_**: æ ç­¾

**_`DC.OverlayType.TILESET`_**: 3DTiles

**_`DC.OverlayType.BOX`_**: ç

**_`DC.OverlayType.CORRIDOR`_**: èµ°å»

**_`DC.OverlayType.CYLINDER`_**: åæ±

**_`DC.OverlayType.ELLIPSE`_**: æ¤­å

**_`DC.OverlayType.ELLIPSOID`_**: çä½

**_`DC.OverlayType.PLANE`_**: é¢æ¿

**_`DC.OverlayType.POLYLINE_VOLUME`_**: ç®¡é

**_`DC.OverlayType.WALL`_**: å¢ä½

**_`DC.OverlayType.DYNAMIC_BILLBOARD`_**: å¨æå¾æ ç¹

**_`DC.OverlayType.DYNAMIC_MODEL`_**: å¨ææ¨¡åç¹

**_`DC.OverlayType.CUSTOM_BILLBOARD`_**: èªå®ä¹å¾æ 

**_`DC.OverlayType.CUSTOM_LABEL`_**: èªå®ä¹æ ç­¾

**_`DC.OverlayType.ATTACK_ARROW`_**: æ»å»ç®­å¤´ **_`å¯æ ç»`_**

**_`DC.OverlayType.DOUBLE_ARROW`_**: åç®­å¤´ **_`å¯æ ç»`_**

**_`DC.OverlayType.FINE_ARROW`_**: ç´ç®­å¤´ **_`å¯æ ç»`_**

**_`DC.OverlayType.GATHERING_PLACE`_**: èéå° **_`å¯æ ç»`_**

**_`DC.OverlayType.TAILED_ATTACK_ARROW`_**: çå°¾æ»å»ç®­å¤´ **_`å¯æ ç»`_**

**_`DC.OverlayType.BILLBOARD_PRIMITIVE`_**: å¾æ å¾å

**_`DC.OverlayType.DIFFUSE_WALL_PRIMITIVE`_**: æ©æ£å¢å¾å

**_`DC.OverlayType.ELEC_ELLIPSOID_PRIMITIVE`_**: çµå¼§çå¾å

**_`DC.OverlayType.FLOW_LINE_PRIMITIVE`_**: æµå¨çº¿å¾å

**_`DC.OverlayType.LABEL_PRIMITIVE`_**: ææ¬å¾å

**_`DC.OverlayType.MODEL_PRIMITIVE`_**: æ¨¡åå¾å

**_`DC.OverlayType.POINT_PRIMITIVE`_**: ç¹å¾å

**_`DC.OverlayType.POLYLINE_PRIMITIVE`_**: çº¿å¾å

**_`DC.OverlayType.SCAN_CIRCLE_PRIMITIVE`_**: æ«æåå¾å

**_`DC.OverlayType.TRAIL_LINE_PRIMITIVE`_**: è½¨è¿¹çº¿å¾å

**_`DC.OverlayType.WATER_PRIMITIVE`_**: æ°´é¢å¾å

**_`DC.OverlayType.VIDEO_PRIMITIVE`_**: è§é¢å¾å

**_`DC.OverlayType.CAMERA_VIDEO`_**: è§é¢èå

**_`DC.OverlayType.PLAN_VIDEO`_**: å¹³é¢è§é¢

### TrackViewMode

**_`DC.TrackViewMode.FP`_**: ç¬¬ä¸äººç§°è§è§

**_`DC.TrackViewMode.TP`_**: ç¬¬ä¸äººç§°è§è§

**_`DC.TrackViewMode.TRACKED`_**: è·éè§è§

**_`DC.TrackViewMode.FREE`_**: èªç±è§è§

### PositionEditorType

**_`DC.PositionEditorType.TRANSLATION`_**: åç§»

**_`DC.PositionEditorType.ROTATION`_**: æè½¬

### ClippingDirection

**_`DC.ClippingDirection.UP`_**: åä¸

**_`DC.ClippingDirection.DOWN`_**: åä¸

**_`DC.ClippingDirection.LEFT`_**: åå·¦

**_`DC.ClippingDirection.RIGHT`_**: åå³

**_`DC.ClippingDirection.FRONT`_**: åå

**_`DC.ClippingDirection.BACK`_**: åå

### AnalysisType

**_`DC.AnalysisType.CONTOUR_LINE`_**ï¼ç­é«çº¿

**_`DC.AnalysisType.SHADOWS`_**ï¼é´å½±

**_`DC.AnalysisType.SIGHT_LINE`_**ï¼éè§åæï¼çº¿ï¼

**_`DC.AnalysisType.SIGHT_CIRCLE`_**ï¼éè§åæï¼åï¼

**_`DC.AnalysisType.VIEWSHED`_**ï¼å¯è§å

## DC.Viewer

> 3D åºæ¯ä¸»è¦æ¥å£ï¼å¨ç»å®ç DivId ä¸­æå»ºä¸ç»´åºæ¯ï¼ä¹å¯ç¨ DC.World.

### example

```html
<div id="viewer-container"></div>
```

```js
let viewer = DC.Viewer('viewer-container')
global.viewer = viewer // æ·»å å°å¨å±åé
```

:::warning
å¦æå¼åä½¿ç¨çæ¯ Vue è¿æ ·ç MVVM æ¡æ¶ï¼ä¸è¦å° viewerãlayerãoverlay æ·»å å°æ°æ®æ¨¡åä¸­ãç±äº 3D åºæ¯ä¸­ä¼ä¸åçå·æ°æ¯ä¸å¸§ï¼å¦æå°æ°æ®æ·»å å°æ°æ®æ¨¡åä¸­ï¼é¿æ¶é´çè¯ä¼å¯¼è´æµè§å¨çååå¢å¤§èå¥æºã
:::

### creation

- **_constructor(id,[options])_**

  æé å½æ°

  - åæ°
    - `{String} id`ï¼å®¹å¨ ID
    - `{Object} options`ï¼å±æ§
  - è¿åå¼ `viewer`

```json
//å±æ§åæ°ï¼å¯éï¼
{
  "contextOptions": {
    "webgl": {
      "alpha": false, //èæ¯
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
  "sceneMode": 3 //1: 2.5Dï¼2: 2Dï¼3: 3D
}
```

### properties

- `{Element} dcContainer`ï¼æ¡æ¶èªå®ä¹å®¹å¨ **_`readonly`_**
- `{Object} scene`ï¼åºæ¯ **_`readonly`_**ï¼è¯¦æåèï¼[Scene](http://resource.dvgis.cn/cesium-docs/Scene.html)
- `{Object} camera`ï¼ç¸æº **_`readonly`_**ï¼è¯¦æåèï¼[Camera](http://resource.dvgis.cn/cesium-docs/Scene.html)
- `{Element} canvas`ï¼canvas èç¹ **_`readonly`_**
- `{Object} clock`ï¼æ¶éï¼è¯¦æåèï¼[Clock](http://resource.dvgis.cn/cesium-docs/Clock.html)
- `{Object} dataSources`ï¼æ°æ®èµæºéåï¼è¯¦æåèï¼[DataSourceCollection](http://resource.dvgis.cn/cesium-docs/DataSourceCollection.html)
- `{Object} imageryLayers`ï¼ç¦çéåï¼è¯¦æåèï¼[ImageryLayerCollection](http://resource.dvgis.cn/cesium-docs/ImageryLayerCollection.html)
- `{Object} entities`ï¼å®ä½éåï¼è¯¦æåèï¼[EntityCollection](http://resource.dvgis.cn/cesium-docs/EntityCollection.html)
- [`{Popup} popup`](#popup)ï¼æ°æ³¡çªå£ **_`readonly`_**
- [`{ContextMenu} contextMenu`](#contextmenu)ï¼å³å»å¼¹æ¡ **_`readonly`_**
- [`{Tooltip} tooltip`](#tooltip)ï¼æç¤ºæ¡ **_`readonly`_**
- [`{MapSplit} mapSplit`](#mapsplit)ï¼å°å¾åå² **_`readonly`_**
- [`{Compass} compass`](#compass)ï¼ç½ç **_`readonly`_**
- [`{ZoomController} zoomController`](#zoomcontroller)ï¼ç½ç **_`readonly`_**
- [`{LocationBar} locationBar`](#locationbar)ï¼åæ ä¿¡æ¯ **_`readonly`_**
- [`{DistanceLegend} distanceLegend`](#distancelegend)ï¼æ¯ä¾å°º **_`readonly`_**
- [`{LoadingMask} loadingMask`](#loadingmask)ï¼å è½½èå± **_`readonly`_**
- `{Position} cameraPosition`ï¼ç¸æºä½ç½® **_`readonly`_**
- `{Number} resolution`ï¼åè¾¨ç **_`readonly`_**
- `{Rect} viewBounds`ï¼è§éèå´ **_`readonly`_**

### methods

- **_setOptions(options)_**

  è®¾ç½®å±æ§

  - åæ°
    - `{Object} options`ï¼å±æ§å¯¹è±¡
      - è¿åå¼ `this`

```json
// å±æ§åæ°(å¯é)
{
  "shadows": false, // æ¯å¦å¼å¯é´å½±
  "resolutionScale": 1, // è®¾ç½®æ¸²æåè¾¨ççç¼©æ¾æ¯ä¾
  "showAtmosphere": true, //æ¯å¦æ¾ç¤ºå¤§æ°å±
  "showSun": true, //æ¯å¦æ¾ç¤ºå¤ªé³
  "showMoon": true, //æ¯å¦æ¾ç¤ºæäº®
  "enableFxaa": true, //æ¯å¦å¼å¯æé¯é½¿
  "cameraController": {
    // ç¸æºæ§å¶
    "enableRotate": true, // æ¯å¦å¯ä»¥æè½¬
    "enableTilt": true, // æ¯å¦å¯ä»¥ç¿»è½¬
    "enableTranslate": true, // æ¯å¦å¯ä»¥å¹³ç§»
    "enableZoom": true, // æ¯å¦å¯ä»¥ç¼©æ¾
    "enableCollisionDetection": true, // æ¯å¦æ¯æç¢°ææ£æµ
    "minimumZoomDistance": 1.0, // æå°ç¼©æ¾è·ç¦»
    "maximumZoomDistance": 40489014.0 // æå¤§ç¼©æ¾è·ç¦»
  },
  "globe": {
    "show": true, // æ¯å¦æ¾ç¤ºå°ç
    "showGroundAtmosphere": true, // æ¾ç¤ºå°é¢å¤§æ°
    "enableLighting": false, //æ¯å¦å¼å¯ç¯åï¼å¼å¯åå°çä¼æ ¹æ®å½åæ¶é´å¯ç¨ç¯å
    "depthTestAgainstTerrain": false, //æ¯å¦å¼å¯æ·±åº¦æ£æµ
    "tileCacheSize": 100, // é»è®¤ç¦çç¼å­å¤§å°
    "preloadSiblings": false, //æ¯å¦åºé¢å è½½æ¸²æåçº§å¾å
    "terrainExaggeration": 1, //å°å½¢å¤¸å¼ ç³»æ°
    "terrainExaggerationRelativeHeight": 1, //å°å½¢ç¸å¯¹é«åº¦å¤¸å¼ ç³»æ°
    "baseColor": new DC.Color(0, 0, 0.5, 1), //å°çé»è®¤åºè²
    "translucency": {
      //å°è¡¨éæ
      "enabled": false, // æ¯å¦å¼å¯å°è¡¨éæ
      "backFaceAlpha": 1, // å°çèé¢éæåº¦
      "backFaceAlphaByDistance": null, //æ ¹æ®è·ç¦»è®¾ç½®å°çèé¢éæåº¦: {near:400,nearValue:0.2,far:800,farValue:1}
      "frontFaceAlpha": 1, // å°çæ­£é¢éæåº¦
      "frontFaceAlphaByDistance": null //æ ¹æ®è·ç¦»è®¾ç½®å°çæ­£é¢éæåº¦: {near:400,nearValue:0.2,far:800,farValue:1}
    }
  },
  "skyBox": {
    "sources": {}, // å­ä¸ªé¢çè´´å¾
    "show": true, //æ¯å¦æ¾ç¤º
    "offsetAngle": 0 //æè½¬è§åº¦
  }
}
```

- **_setPitchRange(min,max)_**

  è®¾ç½®ç¿»è½¬è§åº¦

  - åæ°
    - `{Number} min`ï¼æå°è§åº¦
    - `{Number} max`ï¼æå¤§è§åº¦
  - è¿åå¼ `this`

- **_limitCameraToGround()_**

  è®¾ç½®éå¶ç¸æºå°å°ä¸

  - è¿åå¼ `this`

- **_changeSceneMode(sceneMode, duration)_**

  æ¹ååºæ¯æ¨¡å¼

  - åæ°
    - `{Number} sceneMode`ï¼åºæ¯æ¨¡å¼ ï¼2ï¼2Dï¼3ï¼3Dï¼2.5ï¼2.5D
    - `{Number} duration`ï¼é´éæ¶é´
  - è¿åå¼ `this`

- **_changeMouseMode(mouseMode)_**

  æ¹åé¼ æ ä½¿ç¨æ¨¡å¼

  - åæ°
    - `{Number} mouseMode`ï¼é¼ æ æ¨¡å¼ï¼è¯¦æåèï¼`DC.MouseMode`
  - è¿åå¼ `this`

- **_addBaseLayer(baseLayers,options)_**

  æ·»å å°å¾

  - åæ°
    - `{baseLayer|Array<baseLayer>} baseLayers`ï¼å°å¾
    - `{Object} options`ï¼å±æ§
  - è¿åå¼ `this`

```json
//å±æ§åæ°
{
  "name": "çµå­å°å¾", //åç§°
  "iconUrl": "../preview.png" //ç¼©ç¥å¾
}
```

- **_changeBaseLayer(index)_**

  æ´æ¹å°å¾

  - åæ°
    - `{Number} index`ï¼å°å¾ç´¢å¼
  - è¿åå¼ `this`

- **_getImageryLayerInfo(windowPosition)_**

  è·åç¦çä¿¡æ¯

  - åæ°
    - `{Object} windowPosition`ï¼çªå£åæ 
  - è¿åå¼ `promise`

- **_addTerrain(terrain)_**

  æ·»å å°å½¢

  - åæ°
    - `{Terrain} terrain`ï¼å°å½¢
  - è¿åå¼ `this`

- **_changeTerrain(index)_**

  åæ¢å°å½¢

  - åæ°
    - `{Number} index`ï¼å°å½¢ç´¢å¼
  - è¿åå¼ `this`

- **_removeTerrain()_**

  ç§»é¤å°å½¢

  - è¿åå¼ `this`

- **_addLayerGroup(layerGroup)_**

  æ·»å å¾å±ç»

  - åæ°
    - `{LayerGroup} layerGroup`ï¼å¾å±ç»
  - è¿åå¼ `this`

- **_removeLayerGroup(layerGroup)_**

  ç§»é¤å¾å±ç»

  - åæ°
    - `{LayerGroup} layerGroup`ï¼å¾å±ç»
  - è¿åå¼ `this`

- **_addLayer(layer)_**

  æ·»å å¾å±

  - åæ°
    - `{Layer} layer`ï¼å¾å±
  - è¿åå¼ `this`

- **_removeLayer(layer)_**

  å é¤å¾å±

  - åæ°
    - `{Layer} layer`ï¼å¾å±
  - è¿åå¼ `this`

- **_getLayer(id)_**

  è·åå¾å±

  - åæ°
    - `{String} id`ï¼å¾å± ID
  - è¿åå¼ `layer`

- **_getLayers()_**

  è·åææå¾å±ï¼ä¸åæ¬å°å¾

  - è¿åå¼ `layer`

- **_eachLayer(method, context)_**

  éåææå¾å±

  - åæ°
    - `{Function} method`ï¼åè°å½æ°
    - `{Object} context`ï¼ä¸ä¸æï¼é»è®¤ä¸º this
  - è¿åå¼ `this`

  ```js
  viewer.eachLayer((layer) => {})
  ```

- **_flyTo(target,duration)_**

  é£åç®æ 

  - åæ°
    - `{VectorLayer|Overlay} target` ï¼ç®æ 
    - `{Number} duration`ï¼é£å°ä½ç½®æ¶é´ï¼åä½ï¼ç§
  - è¿åå¼ `this`

- **_zoomTo(target)_**

  ç¼©æ¾å°ç®æ 

  - åæ°
    - `{VectorLayer|Overlay} target` ï¼ç®æ 
  - è¿åå¼ `this`

- **_flyToPosition(position, completeCallback, duration)_**

  é£å°å·ä½ä½ç½®

  - åæ°
    - `{Position} position`ï¼ä½ç½®
    - `{Function} completeCallback`ï¼é£å®ä¹åè§¦åçåè°
    - `{Number} duration`ï¼é£å°ä½ç½®æ¶é´ï¼åä½ï¼ç§
  - è¿åå¼ `this`

- **_zoomToPosition(position, completeCallback)_**

  ç¼©æ¾å°å·ä½ä½ç½®

  - åæ°
    - `{DC.Position} position`ï¼ä½ç½®
    - `{Function} completeCallback`ï¼ç¼©æ¾å®æåè§¦åçåè°
  - è¿åå¼ `this`

- **_on(type, callback, context)_**

  äºä»¶è®¢é

  - åæ°
    - `{Object} type` ï¼è®¢éç±»å
    - `{Function} callback` ï¼è®¢éåè°
    - `{Object} context` ï¼ä¸ä¸æ
  - è¿åå¼ `this`

- **_once(type, callback, context)_**

  äºä»¶è®¢é(ä¸æ¬¡)

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

- **_destroy()_**

  éæ¯ä¸ç»´åºæ¯

  - è¿åå¼ `this`

- **_exportScene(name)_**

  å¯¼åºåºæ¯

  - åæ°
    - `{String} name` ï¼åç§°ï¼é»è®¤ä¸º scene
  - è¿åå¼ `this`

- **_use(plugin)_**

  ä½¿ç¨æä»¶(`æç¨`)ï¼è¿ä¸ªåå¨å±çä¸åãè¯¥å½æ°ä¼å° 3D åºæ¯ä½ä¸ºåæ°ä¼ å¥å°æä»¶ä¸­

  - åæ°
    - `{Object} plugin` ï¼æä»¶
  - è¿åå¼ `this`

  ```js
  let plugin = {
    install: (viewer) => {},
  }
  viewer.use(plugin)
  ```

## Popup

> æ°æ³¡çªå£

### example

```js
let popup = viewer.popup
popup.setContent('<div></div>')
```

### properties

- `{String} state`ï¼ç¶æ **_`readonly`_**
- `{Object} config`ï¼éç½® **_`writeOnly`_**

```json
// éç½®ï¼å¯éï¼
// éç½®åä¼å½±åå¨å±çpopupçæ¾ç¤ºæ ·å¼ï¼è¯·æéã
{
  "position": "center", // popupçä½äºé¼ æ çç¹å»ä½ç½®çæ¹å,æï¼centerï¼left ï¼right
  "customClass": "custom" // æ·»å èªå®ä¹çCss ç±»åå°popupä¸­ï¼å¤ä¸ªç¨ç©ºæ ¼éå¼
}
```

### methods

- **_setPosition(position)_**

  è®¾ç½®ä½ç½®

  - åæ°
    - `{Cartesian3} position`ï¼ä¸çåæ 
  - è¿åå¼ `this`

- **_setContent(content)_**

  è®¾ç½®åå®¹

  - åæ°
    - `{String|Element} content`ï¼åå®¹
  - è¿åå¼ `this`

- **_setWrapper(wrapper)_**

  è®¾ç½®å®¹å¨

  - åæ°
    - `{Element} wrapper`ï¼å®¹å¨ **_`(ä¸è¬ç¨äº MVVM æ¡æ¶çæ¨¡æ¿)`_**
  - è¿åå¼ `this`

- **_showAt(position, content)_**

  è®¾ç½®åå®¹

  - åæ°
    - `{Cartesian3} position`ï¼ä¸çåæ 
    - `{String|Element} content`ï¼åå®¹
  - è¿åå¼ `this`

- **_hide()_**

  éèæ°æ³¡çªå£

  - è¿åå¼ `this`

## ContextMenu

> å³å»èå

### example

```js
let contextMenu = viewer.contextMenu
contextMenu.enable = true
contextMenu.DEFAULT_MENU = [
  {
    label: 'æµè¯',
    callback: (e) => {}, // eæ¯ä¸ä¸ªå¯¹è±¡ä¸»è¦åæ¬ windowPosition,position,surfacePosition,overlay
    context: this,
  },
] // è®¾ç½®é»è®¤çå³å»èåï¼ä¼å½±åå¨å±å³å»èå(æç¨)ã
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**
- `{Array} DEFAULT_MENU`ï¼é»è®¤èåï¼èåçåè°å½æ°åæ°ä¸ºä¸ä¸ªå¯¹è±¡ **_`writeOnly`_**

## Tooltip

> æç¤ºæ¡

### example

```js
let tooltip = viewer.tooltip
tooltip.enable = true
tooltip.showAt({ x: 100, y: 100 }, 'æµè¯')
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

### methods

- **_showAt(position,content)_**

  è®¾ç½®ä½ç½®

  - åæ°
    - `{Cartesian2} position`ï¼å±å¹åæ 
    - `{String|Element} content`ï¼åå®¹
  - è¿åå¼ `this`

## MapSplit

> å°å¾åå²

### examples

```js
let baseLayer_elc = DC.ImageryLayerFactory.createGoogleImageryLayer()
viewer.mapSplit.enable = true
viewer.mapSplit.addBaseLayer(baseLayer_elc, -1)
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

### methods

- **_addBaseLayer(baseLayer,[splitDirection])_**

  æ·»å å°å¾

  - åæ°
    - `{BaseLayer} baseLayer`ï¼å°å¾
    - `{Number} splitDirection`ï¼åå²æ¹åï¼-1ï¼å·¦ï¼0ï¼æ ï¼1ï¼å³
  - è¿åå¼ `this`

## Compass

> ç½ç

### examples

```js
viewer.compass.enable = true
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

## ZoomController

> ç¼©æ¾æ§å¶

### examples

```js
viewer.zoomController.enable = true
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

## LocationBar

> åæ ä¿¡æ¯

### examples

```js
viewer.locationBar.enable = true
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

## DistanceLegend

> æ¯ä¾å°º

### examples

```js
viewer.distanceLegend.enable = true
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

## LoadingMask

> å è½½èå±

### examples

```js
viewer.loadingMask.enable = true
```

### properties

- `{Boolean} enable`ï¼æ¯å¦å¯ç¨
- `{String} state`ï¼ç¶æ **_`readonly`_**

## DC.SkyBox

> å¤©ç©ºçï¼[è¯¦æåè](http://resource.dvgis.cn/cesium-docs/SkyBox.html)

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

  æé å½æ°

  - åæ°
    - `{Object} options`ï¼éç½®
  - è¿åå¼ `skyBox`

```json
//options(å¯é)
{
  "sources": {}, // å­ä¸ªé¢çè´´å¾
  "show": true //æ¾ç¤º
}
```

### properties

- `{Object} sources`ï¼å­ä¸ªé¢çè´´å¾
- `{Boolean} show`ï¼æ¾ç¤º

## DC.GroundSkyBox

> è¿å°å¤©ç©ºçï¼[è¯¦æåè](http://resource.dvgis.cn/cesium-docs/SkyBox.html)

### example

```js
scene.skyBox = new DC.GroundSkyBox({
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

  æé å½æ°

  - åæ°
    - `{Object} options`ï¼éç½®
  - è¿åå¼ `skyBox`

```json
//options(å¯é)
{
  "sources": {}, // å­ä¸ªé¢çè´´å¾
  "show": true, //æ¾ç¤º
  "offsetAngle": 0 //æè½¬è§åº¦
}
```

### properties

- `{Object} sources`ï¼å­ä¸ªé¢çè´´å¾
- `{Boolean} show`ï¼æ¾ç¤º
- `{Number} offsetAngle`ï¼æè½¬è§åº¦

## DC.Position

> åæ ç±»ï¼ç¨äºæè¿°ç©ä½å¨åºæ¯ä¸­çå·ä½ä½ç½®ï¼éç¨å³ææ å

### example

```js
let position = new DC.Position(120, 22, 102)

let position1 = DC.Position.fromString('120,22,102')

let position2 = DC.Position.fromArray([120, 22, 102])

let position3 = DC.Position.fromObject({ lng: 120, lat: 22, height: 102 })
```

### creation

- **_constructor(lng,lat,alt,heading,pitch,roll)_**

  æé å½æ°

  - åæ°
    - `{Number} lng`ï¼ç»åº¦
    - `{Number} lat`ï¼çº¬åº¦
    - `{Number} alt`ï¼é«åº¦ï¼åä½ï¼ç±³ï¼é»è®¤ï¼0
    - `{Number} heading`ï¼åèªè§åº¦ï¼å¯è½å¶ä»æ¡æ¶ä½ yawï¼è¡¨ç¤ºç» Z è½´æè½¬ãé»è®¤ï¼0
    - `{Number} pitch`ï¼ä¿¯ä»°è§åº¦ï¼è¡¨ç¤ºç» Y è½´æè½¬ãé»è®¤ï¼0
    - `{Number} roll`ï¼ç¿»è½¬è§åº¦ï¼è¡¨ç¤ºç» X è½´æè½¬ãé»è®¤ï¼0
  - è¿åå¼ `position`

### properties

- `{Number} lng`ï¼ç»åº¦
- `{Number} lat`ï¼çº¬åº¦
- `{Number} alt`ï¼é«åº¦ï¼åä½ï¼ç±³ï¼é»è®¤ï¼0
- `{Number} heading`ï¼åèªè§åº¦ï¼å¯è½å¶ä»æ¡æ¶ä½ yawï¼è¡¨ç¤ºç» Z è½´æè½¬ãé»è®¤ï¼0
- `{Number} pitch`ï¼ä¿¯ä»°è§åº¦ï¼è¡¨ç¤ºç» Y è½´æè½¬ãé»è®¤ï¼0
- `{Number} roll`ï¼ç¿»è½¬è§åº¦ï¼è¡¨ç¤ºç» X è½´æè½¬ãé»è®¤ï¼0

### methods

- **_serialize()_**

  åºåå

  - è¿åå¼ `string`

- **_copy()_**

  å¤å¶ä¸ä¸ªæ°çä½ç½®

  - è¿åå¼ `position`

- **_toString()_**

  å°åæ å­ç¬¦å

  - è¿åå¼ `string`

- **_toArray()_**

  å°åæ æ°ç»å

  - è¿åå¼ `array`

- **_toObject()_**

  å°åæ å¯¹è±¡å

  - è¿åå¼ `Object`

### static methods

- **_fromString(str)_**

  å°å­ç¬¦ååæ è½¬æ¢ä¸ºåæ å¯¹è±¡

  - åæ°
    - `{String} str`ï¼å­ç¬¦ååæ 
  - è¿åå¼ `position`

- **_fromArray(array)_**

  å°æ°ç»ååæ è½¬æ¢ä¸ºåæ å¯¹è±¡

  - åæ°
    - `{Array} array`ï¼æ°ç»ååæ 
  - è¿åå¼ `position`

- **_fromObject(obj)_**

  å° Json å¯¹è±¡åæ è½¬æ¢ä¸ºåæ å¯¹è±¡

  - åæ°
    - `{Object} obj`ï¼Json å¯¹è±¡åæ 
  - è¿åå¼ `position`

- **_fromCoordString(str)_** `deprecated`

  å­ç¬¦åæ ä¸²è½¬æ¢ä¸ºåæ å¯¹è±¡

  - åæ°
    - `{String} str`ï¼å­ç¬¦åæ ä¸²
  - è¿åå¼ `position`

- **_fromCoordArray(array)_** `deprecated`

  åæ æ°ç»è½¬æ¢ä¸ºåæ å¯¹è±¡

  - åæ°
    - `{Array<String|Number>} array`ï¼åæ æ°ç»
  - è¿åå¼ `position`

- **_deserialize(valStr)_**

  ååºåå

  - åæ°
    - `{String} valStr`ï¼åºååçå¯¹è±¡
  - è¿åå¼ `position`

## DC.Color

> é¢è²ç±»

### example

```js
let red = DC.Color.RED
```

### properties

- `{Color} RED`ï¼çº¢è²
- `{Color} YELLOW`ï¼é»è²
- `{Color} WHITE`ï¼ç½è²
- `{Color} GREEN`ï¼ç»¿è²

[å¶ä»é¢è²](http://resource.dvgis.cn/cesium-docs/Color.html)

## DC.TilesetStyle

> tileset æ ·å¼ï¼ç¨äºè®¾ç½® 3dtiles çé¢è²è®¾ç½®

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

[è¯¦æåè](http://resource.dvgis.cn/cesium-docs/Cesium3DTileStyle.html)

## DC.JulianDate

> æ±èå®æ¥å

```js
let date = DC.JulianDate.now()
```

### static methods

- **_now()_**

  å½åæ±èå®æ¶é´

  - è¿åå¼ `date`

- **_fromDate(date)_**

  éè¿ Js æ¶é´åå»ºæ±èå®æ¶é´

  - åæ°
    - `{Date} date`ï¼Js æ¶é´
  - è¿åå¼ `date`

[JulianDate](http://resource.dvgis.cn/cesium-docs/JulianDate.html)

## DC.Rect

> ç©å½¢ç¸å³å½æ°

### example

```js
let r = DC.Rect.fromDegrees(10, 20, 12, 31)
```

[è¯¦æåè](http://resource.dvgis.cn/cesium-docs/Rectangle.html)

## DC.CallbackProperty

> åè°å±æ§ï¼ç¨æ·éè¿èªå®ä¹åè°å½æ°æ¥è¿åéè¦çå¼ãåè°å½æ°ä¸­ï¼ç¨æ·å¯ä»¥ä½¿ç¨ time ç»å® valueï¼ä¹å¯ä»¥èªå®è®¾ç½®ã

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

## DC.Parse

> åæ è§£æå·¥å·ç±»,å¯ç®åä¸º DC.P

```js
let position = DC.P.parsePosition('123,32,0')
```

### static methods

- **_parsePosition(position)_**

  è§£æåæ ä¸º DC.Position

  - åæ°
    - `{String|Array|Position} position`ï¼åæ 
  - è¿åå¼ `position`

- **_parsePositions(positions)_**

  è§£æåæ ä¸º Array<DC.Position>

  - åæ°
    - `{String|Array} positions`ï¼ åæ 
  - è¿åå¼ `array`

- **_parsePointCoordToArray(position)_**

  è§£æç¹ä½åæ ä¸ºæ°ç»

  - åæ°
    - `{String|Position} position`ï¼ç¹ä½åæ 
  - è¿åå¼ `array`

- **_parsePolylineCoordToArray(positions)_**

  è§£æçº¿åæ ä¸ºäºç»´æ°ç»

  - åæ°
    - `{String|Array} positions`ï¼çº¿åæ 
  - è¿åå¼ `array`

- **_parsePolygonCoordToArray(positions,loop)_**

  è§£æé¢åæ ä¸ºä¸ç»´æ°ç»

  - åæ°
    - `{String|Array} positions`ï¼é¢åæ 
    - `{Boolean} loop`ï¼é­å
  - è¿åå¼ `array`

## DC.Transform

> åæ è½¬æ¢å·¥å·ç±» ,å¯ç®åä¸º DC.T

```js
let cartesian3 = DC.T.transformWGS84ToCartesian(new DC.Position(120, 20))
```

### static methods

- **_transformCartesianToWGS84(cartesian)_**

  ä¸çåæ è½¬æ¢ä¸º 84 åæ 

  - åæ°
    - `{Cartesian3} cartesian`ï¼ä¸çåæ 
  - è¿åå¼ `position`

- **_transformWGS84ToCartesian(position)_**

  84 åæ è½¬æ¢ä¸ºä¸çåæ 

  - åæ°
    - `{Position} position`ï¼84 åæ 
  - è¿åå¼ `cartesian`

- **_transformWGS84ToCartographic(position)_**

  84 åæ è½¬æ¢ä¸ºå¶å¾åæ 

  - åæ°
    - `{Position} position`ï¼84 åæ 
  - è¿åå¼ `cartographic`

- **_transformCartesianArrayToWGS84Array(cartesianArr)_**

  ä¸çåæ æ°ç»è½¬ 84 åæ æ°ç»

  - åæ°
    - `{Array<cartesian3>} cartesianArr`ï¼ä¸çåæ æ°ç»
  - è¿åå¼ `array`

- **_transformWGS84ArrayToCartesianArray(WGS84Arr)_**

  84 åæ æ°ç»è½¬ä¸çåæ æ°ç»

  - åæ°
    - `{Array<cartesian3>} WGS84Arr`ï¼84 åæ æ°ç»
  - è¿åå¼ `array`

- **_transformWGS84ToMercator(position)_**

  84 åæ è½¬ Mercator

  - åæ°
    - `{Position} position`ï¼84 åæ 
  - è¿åå¼ `position`

- **_transformMercatorToWGS84(position)_**

  Mercator åæ è½¬ 84

  - åæ°
    - `{Position} position`ï¼Mercator åæ 
  - è¿åå¼ `position`

- **_transformWindowToWGS84(position,viewer)_**

  å±å¹åæ è½¬ 84

  - åæ°
    - `{Object} position`ï¼ å±å¹åæ ï¼æ ¼å¼`{x:1,y:1}`
    - `{Viewer} viewer`ï¼3D åºæ¯
  - è¿åå¼ `position`

- **_transformWGS84ToWindow(position,viewer)_**

  84 è½¬å±å¹åæ 

  - åæ°
    - `{Position} position`ï¼ 84 åæ 
    - `{Viewer} viewer`ï¼3D åºæ¯
  - è¿åå¼ `Object`

## DC.CoordTransform

> å½ååæ è½¬æ¢å·¥å·

```js
let point = DC.CoordTransform.BD09ToGCJ02(120, 20)
```

### static methods

- **_BD09ToGCJ02(lng, lat)_**

  ç¾åº¦åæ ç³» (BD-09) çè½¬æ¢ ç«æåæ ç³» (GCJ-02)

  - åæ°
    - `{Number} lng`ï¼ç»åº¦
    - `{Number} lat`ï¼çº¬åº¦
  - è¿åå¼ `[]`

- **_GCJ02ToBD09(lng, lat)_**

  ç«æåæ ç³» (GCJ-02) è½¬æ¢ä¸º ç¾åº¦åæ ç³» (BD-09)

  - åæ°
    - `{Number} lng`ï¼ç»åº¦
    - `{Number} lat`ï¼çº¬åº¦
  - è¿åå¼ `[]`

- **_WGS84ToGCJ02(lng, lat)_**

  WGS-84 è½¬æ¢ä¸º ç«æåæ ç³» (GCJ-02)

  - åæ°
    - `{Number} lng`ï¼ç»åº¦
    - `{Number} lat`ï¼çº¬åº¦
  - è¿åå¼ `[]`

- **_GCJ02ToWGS84(lng, lat)_**

  ç«æåæ ç³» (GCJ-02) è½¬æ¢ä¸º WGS-84

  - åæ°
    - `{Number} lng`ï¼ç»åº¦
    - `{Number} lat`ï¼çº¬åº¦
  - è¿åå¼ `[]`

## DC.Math

> åºæ¬å½æ°ç±»

### static methods

- **_area(positions)_**

  é¢ç§¯ï¼åä½ï¼å¹³æ¹ç±³

  - åæ°
    - `{Array<Position>} positions`ï¼ ç¹ä½æ°æ®
  - è¿åå¼ `number`

- **_bounds(positions , expand)_**

  è¾¹ç

  - åæ°
    - `{Array<Position>} positions`ï¼ ç¹ä½æ°æ®
    - `{Number}} expand`ï¼ æ©å±æ¯ä¾ï¼0~1
  - è¿åå¼ `object`

- **_mid(start , end)_**

  ä¸¤ç¹ä¹é´çä¸­å¿ç¹

  - åæ°
    - `start`ï¼ å¼å§ä½ç½®
    - `end`ï¼ ç»æä½ç½®
  - è¿åå¼ `position`

- **_center(positions)_**

  ä¸­å¿ç¹

  - åæ°
    - `{Array<Position>} positions`ï¼ ç¹ä½æ°æ®
  - è¿åå¼ `position`

- **_distance(positions)_**

  è·ç¦»,åä½ï¼ç±³

  - åæ°
    - `{Array<Position>} positions`ï¼ ç¹ä½æ°æ®
  - è¿åå¼ `number`

- **_heading(start,end)_**

  åè½¬è§åº¦,åä½ï¼åº¦

  - åæ°
    - `start`ï¼ å¼å§ä½ç½®
    - `end`ï¼ ç»æä½ç½®
  - è¿åå¼ `number`

- **_parabola(start, end,height,count)_**

  æç©çº¿

  - åæ°
    - `start`ï¼ å¼å§ä½ç½®
    - `end`ï¼ ç»æä½ç½®
    - `{Number} height`ï¼ æé«ç¹é«åº¦
    - `{Number} count`ï¼ ç¹ä½æ°é
  - è¿åå¼ `Array`

> [more](http://resource.dvgis.cn/cesium-docs/Math.html)

## DC.Util

> å·¥å·ç±»

### static methods

- **_uuid(prefix)_**

  çæ uuid

  - åæ°
    - `{String} prefix`ï¼åç¼ï¼é»è®¤ä¸º D
  - è¿åå¼ `string`

- **_merge(dest, ...sources)_**

  å±æ§åå¹¶

  - åæ°
    - `{Object} dest`ï¼ç®æ å¯¹è±¡
    - `{Object|Array} sources`ï¼éè¦åå¹¶çå±æ§
  - è¿åå¼ `object`

- **_emptyImageUrl()_**

  ç©ºå¾ç

- **_debounce(fn,delay)_**

  é²æ

- **_throttle(fn,delay)_**

  èæµ

## DC.DomUtil

> Dom å·¥å·ç±»

### static methods

- **_get(id)_**

  åå»º dom

  - åæ°
    - `{String} id`ï¼ è¦ç´  ID
  - è¿åå¼ `Element`

- **_create(tagName, className, [container])_**

  åå»º dom

  - åæ°
    - `{String} tagName`ï¼ æ ç­¾å
    - `{String} className`ï¼ æ ·å¼åï¼å¤ä¸ªç¨ç©ºæ ¼éå¼
    - `{Element} [container]`ï¼ ç¶å®¹å¨
  - è¿åå¼ `Element`

- **_addClass(el, name)_**

  æ·»å ç±»å

  - åæ°
    - `{Element} el`ï¼ è¦ç´ 
    - `{String} className`ï¼ æ ·å¼åï¼å¤ä¸ªç¨ç©ºæ ¼éå¼

- **_removeClass(el, name)_**

  å é¤ç±»å

  - åæ°
    - `{Element} el`ï¼ è¦ç´ 
    - `{String} className`ï¼ æ ·å¼åï¼å¤ä¸ªç¨ç©ºæ ¼éå¼

- **_addClass(el, name)_**

  æ·»å ç±»å

  - åæ°
    - `{Element} el`ï¼ è¦ç´ 
    - `{String} className`ï¼ æ ·å¼åï¼å¤ä¸ªç¨ç©ºæ ¼éå¼

- **_createSvg(width, height, path, [container])_**

  æ·»å ç±»å

  - åæ°
    - `{Number} width`ï¼ å®½åº¦
    - `{Number} height`ï¼ é«åº¦
    - `{String} path`ï¼ è·¯å¾
    - `{Element} [container]`ï¼ ç¶å®¹å¨
  - è¿åå¼ `svg`

- **_parseDom(domStr, [withWrapper], [className])_**

  å­ç¬¦ä¸²è½¬ Dom

  - åæ°
    - `{String} domStr`ï¼ dom å­ç¬¦ä¸²
    - `{Boolean} withWrapper`ï¼è¿åæ¯å¦å«æç¶å®¹å¨
    - `{String} className`ï¼ ç±»æ ·å¼åç§°
  - è¿åå¼ `Element | Nodes`

- **_enterFullscreen(el)_**

  è¿å¥å¨å±

  - åæ°
    - `{Element} el`ï¼ è¦ç´ 

- **_exitFullscreen()_**

  éåºå¨å±

- **_createVideo(url, className, [container])_**

  åå»ºè§é¢èç¹

  - åæ°
    - `{String} url`ï¼ è§é¢å°å
    - `{String} className`ï¼ æ ·å¼åï¼å¤ä¸ªç¨ç©ºæ ¼éå¼
    - `{Element} [container]`ï¼ ç¶å®¹å¨
  - è¿åå¼ `Element | Nodes`
