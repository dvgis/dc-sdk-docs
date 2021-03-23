---
sidebar: auto
---

# 教程 🌎

## 简介

### DC-SDK 是什么

**_`DC-SDK`_** 是基于开源项目 **_`Cesium`_** 进行二次开发的二三维一体的 **_`WebGis`_** 应用框架,该框架优化了 **_`Cesium`_** 的使用方式和增添了一些额外功能，旨在为开发者快速构建 **_`WebGis`_** 应用。

### 坐标系统

**`世界坐标`**

笛卡尔坐标，以椭球中心为原点的空间直角坐标系中的一个点的坐标。

**`地理坐标`**

地理坐标系，坐标原点在椭球的质心。

经度：参考椭球面上某点的大地子午面与本初子午面间的两面角。东正西负。

纬度 ：参考椭球面上某点的法线与赤道平面的夹角。北正南负。

**`屏幕坐标`**

浏览器窗口坐标

### WebGL

WebGL 是一种 JavaScript API，用于在不使用插件的情况下在任何兼容的网页浏览器中呈现交互式 2D 和 3D 图形。WebGL 完全集成到浏览器的所有网页标准中，可将影像处理和效果的 GPU 加速使用方式当做网页 Canvas 的一部分。WebGL 元素可以加入其他 HTML 元素之中并与网页或网页背景的其他部分混合。WebGL 程序由 JavaScript 编写的句柄和 OpenGL Shading Language（ **`GLSL`** ）编写的着色器代码组成。

### 三维数据

**`glb/gltf`**

GLTF 代表 Graphics Language Transmission Format（图形语言传输格式）。这种跨平台格式已成为 Web 上的 3D 对象标准。它由 OpenGL 和 Vulkan 背后的 3D 图形标准组织 Khronos 所定义，这使得 GLTF 基本上成为 3D 模型的 JPG 格式：Web 导出的通用标准。

**`3dtiles`**

3D Tiles 是用于流式传输大规模异构 3D 地理空间数据集的开放规范。3D Tiles 数据可以通过 shp、osgb(倾斜摄影)、3dmax 等数据生成。

**`geojson`**

GeoJSON 是一种对各种地理数据结构进行编码的格式，基于 Javascript 对象表示法的地理空间信息数据交换格式。GeoJSON 对象可以表示几何、特征或者特征集合。GeoJSON 支持下面几何类型：点、线、面、多点、多线、多面和几何集合。GeoJSON 里的特征包含一个几何对象和其他属性，特征集合表示一系列特征。

**`kml/czml`**

KML/CZML 是一个 JSON 格式的数据,描述 time-dynamic（时间、动态）图形场景,它描述了线、点、广告牌(标记)、模型、和其他图形原语,并指定他们如何随时间变化。

<img src="http://dc.dvgis.cn/examples/images/base/data_transform.png" style="width:100%;height:500px">

