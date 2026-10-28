# GitHub 日常使用指南（新手版）

针对你的仓库：**rickykingding/my-first-repo**
地址：https://github.com/rickykingding/my-first-repo

本机已具备：git、gh（v2.103.3）、已登录账号 `rickykingding`、git 提交身份已配置。

---

## 一、三个核心动作是什么（大白话）

### 1. 提交代码（commit + push）
- **是什么**：把你改过的文件"存档"并上传到 GitHub 仓库。
- **为什么**：让仓库始终保存最新版本，别人（或未来的你）能同步你的工作。
- **日常意思**：你写了一段代码/改了一行文档 → 存一下 → 传到网上。

### 2. 开 Issue
- **是什么**：在仓库里记一条"待办 / 问题 / 想法"，可指派、可讨论、可关闭。
- **为什么**：它是项目的"记事本 + 讨论区"，用来跟踪任务和收集反馈。
- **日常意思**：想到了要做的点、发现了 bug、有疑问 → 开一条 Issue。

### 3. 提 PR（Pull Request，拉取请求）
- **是什么**：你在一个**分支**上改了代码，请求把改动"合并"回主分支（main）。别人可以 review（审查）、评论，同意后才合并。
- **为什么**：协作开发的标配——改动不直接进主干，先经过审查，保证质量。
- **日常意思**：我做了个功能/修了个 bug → 请大家看看 → 没问题就合进去。

> 一句话区分：**Issue 是"说事"，PR 是"交活"，提交代码是"把活存上去"。**

---

## 二、方式一：网页操作（最简单，零安装，新手首选）

### 提交代码（网页加/改文件）
1. 打开 https://github.com/rickykingding/my-first-repo
2. 点绿色 **"Add file"** → 选 "Create new file"（新建）或 "Upload files"（上传）
3. 编辑内容，页面底部填一句 commit 说明 → 点 **"Commit changes"**

### 开 Issue
1. 仓库页面点 **"Issues"** 标签 → **"New issue"**
2. 填标题和内容 → **"Submit new issue"**

### 提 PR（网页改文件 → 自动提 PR）
1. 在仓库里点开某个文件 → 点右上角**铅笔图标**编辑
2. 改完后提交时，选 **"Create a new branch"**（不要直接提交到 main）
3. 提交后会弹出 **"Compare & pull request"** → 点它，填说明 → **"Create pull request"**

---

## 三、方式二：命令行（日常开发推荐，你已经配好了）

### 第一次：把仓库拉到本地（建议放常用目录，比如文稿）
```bash
gh repo clone rickykingding/my-first-repo ~/Documents/my-first-repo
cd ~/Documents/my-first-repo
```

### 提交代码
```bash
git add .                      # 把改动加入"暂存区"
git commit -m "描述你改了什么"   # 本地存档（必须写说明）
git push                       # 上传到 GitHub
```
> 第一次推送到 main 可能需：`git push -u origin main`

### 开 Issue
```bash
gh issue create --title "标题" --body "内容"
```

### 提 PR（标准流程：分支 → 改 → 推 → 提）
```bash
git checkout -b my-feature     # 新建并切换到分支
# ……编辑文件……
git add .
git commit -m "做了什么改动"
git push -u origin my-feature  # 把分支推上去
gh pr create --title "标题" --body "说明"   # 发起 PR
```
> 这正是你之前看到的演示 PR #2 走过的流程。

---

## 四、它们和"每周工作周报"的关系
- 周报自动统计**本周**新增 / 关闭的 Issue、PR 以及评论讨论。
- 你平时**越多提交、越多开 Issue / 提 PR**，周报内容就越丰富真实。
- 演示用的 **Issue #1、PR #2** 建议关闭，避免干扰以后的周报；示例分支 `demo/example-pr` 也可删除。

---

## 五、常见术语速查
| 术语 | 含义 |
| --- | --- |
| commit | 一次本地存档（带说明） |
| push | 把本地存档上传到远端仓库 |
| branch | 分支，一条独立的开发线 |
| main | 主分支，默认主干 |
| merge | 把分支的改动合并进主干 |
| review | 审查他人的代码改动 |
| clone | 把远端仓库完整下载到本地 |

---

## 六、建议你现在做的两件事
1. 把仓库克隆到常用目录：`gh repo clone rickykingding/my-first-repo ~/Documents/my-first-repo`
2. 试着在网页上开一条真实 Issue（比如"本周想学 GitHub Actions"），感受一下流程。
