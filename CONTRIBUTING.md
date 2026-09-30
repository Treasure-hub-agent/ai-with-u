# 参与贡献

感谢你愿意帮助这个项目变得更好！🎉

## 提交 Issue

- 🐛 **Bug 报告**：请使用 [Bug 报告模板](.github/ISSUE_TEMPLATE/bug_report.md)，说明复现步骤、期望行为与实际行为。
- ✨ **功能建议**：请使用 [功能建议模板](.github/ISSUE_TEMPLATE/feature_request.md)，描述使用场景与期望效果。

## 提交 Pull Request

1. Fork 本仓库并创建你的分支：`git checkout -b feat/your-feature`
2. 修改内容，保持与项目现有风格一致
3. 提交 PR 时使用 [PR 模板](.github/PULL_REQUEST_TEMPLATE.md)

## 开发约定

- 本仓库是 AI Agent 使用的 skill 包，修改 `SKILL.md` 与 `extended/`、`references/`、`schema/` 时请保持格式规范
- 新增/删除/修改文件后，请重新生成 `MANIFEST.json`（每文件 sha256 + bytes，含 `total_files` / `total_bytes` 汇总；`MANIFEST.json` 自身不入清单）。生成示例：

  ```bash
  python3 - <<'EOF'
  import json, hashlib, os, datetime
  files = {}
  for root, dirs, fs in os.walk('.'):
      dirs[:] = [d for d in dirs if d != '.git']
      for f in sorted(fs):
          p = os.path.relpath(os.path.join(root, f), './')
          if p == 'MANIFEST.json':
              continue
          b = open(p, 'rb').read()
          files[p] = {"sha256": hashlib.sha256(b).hexdigest(), "bytes": len(b)}
  out = {"version": open('VERSION').read().strip(),
         "generated": datetime.datetime.now(datetime.timezone.utc).strftime('%Y-%m-%dT%H:%M:%SZ'),
         "root": ".", "files": files, "total_files": len(files),
         "total_bytes": sum(m["bytes"] for m in files.values())}
  json.dump(out, open('MANIFEST.json', 'w'), indent=2, ensure_ascii=False)
  EOF
  ```

- 版本号变更时，请同步六处版本源：`VERSION` / `package.json` / `SKILL.md`（frontmatter）/ `README.md` + `README.en.md` / `MANIFEST.json` / `CHANGELOG.md`（详细条目写入 `references/changelog.md`）
- 提交信息使用简洁的约定式前缀（`feat:` / `fix:` / `docs:` / `chore:`）

## 行为准则

请遵守 [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md)，友善交流。
