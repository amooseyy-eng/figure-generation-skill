# 运行环境

本 skill 是工作指令，不自带文件处理程序。执行环境需要能读取论文、写入项目目录，并运行生成文档和图片所需的工具。先检查已有能力，再安装缺少的组件；安装到项目环境，避免修改系统 Python。

## 常用组件

| 组件 | 用途 | 何时需要 |
| --- | --- | --- |
| Python、pip、`venv` | 运行绘图和文档脚本 | 使用 Python 自动化时 |
| `python-docx` | 读取、标注、插图和保存 DOCX | 输入或输出为 Word 时 |
| `matplotlib` | 生成科研图 PNG/SVG | 生成数据图时 |
| `python-pptx` | 生成原生图表、形状和文本可编辑的 PPTX | 生成两份演示文稿时 |
| `pandas` | 整理较大的 CSV/表格 | 数据复杂时，可选 |
| `PyMuPDF`（pip 包名 `pymupdf`） | 读取、标注和渲染 PDF | 输入或输出为 PDF 时 |
| `openpyxl` | 读取 XLSX 附件，或读写独立 XLSX 工作簿 | 提供 Excel 附件或要求 XLSX 时 |
| Node.js、npm、`@mermaid-js/mermaid-cli` | 将 `.mmd` 渲染为 SVG/PNG | 没有其他 Mermaid 渲染器时 |
| SVG 查看或渲染工具（浏览器、Inkscape 等） | 预览完整 SVG 代码并生成技术路线图 PNG | 制作技术路线图时；PNG 转换需要可用渲染器 |
| Tesseract OCR 与论文语言模型 | 读取扫描页 | 页面无法提取文字时 |
| Word/PowerPoint 或 LibreOffice Writer/Impress | 打开成品，检查分页、字体和编辑性 | 最终人工检查时推荐 |
| VS Code 与 Python 扩展 | 查看、编辑和运行生成的 Python 源码 | 使用者自行改代码时，可选 |
| 中文字体 | 避免中文标题或图注显示为方框 | 系统缺少中文字体时 |

Python 包可在项目虚拟环境中按需安装：

```text
python -m pip install python-docx matplotlib python-pptx pandas pymupdf
```

若需要读取 XLSX 附件或输出独立 XLSX，再安装 `openpyxl`。若使用 Mermaid CLI，按其官方说明安装兼容的 Node.js 和 CLI；不要把某个 Node/Python 版本写死为长期要求。首次下载依赖通常需要网络，已安装时可以离线运行。无需 GPU。

## 执行前检查

1. 检查输入是 DOCX、可提取文字的 PDF，还是扫描 PDF；检查输出目录写入权限。
2. 只检查当前任务需要的组件及其版本兼容性。中文论文检查 OCR 语言模型和可显示中文的字体；若选择技术路线图，检查 SVG 预览和 PNG 渲染能力。
3. 缺少组件时，说明用途和安装方法；先完成不依赖该组件的工作。无法渲染 Mermaid 时交付 `.mmd` 并明确图片未生成；无法可靠 OCR 时列出受影响页码。
4. 若没有 Word、PowerPoint 或 LibreOffice，仍可生成文件，但需说明未完成对应应用中的视觉检查。

## 官方资料

- [Python 下载](https://www.python.org/downloads/)；[VS Code 的 Python 环境](https://code.visualstudio.com/docs/languages/python/)
- [python-docx](https://python-docx.readthedocs.io/en/latest/user/install.html)、[Matplotlib](https://matplotlib.org/stable/install/index.html)、[python-pptx](https://python-pptx.readthedocs.io/en/latest/user/charts.html)、[PyMuPDF](https://pymupdf.readthedocs.io/en/latest/installation.html)
- [Mermaid CLI](https://github.com/mermaid-js/mermaid-cli)、[Tesseract](https://github.com/tesseract-ocr/tessdoc/blob/main/Installation.md)、[LibreOffice](https://www.libreoffice.org/download/)

