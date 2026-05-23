# Shiguang Qingqian Personal AI Learning Site Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a responsive static personal website for 「时光清浅」 that presents an AI beginner's learning path, articles, experiments, and contact section.

**Architecture:** Use a small static site with one HTML document, one CSS file, and one JavaScript file. Content is embedded in semantic sections so the owner can update text, article cards, and project cards without learning a framework.

**Tech Stack:** HTML5, CSS3, plain JavaScript, local browser verification.

---

## File Structure

- Create: `index.html`
  - Owns the page structure, navigation, section content, article cards, experiment cards, and contact content.
- Create: `styles.css`
  - Owns all visual styling, responsive layout, colors, spacing, typography, cards, buttons, and mobile navigation states.
- Create: `script.js`
  - Owns mobile menu toggle behavior, smooth section navigation, and active navigation highlighting.
- Create: `README.md`
  - Explains how to open and edit the static website.
- Existing reference: `docs/superpowers/specs/2026-05-23-shiguang-qingqian-personal-ai-learning-site-design.md`
  - Use as the product spec while implementing.

## Visual Direction

- Background: warm white and very light gray.
- Primary color: calm blue-green.
- Text: dark gray, high contrast, readable.
- Shape: cards with subtle border and radius no larger than 8px.
- Tone: professional, clear, friendly.
- Avoid: large marketing hero, excessive gradients, purple-heavy palette, complex animation, nested cards.

---

### Task 1: Create Semantic HTML Structure

**Files:**
- Create: `index.html`

- [ ] **Step 1: Create the base HTML document**

Create `index.html` with this complete content:

