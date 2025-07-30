---
layout: default
title: Alle oppskrifter
permalink: /alle-oppskrifter/
---

# Alle veganske oppskrifter 📚

Her finner du alle våre plantebaserte oppskrifter sortert alfabetisk.

{% assign all_recipes = site.recipes | sort: "title" %}

<div class="search-box">
  <input type="text" id="recipe-search" placeholder="Søk etter oppskrifter..." onkeyup="filterRecipes()">
</div>

<div class="recipes-grid" id="recipes-container">
{% for recipe in all_recipes %}
  <div class="recipe-card" data-title="{{ recipe.title | downcase }}" data-category="{{ recipe.category | downcase }}" data-tags="{% for tag in recipe.tags %}{{ tag | downcase }} {% endfor %}">
    <h3><a href="{{ recipe.url | relative_url }}">{{ recipe.title }}</a></h3>
    {% if recipe.description %}
      <p class="description">{{ recipe.description }}</p>
    {% endif %}
    <div class="recipe-meta">
      <span class="category">{{ recipe.category }}</span>
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

<script>
function filterRecipes() {
  const searchTerm = document.getElementById('recipe-search').value.toLowerCase();
  const recipes = document.querySelectorAll('.recipe-card');
  
  recipes.forEach(recipe => {
    const title = recipe.getAttribute('data-title');
    const category = recipe.getAttribute('data-category');
    const tags = recipe.getAttribute('data-tags');
    
    if (title.includes(searchTerm) || category.includes(searchTerm) || tags.includes(searchTerm)) {
      recipe.style.display = 'block';
    } else {
      recipe.style.display = 'none';
    }
  });
}
</script>

<style>
.search-box {
  margin: 2rem 0;
  text-align: center;
}

#recipe-search {
  width: 100%;
  max-width: 400px;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 1rem;
}

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

.recipe-meta .category {
  background: #e7f3ff;
  color: #007acc;
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  font-weight: bold;
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
