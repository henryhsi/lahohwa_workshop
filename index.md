---
layout: default
title: Welcome to LaHohwa Workshop!
---

<div class="category-filters">
  <button class="category-pill active">All</button>
  <button class="category-pill">Recipes</button>
  <button class="category-pill">Projects</button>
  <button class="category-pill">Notes</button>
</div>

<div class="post-grid">
  {% for post in site.posts %}
    <article class="post-card">
      <div class="post-card-image">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        {% else %}
          <img src="{{ site.baseurl }}/assets/images/default-placeholder.jpg" alt="Default Image">
        {% endif %}
      </div>
      <div class="post-card-content">
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <div class="post-card-date">{{ post.date | date: "%B %d, %Y" }}</div>
        {% if post.tags %}
          <div class="post-card-tags">
            {% for tag in post.tags %}
              <span class="post-tag">{{ tag }}</span>
            {% endfor %}
          </div>
        {% endif %}
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
        <a href="{{ post.url | relative_url }}" class="read-more">Read More</a>
      </div>
    </article>
  {% endfor %}
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const pills = document.querySelectorAll('.category-pill');
    
    pills.forEach(pill => {
        pill.addEventListener('click', function() {
            // Remove active class from all pills
            pills.forEach(p => p.classList.remove('active'));
            // Add active class to clicked pill
            this.classList.add('active');
            
            // Here you can add filtering logic based on categories
            // For now, it's just visual feedback
        });
    });
});
</script>