```html
<!doctype html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta
      name="description"
      content="时光清浅是一个 AI 初学者的学习记录网站，记录 AI 工具、提示词、工作流和实践心得。"
    >
    <title>时光清浅 | AI 学习记录</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <header class="site-header">
      <a class="brand" href="#home" aria-label="回到首页">时光清浅</a>
      <button class="menu-toggle" type="button" aria-expanded="false" aria-controls="site-nav">
        <span class="menu-toggle__line"></span>
        <span class="menu-toggle__line"></span>
        <span class="menu-toggle__line"></span>
        <span class="sr-only">打开导航</span>
      </button>
      <nav class="site-nav" id="site-nav" aria-label="主导航">
        <a href="#home">首页</a>
        <a href="#path">学习路线</a>
        <a href="#articles">文章</a>
        <a href="#experiments">实验项目</a>
        <a href="#about">关于我</a>
      </nav>
    </header>

    <main id="home">
      <section class="hero" aria-labelledby="hero-title">
        <div class="hero__content">
          <p class="eyebrow">AI 初学者的学习记录</p>
          <h1 id="hero-title">时光清浅</h1>
          <p class="hero__lead">
            我正在学习如何把 AI 用到真实生活和工作中。这里记录我的学习路径、实践实验、提示词心得，以及一路踩过的坑。
          </p>
          <div class="hero__actions" aria-label="主要操作">
            <a class="button button--primary" href="#articles">查看学习记录</a>
            <a class="button button--secondary" href="#experiments">查看实验项目</a>
          </div>
        </div>
        <aside class="hero__note" aria-label="网站定位">
          <span class="note-label">当前阶段</span>
          <strong>从真实任务开始学习 AI</strong>
          <p>把工具、提示词、工作流和实践心得，慢慢整理成可复用的经验。</p>
        </aside>
      </section>

      <section class="section about-preview" id="about" aria-labelledby="about-title">
        <div class="section__header">
          <p class="eyebrow">About</p>
          <h2 id="about-title">关于我</h2>
        </div>
        <div class="about-preview__body">
          <p>
            你好，我是时光清浅。我不是 AI 专家，而是一个正在认真学习 AI 的普通使用者。
          </p>
          <p>
            我希望通过真实任务来理解 AI：怎么写提示词，怎么整理资料，怎么提升工作效率，怎么把想法变成可以运行的小工具。这个网站会记录我的学习过程，也欢迎你和我一起交流。
          </p>
        </div>
      </section>

      <section class="section" id="path" aria-labelledby="path-title">
        <div class="section__header">
          <p class="eyebrow">Learning Path</p>
          <h2 id="path-title">AI 学习路线</h2>
          <p>先从能用起来的地方开始，把每一次尝试都整理成下一次可以复用的方法。</p>
        </div>
        <div class="path-grid">
          <article class="path-card">
            <span>01</span>
            <h3>AI 工具入门</h3>
            <p>记录尝试过的工具和真实使用感受。</p>
          </article>
          <article class="path-card">
            <span>02</span>
            <h3>提示词写作</h3>
            <p>整理好用的提示词方法和案例。</p>
          </article>
          <article class="path-card">
            <span>03</span>
            <h3>AI 辅助办公</h3>
            <p>用 AI 做资料整理、总结、计划和表达。</p>
          </article>
          <article class="path-card">
            <span>04</span>
            <h3>AI 辅助创作</h3>
            <p>用 AI 帮助写作、设计和内容构思。</p>
          </article>
          <article class="path-card">
            <span>05</span>
            <h3>AI 辅助编程</h3>
            <p>记录从零开始尝试做网页和小工具的过程。</p>
          </article>
          <article class="path-card">
            <span>06</span>
            <h3>自动化工作流</h3>
            <p>探索如何把重复任务交给 AI 或自动化工具。</p>
          </article>
        </div>
      </section>

      <section class="section" id="articles" aria-labelledby="articles-title">
        <div class="section__header section__header--split">
          <div>
            <p class="eyebrow">Notes</p>
            <h2 id="articles-title">最新学习记录</h2>
          </div>
          <p>这些文章是学习过程的阶段性整理，不追求完美，重点是真实和可复用。</p>
        </div>
        <div class="article-list">
          <article class="article-card">
            <div class="article-card__meta">
              <time datetime="2026-05-23">2026.05.23</time>
              <span>开始学习</span>
            </div>
            <h3>我为什么开始学习 AI</h3>
            <p>记录开始学习 AI 的原因，以及我希望通过这个网站沉淀什么。</p>
          </article>
          <article class="article-card">
            <div class="article-card__meta">
              <time datetime="2026-05-23">2026.05.23</time>
              <span>提示词</span>
            </div>
            <h3>第一次认真写提示词，我发现了什么</h3>
            <p>从一句模糊需求到结构化表达，整理提示词带来的几个变化。</p>
          </article>
          <article class="article-card">
            <div class="article-card__meta">
              <time datetime="2026-05-23">2026.05.23</time>
              <span>复盘</span>
            </div>
            <h3>AI 初学者最容易犯的几个错误</h3>
            <p>把初学阶段容易出现的误解和踩坑记录下来，提醒自己慢慢改进。</p>
          </article>
          <article class="article-card">
            <div class="article-card__meta">
              <time datetime="2026-05-23">2026.05.23</time>
              <span>办公</span>
            </div>
            <h3>用 AI 帮我整理资料的一次尝试</h3>
            <p>记录一次资料整理任务中，AI 哪些地方有帮助，哪些地方还需要人工判断。</p>
          </article>
          <article class="article-card">
            <div class="article-card__meta">
              <time datetime="2026-05-23">2026.05.23</time>
              <span>建站</span>
            </div>
            <h3>我如何让 AI 帮我规划一个个人网站</h3>
            <p>从网站定位、读者、风格到首页结构，记录一次 AI 协作设计过程。</p>
          </article>
        </div>
      </section>

      <section class="section" id="experiments" aria-labelledby="experiments-title">
        <div class="section__header">
          <p class="eyebrow">Experiments</p>
          <h2 id="experiments-title">实验项目</h2>
          <p>用小任务验证想法，记录问题、工具和当前状态。</p>
        </div>
        <div class="experiment-grid">
          <article class="experiment-card">
            <div class="status status--active">进行中</div>
            <h3>个人网站搭建实验</h3>
            <p>用 AI 帮助我从想法到网站设计。</p>
            <dl>
              <div>
                <dt>问题</dt>
                <dd>如何把学习记录整理成一个清晰的网站？</dd>
              </div>
              <div>
                <dt>工具</dt>
                <dd>AI 对话工具、代码助手</dd>
              </div>
            </dl>
          </article>
          <article class="experiment-card">
            <div class="status">计划中</div>
            <h3>提示词整理库</h3>
            <p>收集自己常用的提示词模板。</p>
            <dl>
              <div>
                <dt>问题</dt>
                <dd>怎样把零散提示词沉淀成可复用模板？</dd>
              </div>
              <div>
                <dt>工具</dt>
                <dd>文档工具、AI 对话工具</dd>
              </div>
            </dl>
          </article>
          <article class="experiment-card">
            <div class="status">计划中</div>
            <h3>AI 学习周记</h3>
            <p>每周总结一次 AI 使用心得。</p>
            <dl>
              <div>
                <dt>问题</dt>
                <dd>怎样让学习过程持续、可回顾？</dd>
              </div>
              <div>
                <dt>工具</dt>
                <dd>AI 总结工具、个人笔记</dd>
              </div>
            </dl>
          </article>
        </div>
      </section>

      <section class="contact" aria-labelledby="contact-title">
        <div>
          <p class="eyebrow">Contact</p>
          <h2 id="contact-title">一起交流 AI 的真实用法</h2>
        </div>
        <p>
          如果你也在学习 AI，或者想交流 AI 在工作和生活里的真实用法，欢迎联系我。
        </p>
        <a class="button button--primary" href="#articles">先看看学习记录</a>
      </section>
    </main>

    <footer class="site-footer">
      <p>© 2026 时光清浅 · AI 学习记录</p>
    </footer>

    <script src="script.js"></script>
  </body>
</html>
```

