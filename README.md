# WeChat Mini Program Personal Developer Skill

A Codex skill for planning and building WeChat Mini Programs under an individual主体, with early checks for category eligibility, content, privacy, filing, review, and release readiness.

## Install in Codex

Copy or clone this repository so the folder containing `SKILL.md` is located at:

```text
%USERPROFILE%\.codex\skills\wechat-miniprogram-personal-dev\
```

The folder should contain `SKILL.md` and `references/`. Then start a new Codex conversation (or reload the app if the skill is not discovered) and invoke it with:

```text
$wechat-miniprogram-personal-dev
```

You can also ask naturally, for example: “用个人主体开发这个小程序，先帮我做审核风险评估。”

## Scope

This skill helps catch avoidable risks early. It cannot guarantee approval, determine eligibility without the current account/category details, or replace legal advice. Category and review rules can change, so verify current official documentation and the logged-in Mini Program console for each project.

## Publish this skill on GitHub

1. On GitHub, create a repository named `wechat-miniprogram-personal-dev`. Choose public or private as you prefer; for the simplest first push, do not initialize it with a README, license, or `.gitignore`.
2. Keep `SKILL.md`, `README.md`, and `references/` at the repository root as shown here.
3. Review the repository for AppIDs, AppSecrets, credentials, real user data, and private review accounts. Do not commit those.
4. In PowerShell, change to this folder and push it (replace `<username>` with your GitHub username):

   ```powershell
   cd path\to\wechat-miniprogram-personal-dev
   git init -b main
   git add SKILL.md README.md references
   git commit -m "Add WeChat Mini Program personal developer skill"
   git remote add origin https://github.com/<username>/wechat-miniprogram-personal-dev.git
   git push -u origin main
   ```

   GitHub may ask you to sign in through the browser / Git Credential Manager. If you already initialized Git, skip `git init -b main`; if `origin` already exists, update it with `git remote set-url origin ...`.
5. Share the repository URL. To install later, clone/download it into `%USERPROFILE%\.codex\skills\wechat-miniprogram-personal-dev\`.

Do not publish private credentials, user data, or review accounts in a public repository.
