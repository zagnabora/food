---
layout: default
title: Frokostretter
permalink: /categories/frokost/
---

# Veganske Frokostretter �

Start dagen riktig med våre sunne og energirike veganske frokostretter!

{% assign frokost_recipes = site.recipes | where: "category", "Frokost" | sort: "title" %}

<div class="recipes-grid">
{% for recipe in frokost_recipes %}
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
}

.recipe-meta span {
  margin-right: 1rem;
  font-size: 0.9rem;
  color: #666;
}
</style>
