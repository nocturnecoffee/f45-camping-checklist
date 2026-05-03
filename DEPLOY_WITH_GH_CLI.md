# 用 GitHub CLI 一鍵部署

在此資料夾執行以下指令：

```bash
git init
git branch -M main
git add .
git commit -m "Deploy camping checklist site"
gh repo create nocturnecoffee/f45-camping-checklist --public --source=. --remote=origin --push
gh api -X POST repos/nocturnecoffee/f45-camping-checklist/pages \
  -f source[branch]=main \
  -f source[path]=/
```

公開網址：

```text
https://nocturnecoffee.github.io/f45-camping-checklist/
```

如果 `gh api` 那行回報 Pages 已存在，請到 GitHub repo 的 Settings → Pages 確認 branch 是 `main`、folder 是 `/(root)`。

如果你想用不同 repo 名稱，把 `f45-camping-checklist` 改掉即可。
