---
sidebar: auto
---

# Analysis 🌎

## DC.VideoLayer

> Inherited from [Layer](../layer/#layer)

### example

```js
let layer = new DC.VideoLayer('id')
viewer.addLayer(layer)
```

### creation

- **_constructor(id)_**

  - parameters
    - `{String} id`
  - returns `videoLayer`

## DC.CameraVideo

> Inherited from [Overlay](../overlay/#overlay)

### example

```js
let position = new DC.Position(120, 20, 200, -20, 19)
let videoEl = new document.getElementById('video')
let cameraVideo = new DC.CameraVideo(position, videoEl)
layer.addOverlay(cameraVideo)
```

### creation

- **_constructor(position, video,[maskUrl])_**

  - parameters
    - `{Position} position`
    - `{Element} video`
    - `{String} [maskUrl]`
  - returns `cameraVideo`

### properties

- `{Position} position`
- `{Element} video`
- `{String} maskUrl`

### methods

- **_showHelp(show)_**

  - parameters
    - `{Boolean} show`
  - returns `this`

- **_setStyle(style)_**

  - parameters
    - `{Object} style`
  - returns `this`

```json
// style(optional)
{
  "fov": 60,
  "near": 1,
  "far": 5000,
  "aspectRatio": 1,
  "alpha": 1,
  "clearBlack": true,
  "disViewColor": DC.Color.WHITE
}
```
