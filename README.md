# Unity Cloud Shadows

## 描述
添加动画云阴影是一种快速、简单且有效的方法，可以为任何户外环境增添活力。此资源非常适合自上而下的策略游戏或城市建设游戏，而且从其他视角和其他类型的游戏中看起来也很棒。

* [**WebGL Demo**](http://entropi-games.com/files/cloud-shadows-demo/)
* [**Video**](https://youtu.be/PmlUwmOPqIw)

![Cloud Shadows Unity](http://www.entropi-games.com/files/cloud-shadows/ScreenshotTanks.png)
![Cloud Shadows Editor](http://www.entropi-games.com/files/cloud-shadows/ScreenshotEditor.png)
![Cloud Shadows Layers](https://forum.unity.com/attachments/screenshotlayers-png.203348/)
![Cloud Shadows 2D](http://www.entropi-games.com/files/cloud-shadows/Screenshot2D.png)

## 主要特点
* **自定义**： 图层系统使您能够自定义效果，使其与项目的视觉风格无缝匹配
* **编辑器预览**： 云阴影可在 Unity 场景编辑器中预览，因此调整起来简单直接
* **易于使用**： 包含完整的源代码，包括几个可立即使用的预制件和完整的文档
* **性能**： 设计时考虑了性能，运行时零分配

## 要求
* 场景需要包含用于模拟阳光的定向光。
* 该定向光需要实时渲染，不支持烘焙光照贴图（其他光源仍可使用光照贴图）。
* 渲染路径必须设置为正向渲染或延迟渲染。不支持顶点光照。

## Supported platforms
* Unity 5.2 or above
* Desktop (PC, Mac, Linux)
* Mobile
* Virtual Reality

## NOT Supported
* Scriptable Render Pipelines (URP, HDRP)
