---
sidebar: auto
---

# Tools 🌎

Auxiliary tools in 3D scenes to facilitate various measurements and markings in the scene

## DC.Plot

> PLot Tool

### example

```js
let plot = new DC.Plot(viewer, {})
plot.draw(DC.OverlayType.POINT, (overlay) => {}, {})
```

### creation

- **_constructor(viewer,[options])_**

  - parameters
    - `{Viewer} viewer`：场景
    - `{Object} options`：属性
  - returns `plot`

```json
// options(optional)
{
  "icon_center": "**.png",
  "icon_anchor": "**.png",
  "icon_midAnchor": "**.png",
  "icon_size": [12, 12]
}
```

### methods

- **_draw(type,callback,style)_**

  - parameters
    - `{String} type` [OverlayType](../base/#overlaytype)
    - `{Function} callback`
    - `{Object} style`
  - returns `this`

- **_edit(overlay,callback)_**

  - parameters
    - `{Overlay} overlay`
    - `{Function} callback`
  - returns `this`

## DC.PositionEditor

> 位置编辑工具

### example

```js
let positionEditor = new DC.PositionEditor(viewer)
```

### creation

- **_constructor(viewer,[options])_**

  - parameters
    - `{Viewer} viewer`
    - `{Object} options`
  - returns `positionEditor`

```json
// options(optional)
{
  "arrow": true, // whether the auxiliary axis is an arrow
  "width": 8, // auxiliary axis width
  "depthFail": true, // whether the auxiliary axis supports depth test
  "axisLineScale": 1 // auxiliary axis scale
}
```

### properties

- `{Overlay} overlay` **_`readonly`_**

### methods

- **_activate(type, callback)_**

  - parameters
    - `{String} type`
    - `{Function} callback` parameter ：position
  - returns `this`

- **_deactivate()_**

  - returns `this`
