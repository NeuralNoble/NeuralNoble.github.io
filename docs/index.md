---
hide:
  - navigation
  - feedback
  - toc
title: Home
icon: octicons/home-fill-24
---

<style>
/* ── Home page ── */
article > h1 { display: none; }

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.home-wrap {
  max-width: 960px;
  margin: 0 auto;
  padding: 1rem 0 2rem;
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 4rem;
}

.home-left {
  position: sticky;
  top: 5rem;
  align-self: start;
}

.home-right {
  min-width: 0;
}

@media (max-width: 768px) {
  .home-wrap {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
  .home-left {
    position: static;
  }
}

/* Name with blinking cursor */
.home-name {
  font-size: 1.7rem;
  font-weight: 800;
  letter-spacing: -0.03em;
  margin: 0 0 0.15rem;
  line-height: 1.15;
  font-family: var(--md-code-font-family);
}

.home-name::after {
  content: "_";
  animation: blink 1s step-end infinite;
  color: var(--md-accent-fg-color);
  font-weight: 400;
}

/* Bio */
.home-bio {
  font-size: 0.85rem;
  line-height: 1.6;
  margin-bottom: 0.8rem;
  color: var(--md-default-fg-color);
}

.home-bio a {
  font-weight: 600;
  color: var(--md-accent-fg-color);
  text-decoration: none;
  border-bottom: 1px dashed var(--md-accent-fg-color);
  transition: border-bottom-style 0.15s;
}

.home-bio a:hover {
  border-bottom-style: solid;
}

/* Social row */
.home-socials {
  display: flex;
  gap: 0.3rem;
  flex-wrap: wrap;
  margin-bottom: 0;
}

.home-socials a {
  display: inline-flex;
  align-items: center;
  gap: 0.35rem;
  padding: 0.3rem 0.7rem;
  font-size: 0.73rem;
  font-weight: 500;
  font-family: var(--md-code-font-family);
  color: var(--md-default-fg-color--light);
  border: 1px solid var(--md-default-fg-color--lightest);
  border-radius: 4px;
  text-decoration: none;
  transition: all 0.2s ease;
}

.home-socials a:hover {
  color: var(--md-accent-fg-color);
  border-color: var(--md-accent-fg-color);
  box-shadow: 0 0 8px rgba(82, 108, 254, 0.15);
}

[data-md-color-scheme="slate"] .home-socials a:hover {
  box-shadow: 0 0 10px rgba(82, 108, 254, 0.25);
}

.home-socials a svg {
  width: 0.9em;
  height: 0.9em;
}

/* Section headings — code-style brackets */
.home-section-title {
  font-size: 0.78rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--md-default-fg-color);
  font-family: var(--md-code-font-family);
  margin: 0 0 0.5rem;
}

.home-section-title::before {
  content: "\222B\00a0";
  color: var(--md-default-fg-color--light);
  font-weight: 400;
}

/* Post cards */
.home-posts {
  display: flex;
  flex-direction: column;
  gap: 0;
  margin-bottom: 0.3rem;
}

.home-post {
  display: block;
  padding: 0.55rem 0.8rem;
  border-radius: 4px;
  border-left: 2px solid transparent;
  text-decoration: none;
  color: var(--md-default-fg-color);
  transition: all 0.15s ease;
}

.home-post:hover {
  background: var(--md-code-bg-color);
  border-left-color: var(--md-accent-fg-color);
}

.home-post-date {
  font-size: 0.68rem;
  font-weight: 500;
  color: var(--md-default-fg-color--light);
  text-transform: uppercase;
  letter-spacing: 0.04em;
  font-family: var(--md-code-font-family);
  margin-bottom: 0.1rem;
}

.home-post-title {
  font-size: 0.88rem;
  font-weight: 600;
  margin-bottom: 0.15rem;
  line-height: 1.3;
}

.home-post-desc {
  font-size: 0.78rem;
  color: var(--md-default-fg-color--light);
  line-height: 1.45;
  margin: 0;
}

