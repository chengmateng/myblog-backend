---
title: 把 developerFolio 里的build文件夹发布到my-website的gh-pages 分支
abbrlink: 2fbd
date: 2024-06-09 23:21:26
tags:
---

---

# 把 developerFolio 里的build文件夹发布到my-website的gh-pages 分支


如果您希望将 `build` 文件夹的内容发布到 `my-website` 仓库的 `gh-pages` 分支，以下是具体步骤：

### 步骤 1: 克隆 `my-website` 仓库

如果您还没有克隆 `my-website` 仓库，请先克隆它：

```bash
git clone https://github.com/<username>/my-website.git
cd my-website
```

### 步骤 2: 生成 `build` 文件夹

在您的 `developerFolio` 仓库中，生成最新的 `build` 文件夹：

```bash
cd path/to/developerFolio
npm run build
```

### 步骤 3: 切换到 `gh-pages` 分支

进入 `my-website` 仓库并切换到 `gh-pages` 分支。如果该分支不存在，请创建它：

```bash
cd path/to/my-website

# 如果 gh-pages 分支已经存在
git checkout gh-pages

# 如果 gh-pages 分支不存在，创建它
git checkout -b gh-pages
```

### 步骤 4: 清空 `gh-pages` 分支中的所有文件

注意，这将删除分支中的所有文件：

```bash
git rm -rf .
```

### 步骤 5: 将 `build` 文件夹的内容复制到 `gh-pages` 分支

将 `build` 文件夹的内容复制到当前目录：

```bash
cp -r ../developerFolio/build/* .
```

### 步骤 6: 提交并推送更改到 `gh-pages` 分支

1. 添加所有更改：

    ```bash
    git add .
    ```

2. 提交更改：

    ```bash
    git commit -m "Deploy build folder to gh-pages"
    ```

3. 推送更改到远程仓库的 `gh-pages` 分支：

    ```bash
    git push origin gh-pages --force
    ```

### 完整操作示例

以下是完整的命令示例：

```bash
# 克隆 my-website 仓库
git clone https://github.com/<username>/my-website.git

# 进入 developerFolio 仓库并生成 build 文件夹
cd path/to/developerFolio
npm run build

# 进入 my-website 仓库
cd path/to/my-website

# 切换到 gh-pages 分支，如果不存在则创建它
git checkout -b gh-pages

# 清空分支内容
git rm -rf .

# 复制 build 文件夹内容到当前目录
cp -r ../developerFolio/build/* .

# 添加所有更改
git add .

# 提交更改
git commit -m "Deploy build folder to gh-pages"

# 推送更改到 gh-pages 分支
git push origin gh-pages --force
```

通过这些步骤，您可以将 `build` 文件夹的内容发布到 `my-website` 仓库的 `gh-pages` 分支。
