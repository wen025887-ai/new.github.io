---
layout: page
title: Portfolio
permalink: /portfolio/
---

<div class="portfolio-wrapper">
  <div class="portfolio-intro">
    <h1 class="portfolio-main-title">PORTFOLIO</h1>
    <p class="portfolio-subtitle">Lorem ipsum dolor sit amet consectetur.</p>
  </div>

  <div class="portfolio-grid">
    {% for post in site.posts %}
      {% if post.thumbnail %}
      <div class="portfolio-item">
        <a href="{{ post.url | relative_url }}">
          <div class="image-container">
            <img src="{{ post.thumbnail | relative_url }}" alt="{{ post.title }}" onerror="this.src='https://via.placeholder.com/400x300?text=Image+Missing'">
          </div>
          <div class="text-container">
            <h3>{{ post.title }}</h3>
            <span>{{ post.category | default: "Project" }}</span>
          </div>
        </a>
      </div>
      {% endif %}
    {% endfor %}
  </div>
</div>

<style>
/* 避免影響到主題 Banner，我們使用專屬類名 */
.portfolio-wrapper {
  max-width: 1100px;
  margin: 0 auto;
  padding: 40px 20px;
}

.portfolio-intro {
  text-align: center;
  margin-bottom: 50px;
}

.portfolio-main-title {
  font-size: 2.5rem;
  font-weight: 800;
  color: #333;
  margin-bottom: 10px;
  letter-spacing: 2px;
}

.portfolio-subtitle {
  font-family: serif;
  font-style: italic;
  color: #777;
  font-size: 1.1rem;
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 30px;
}

.portfolio-item {
  background: #fff;
  transition: all 0.3s ease;
}

.portfolio-item a {
  text-decoration: none;
  color: inherit;
}

.image-container {
  width: 100%;
  aspect-ratio: 4 / 3;
  overflow: hidden;
  background: #f0f0f0; /* 圖片載入前的底色 */
}

.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.text-container {
  padding: 20px 10px;
  text-align: center;
}

.text-container h3 {
  font-size: 1.4rem;
  margin: 0 0 5px 0;
  font-weight: 700;
}

.text-container span {
  font-family: serif;
  font-style: italic;
  color: #999;
}

.portfolio-item:hover {
  opacity: 0.8;
  transform: translateY(-5px);
}

/* 手機版縮減為單欄 */
@media (max-width: 600px) {
  .portfolio-grid {
    grid-template-columns: 1fr;
  }
}
</style>
