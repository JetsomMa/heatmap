---
layout: post
title: Aframe热力图heatmap组件
date: 2020-11-05
tags: Aframe   
---
## 功能介绍

支持图片渲染和点阵渲染两种格式，且支持平面渲染和立体渲染

## 源码路径

[github源码](https://github.com/jetsoman/heatmap) https://github.com/jetsoman/heatmap

## 体验路径

[热力图体验路径](https://www.mashaojie.club/github/heatmap/index.html) https://www.mashaojie.club/github/heatmap/index.html

## 接口文档

 属性 | 类型 | 描述 | 默认值
 --- | --- | --- | ---
 points | array | 生成图形的点位数据，为一维数组，与src互斥，且优先级高于src属性 | []
 show | boolean | 控制热力图层显示与隐藏 | true
 pointKey | string | 当为""时候表示points数组中只存储了热力点数据，没有坐标数据，系统将自动分配坐标；否则，则表示热力渲染所取的属性值 | ""
 space | string | 决定点位数据从[x、y]属性中获取还是从[x, z]属性中获取，为了兼容3D坐标系,当points有长度且pointKey非空时候生效  | 默认"2D"，也可取值"3D"
 minValue | number | points非空时候生效，为过滤阀值，取值0～1之间，单点除以数组中最大值作为比较值，小于阀值则会被置空 | 0,表示不进行值过滤
 gauss | number | points非空时候生效，为矩阵点进行高斯模糊算法处理的高斯数组阶数 | 4
 heightPointNumber | number | points非空时候生效，为热力数据高度方向单列点位数，2D时候对应y轴，3D时候对应z轴 | 1
 widthPointNumber | number | points非空时候生效，为热力数据宽度方向单列点位数，对应x轴 | 1
 heightStep | number | points非空时候生效，高度方向单点步长，默认单位为原子单位，2D时候对应y轴，3D时候对应z轴 | 1
 widthStep | number | points非空时候生效，宽度方向单点步长，默认单位为原子单位，对应x轴 | 1
 src | asset | 图片元素资源的ID值 (e.g. '#myImage')  |
 srcOpacity | asset | 图片元素资源的ID值 (e.g. '#myImage'),用于透明过滤背景  |
 palette | string/array | 热力色阶类型或者数组 | 'redblue'
 renderMode | string | 渲染模式 surface-面模式；particles-点阵模式 | 'surface'
 particleSize | number | 点阵单个点的大小，为小方块，renderMode取值particles时候生效 | 1.0
 ignoreZeroValues | boolean | 忽略0值，为true时候，0值位置会镂空 | true
 ignoreTransparentValues | boolean | 忽略小于0的值，为true时候，小于0值位置会镂空 | true
 stackBlurRadius | number | 设置图像圆润程度，src属性生效时候起作用 | 0
 opacityMin | number | 最小透明度，取值0～1之间 | 0
 opacityMax | number | 最大透明度，取值0～1之间 | 1

<!-- flipPalette | Flip color palette upside-down? | false
scaleOpacity | Scale opacity of peaks? | true
scaleOpacityMethod | "log","log2", log10", "linear", or "const" scaling of opacity | "log2"
opacityMin | Minimum opacity | 0.2 
opacityMax | Max opacity | 1
ignoreZeroValues | If true, zero values in the data will not be rendered (note: requires `scaleOpacity` be true) | true
ignoreTransparentValues | If true, pixels with zero opacity will not be included in the terrain mesh | true
stretch | If true, we will stretch the image values so they fill the range 0-255. | false
stackBlurRadius | Blur effect. See below. | null
stackBlurRadiusMobile | Blur effect. See below. | =stackBlurRadius
invertElevation | Default: white=1, black=0. If this is true, white=0, black=1 | false
renderMode | "surface" or "particles" | surface
wireframe | Display as wireframe? | false
emissive | Emissive color for materials | #000000
emissiveIntensity | EmissiveIntensity property for materials | 1
shininess | Shininess property for phong material | 30
metalness | Metalness property for standard material | 0.5
roughness | Roughness property for standard material | 0.5
particleSize | Particle size, for renderMode=particles | 1.0
material | Material type: can be "lambert", "phong", or "standard". Ignored if per-vertex opacity is used | "standard"
blending | Blending mode (as string, eg "THREE.AdditiveBlending") | THREE.NormalBlending
specular | Specular highlights color | #111111
loadingAnimDur | How long the loading animation runs, in ms | 1800
unloadingAnimDur | Duration, in ms | 1500
height | depth of component (on Z axis, not Y axis) |  1
width | width of component, in AFrame units | (see below) -->

## 注意事项

1、点阵属性渲染的优先级高于图片渲染的优先级

## 联系方式

QQ/WeChat：1215458034

## 参考文献

[aframe-heatmap3d](https://github.com/morandd/aframe-heatmap3d) https://github.com/morandd/aframe-heatmap3d