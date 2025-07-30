---
layout: default
title: Middagsoppskrifter
permalink: /categories/middag/
---

# Veganske Middagsretter �

Alle våre plantebaserte middagsoppskrifter - fra enkle hverdagsretter til festlige helgeretter.

{% assign middag_recipes = site.recipes | where: "category", "Middag" | sort: "title" %}

<div class="recipes-grid">
{% for recipe in middag_recipes %}
  <div class="recipe-card">
    <h3><a href="{{ recipe.url | relative_url }}">{{ recipe.title }}</a></h3>
    {% if recipe.description %}
      <p class="description">{{ recipe.description }}</p>
    {% endif %}
    <div class="recipe-meta">
      {% if recipe.tid %}<span class="time">⏱️ {{ recipe.tid }}</span>{% endif %}
      {% if recipe.portion %}<span class="portions">👥 {{ recipe.portion }}</span>{% endif %}
      {% if recipe.difficulty %}<span class="difficulty">📊 {{ recipe.difficulty }}</span>{% endif %}
    </div>
    {% if recipe.tags %}
      <div class="tags">
        {% for tag in recipe.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
    {% endif %}
  </div>
{% endfor %}
</div>

<style>
.recipes-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin: 2rem 0;
}

.recipe-card {
  border: 1px solid #ddd;
  border-radius: 12px;
  padding: 1.5rem;
  background: white;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  transition: transform 0.2s;
}

.recipe-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}

.recipe-card h3 {
  margin: 0 0 1rem 0;
}

.recipe-card a {
  text-decoration: none;
  color: #333;
}

.recipe-card a:hover {
  color: #007acc;
}

.description {
  color: #666;
  margin: 0.5rem 0 1rem 0;
  font-size: 0.95rem;
}

.recipe-meta {
  margin: 1rem 0;
  font-size: 0.9rem;
  color: #666;
}

.recipe-meta span {
  margin-right: 1rem;
  display: inline-block;
}

.tags {
  margin-top: 1rem;
}

.tag {
  background: #f0f8ff;
  color: #007acc;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  font-size: 0.8rem;
  margin-right: 0.5rem;
  margin-bottom: 0.25rem;
  display: inline-block;
}
</style>
