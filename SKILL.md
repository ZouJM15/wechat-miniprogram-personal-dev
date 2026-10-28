---
name: wechat-miniprogram-personal-dev
description: Help individual developers plan, build, review, and release WeChat Mini Programs, with early checks for personal-account eligibility, service categories, content rules, privacy, filing, and review readiness. Use for Mini Program product planning, implementation, pre-review audits, or rejection fixes.
---

# WeChat Mini Program development for individual developers

Help the user reduce avoidable review and compliance problems before implementation. Treat WeChat platform rules, available APIs, service categories, qualification requirements, and filing procedures as changeable. Do not promise approval or treat this checklist as a substitute for checking the live WeChat Official Accounts Platform and current official documentation.

## Start with feasibility

Before proposing architecture or writing a large feature, identify:

- Whether the account is an individual/personal主体 and its registration region.
- The Mini Program's core user benefit, target audience, data collected, user-generated content, monetization, and external services.
- The closest service category and whether that category is currently available to a personal主体; whether it requires qualifications, permits, or a non-personal主体.
- Whether the feature requires capabilities that the account type may not have, such as payment, live streaming, publishing, medical/education/financial services, or content/community functions.
- Whether ICP filing, domain filing, pre-approval, or other records/permissions are needed before launch.

Use the current service-category and qualification tables in the Mini Program console / official documentation. Never infer eligibility from another Mini Program, old articles, a sample project, or the fact that an API exists. If the service category is unavailable or the business requires an organizational主体, say so before the user invests in implementation; suggest narrowing the product to a genuinely eligible use case or changing the主体, not disguising the service.

For ambiguous or regulated products, ask only for the missing facts that change feasibility. State which points are verified, which are assumptions, and what the developer must confirm in the console.

## Work through the lifecycle

1. **Scope and category:** Map every user-visible feature and content type to a real service category. Include secondary features, not only the home page. Remove dormant or unrelated categories. Check category scope, account-type restrictions, evidence requirements, and special approvals before implementation.
2. **Content and business model:** Check both developer-provided and user-generated content. Consider text, images, audio/video, comments, uploads, search, recommendations, AI-generated content, and external links. Plan moderation/reporting/removal and escalation where users can publish content. Do not present a regulated or prohibited service as a harmless tool or personal portfolio.
3. **Privacy and permissions:** Inventory each data item, API, SDK, and backend recipient. Collect only what the core feature needs; explain purpose, use, retention, sharing, and user rights. Make the privacy policy / Mini Program privacy-protection guideline match actual code, SDK behavior, and backend processing. Request permissions in context, allow refusal where the feature can still work, and implement the current WeChat privacy authorization flow before privacy-related APIs/components. Avoid collecting sensitive information unless essential and supported by a lawful basis and adequate safeguards. Do not fabricate policy text or claim a generic template is legally sufficient.
4. **Technical readiness:** Use configured and valid HTTPS request/upload/download/socket domains, compliant server and domain records, supported APIs and components, and secure secret handling. Keep AppSecret and server credentials out of client code and Git. Provide functional pages, accurate descriptions, working navigation, and no misleading buttons, dead ends, test content, placeholder claims, or hidden functionality.
5. **Review preparation:** Test the submitted build on real WeChat clients and relevant device sizes. Exercise first launch, login/consent refusal, permission denial, empty/error/loading states, every key path, payment or gated paths if applicable, and content-reporting flows. Provide review instructions and test credentials when needed; ensure the reviewer can access the complete submitted feature without contacting the developer. Confirm the submitted category, name, screenshots, descriptions, privacy declarations, and actual behavior agree.
6. **Submit and release:** Confirm备案 and any other prerequisites in the console. Upload the intended commit/build, submit it for review, and wait for the review result. Treat audit approval and actually publishing the version as separate steps; explain the release action and rollback plan. For a rejection, translate each review note into a reproducible issue, identify the relevant screen/API/category, fix the underlying product or implementation mismatch, and resubmit. Do not recommend evasion, reviewer deception, or rotating wording to bypass checks.
7. **After launch:** Keep category, privacy declarations, domains, and descriptions aligned as features change. Monitor user reports and platform notices, keep a rollback path, and re-check current rules before adding payments, community features, data collection, or regulated content.

## Risk triage

Use these labels in project audits:

- **阻断上线** — likely category/account mismatch, missing required filing/approval, prohibited service/content, privacy flow absent for used APIs, material security issue, or review cannot reach core functionality.
- **高风险** — eligibility/qualification uncertain; sensitive or children's data; UGC/community, AI publishing, payment, advertising, location, external content, or third-party SDK behavior not yet validated.
- **需确认** — rule or account-specific status needs a current console check or official answer.
- **可整改** — a concrete implementation or submission inconsistency with a clear fix.
- **已核验** — evidence was checked against a current official source or live console; include the source/date and scope.

Do not assign a pass solely because code compiles or a similar product is already online. Give the user a short finding, evidence, owner/action, and whether it blocks proceeding.

## Content and product checks

Read [the review checklist](references/review-checklist.md) when planning features, auditing a build, or diagnosing a rejection. At minimum, flag:

- Illegal, harmful, deceptive, pornographic, gambling, violence, hate, fraud, infringement, or otherwise prohibited material and services.
- News, publishing, medical, education, finance, games, live streaming, e-commerce, social/community, and other category-sensitive offerings; validate exact current scope and required qualifications rather than relying on broad labels.
- Claims that imply guaranteed outcomes, official affiliation, professional qualifications, or capabilities the developer does not have.
- Unlicensed media, copied UI/branding, personal data exposure, unsafe user uploads, unmoderated UGC, and unauthorized external navigation.
- Incentives or coercive flows that mislead users into sharing, granting permissions, paying, inviting contacts, or providing personal information.

These are screening prompts, not a complete statement of law or platform policy. Determine the exact rule from the relevant current official source.

## Output format

For planning, provide a short feasibility verdict first, then a feature-to-category/risk table and a staged implementation plan. For a code review, list findings by severity with file/page/API evidence and a specific fix; separate verified platform requirements from recommendations. For rule questions, cite the official page and date checked. If current official sources are unavailable or conflict, say what could not be verified and identify the precise console check needed.

## GitHub / repository handling

When asked to prepare or publish this skill as a repository, keep this folder self-contained, do not include AppIDs, AppSecrets, real user data, review credentials, unpublished customer material, or local environment files. Explain that the skill reduces avoidable risk but cannot guarantee review approval. Do not create a public repository, push code, or change GitHub visibility without explicit authorization.
