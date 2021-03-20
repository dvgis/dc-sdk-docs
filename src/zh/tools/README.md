---
sidebar: auto
---

# 实用工具 🌎

三维场景中的辅助工具，方便在场景中进行各种测量和标绘

## DC.Plot

> 标绘类

### example

```js
let plot = new DC.Plot(viewer, {})
plot.draw(DC.OverlayType.POINT, (overlay) => {}, {})
```

### creation

- **_constructor(viewer,options)_**

  DC.Plot 构造函数

  - 参数
    - `{Viewer} viewer`：场景
    - `{Object} options`：属性
  - 返回值：`plot`

```json
//属性参数(可选)
{
  "icon_center": "**.png", // 自定义的中心点图标
  "icon_anchor": "**.png", //自定义的锚点图标
  "icon_midAnchor": "**.png", //自定义的中心锚点图标
  "icon_size": [12, 12] //自定义的中心锚点大小
}
```

### methods

- **_draw(type,callback,style)_**

标绘

- 参数
  - `{String} type`：覆盖物类型，参照 [OverlayType](../base/#overlaytype)
  - `{Function} callback`：标绘完成的回调函数，参数为覆盖物
  - `{Object} style`：标绘的覆盖物样式设置
- 返回值：`this`

- **_edit(overlay,callback)_**

编辑

- 参数
  - `{Overlay} overlay`：覆盖物
  - `{Function} callback`：编辑完成的回调函数，参数为覆盖物
- 返回值：`this`
