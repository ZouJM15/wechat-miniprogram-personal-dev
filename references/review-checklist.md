# WeChat Mini Program: early review and release checklist

Use this as a discovery checklist, not as a frozen list of current platform prohibitions. Check live official materials and the account console for the project's exact主体, category, region, feature, and release date.

## 1. Personal account and category gate

- Confirm the registered主体 and current account capabilities in the console.
- Compare the complete product experience against the current personal主体 service-category table, including secondary flows and content types.
- Check qualification/filing requirements and whether any service requires a company, government/media主体, or other approved organization.
- Validate each category against what users can actually do. Do not add irrelevant categories “just in case” or omit one to hide functionality.
- Treat monetization, paid access, advertising, transactions, payment, user publishing, and professional advice as separate eligibility questions.
- If eligibility is unclear, pause implementation of the dependent feature and request confirmation from current official documentation or platform support.

## 2. Content, claims, and moderation

For all developer-published and user-submitted content, inspect text, images, audio/video, links, search results, comments, profiles, AI output, and recommendations.

- Remove prohibited or unlawful material and services; do not implement a workaround to make them less visible to review.
- Check copyright, trademark, portrait, privacy, and attribution rights for assets and imported content.
- Do not imply government/WeChat affiliation, professional licenses, guaranteed results, or factual authority the developer cannot substantiate.
- If users can publish or share content, design review, report, block, remove, and repeat-offender handling before launch; confirm the current platform and legal duties for the exact service.
- Gate or exclude high-risk regulated topics until eligibility and required credentials are confirmed. The examples (news/publishing, medical, financial, education, games, live streaming, e-commerce, social networking) are prompts to verify, not categorical legal advice.
- Ensure any AI-generated or externally sourced content is handled in line with current rules; do not claim that a model filter alone meets platform requirements.

## 3. Personal information, privacy, and SDKs

- Inventory fields, purpose, collection moment, retention, backend destination, SDK recipient, and user-facing disclosure.
- Remove data that is not necessary for the core feature. A non-essential permission or data request must not unnecessarily block basic functionality.
- Make the published privacy-protection guideline / privacy notice accurately reflect code, SDKs, backend use, retention, sharing, and deletion/contact channels.
- Inspect SDK documentation and actual behavior; do not omit an SDK because it was added by a template or cloud provider.
- Use the currently documented WeChat privacy authorization events/APIs/components for privacy-related operations. Ensure declaration, user notice/choice, and API calls line up; handle refusal and settings changes gracefully.
- Use permission prompts only in context. Do not request location, address book, phone number, profile, album, camera, microphone, or other sensitive access at launch if it is not immediately needed.
- Protect credentials, tokens, and personal data in transit and at rest; restrict staff access, logs, exports, backups, and test fixtures.
- If minors or sensitive personal information are involved, stop for a focused legal and platform review; do not rely on a generic privacy template.

## 4. Technical and UX review

- Check all configured request, upload, download, and socket domains; HTTPS/TLS; domain and ICP status; environment separation; and server allowlists.
- Keep secrets server-side. Never ship AppSecret, private keys, database credentials, or production tokens in the Mini Program bundle or Git.
- Use supported APIs and components and verify current base-library/client compatibility.
- Ensure every declared feature works and every visible control has a meaningful result. Remove placeholders, debug panels, test data, misleading controls, empty routes, and unfinished pages.
- Verify name, icon, description, screenshots, service category, in-app copy, and actual behavior tell the same story.
- If login or gated pages are part of the core experience, give reviewers a valid test route and instructions; don't leave credentials in a public repository.
- Exercise network failures, permission refusal, privacy refusal, empty states, and malformed user input; handle errors without exposing secrets or personal data.

## 5. Filing, submission, and release

- Verify the Mini Program filing status and any pre-approval/special filing in the official console and current official guidance. Do not assume a website ICP filing alone satisfies Mini Program filing.
- Ensure主体 identity, contact, Mini Program name, service category, domains, privacy declarations, and required qualifications are accurate and consistent.
- Submit a tested build. Record the uploaded version/commit and reviewer instructions.
- After approval, explicitly publish the approved version and confirm the live version. Keep a rollback plan and monitor review notices and user feedback.
- On rejection, preserve the exact rejection text, reproduce it on the submitted version, map it to a screen/API/category, fix the underlying issue, and resubmit. Avoid repeated blind submissions.

## 6. Evidence worksheet

For each finding, record:

| Field | What to capture |
|---|---|
| Feature | What the user can do, including hidden/gated flows |
| Category | Current official category and eligibility evidence |
| Data/API/SDK | What is collected or invoked and why |
| Risk | 阻断上线 / 高风险 / 需确认 / 可整改 / 已核验 |
| Evidence | File/page/API, screenshot, console status, rejection note, or official link |
| Action | Specific owner and fix/confirmation needed |
| Checked | Date, account/region scope, and source version if shown |

