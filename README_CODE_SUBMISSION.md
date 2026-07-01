# 代码提交指南

本仓库采用“分支开发 + Pull Request 合并”的协作方式。请不要直接向主分支提交代码，所有新功能、Bug 修复和文档修改都应先提交到自己的分支，再发起 Pull Request。

## 1. 克隆仓库

```bash
git clone https://github.com/shaashou/MY-Robotics.git
cd MY-Robotics
```

## 2. 更新主分支
开始开发前，先同步最新代码：仓库主分支是 `master`

```bash
git checkout master
git pull origin master
```

## 3. 创建自己的分支

不要直接在主分支上开发。每个任务都应该创建一个单独分支：

```bash
git checkout -b feature/your-name/task-name
```
示例：

```bash
git checkout -b feature/zhangsan/path-planning
git checkout -b fix/lisi/gazebo-model-path
git checkout -b docs/wangwu/submit-guide
```

推荐分支命名：

```text
feature/姓名或昵称/功能名
fix/姓名或昵称/问题名
docs/姓名或昵称/文档名
experiment/姓名或昵称/实验名
```

## 4. 修改并检查代码

修改完成后，先查看本地改动：

```bash
git status
git diff
```

确认没有无关文件后再提交。

## 5. 提交代码

```bash
git add .
git commit -m "feat: add path planning demo"
```

推荐提交信息格式：

```text
类型: 简短说明
```

常用类型：

```text
feat      新功能
fix       修复问题
docs      文档修改
style     格式调整，不影响代码逻辑
refactor  代码重构
test      测试相关
chore     配置、工具、依赖等杂项
```

示例：

```bash
git commit -m "feat: add formation control demo"
git commit -m "fix: correct mavros launch config"
git commit -m "docs: add code submission guide"
```

请避免使用过于模糊的提交信息，例如：

```text
update
fix bug
test
修改一下
```

## 6. 推送分支

```bash
git push origin feature/your-name/task-name
```

推送成功后，打开 GitHub 仓库页面，创建 Pull Request。

## 7. 创建 Pull Request

Pull Request 中请说明：

- 本次修改了什么
- 为什么要修改
- 如何运行或测试
- 是否影响已有功能
- 是否有已知问题

PR 标题示例：

```text
feat: add path planning demo
fix: correct gazebo model path
docs: add code submission guide
```

## 8. 合并前检查

提交 Pull Request 前，请确认：

- 代码可以正常运行
- 已经完成必要测试
- 没有提交无关文件
- 没有提交缓存、日志、大文件
- 没有写死个人电脑上的绝对路径
- 新增功能有必要说明
- 修改仿真配置时说明了影响范围

## 9. 不要提交的文件

请不要提交以下文件：

```text
__pycache__/
*.pyc
build/
devel/
install/
logs/
.catkin_tools/
.vscode/
.idea/
*.bag
*.mp4
*.avi
```

## 10. 遇到冲突

如果 Pull Request 提示有冲突，先更新目标分支：

```bash
git fetch origin
git checkout feature/your-name/task-name
git merge origin/main
```

如果主分支是 `master`：

```bash
git merge origin/master
```

解决冲突后：

```bash
git add .
git commit
git push origin feature/your-name/task-name
```

如果冲突涉及他人代码，请先沟通后再修改，不要直接覆盖别人的内容。

## 11. 简短流程

```text
更新主分支
  ↓
创建自己的功能分支
  ↓
修改代码或文档
  ↓
本地测试
  ↓
提交 commit
  ↓
推送分支
  ↓
创建 Pull Request
  ↓
Review 后合并
```

## 12. 常用命令

```bash
git clone https://github.com/shaashou/MY-Robotics.git
cd MY-Robotics

git checkout main
git pull origin main

git checkout -b feature/your-name/task-name

# 修改代码或文档

git status
git add .
git commit -m "feat: describe your change"
git push origin feature/your-name/task-name
```

然后在 GitHub 上创建 Pull Request，等待团队成员 review 后合并。
