# MBZUAI Beamer 主题

基于**穆罕默德·本·扎耶德人工智能大学（MBZUAI）**品牌指南（2026年3月，V1）的 LaTeX Beamer 演示文稿主题。

## 特性

- 🎨 官方 MBZUAI 品牌配色
- 📐 16:9 宽屏布局
- 🖼️ 带有纹理背景的标题栏横幅
- 📄 自定义首页和尾页（Thank You）
- 🧱 品牌风格的 Block（标准、警告、示例）
- 📊 品牌配色表格
- 🔷 目录中的菱形标记

## 预览

<p align="center">
  <img src="assets/slides/slide-01.jpg" width="800" alt="首页"><br>
  <em>首页</em>
</p>

<p align="center">
  <img src="assets/slides/slide-02.jpg" width="800" alt="目录"><br>
  <em>目录</em>
</p>

<p align="center">
  <img src="assets/slides/slide-04.jpg" width="800" alt="内容页"><br>
  <em>内容页（Block）</em>
</p>

<p align="center">
  <img src="assets/slides/slide-05.jpg" width="800" alt="双栏布局"><br>
  <em>双栏布局</em>
</p>

<p align="center">
  <img src="assets/slides/slide-07.jpg" width="800" alt="TikZ 图表"><br>
  <em>TikZ 图表</em>
</p>

<p align="center">
  <img src="assets/slides/slide-08.jpg" width="800" alt="表格示例"><br>
  <em>表格示例</em>
</p>

<p align="center">
  <img src="assets/slides/slide-10.jpg" width="800" alt="尾页"><br>
  <em>尾页</em>
</p>

## 安装

### 方式一：本地安装（推荐）

将 `beamerthemeMBZUAI/` 目录复制到你的项目中：

```bash
cp -r beamerthemeMBZUAI/ /path/to/your/project/
```

### 方式二：TeXMF 全局安装

```bash
cp -r beamerthemeMBZUAI/ ~/Library/texmf/tex/latex/beamer/
```

## 使用方法

```latex
\documentclass[aspectratio=169, 11pt]{beamer}

\usetheme{MBZUAI}

\title[短标题]{演示文稿标题}
\subtitle{副标题}
\author[作者姓名]{作者姓名 \\ \texttt{author@mbzuai.ac.ae}}
\institute[MBZUAI]{穆罕默德·本·扎耶德人工智能大学}
\date{\today}

\begin{document}

% 首页（自动生成）
\begin{frame}[t]
\titlepage
\end{frame}

% 内容页
\section{简介}
\begin{frame}{简介}
    \begin{itemize}
        \item 你的内容
    \end{itemize}
\end{frame}

% 尾页
{
\setbeamertemplate{footline}{}
\setbeamertemplate{frametitle}{}
\begin{frame}[t]
    \mbzuaiThankYou
\end{frame}
}

\end{document}
```

## 可用颜色

| 颜色名称 | 色值 | 用途 |
|----------|------|------|
| `mbzuai-dark-navy` | `#0C2945` | 主背景、标题栏 |
| `mbzuai-navy` | `#154677` | 次背景、渐变 |
| `mbzuai-sand` | `#E5C687` | 强调元素、高亮 |
| `mbzuai-dark-sand` | `#8A764D` | 次强调色 |
| `mbzuai-light-gray` | `#F5F5F5` | Block 背景 |
| `mbzuai-text` | `#1A1A1A` | 正文文字 |
| `mbzuai-subtle` | `#666666` | 次要文字 |

使用示例：

```latex
\textcolor{mbzuai-navy}{\textbf{重要文字}}
\color{mbzuai-sand} 高亮文字
```

## 自定义

### 尾页（Thank You）

`\mbzuaiThankYou` 宏生成尾页，包含：
- 纹理背景
- 深蓝顶部栏
- "Thank You" 标题
- "Questions?" 副标题
- 作者和机构信息

### 首页

首页由 `\title`、`\subtitle`、`\author`、`\institute` 和 `\date` 自动生成，标题字号为 `\Huge`，超长时自动缩小以适应页面宽度。

## 重新生成横幅

标题栏横幅（`assets/banner-bg.pdf`）已预构建。如需重新生成：

```bash
cd assets/
pdflatex make-banner-bg.tex
cp make-banner-bg.pdf banner-bg.pdf
```

**注意：** 重新生成需要 MBZUAI 纹理素材：
`MBZUAI-Patterns/CROPS/CMYK/PDF/MBZUAI_PATTERN_CROP 01_NAVY_CMYK.pdf`

## 编译

**推荐使用 `latexmk`（自动处理多次编译）：**

```bash
cd beamerthemeMBZUAI/
latexmk -pdf demo.tex
```

**或手动编译（至少两次）：**

```bash
pdflatex demo.tex
pdflatex demo.tex
pdflatex demo.tex  # 确保所有 overlay 渲染正确
```

> **⚠️ 为什么需要多次编译？**
>
> 首页和尾页的背景（纹理、深蓝栏）使用了 TikZ 的 `remember picture, overlay` 机制，需要将节点绝对位置写入 `.aux` 文件后再次读取才能正确定位。第一次编译记录位置，第二次编译才能正确渲染背景。这是 LaTeX 的固有行为。

## 文件结构

```
beamerthemeMBZUAI/
├── beamerthemeMBZUAI.sty          # 主题入口
├── beamercolorthemeMBZUAI.sty     # 品牌颜色定义
├── beamerinnerthemeMBZUAI.sty     # 首页、尾页、Block
├── beamerouterthemeMBZUAI.sty     # 标题栏、页脚
├── beamerfontthemeMBZUAI.sty      # 字体设置
├── assets/
│   ├── banner-bg.pdf              # 标题栏横幅背景
│   ├── pattern-bg.pdf             # 首页/尾页纹理
│   ├── logo_sand.pdf              # 沙色 Logo（标题栏）
│   ├── logo_dark.pdf              # 深色 Logo（首页/尾页）
│   └── make-banner-bg.tex         # 横幅源文件
├── demo.tex                       # 示例演示文稿
├── README.md                      # 本文件
└── LICENSE                        # MIT 许可证
```

## 许可证

MIT 许可证 — 详见 [LICENSE](LICENSE)。

## 品牌指南

本主题基于 MBZUAI 官方品牌指南（2026年3月，V1）。品牌规范以官方文档为准。

**纹理素材**版权归穆罕默德·本·扎耶德人工智能大学所有，已获授权用于演示文稿。
