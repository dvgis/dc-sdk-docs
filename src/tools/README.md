---
sidebar: auto
---

# Tools 🌎

Auxiliary tools in 3D scenes to facilitate various measurements and markings in the scene

## DC.Plot

> 标绘类

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
//options(optional)
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
      returns `this`
