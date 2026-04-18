---
title: Notes
icon: material/notebook-outline
hide:
  - toc
---

<style>
  .notes-intro {
    font-size: 0.88rem;
    color: var(--md-default-fg-color--light);
    margin-bottom: 1.8rem;
  }
  .notes-list {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }
  .note-card {
    display: block;
    padding: 1rem 1.2rem;
    border: 1px solid var(--md-default-fg-color--lightest);
    border-radius: 8px;
    text-decoration: none;
    color: var(--md-default-fg-color);
    transition: all 0.15s ease;
    position: relative;
  }
  .note-card:hover {
    border-color: var(--md-accent-fg-color);
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.06);
  }
  [data-md-color-scheme="slate"] .note-card:hover {
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.25);
  }
  .note-card-meta {
    font-family: var(--md-code-font-family);
    font-size: 0.7rem;
    color: var(--md-default-fg-color--light);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 0.3rem;
  }
  .note-card-title {
    font-family: var(--md-text-font-family);
    font-size: 1rem;
    font-weight: 700;
    color: var(--md-default-fg-color);
    margin-bottom: 0.3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 0.5rem;
  }
  .note-card:hover .note-card-title {
    color: var(--md-accent-fg-color);
  }
  .note-card-title .arrow {
    font-size: 1.1rem;
    opacity: 0.4;
    transition: all 0.15s ease;
  }
  .note-card:hover .arrow {
    opacity: 1;
    transform: translateX(3px);
    color: var(--md-accent-fg-color);
  }
  .note-card-desc {
    font-family: var(--md-text-font-family);
    font-size: 0.83rem;
    color: var(--md-default-fg-color--light);
    line-height: 1.5;
    margin: 0;
  }
</style>

# 📓 Notes

<p class="notes-intro">
Short observations, quick experiments, and things I learned that don't need a full blog post. Less polished, more frequent.<br><br>
I'm still learning, so if you spot any mistakes or think something could be done better, please point it out. I'd genuinely appreciate it 🙏
</p>

<div class="notes-list">
  <a href="broadcasting-pytorch/" class="note-card">
    <div class="note-card-meta">Apr 2026 · 3 min read</div>
    <div class="note-card-title">Broadcasting in PyTorch <span class="arrow">→</span></div>
    <p class="note-card-desc">The rules PyTorch uses to handle tensors of different shapes, with a few examples and a common gotcha to watch out for.</p>
  </a>
</div>
