# 演讲比赛组卷工具 (Speech Contest Paper Builder)

一个简单易用的演讲比赛命题工具，支持题库管理、智能组卷、A/B卷生成等功能。

## 功能特点

- 📝 **题库管理**：支持手动录入和 Excel 批量导入演讲主题
- 🎯 **智能组卷**：按题型、难度、标签自动匹配生成试卷
- 📊 **A/B卷生成**：自动去重，支持难度偏移
- 📄 **导出功能**：一键导出 Word 文档，可直接打印
- 💾 **本地存储**：所有数据保存在浏览器本地，无需服务器

## 使用方式

1. 直接在浏览器中打开 `index.html` 即可使用
2. 或访问在线版本：[https://yang615-yyw.github.io/speech-builder/](https://yang615-yyw.github.io/speech-builder/)

## 题型说明

- **一句话演讲**：给出一个完整的演讲命题
- **关键词演讲**：提供一组关键词，选手需要融入演讲

## 难度说明

难度 1-5 代表演讲话题的思辨深度：
- 1-2：简单话题（个人经历、基础观点）
- 3-4：中等难度（社会现象、价值讨论）
- 5：高难度（哲学命题、批判性思维）

## 技术栈

- 纯前端实现（HTML + CSS + JavaScript）
- 使用 LocalStorage 存储数据
- 使用 SheetJS (xlsx) 处理 Excel 导入导出

## 贡献

欢迎提交 Issue 和 Pull Request！

## 许可

MIT License
