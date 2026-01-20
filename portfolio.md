---
layout: page
title: Portfolio
permalink: /portfolio/
---

<div class="portfolio-header">
  <h1>PORTFOLIO</h1>
  <p class="subtitle">Lorem ipsum dolor sit amet consectetur.</p>
</div>

<div class="portfolio-grid">
  {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}" class="portfolio-card">
      <div class="card-image-box">
        <img src="{{ post.thumbnail | relative_url }}" alt="{{ post.title }}">
      </div>
      <div class="card-text-box">
        <h3 class="post-title">{{ post.title }}</h3>
        <p class="post-category">{{ post.category }}</p>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.portfolio-header { text-align: center; padding: 50px 0; }
.portfolio-header h1 { font-size: 48px; font-weight: 800; letter-spacing: 2px; margin-bottom: 10px; color: #333; }
.portfolio-header .subtitle { font-family: serif; font-style: italic; color: #888; font-size: 18px; }

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
}

.portfolio-card { text-decoration: none; background: #fff; display: block; }
.portfolio-card:hover { opacity: 0.8; }

.card-image-box img {
  width: 100%;
  aspect-ratio: 4/3;
  object-fit: cover;
  display: block;
}

.card-text-box { padding: 20px 10px; text-align: center; }
.post-title { font-size: 22px; font-weight: 700; color: #222; margin: 0; }
.post-category { font-family: serif; font-style: italic; color: #999; font-size: 14px; margin-top: 5px; }

@media (max-width: 768px) { .portfolio-grid { grid-template-columns: 1fr; } }
</style>
