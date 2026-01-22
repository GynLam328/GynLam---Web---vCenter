# RULES.MD - VIBE CODING WEBPAGE PROJECT (jQuery-based)
## BẮT BUỘC ĐỌC TRƯỚC MỌI PROMPT ĐỂ DETECT STATE
- **Current Version**: v1.0.0 (parse từ SUMMARY.md để update)
- **Tính năng đã implement** (từ SUMMARY.md): Navbar responsive, Login form (update khi add new)
- **Tech Stack**: HTML5, CSS3 (Flexbox/Grid), jQuery 3.7+, Semantic tags, WCAG AA
- **Coding Rules**:
  - Mobile-first: Luôn dùng media queries (@media (max-width: 768px), 480px)
  - Responsive: Flexbox/Grid, viewport meta, test iPhone/Android
  - jQuery: No-conflict, modular plugins, tránh inline JS
  - Refactor: DRY (extract utils.js), optimize CSS (no unused), accessibility (aria-labels)
  - Không duplicate features từ list trên!

## CẤU TRÚC THƯ MỤC (TẠO MỚI NẾU CHƯA CÓ)
project-root/
├── index.html # Main page
├── css/
│ └── style.css # Global styles (responsive)
├── js/
│ ├── jquery-3.7.min.js
│ ├── utils.js # Reusable jQuery plugins
│ └── app.js # Main logic
├── logs/ # Tất cả logs MD
│ ├── SUMMARY.md # Tổng quan version + features
│ ├── changes-vX.Y.Z.md # Chi tiết changes/refactor mỗi version (before/after diff)
│ └── tests-vX.Y.Z.md # Test results + Lighthouse scores
└── README.md # Deploy instructions (GitHub Pages)

- **Auto-create**: Nếu thư mục thiếu, dùng `mkdir -p css js logs` hoặc Node fs.mkdirSync.

## Workflow Bắt buộc (Mọi Prompt)
1. **Đọc State**: Parse SUMMARY.md → Update version (major.minor.patch), list features.
2. **Gen Code**: Theo prompt, tuân rules, ưu tiên mobile responsive.
3. **Review & Refactor**: Check bugs, refactor (log reasons), test responsive (simulate devices).
4. **Log**:
   - Update SUMMARY.md: `## Version v1.1.0\n- New: Feature X\n- Fixed: Mobile navbar overlap`
   - Tạo changes-v1.1.0.md: ```
     ## Changes v1.1.0
     **Prompt**: [paste prompt]
     **Before**:
     ```diff
     - Old code snippet
     + New refactored
     ```
     **Refactor Reasons**: Fixed mobile flex-wrap.
     **Lighthouse Mobile**: Score 95/100
     ```
5. **Test & Commit**: Chạy Lighthouse (CLI), log scores >90 mobile, git commit với version tag.

## Mobile Responsive Rủi ro Mitigation
- **Mandatory Checks**: Viewport `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Media: `@media (max-width: 768px) { .nav { flex-direction: column; } }`
- Test: Log screenshots/devices (Chrome DevTools), ưu tiên score mobile [web:162].