- [ ] **Step 2: Verify the HTML file exists**

Run:

```bash
ls -la index.html
```

Expected: output includes `index.html`.

---

### Task 2: Add Base Styling and Responsive Layout

**Files:**
- Create: `styles.css`
- Modify: `index.html`

- [ ] **Step 1: Create the stylesheet**

Create `styles.css` with this complete content:

```css
:root {
  --bg: #fbfcfb;
  --surface: #ffffff;
  --surface-muted: #f2f6f5;
  --text: #23302f;
  --muted: #64716f;
  --line: #dce6e3;
  --primary: #1f7a74;
  --primary-dark: #155e59;
  --accent: #2b6f9f;
  --shadow: 0 16px 40px rgba(34, 48, 47, 0.08);
  --radius: 8px;
  font-family: "PingFang SC", "Microsoft YaHei", "Noto Sans CJK SC", system-ui, sans-serif;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  background: var(--bg);
  color: var(--text);
  font-size: 16px;
  line-height: 1.7;
}

a {
  color: inherit;
  text-decoration: none;
}

p,
h1,
h2,
h3 {
  margin-top: 0;
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

.site-header {
  position: sticky;
  top: 0;
  z-index: 20;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  min-height: 72px;
  padding: 0 6vw;
  background: rgba(251, 252, 251, 0.92);
  border-bottom: 1px solid rgba(220, 230, 227, 0.9);
  backdrop-filter: blur(12px);
}

.brand {
  color: var(--text);
  font-size: 20px;
  font-weight: 700;
}

.site-nav {
  display: flex;
  align-items: center;
  gap: 22px;
  color: var(--muted);
  font-size: 15px;
}

.site-nav a {
  padding: 8px 0;
  border-bottom: 2px solid transparent;
}

.site-nav a:hover,
.site-nav a.is-active {
  color: var(--primary);
  border-color: var(--primary);
}

.menu-toggle {
  display: none;
  width: 42px;
  height: 42px;
  padding: 9px;
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius);
}

.menu-toggle__line {
  display: block;
  width: 100%;
  height: 2px;
  margin: 5px 0;
  background: var(--text);
}

.hero {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 360px;
  gap: 40px;
  align-items: end;
  max-width: 1120px;
  min-height: calc(100vh - 72px);
  margin: 0 auto;
  padding: 88px 24px 72px;
}

.hero__content {
  max-width: 720px;
}

.eyebrow {
  margin-bottom: 12px;
  color: var(--primary);
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0;
  text-transform: uppercase;
}

h1 {
  margin-bottom: 22px;
  color: var(--text);
  font-size: clamp(48px, 8vw, 88px);
  line-height: 1.05;
  letter-spacing: 0;
}

h2 {
  margin-bottom: 14px;
  font-size: clamp(28px, 4vw, 42px);
  line-height: 1.2;
  letter-spacing: 0;
}

h3 {
  margin-bottom: 10px;
  font-size: 21px;
  line-height: 1.35;
}

.hero__lead {
  max-width: 640px;
  margin-bottom: 30px;
  color: var(--muted);
  font-size: 20px;
}

.hero__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
}

.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 46px;
  padding: 10px 18px;
  border: 1px solid var(--primary);
  border-radius: var(--radius);
  font-weight: 700;
  transition: background 160ms ease, color 160ms ease, border-color 160ms ease;
}

.button--primary {
  background: var(--primary);
  color: #ffffff;
}

.button--primary:hover {
  background: var(--primary-dark);
  border-color: var(--primary-dark);
}

.button--secondary {
  background: transparent;
  color: var(--primary);
}

.button--secondary:hover {
  background: var(--surface-muted);
}

.hero__note {
  padding: 24px;
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
}

.hero__note strong {
  display: block;
  margin: 8px 0 10px;
  font-size: 22px;
  line-height: 1.35;
}

.hero__note p {
  margin-bottom: 0;
  color: var(--muted);
}

.note-label,
.status {
  display: inline-flex;
  align-items: center;
  min-height: 28px;
  padding: 3px 10px;
  color: var(--primary-dark);
  background: #e8f3f1;
  border-radius: 999px;
  font-size: 13px;
  font-weight: 700;
}

.section {
  max-width: 1120px;
  margin: 0 auto;
  padding: 76px 24px;
}

.section__header {
  max-width: 720px;
  margin-bottom: 30px;
}

.section__header p {
  color: var(--muted);
}

.section__header--split {
  display: grid;
  grid-template-columns: 1fr minmax(240px, 420px);
  gap: 32px;
  align-items: end;
  max-width: none;
}

.about-preview {
  display: grid;
  grid-template-columns: 320px minmax(0, 1fr);
  gap: 40px;
  border-top: 1px solid var(--line);
  border-bottom: 1px solid var(--line);
}

.about-preview__body {
  color: var(--muted);
  font-size: 18px;
}

.path-grid,
.experiment-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 18px;
}

.path-card,
.article-card,
.experiment-card {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius);
}

.path-card {
  padding: 24px;
}

.path-card span {
  display: inline-block;
  margin-bottom: 18px;
  color: var(--accent);
  font-weight: 800;
}

.path-card p,
.article-card p,
.experiment-card p {
  margin-bottom: 0;
  color: var(--muted);
}

.article-list {
  display: grid;
  gap: 14px;
}

.article-card {
  display: grid;
  grid-template-columns: 180px minmax(0, 1fr) minmax(220px, 340px);
  gap: 22px;
  align-items: start;
  padding: 22px;
}

.article-card__meta {
  display: flex;
  flex-direction: column;
  gap: 8px;
  color: var(--muted);
  font-size: 14px;
}

.article-card__meta span {
  width: fit-content;
  padding: 2px 8px;
  color: var(--primary-dark);
  background: var(--surface-muted);
  border-radius: 999px;
  font-weight: 700;
}

.experiment-card {
  padding: 24px;
}

.status {
  margin-bottom: 18px;
  background: #eef2f2;
  color: var(--muted);
}

.status--active {
  background: #e8f3f1;
  color: var(--primary-dark);
}

dl {
  margin: 22px 0 0;
}

dl div {
  padding-top: 14px;
  border-top: 1px solid var(--line);
}

dl div + div {
  margin-top: 14px;
}

dt {
  color: var(--text);
  font-weight: 800;
}

dd {
  margin: 4px 0 0;
  color: var(--muted);
}

.contact {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(220px, 420px) auto;
  gap: 28px;
  align-items: center;
  max-width: 1120px;
  margin: 40px auto 80px;
  padding: 34px 24px;
  border-top: 1px solid var(--line);
  border-bottom: 1px solid var(--line);
}

.contact p {
  margin-bottom: 0;
  color: var(--muted);
}

.site-footer {
  padding: 28px 24px;
  color: var(--muted);
  text-align: center;
  border-top: 1px solid var(--line);
}

.site-footer p {
  margin-bottom: 0;
}

@media (max-width: 860px) {
  .site-header {
    min-height: 64px;
  }

  .menu-toggle {
    display: block;
  }

  .site-nav {
    position: absolute;
    top: 64px;
    right: 6vw;
    left: 6vw;
    display: none;
    flex-direction: column;
    align-items: stretch;
    gap: 0;
    padding: 10px;
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
  }

  .site-nav.is-open {
    display: flex;
  }

  .site-nav a {
    padding: 12px;
  }

  .hero {
    grid-template-columns: 1fr;
    min-height: auto;
    padding-top: 68px;
  }

  .section,
  .hero,
  .contact {
    padding-right: 18px;
    padding-left: 18px;
  }

  .about-preview,
  .section__header--split,
  .contact {
    grid-template-columns: 1fr;
  }

  .path-grid,
  .experiment-grid {
    grid-template-columns: 1fr;
  }

  .article-card {
    grid-template-columns: 1fr;
    gap: 12px;
  }
}

@media (max-width: 520px) {
  body {
    font-size: 15px;
  }

  h1 {
    font-size: 48px;
  }

  .hero__lead,
  .about-preview__body {
    font-size: 17px;
  }

  .hero__actions,
  .contact .button {
    width: 100%;
  }

  .button {
    width: 100%;
  }
}
```

