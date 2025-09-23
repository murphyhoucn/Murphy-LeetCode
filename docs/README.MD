# Murphy-LeetCode 🚀

![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen?style=for-the-badge&logo=github)
![MkDocs](https://img.shields.io/badge/MkDocs-Material-blue?style=for-the-badge&logo=markdown)
![Language](https://img.shields.io/badge/Language-C%2B%2B-orange?style=for-the-badge&logo=cplusplus)

> 基于 MkDocs Material 构建的 LeetCode 算法题解文档库，包含详细的解题思路、代码实现和复杂度分析。

## 📖 仓库介绍

本仓库是一个 LeetCode 算法题解的在线文档库，主要特点：

- 📚 **系统整理**：按题号顺序整理 LeetCode 经典算法题目
- 💡 **详细解析**：每道题包含问题概述、解题思路、多种解法对比
- 🎯 **C++ 实现**：主要使用 C++ 语言实现，符合 Google C++ Style Guide
- 📈 **复杂度分析**：详细标注时间复杂度和空间复杂度
- 🌐 **在线访问**：通过 GitHub Pages 自动部署，随时随地查看

**在线访问地址**：[https://murphyhoucn.github.io/Murphy-LeetCode/](https://murphyhoucn.github.io/Murphy-LeetCode/)

## 📚 关于 MkDocs

MkDocs 是一个快速、简单且华丽的静态网站生成器，专为构建项目文档而设计。

### 主要特点

- **Markdown 原生支持**：使用 Markdown 语法编写文档，简单易用
- **实时预览**：内置开发服务器，支持实时预览和热重载
- **主题丰富**：支持多种主题，本项目使用 Material for MkDocs 主题
- **插件生态**：丰富的插件系统，支持搜索、数学公式、代码高亮等功能
- **部署简单**：一键部署到 GitHub Pages、Netlify 等平台

### 为什么选择 MkDocs Material？

- 🎨 **现代化设计**：响应式设计，支持深色/浅色主题切换
- 🔍 **强大搜索**：内置全文搜索功能
- 📱 **移动端友好**：完美适配移动设备
- 🎯 **专为技术文档优化**：支持代码块、数学公式、图表等

## ⚙️ 配置 MkDocs 和 GitHub Actions

### 本地开发环境搭建

1. **克隆仓库**
   ```bash
   git clone https://github.com/murphyhoucn/Murphy-LeetCode.git
   cd Murphy-LeetCode
   ```

2. **安装依赖**
   ```bash
   pip install -r requirements.txt
   ```

3. **启动本地服务器**
   ```bash
   mkdocs serve
   ```
   访问 `http://127.0.0.1:8000` 即可预览网站

### GitHub Actions 自动部署

本项目已配置 GitHub Actions 工作流，实现以下功能：

- ✅ **自动触发**：当推送到 `main` 或 `master` 分支时自动触发
- ✅ **环境准备**：自动安装 Python 和 MkDocs 依赖
- ✅ **缓存优化**：使用缓存机制提高构建速度
- ✅ **自动部署**：构建完成后自动部署到 GitHub Pages
- ✅ **Bot 提交**：使用 `github-actions[bot]` 进行提交，保持提交历史整洁

#### 工作流配置文件

位置：`.github/workflows/main.yml`

关键配置：
```yaml
- name: Configure Git Credentials
  run: |
    git config user.name github-actions[bot]
    git config user.email 41898282+github-actions[bot]@users.noreply.github.com
```

### 启用 GitHub Pages

1. 进入仓库 Settings → Pages
2. Source 选择 "Deploy from a branch"
3. Branch 选择 "gh-pages"
4. 等待部署完成即可访问

## 📁 目录结构

```
Murphy-LeetCode/
├── .github/
│   └── workflows/
│       └── main.yml          # GitHub Actions 工作流
├── docs/                     # 文档源文件
│   ├── index.md             # 首页
│   └── CPP/                 # C++ 题解目录
│       ├── 0001.md          # 两数之和
│       ├── 0009.md          # 回文数
│       ├── 0013.md          # 罗马数字转整数
│       └── ...              # 更多题解
├── site/                     # 生成的静态网站（自动生成）
├── mkdocs.yml               # MkDocs 配置文件
├── requirements.txt         # Python 依赖
└── README.md               # 项目说明
```

## ➕ 如何添加新的题解

### 1. 创建新的 Markdown 文件

在 `docs/CPP/` 目录下创建新文件，命名格式：`题号.md`

```bash
# 例如添加题目 0100
touch docs/CPP/0100.md
```

### 2. 编写题解内容
使用以下模板格式：
```markdown
# 题号 题目名称
- ![Built with Material for MkDocs](https://img.shields.io/badge/-难度级别-颜色.svg?style=for-the-badge")
- `C++`
## 问题概述
[在此描述题目要求和示例]
## 解题思路
### Solution 1: 解法名称
- `算法标签`
- **Time:** *O(时间复杂度)*
- **Space:** *O(空间复杂度)*

// 代码块/代码实现

[解题思路说明]
### Solution 2: 另一种解法
[如果有多种解法，继续添加]
```

### 3. 更新导航配置

在 `mkdocs.yml` 的 `nav` 部分添加新页面：

```yaml
nav:
  - Index: 'index.md'
  # ... 现有页面
  - 0100 题目名称: 'CPP/0100.md'  # 新增页面
```

### 4. 提交和部署

```bash
git add .
git commit -m "add: 新增 0100 题目题解"
git push origin main
```

GitHub Actions 会自动构建并部署到 GitHub Pages。

## 🎨 难度标签颜色规范

- **Easy**：`https://img.shields.io/badge/-Easy-00a690.svg?style=for-the-badge`
- **Medium**：`https://img.shields.io/badge/-Medium-ffb800.svg?style=for-the-badge`
- **Hard**：`https://img.shields.io/badge/-Hard-ff2d55.svg?style=for-the-badge`

## 🤝 贡献指南

欢迎提交 Pull Request 来完善题解！请确保：

1. 代码符合 [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
2. 包含详细的解题思路说明
3. 标注正确的时间和空间复杂度
4. 测试代码正确性

## 📈 学习资源

- [LeetCode 官网](https://leetcode.com/)
- [LeetCode 中国](https://leetcode.cn/)
- [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)
- [大雪菜的算法基础课](https://space.bilibili.com/7836741/channel/seriesdetail?sid=369277)

## 📄 许可证

本项目采用 MIT 许可证，详见 [LICENSE](LICENSE) 文件。

---

⭐ **如果这个项目对你有帮助，请给个 Star！**
