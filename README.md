# 太阳系演示 · Solar System

基于 **Three.js** 的交互式太阳系科普演示：九大行星（含冥王星）轨道与自转公转、主要卫星、小行星带 / 柯伊伯带，以及适合小朋友阅读的中文科普卡片。

## 演示视频

仓库 [`demo/`](./demo/) 中附有交互录屏，可在下方直接播放（或点进文件下载）：

### 桌面端（横屏，约 17s）

全景公转 → 地球 / 土星环 / 木星卫星 → 拉远碎石带 → 暂停与时间倍速

<video src="demo/solar-demo-wide.mp4" width="100%" controls preload="metadata"></video>

### 手机竖屏（约 4s）

总览默认收起、点选地球与科普卡片

<video src="demo/solar-demo-phone.mp4" width="320" controls preload="metadata"></video>

| 文件 | 说明 |
|------|------|
| [`demo/solar-demo-wide.mp4`](./demo/solar-demo-wide.mp4) | 桌面端完整交互演示 |
| [`demo/solar-demo-phone.mp4`](./demo/solar-demo-phone.mp4) | 手机端 UI 演示 |

## 功能

- **天体**：太阳、水星、金星、地球、火星、木星、土星、天王星、海王星、冥王星、谷神星（矮行星）
- **运动**：公转 + 自转（轴倾角）、地球云层、主要卫星绕行
- **卫星**：月球、火卫一/二、伽利略四卫、土卫二/三/六、天卫三/四、海卫一、冥卫一；点击卫星可看独立科普
- **碎石带**：火星–木星间小行星带、海王星外侧柯伊伯带（尘埃粒子 + 淡雾环）
- **交互**：
  - 拖拽旋转视角、滚轮 / 双指缩放
  - 点击天体查看科普卡片
  - 暂停 / 轨道 / 碎石带 / 标签开关、时间倍速（0.05×–8×）
  - 重置视角（快捷键 `R`，暂停 `Space`，关闭面板 `Esc`）
- **贴图**：基于 NASA 数据的 2K 行星贴图（Solar System Scope，CC BY 4.0）；手机端自动降采样
- **响应式**：手机竖屏底部操作条、总览默认收起、拖拽画布自动收起卡片

## 本地运行

项目为纯静态页面，无需构建。推荐用本地 HTTP 服务打开（ES Module 需要 http 协议）：

```bash
# 在项目根目录
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

或使用任意静态服务器（如 `npx serve .`）。

## 目录结构

```
.
├── index.html          # 主页面（场景、UI、逻辑）
├── demo/               # 演示录屏（桌面 / 手机）
├── vendor/
│   ├── three.module.js # Three.js
│   └── OrbitControls.js
└── assets/
    └── textures/       # 行星 / 星空贴图（2K 与部分 1K / 8K）
```

## 贴图说明

行星与星空贴图来自 [Solar System Scope](https://www.solarsystemscope.com/textures/)（基于 NASA 影像与高程数据），许可为 **CC BY 4.0**。移动端会加载较轻的 2K 银河图，并将行星贴图降采样以节省内存。

## 浏览器支持

需要支持 WebGL 与 ES modules 的现代浏览器（Chrome / Edge / Firefox / Safari 近年版本）。手机端建议系统浏览器或 Chrome。

## 许可


贴图资源：CC BY 4.0（Solar System Scope / NASA 数据）。
