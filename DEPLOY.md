# 演讲比赛组卷工具 - 部署指南

## 项目说明

这是一个纯前端的演讲比赛命题工具，无需服务器，可直接部署到 GitHub Pages。

**项目地址**：`E:\WorkBuddy\2026-06-11-16-44-41\speech-builder`

---

## 快速部署到 GitHub Pages（3 分钟完成）

### 第一步：在 GitHub 创建仓库

1. 访问：https://github.com/new
2. **Repository name**：填写 `speech-builder`
3. 选择 **Public**
4. **不要**勾选 "Add a README file"（我们已经有了）
5. 点击 **Create repository**

### 第二步：推送代码到 GitHub

在你的电脑上打开 **Git Bash** 或 **命令提示符**，运行以下命令：

```bash
# 进入项目目录
cd E:\WorkBuddy\2026-06-11-16-44-41\speech-builder

# 添加远程仓库（替换成你的用户名）
git remote add origin https://github.com/yang615-yyw/speech-builder.git

# 推送代码（会要求输入用户名和密码）
# 用户名：yang615-yyw
# 密码：使用你的 Personal Access Token（不是 GitHub 登录密码）
git push -u origin main
```

**⚠️ 重要**：Git 推送时会要求输入密码，这里要输入你的 **Personal Access Token**（就是之前生成的那个 `ghp_` 开头的字符串），而不是 GitHub 的登录密码。

### 第三步：启用 GitHub Pages

1. 访问：https://github.com/yang615-yyw/speech-builder/settings/pages
2. **Source** 选择：**Deploy from a branch**
3. **Branch** 选择：**main** 和 **/ (root)**
4. 点击 **Save**

等待 1-2 分钟，然后访问：

**🎉 你的在线组卷工具**：https://yang615-yyyw.github.io/speech-builder/

---

## 团队协作说明

由于数据存储在浏览器 LocalStorage 中，团队成员需要：

1. 每个人访问同一个网址
2. 第一次打开时，页面会自动加载 310 个预设演讲主题
3. 如果有人添加了新题目，需要：**导出 JSON** → 发给团队 → 其他人 **导入 JSON**

**未来改进方向**：如果需要真正的多人实时协作（共享题库），需要添加后端数据库（如 Firebase、Supabase 等）。

---

## 更新题库

如果后续需要添加新的演讲主题：

1. 在网页中正常添加/编辑题目
2. 点击"导出题库"按钮，下载 JSON 文件
3. 将 JSON 文件放到仓库中，提交更新
4. 其他团队成员拉取更新后，在网页中点击"导入题库"

---

## 常见问题

### Q：推送代码时提示"Authentication failed"

**A**：确保使用的是 Personal Access Token 作为密码，而不是 GitHub 登录密码。

### Q：GitHub Pages 网址打不开

**A**：等待 1-2 分钟后再试，GitHub Pages 需要时间构建。如果还是打不开，检查：
- 仓库是否是 Public
- GitHub Pages 是否已启用（Settings → Pages）
- 仓库中是否有 `index.html` 文件

### Q：如何让团队成员都能编辑题库？

**A**：当前版本数据是本地存储的。如果需要共享题库，可以：
1. 一个人负责维护题库，定期导出 JSON 发给团队
2. 或者后续升级为使用在线数据库（需要改代码）

---

## 项目结构

```
speech-builder/
├── index.html          # 主页面（包含 310 个预设演讲主题）
├── README.md          # 项目说明
└── DEPLOY.md         # 本部署指南
```

---

**部署完成后，记得把你之前生成的 Personal Access Token 删掉**（为了安全）：

1. 访问：https://github.com/settings/tokens
2. 找到你生成的 Token
3. 点击 **Delete**
4. 确认删除

（以后需要更新代码时，再生成新的 Token 即可）