- [ ] **Step 2: Verify stylesheet is linked**

Run:

```bash
rg -n "styles.css" index.html
```

Expected: output includes `<link rel="stylesheet" href="styles.css">`.

- [ ] **Step 3: Verify responsive CSS exists**

Run:

```bash
rg -n "@media \\(max-width: 860px\\)|@media \\(max-width: 520px\\)" styles.css
```

Expected: output includes both media query lines.

---

### Task 3: Add Mobile Navigation and Active Link Behavior

**Files:**
- Create: `script.js`
- Modify: `index.html`

- [ ] **Step 1: Create JavaScript behavior**

Create `script.js` with this complete content:

```javascript
const menuToggle = document.querySelector(".menu-toggle");
const siteNav = document.querySelector(".site-nav");
const navLinks = Array.from(document.querySelectorAll(".site-nav a"));
const sections = navLinks
  .map((link) => document.querySelector(link.getAttribute("href")))
  .filter(Boolean);

function closeMenu() {
  siteNav.classList.remove("is-open");
  menuToggle.setAttribute("aria-expanded", "false");
}

menuToggle.addEventListener("click", () => {
  const isOpen = siteNav.classList.toggle("is-open");
  menuToggle.setAttribute("aria-expanded", String(isOpen));
});

navLinks.forEach((link) => {
  link.addEventListener("click", () => {
    closeMenu();
  });
});

const observer = new IntersectionObserver(
  (entries) => {
    entries.forEach((entry) => {
      if (!entry.isIntersecting) {
        return;
      }

      const activeLink = navLinks.find((link) => link.getAttribute("href") === `#${entry.target.id}`);
      navLinks.forEach((link) => link.classList.toggle("is-active", link === activeLink));
    });
  },
  {
    rootMargin: "-35% 0px -55% 0px",
    threshold: 0
  }
);