.home-post-badge {
  display: inline-block;
  font-size: 0.6rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  padding: 0.08rem 0.4rem;
  border-radius: 3px;
  background: var(--md-accent-fg-color--transparent);
  color: var(--md-accent-fg-color);
  font-family: var(--md-code-font-family);
  margin-left: 0.4rem;
  vertical-align: middle;
}

/* See all link */
.home-see-all {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 500;
  font-family: var(--md-code-font-family);
  color: var(--md-default-fg-color--light);
  text-decoration: none;
  padding-left: 0.8rem;
  transition: color 0.15s;
}

.home-see-all::before {
  content: "\2192\00a0";
  opacity: 0.5;
}

.home-see-all:hover {
  color: var(--md-accent-fg-color);
}

/* Divider */
.home-divider {
  border: none;
  border-top: 2px solid var(--md-default-fg-color--light);
  margin: 1.2rem 0;
}
</style>

<div class="home-wrap">

  <div class="home-left">
    <p class="home-name">Aman Anand</p>

    <p class="home-bio">
      I build things to understand them. Most of my time goes into deep learning, language models, and figuring out how intelligent systems work end to end. I like deriving the math, reading the papers, and reimplementing ideas from scratch. This site is where I write about what I learn.
    </p>
    <p class="home-bio">
      Currently training voice and perception models at <a href="https://rumik.ai/" target="_blank">Rumik AI</a>. Previously at <a href="https://www.vedantu.com/" target="_blank">Vedantu</a> and <a href="https://vverse.ai/" target="_blank">VideoVerse</a>.
    </p>

    <div class="home-socials">
      <a href="https://github.com/NeuralNoble" target="_blank">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="currentColor"><path d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"/></svg>
        GitHub
      </a>
      <a href="https://x.com/NeuralWarlock" target="_blank">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="currentColor"><path d="M18.901 1.153h3.68l-8.04 9.19L24 22.846h-7.406l-5.8-7.584-6.638 7.584H.474l8.6-9.83L0 1.154h7.594l5.243 6.932ZM17.61 20.644h2.039L6.486 3.24H4.298Z"/></svg>
        X
      </a>
      <a href="https://www.linkedin.com/in/aman-anand-10b51320b/" target="_blank">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="currentColor"><path d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2zm-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.32 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93zM6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:amananand1618@gmail.com">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="currentColor"><path d="m20 8-8 5-8-5V6l8 5 8-5m0-2H4c-1.11 0-2 .89-2 2v12a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V6a2 2 0 0 0-2-2"/></svg>
        Email
      </a>
      <a href="https://drive.google.com/file/d/1Ayas_XU3wuED2tkXwbdQnpaExunZOrQw/view?usp=sharing" target="_blank">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="16" height="16" fill="currentColor"><path d="M13 9h5.5L13 3.5zM6 2h8l6 6v12a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V4c0-1.11.89-2 2-2m9 16v-2H6v2zm3-4v-2H6v2z"/></svg>
        Resume
      </a>
    </div>
  </div>

  <div class="home-right">
    <p class="home-section-title">Latest Blog</p>

    <div class="home-posts">
      <a class="home-post" href="blog/gelu/">
        <div class="home-post-date">Nov 2025</div>
        <div class="home-post-title">Gaussian Error Linear Units (GELUs)</div>
        <p class="home-post-desc">Deriving GELU from probability basics, understanding the erf function, and why deep learning uses the tanh approximation.</p>
      </a>
    </div>

    <a class="home-see-all" href="blog/">See all posts &rarr;</a>

    <hr class="home-divider">

    <p class="home-section-title">Projects</p>

    <div class="home-posts">
      <a class="home-post" href="Projects/posts/portfolio-chatbot/">
        <div class="home-post-date">Apr 2025</div>
        <div class="home-post-title">Portfolio Chatbot</div>
        <p class="home-post-desc">A lightweight OpenAI-powered chatbot that reads a JSON resume, answers visitor questions, and pushes leads to my phone in real time.</p>
      </a>
    </div>

    <a class="home-see-all" href="Projects/">See all projects &rarr;</a>
  </div>

</div>
