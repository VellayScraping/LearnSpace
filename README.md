# LearnSpace
这是一个**单文件、无后端、本地化**的智能知识备考引擎。

它能够将普通的 Markdown 笔记文件瞬间转化为一个包含**全景思维导图**、**深度名词解释**、**智能填空背诵**和**真题模拟测试**的交互式学习系统。通过接入 OpenAI 兼容协议（如 DeepSeek、ChatGPT 等）的大模型能力，利用“随机滑动窗口”算法，它能针对你的笔记内容进行精准的即时出题与辅导。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Vue.js](https://img.shields.io/badge/vue-3.x-42b883.svg)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-3.x-38b2ac.svg)

## ✨ 核心功能 (Key Features)

### 1. 📂 本地笔记解析与可视化（暂未完善）
- **Markdown 直读**：直接导入本地 `.md` 文件，自动解析标题层级（H1-H6）。
- **交互式思维导图**：基于 ECharts 构建，支持滚轮缩放、拖拽、一键复位。
- **全局检索**：内置搜索栏，可快速定位知识节点，并在导图中高亮显示。

### 2. 🤖 AI 驱动的学习模块
利用 LLM (大语言模型) 对笔记内容进行深度理解与重组：

* **🔖 深度名词解释 (Flashcards)**
    * **语境提取**：AI 不仅解释名词，还会标注该词所属的背景（如“儒家美学”、“现代主义”）。
    * **原文溯源**：强制 AI 基于上传的笔记原文生成解释，保留长难句逻辑。
    * **防偷看设计**：解释内容默认采用**重度高斯模糊**覆盖，点击后显形，杜绝无意识的偷看。

* **📝 智能填空检测 (Cloze Test)**
    * AI 自动识别核心知识点并进行“挖空”。
    * 支持点击遮罩查看答案，适合背诵记忆。

* **✅ 全真模拟测试 (Quiz)**
    * 生成单项选择题。
    * 提供基于笔记内容的**深度解析**，知其然更知其所以然。

### 3. ⚙️ 高级控制与算法
- **章节锁定**：支持选择“全部章节”或“特定章节”进行出题，实现精准突击。
- **随机切片算法 (Random Slicing)**：针对长文本笔记，系统自动执行“随机滑动窗口”截取片段投喂给 AI，有效规避 Token 限制，同时保证多次出题能覆盖全书角落。
- **OpenAI 兼容接口**：支持自定义 API Base URL、API Key 和模型名称（完美支持 DeepSeek, Moonshot, GPT-4 等）。

---

## 🚀 快速开始 (Quick Start)

### 前置要求
- 一个现代浏览器（Chrome, Edge, Safari 等）。
- 一个 OpenAI 格式的 API Key（推荐使用 DeepSeek 以获得高性价比体验）。
- 一份 Markdown 格式的笔记文件（`.md`）。

### 安装与运行
本项目为 **Single-file HTML** 架构，无需安装 Node.js 或 Python 环境。

1.  下载本项目中的 `index.html` 文件。
2.  直接双击使用浏览器打开。
3.  点击右上角 **“导入笔记”**，选择你的复习资料。
4.  点击右上角 **“齿轮图标”** 配置 API：
    * **Base URL**: 例如 `https://api.deepseek.com` (注意不要带 `/chat/completions` 后缀)
    * **API Key**: `sk-xxxxxxxx`
    * **Model**: `deepseek-chat`
5.  开始学习！

---

## 🛠️ 技术栈 (Tech Stack)

* **Core**: Vue.js 3 (CDN 引入，轻量级响应式框架)
* **UI/Styling**: Tailwind CSS (原子化 CSS)
* **Visualization**: Apache ECharts (高性能图表库)
* **Parser**: Marked.js (Markdown 解析)
* **Icons**: FontAwesome

---

## 📸 功能预览

### 1. 智能名词卡片 (带语境与模糊遮罩)
> AI 提取核心概念，解释部分高斯模糊，点击即可背诵。

### 2. 动态思维导图
> 自动将线性笔记转化为树状知识图谱，支持缩放与搜索。

### 3. 章节精准出题
> 选择特定章节，AI 仅在该范围内生成填空题或选择题。

---

## ⚠️ 注意事项

1.  **跨域问题 (CORS)**：
    * 如果你使用第三方中转 API，请确保服务商支持跨域请求（CORS）。
    * DeepSeek 官方 API 目前支持直连。
2.  **Token 消耗**：
    * 虽然采用了切片算法优化，但高频使用仍会消耗一定的 Token，建议关注 API 余额。
3.  **数据隐私**：
    * 笔记解析完全在**本地浏览器**完成，除了发送给 AI 的切片文本外，数据不会上传至任何第三方服务器。

---

## 🤝 贡献 (Contributing)

欢迎提交 Issue 或 Pull Request 来改进 Prompt 提示词或 UI 交互体验。

## 📄 开源协议 (License)

MIT License
