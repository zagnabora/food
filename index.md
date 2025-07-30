---
layout: default
title: Hjem
---

# Velkommen til veganske oppskrifter! �

Oppdag verden av plantebasert mat med våre deilige, næringsrike og miljøvennlige oppskrifter. Fra enkle hverdagsretter til festlige måltider - alt 100% vegansk!

## Hvorfor vegansk? 🌍

- **Miljøvennlig**: Reduserer CO2-avtrykket ditt
- **Sunn**: Rik på fiber, vitaminer og antioksidanter  
- **Dyrevennlig**: Ingen dyr kommer til skade
- **Variert**: Utforsk nye smaker og ingredienser

## Kategorier

{% assign categories = site.recipe_categories %}
<div class="category-grid">
{% for category in categories %}
  {% assign recipes_in_category = site.recipes | where: "category", category.name %}
  {% if recipes_in_category.size > 0 %}
    <div class="category-card">
      <h3><a href="/food/categories/{{ category.slug }}">{{ category.name }}</a></h3>
      <p>{{ recipes_in_category.size }} oppskrift{% if recipes_in_category.size != 1 %}er{% endif %}</p>
    </div>
  {% endif %}
{% endfor %}
</div>

## Siste oppskrifter

{% assign recent_recipes = site.recipes | sort: 'date' | reverse | limit: 6 %}
<div class="recipes-grid">
{% for recipe in recent_recipes %}
  <div class="recipe-card">
    <h4><a href="{{ recipe.url | relative_url }}">{{ recipe.title }}</a></h4>
    <p class="recipe-meta">
      {% if recipe.category %}<span class="category">{{ recipe.category }}</span>{% endif %}
      {% if recipe.tid %}<span class="time">⏱️ {{ recipe.tid }}</span>{% endif %}
    </p>
    {% if recipe.description %}
      <p class="description">{{ recipe.description | truncate: 100 }}</p>
    {% endif %}
  </div>
{% endfor %}
</div>

<style>
.category-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin: 2rem 0;
}

.category-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1rem;
  text-align: center;
  background: #f9f9f9;
}

.category-card h3 {
  margin: 0 0 0.5rem 0;
}

.category-card a {
  text-decoration: none;
  color: #333;
}

.category-card a:hover {
  color: #007acc;
}

.recipes-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.recipe-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1rem;
  background: white;
}

.recipe-card h4 {
  margin: 0 0 0.5rem 0;
}

.recipe-card a {
  text-decoration: none;
  color: #333;
}

.recipe-card a:hover {
  color: #007acc;
}

.recipe-meta {
  margin: 0.5rem 0;
  font-size: 0.9rem;
  color: #666;
}

.recipe-meta .category {
  background: #e7f3ff;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
  margin-right: 0.5rem;
}

.recipe-meta .time {
  margin-left: 0.5rem;
}

.description {
  font-size: 0.9rem;
  color: #666;
  margin: 0.5rem 0 0 0;
}
</style>