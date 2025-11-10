# Unity Cloud Shadows
## 参数
<img width="537" height="393" alt="image" src="https://github.com/user-attachments/assets/b17bbd1c-ba7a-447e-b08d-304204ef4f64" /><br>
- 基础部分

|参数|说明|建议|
|:--|:--:|:--:|
|Preview In Editor|是否在编辑器 Scene 视图中预览云阴影效果。取消勾选可在仅运行时显示。|建议开发调试时打开，打包前关闭可省性能。|
|Project Mode|云阴影模式。常见选项：<br>Mode 3D：基于三维云层（体积感）<br>Mode 2D：平面贴图模式（效率高）|若场景为开放户外建议用 3D 模式；<br>若仅需地面动态阴影可用 2D 模式。|
|Cloud Layers|引用的云层配置文件（ScriptableObject），定义云的噪声、密度、移动方式等。|该文件是插件的核心配置，通常命名为 Clouds_Simple_A / B / C 等。可复制修改以适配不同天气风格。|
|World Size|控制阴影投影区域在世界坐标中的范围大小。|值越大阴影分布范围越广，但分辨率分布变稀；建议与场景比例匹配，如 50~200|
|Render Texture Resolution|渲染阴影贴图的分辨率|1024 是默认值，增大会更清晰但耗性能。移动端可降到 512|

- Global Mutators（全局调制器）：这些参数用于实时全局调整阴影强度、覆盖范围、柔和度等特性。
  
|参数|说明|建议|
|:--|:--:|:--:|
|Opacity Multiplier|阴影整体不透明度乘数。数值越高阴影越深。|一般保持在 0.5~1|
|Coverage Modifier|调整云层覆盖率，类似云的稀疏程度（负值=稀疏，正值=密集）|默认 0 为原始值，-0.1 稀疏、+0.1 更密|
|Softness Modifier|控制阴影边缘柔和程度。负值使阴影更锐利，正值更柔|推荐保持 -0.05 ~ 0.1，避免过硬或模糊|
|Speed Multiplier|控制云层移动速度。正值与风向一致，负值反向|-0.5 表示反向缓慢移动。根据风向与时间匹配调整|
|Direction Modifier|控制阴影移动方向（角度，0–360°）|与太阳光方向保持一致最自然|

- Advanced 3D Settings
  
|参数|说明|建议|
|:--|:--:|:--:|
|Horizon Angle Thre|控制云阴影在地平线处的渐隐角度阈值。值越大，阴影在远处淡出更平滑。|默认 10° 足够，可适当调高到 15–20° 提升平滑度。|
|Horizon Angle Fade|控制渐隐过渡的范围宽度。|与上一个参数配合使用；较大值让阴影在地平线淡化更自然。|


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
