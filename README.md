WeChat Mini Program Personal Developer Skill

一个供 Codex 使用的中文 skill，帮助个人开发者在微信小程序的选题、设计和开发早期发现可能影响备案、类目、隐私合规和审核发布的问题。

## 这个 skill 能做什么

你可以让它协助：

- 开发前判断个人主体是否适合当前小程序方向，提前核对服务类目、主体限制和可能需要的资质。
- 按功能梳理内容规范、用户生成内容、隐私与权限、SDK、备案、服务器域名和技术要求。
- 在开发过程中检查方案或代码，列出审核风险和具体整改动作。
- 提审前按清单检查页面完整性、审核体验路径、测试账号、隐私声明和提审信息。
- 根据审核驳回理由定位涉及的功能或页面，分析原因并给出修复建议。

检查结果会使用以下标签：

- **阻断上线**：在解决前不建议继续提审或发布。
- **高风险**：涉及主体、资质、隐私、用户内容等重要不确定性，需要尽早核实。
- **需确认**：需要查看当前公众平台后台或向官方确认。
- **可整改**：问题明确，按建议修改后复查。
- **已核验**：已对照当前官方来源或后台状态核实，并注明核验范围和日期。

Skill 的检查范围和清单见 [`SKILL.md`](SKILL.md) 与 [`references/review-checklist.md`](references/review-checklist.md)。官方核验入口见 [`references/official-sources.md`](references/official-sources.md)。

## 如何使用

### 安装

将本仓库克隆到 Codex 个人 skills 目录。Windows PowerShell 示例：

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
git clone https://github.com/<GitHub用户名>/wechat-miniprogram-personal-dev.git `
  "$env:USERPROFILE\.codex\skills\wechat-miniprogram-personal-dev"
```

将 `<GitHub用户名>` 换成仓库所有者的用户名。如果仓库是私有的，先确保当前 Git 客户端已经获得访问权限。

macOS / Linux 示例：

```bash
mkdir -p "$HOME/.codex/skills"
git clone https://github.com/<GitHub用户名>/wechat-miniprogram-personal-dev.git \
  "$HOME/.codex/skills/wechat-miniprogram-personal-dev"
```

如果你的 Codex 使用自定义 `CODEX_HOME`，请把仓库放到 `$CODEX_HOME/skills/wechat-miniprogram-personal-dev`。也可以从 GitHub 下载 ZIP，解压后把包含 `SKILL.md` 的整个文件夹放入对应目录。安装后新开一个 Codex 对话；如果还没有发现 skill，重启 Codex 再试。

### 调用

显式调用：

```text
$wechat-miniprogram-personal-dev
先帮我评估这个个人主体小程序想法能不能做，以及有哪些审核风险：……
```

也可以在请求前加 `$wechat-miniprogram-personal-dev`，然后贴上产品需求、代码路径、隐私接口清单或审核驳回文本。例子：

```text
$wechat-miniprogram-personal-dev
我想做一个个人记账小程序，只在本地保存数据。请先做主体和类目可行性检查，再列开发前必须确认的事项。
```

```text
$wechat-miniprogram-personal-dev
请检查这个小程序的隐私授权和 SDK 使用：列出实际收集的数据、对应功能、声明是否一致，以及需要修改的代码。
```

```text
$wechat-miniprogram-personal-dev
下面是微信审核驳回理由和对应页面。请逐条解释、定位可能原因，并给出整改和重新提审前的检查项：……
```

需求越具体越好：提供主体类型、目标用户、主要功能、服务类目、是否收费、是否允许用户发布内容、使用的隐私 API/SDK，以及后台已有的备案或审核状态。不要把 AppSecret、密码、真实用户资料或公开仓库不应包含的审核凭据贴进请求或提交到仓库。

## 仓库内容

| 文件 | 用途 |
|---|---|
| `SKILL.md` | 触发条件、工作流程、风险分级和输出要求 |
| `references/review-checklist.md` | 个人主体、内容、隐私、技术、备案和提审自查项 |
| `references/official-sources.md` | 微信与政府官方核验入口及来源核查方法 |
| `README.md` | 使用者安装、调用和仓库维护说明 |

## 重要边界

服务类目、主体能力、备案流程、接口和审核规范会变化。Skill 会要求针对具体项目核对当时的微信官方文档和登录后的公众平台后台，并标出未确认事项。它能帮助提前发现常见风险，但不能保证审核通过，也不能替代平台给出的正式审核结论或法律意见。