sections.forEach((section) => observer.observe(section));
```

- [ ] **Step 2: Verify JavaScript is linked**

Run:

```bash
rg -n "script.js" index.html
```

Expected: output includes `<script src="script.js"></script>`.

- [ ] **Step 3: Verify menu behavior selectors match HTML**

Run:

```bash
rg -n "menu-toggle|site-nav|is-open|is-active" index.html styles.css script.js
```

Expected: output includes matching references in all three files.

---

### Task 4: Add Maintenance Documentation

**Files:**
- Create: `README.md`

- [ ] **Step 1: Create README**

Create `README.md` with this complete content:

```markdown
# 时光清浅

这是一个静态个人网站，用来记录 AI 初学过程、学习路线、文章和实验项目。

## 打开网站

直接在浏览器中打开 `index.html` 即可预览。

## 文件说明

- `index.html`：页面内容，包括首页介绍、学习路线、文章、实验项目和联系方式。
- `styles.css`：页面样式，包括颜色、排版、布局和移动端适配。
- `script.js`：移动端导航和当前导航高亮。

## 更新文章

在 `index.html` 中搜索 `article-card`，复制一段文章卡片并修改：

- 日期：`time datetime`
- 标签：文章分类
- 标题：`h3`
- 摘要：`p`

## 更新实验项目

