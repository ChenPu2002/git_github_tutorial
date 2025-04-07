将本地和远程的默认分支从 `master` 改为 `main` 是个很常见的需求。以下是具体步骤，确保你的本地和远程仓库都同步更名为 `main`。

---

### 1. **重命名本地的 `master` 为 `main`**

在本地仓库中，将当前分支从 `master` 重命名为 `main`：

```bash
git branch -m master main
```

- `-m` 表示重命名分支。
- 如果当前分支是 `master`，这条命令会将它重命名为 `main`。

---

### 2. **将远程的 `master` 分支重命名为 `main`**

#### （1）推送本地 `main` 分支到远程
将本地的 `main` 分支推送到远程仓库，并设置为默认的远程分支：

```bash
git push origin main
```

#### （2）将远程的默认分支设置为 `main`

在你的远程代码托管平台（如 GitHub、GitLab 等）上，将默认分支更改为 `main`：

1. 打开你的仓库页面。
2. 进入 **Settings**（设置）。
3. 找到 **Branches**（分支）设置。
4. 将默认分支从 `master` 改为 `main`。

#### （3）删除远程的 `master` 分支（可选）
如果你确定所有工作都已迁移到 `main` 分支，可以删除远程的 `master` 分支：

```bash
git push origin --delete master
```

---

### 3. **更新本地的远程默认分支**

修改本地 Git 配置，使默认分支指向 `main`：

```bash
git fetch origin
git branch --unset-upstream
git branch -u origin/main
```

- `git branch --unset-upstream`：取消当前分支与旧远程分支的关联。
- `git branch -u origin/main`：将本地 `main` 分支与远程 `main` 分支关联起来。

---

### 4. **验证更改**

确认本地和远程分支是否都已更改为 `main`：

#### 查看本地分支
```bash
git branch
```

输出应显示 `main` 作为当前分支。

#### 查看远程分支
```bash
git branch -r
```

输出应显示远程的 `origin/main`。

---

### 5. **通知团队（如果需要）**

如果你与其他人协作，需要通知团队成员拉取更改，并更新本地默认分支：

```bash
git fetch origin
git switch main
```

---

### 总结

1. **本地分支重命名：** `git branch -m master main`
2. **推送到远程：** `git push origin main`
3. **设置远程默认分支：** 在代码托管平台上将默认分支改为 `main`。
4. **删除远程 `master` 分支（可选）：** `git push origin --delete master`
5. **更新本地与远程分支的关联：** `git branch -u origin/main`

完成后，本地和远程分支都将以 `main` 为默认分支。
