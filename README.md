# 🤖 MenBot-Face · 表情工坊

---

## 🌟 项目简介

**MenBot-Face** 是一个复刻并改进的灵动 AI 机器人表情与交互组件库。项目采用纯原生 Web 技术（Vanilla JS + SVG + CSS），无需任何构建打包步骤，即可在任意网页中嵌入生动、Q 弹的机器人虚拟形象。

* 🌐 **在线预览**：[https://menbot-face.pages.dev](https://www.google.com/search?q=https://menbot-face.pages.dev)
* 🎯 **致敬来源**：移植与动效算法参考自 [zhulin025/LaoA-GrokBot](https://github.com/zhulin025/LaoA-GrokBot)。

---

## ✨ 核心特性

* 🎭 **高保真表情资产**：内置 26 套精细采样的矢量表情数据，覆盖 39 种细分状态（生命周期、情绪反应、代理形态、工作循环）。
* 🌊 **弹簧物理 Morphing**：基于弹簧振子模型（Spring Physics）与贝塞尔平滑算法（Bézier Curve），实现表情切换时的丝滑形变过渡。
* 👀 **灵动视线跟随**：眼睛根据鼠标在机器人面部的相对坐标产生有限偏移（Gaze Tracking），更具生命感与交互性。
* 💓 **自发生理特征**：包含自然的周期性微呼吸起伏、随机眨眼动效与点触 Q 弹抖动反馈。
* 🎨 **自由配色与交互**：支持 10 种身体主题色实时切换、随机文案气泡对话、自动轮播与手动点选模式。
* ⚡ **轻量纯原生**：单文件开箱即用，零第三方库依赖，极低内存与 CPU 占用。

---

## 📂 目录结构

```text
.
├── index.html                          # 表情工坊主程序（完整动效与交互调试面板）
├── 02-MenBot表情轮播组件-嵌入用.html      # 纯粹的轻量级组件文件（方便提取嵌入）
└── 03-MenBot轮播嵌入示例-演示页.html      # 外部页面嵌入调用示例

```

---

## 🚀 快速上手

### 1. 本地运行

克隆本仓库到本地，直接用浏览器打开 `index.html` 即可：

```bash
git clone https://github.com/MicageEritc/MenBot-Face.git
cd MenBot-Face
# 双击 index.html 或使用本地静态服务器打开

```

### 2. 嵌入已有网页

核心逻辑仅依赖一个 SVG 容器与一段轻量 JavaScript，可以直接将 `index.html` 中的 `#faceWrap` SVG 节点及对应的弹簧循环脚本复制到你的项目中。

---

## 🔬 技术实现要点

1. **多边形环形平滑 (Ring Smoothing)**：通过对封闭离散坐标点集进行 Catmull-Rom / Bézier 拟合，在保持边缘柔和的同时动态计算切线控制点。
2. **状态驱动的弹簧动力学**：

$$\text{acc} = -k \cdot (x - x_{\text{target}}) - d \cdot v$$



通过阻尼振子公式实时插值表情控制点坐标及身体缩放旋转比例。
3. **视线坐标映射**：将鼠标相对于头像中心的归一化距离 $[-1, 1]$ 映射到眼睛中心的最大偏移矢量限制范围内。

---

## 🙏 致谢与参考 (Credits)

本项目在开发过程中，表情数据提取与核心动效逻辑移植参考了开源项目：

* **[zhulin025/LaoA-GrokBot](https://github.com/zhulin025/LaoA-GrokBot)** - 感谢原作者对 GrokBot 表情资产与动效逻辑的精彩逆向与开源贡献！

---

## 📄 开源协议

本项目采用 [MIT License](https://www.google.com/search?q=LICENSE) 协议开源。
