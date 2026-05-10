# Primary prompts · V-Museum / CPT208

以下提示词为**代表性主提示**（可与实际迭代中的措辞略有出入），对应仓库中的核心交付物：**过程作品集单页（`index.html` + `css/styles.css` + `js/main.js`）** 与 **`system/` 下高保真 HTML 原型**。

---

## 1 · Process Portfolio：单页结构、导航与无障碍

```
You are helping with a CPT208 HCI process portfolio for a project called "My Stories in Museums" (V-Museum).

Tech: plain HTML5 + one CSS file + minimal vanilla JS (no framework).

Tasks:
1) Build a single long-scroll index.html with semantic sections: motivation/research, user requirements, ideation, implementation, evaluation. Each section has an id matching the nav anchor links.
2) Add a sticky header with a mobile-friendly nav: a "menu" button toggles the nav list on small screens; use aria-expanded and aria-controls correctly.
3) Add a skip link as the first focusable element that jumps to #main.
4) Use Noto Sans SC + Fraunces from Google Fonts; keep typography readable and museum-adjacent (warm neutrals), not generic "AI slop" purple gradients.
5) Do not remove existing Chinese copy—only structure and classes around it.

Output: show the HTML skeleton and the exact data attributes / class names needed for the toggle script.
```

---

## 2 · Process Portfolio：响应式图集、表格与 Before/After 版式

```
In css/styles.css for the same portfolio:

1) Style .section, .subsection, .table-wrap with horizontal scroll on narrow screens so wide comparison tables don't break layout.
2) Add a responsive image gallery grid for survey charts: consistent border, subtle shadow, lazy loading on img.
3) For "iteration" visuals: layout must be (a) one full-width manuscript image on top, (b) two screenshots (Before / After) in a 2-column grid below, stacking to 1 column under ~640px. Use BEM-like classes: .before-after, .before-after__manuscript, .before-after__pair.
4) Ensure .figure > img uses height: auto and object-fit: contain where we need uncropped screenshots.

Only change CSS; list any new classes I must add to index.html.
```

---

## 3 · `js/main.js`：移动端导航切换

```
Write a small deferred vanilla JS module for the portfolio:

- Select [data-nav-toggle] and [data-nav-list].
- On click: toggle class "is-open" on the nav list; flip aria-expanded between "true" and "false".
- On Escape key: close menu and return focus to the toggle button.
- Close menu when a nav link is clicked (hash navigation).
- No jQuery; no global pollution; use strict mode.

Return the full contents of main.js only.
```

---

## 4 · System 原型（`system/index0501整合.html` 类页面）：页面壳与组件分区

```
I have a museum visitor + admin-center concept. Build a single self-contained HTML file (no build step) that prototypes:

- Top bar: logo placeholder, language toggle zh/en (toggle body class, swap text nodes or data-i18n attributes—pick one simple approach).
- Main tabs or sections: Visitor home, XR / guide experience, tour plan builder, AI memorial video flow, admin-style panel (can be shallow mock).
- Use CSS variables for colors and spacing; layout must work on 375px width without horizontal scroll on the main shell.
- Use semantic landmarks: header, main, nav, section, footer.
- Mock data only; wire buttons to console.log or simple show/hide panels.

Deliver: one HTML file with embedded <style> in head and <script> at end, heavily commented where a designer would replace copy.
```

---

## 5 · 迭代排错：移动端横向溢出与触摸目标

```
The museum prototype looks fine on desktop but on iPhone Safari there is slight horizontal overflow and some buttons feel too small.

1) Find common culprits: 100vw including scrollbar, fixed widths, long unbroken strings, negative margins.
2) Propose minimal CSS fixes: max-width: 100% on media, overflow-x: clip on body (only if safe), min-height 44px for primary buttons.
3) If you need to change HTML, keep diffs tiny and list line-level edits.

Assume files are plain HTML/CSS in a folder named system/.
```

---

## 使用说明（提交用一句话）

可将 portfolio 根目录下的 **`ai logs/`** 作为「Vibe Coding Logs」附件；若课程要求固定目录名，请将本文件夹重命名为作业说明中的确切名称（含空格与否以 rubric 为准）。
