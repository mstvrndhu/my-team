> Handoff / 交接：This folder is fully connected to Git and GitHub (mstvrndhu/my-team) with GitHub CLI authenticated; both Leader and Member can stage, commit, and push directly; details and commands are documented below. / 本專案資料夾已完整設定 Git 與 GitHub 遠端連線，GitHub CLI 亦已登入授權完畢，領隊與隊員皆可直接執行 git add、commit 與 push。

# Note for Leader · Wailan (洄瀾): Git & GitHub Setup Details / 給領隊的 Git 與 GitHub 設定說明

- Date: 2026-10-12
- From: Member · Taroko (太魯閣)
- To: Leader · Wailan (洄瀾)
- Subject: Git & GitHub integration in this folder

---

## 1. Current Status / 目前狀態

* **Local Git Repository**: Initialized on branch `main` inside this project directory (`my-team`).
* **Remote Repository**: Connected to `origin` → **`https://github.com/mstvrndhu/my-team.git`** (Public repo).
* **GitHub CLI (`gh`)**: Installed (`gh version 2.101.0`) and authenticated to account **`mstvrndhu`** via HTTPS keyring.
* **Ignored Files**: [`.gitignore`](file:///c:/Users/user/Documents/Stuff%20for%20Intro%20to%20AI%20class/my-team/.gitignore) is present in root (filters out OS and editor cache files).

---

## 2. How the Leader Can Commit and Push / 領隊如何執行提交與推送

Whenever you need to commit changes or new task notes directly, you can run the following standard commands in PowerShell / terminal:

### Step 1: Check status
```powershell
git status
```

### Step 2: Stage changes
```powershell
# Stage a specific file
git add workspace/inbox/20261012-task-name.md

# Or stage all current modifications
git add .
```

### Step 3: Commit
```powershell
git commit -m "Your descriptive commit message"
```

### Step 4: Push to GitHub
```powershell
git push
```

---

## 3. Useful Quick Commands / 實用輔助指令

* **Check commit history**: `git log --oneline -n 5`
* **Check GitHub repo status via CLI**: `gh repo view`
* **Open repo in web browser via CLI**: `gh repo view --web`
* **Revert a commit safely**: `git revert HEAD --no-edit` followed by `git push`

---

Both Leader and Member have full access to run these commands in this workspace.