:::tip
此图转自于[西部世界](http://www.cesiumlab.com)
:::

## 准备工作

`运行环境`

DC-SDK 是依赖于[`WebGL`](#webgl)运行的一套开发平台，需要开发或运行终端配置 `独立显卡` 和安装支持 `WebGL` 的浏览器，推荐使用 **_Chrome(谷歌)_**、**_Firefox(火狐)_**

`静态服务器`

静态服务器主要用于发布地图瓦片、地形、模型数据等数据服务，如：**_Apache Http Sever_**、**_Tomcat_** 、**_Nginx_**，推荐使用 **_Nginx_**

## 安装

`NPM / YARN` **_`(推荐使用)`_**

NPM / YARN 的方式安装，它能更好地和 `webpack` 打包工具配合使用。

```shell
yarn add @dvgis/dc-sdk
-------------------------
npm install @dvgis/dc-sdk
```

```js
import DC from '@dvgis/dc-sdk/dist/dc.base.min' //基础包
import DcCore from '@dvgis/dc-sdk/dist/dc.core.min' //核心包
import DcChart from '@dvgis/dc-sdk/dist/dc.chart.min' //chart包
import DcMapv from '@dvgis/dc-sdk/dist/dc.mapv.min' //mapv包
import '@dvgis/dc-sdk/dist/dc.core.min.css' // 主要样式
```

`NPM / YARN` **_`(按需安装)`_**

```shell
yarn add @dvgis/dc-base
yarn add @dvgis/dc-core
yarn add @dvgis/dc-chart
yarn add @dvgis/dc-mapv
-------------------------
npm install @dvgis/dc-base
npm install @dvgis/dc-core
npm install @dvgis/dc-chart
npm install @dvgis/dc-mapv
```

```js
import DC from '@dvgis/dc-base' //基础包
import DcCore from '@dvgis/dc-core' //核心包
import DcChart from '@dvgis/dc-chart' //chart包
import DcMapv from '@dvgis/dc-mapv' //mapv包
import '@dvgis/dc-core/dist/dc.core.min.css' // 主要样式
```

`CDN`

[Resources 下载链接](https://github.com/dvgis/dc-sdk/releases)

```html
<!--基础包-->
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.base.min.js"></script>
<!--核心包-->
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.core.min.js"></script>
<!--chart包-->
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.chart.min.js"></script>
<!--mapv包-->
<script src="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.mapv.min.js"></script>
<!--主要样式-->
<link
  href="https://cdn.jsdelivr.net/npm/@dvgis/dc-sdk/dist/dc.core.min.css"
  rel="stylesheet"
  type="text/css"
/>
```

::: danger
请将 resources 放置工程根目录 libs/dc-sdk 下，如果放置到其他目录下，框架将无法正常运行
:::

## 配置

> 配置主要用于 `NPM / YARN` 的方式

由于 DC 框架中将 `CESIUM_BASE_URL` 设置为 `JSON.stringify('./libs/dc-sdk/resources/')`，这样需将 `Cesium` 相关的静态资源文件: `Assets`、`Workers` 、`ThirdParty` 复制到工程的 `libs/dc-sdk/resources` 目录下以保证三维场景能够正常呈现

`Webpack`

[工程模板](https://github.com/cavencj/dc-vue-app)

```js
// webpack.config.js

const path = require('path')
const CopywebpackPlugin = require('copy-webpack-plugin')
const dvgisDist = './node_modules/@dvgis'

module.exports = {
  plugins: [
    new CopyWebpackPlugin([
      {
        from: path.join(dvgisDist, 'dc-sdk/dist/resources'),
        to: 'libs/dc-sdk/resources',
      },
    ]),
  ],
}
```

`Vue2.x`

[工程模板](https://github.com/dvgis/dc-vue)

```js
// vue.config.js

const path = require('path')
const CopywebpackPlugin = require('copy-webpack-plugin')
const dvgisDist = './node_modules/@dvgis'

module.exports = {
  // 其他配置
  chainWebpack: (config) => {
    config.plugin('copy').use(CopywebpackPlugin, [
      [
        {
          from: path.join(dvgisDist, 'dc-sdk/dist/resources'),
          to: 'libs/dc-sdk/resources',
        },
      ],
    ])
  },
}
```

`Vue3.x`

[工程模板](https://github.com/dvgis/dc-vue-next)

```js
// vue.config.js

const path = require('path')
const CopywebpackPlugin = require('copy-webpack-plugin')
const dvgisDist = './node_modules/@dvgis'

module.exports = {
  // 其他配置
  chainWebpack: (config) => {
    config.plugin('copy').use(CopywebpackPlugin, [
      {
        patterns: [
          {
            from: path.join(dvgisDist, 'dc-sdk/dist/resources'),
            to: path.join(__dirname, 'dist', 'libs/dc-sdk/resources'),
          },
        ],
      },
    ])
  },
}
```

## 结构图

> DC 结构图，建议使用前先熟悉整体结构图，以便能够快速使用。

<img src="http://dc.dvgis.cn/examples/images/base/dc2.x.png" style="width:100%;height:800px">

## 群聊

<p>
<img src="http://dc.dvgis.cn/examples/images/base/q1.png?v=2" title="数字视觉"/>
<img src="http://dc.dvgis.cn/examples/images/base/q2.png?v=6" title="Cesium开心农场"/>
</p>

## 支持

> 如果 dc-sdk 能够给您带来效益，请支持一下呗~

<p style="display:flex">
<a href="https://www.paypal.com/paypalme/cavencj" target="_blank">
<img src="https://www.paypalobjects.com/images/shared/paypal-logo-129x32.svg" style="margin-top:10px;margin-right:20px" />
</a>
<img src="http://dc.dvgis.cn/examples/images/base/sponsor.jpg?v=2" title="数字视觉"/>
</p>