在 `index.html` 中搜索 `experiment-card`，复制一段项目卡片并修改：

- 状态：计划中、进行中、已完成
- 项目名称：`h3`
- 目标说明：`p`
- 问题和工具：`dl` 中的内容

## 后续可改进

- 补充邮箱、微信或其他社交链接。
- 给文章增加独立详情页。
- 给实验项目增加完成后的复盘链接。
```

- [ ] **Step 2: Verify README content**

Run:

```bash
rg -n "打开网站|更新文章|更新实验项目" README.md
```

Expected: output includes all three headings.

---

### Task 5: Verify the Static Website End to End

**Files:**
- Verify: `index.html`
- Verify: `styles.css`
- Verify: `script.js`
- Verify: `README.md`

- [ ] **Step 1: Confirm all expected files exist**

Run:

```bash
ls -la index.html styles.css script.js README.md
```

Expected: output lists all four files.

- [ ] **Step 2: Check required site content exists**

Run:

```bash
rg -n "时光清浅|AI 学习路线|最新学习记录|实验项目|一起交流 AI 的真实用法" index.html
```

Expected: output includes all five phrases.

- [ ] **Step 3: Start a local static server**

Run:

```bash
python3 -m http.server 4173
```

Expected: output includes `Serving HTTP on`.

- [ ] **Step 4: Open and inspect the site**

Open:

```text
http://localhost:4173
```

Expected:

- The first viewport clearly shows 「时光清浅」 and the AI learning record positioning.
- Navigation links are visible on desktop.
- On a narrow viewport, the menu button opens and closes the navigation.
- Buttons jump to the article and experiment sections.
- Text does not overlap on desktop or mobile.
- The design reads as clean and professional, not like an enterprise landing page.

- [ ] **Step 5: Stop the local server**

Stop the server with `Ctrl+C`.

- [ ] **Step 6: Check repository state or file list**

Because the current workspace is not a git repository, run:

```bash
find . -maxdepth 3 -type f | sort
```

Expected: output includes the site files and the design/plan documents.

---

## Self-Review Checklist

- Spec coverage:
  - Website name and AI learning positioning are implemented in Task 1.
  - Navigation, hero, about, learning path, articles, experiments, and contact sections are implemented in Task 1.
  - Clean, professional, friendly visual direction is implemented in Task 2.
  - Mobile usability is implemented in Tasks 2 and 3.
  - Maintenance instructions are implemented in Task 4.
- Placeholder scan:
  - The plan does not use fake email addresses or unfinished placeholder fields.
  - No task contains incomplete marker instructions.
- Type and selector consistency:
  - `.menu-toggle`, `.site-nav`, `.is-open`, and `.is-active` are defined consistently across HTML, CSS, and JavaScript.
