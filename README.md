# Veganske Oppskrifter �

En Jekyll-basert samling av deilige veganske oppskrifter med jekyll-theme-recipe.

## Funksjoner

- ✅ 100% veganske oppskrifter
- ✅ Kategoriserte oppskrifter (Frokost, Lunsj, Middag, Dessert, Smoothies, Bakevarer, Proteiner)
- ✅ Søkefunksjon
- ✅ Responsive design
- ✅ Navigasjon med kategorier
- ✅ Metadatafelter (tid, porsjoner, vanskelighetsgrad)
- ✅ Tags for oppskrifter
- ✅ Næringsinfo og plantebaserte alternativer

## Installasjon

### 1. Installer Ruby og Jekyll

**Windows:**
1. Last ned og installer Ruby fra [RubyInstaller](https://rubyinstaller.org/)
2. Åpne kommandoprompten og installer Jekyll:
   ```
   gem install jekyll bundler
   ```

**macOS:**
```bash
# Med Homebrew
brew install ruby
gem install jekyll bundler
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
gem install jekyll bundler
```

### 2. Installer avhengigheter

```bash
cd path/to/food
bundle install
```

### 3. Kjør Jekyll

```bash
bundle exec jekyll serve
```

Nettsiden vil være tilgjengelig på `http://localhost:4000/food`

## Struktur

```
food/
├── _config.yml              # Jekyll konfigurasjon
├── _recipes/                # Oppskrifter
│   ├── lasagne.md
│   ├── wok.md
│   ├── pannekaker.md
│   ├── caesar-salat.md
│   └── vegetar-chili.md
├── categories/              # Kategorisider
│   ├── middag.md
│   ├── frokost.md
│   ├── lunsj.md
│   └── dessert.md
├── _includes/
│   └── navigation.html      # Navigasjonskomponent
├── index.md                 # Hovedside
├── alle-oppskrifter.md      # Side med alle oppskrifter og søk
└── Gemfile                  # Ruby avhengigheter
```

## Legge til nye oppskrifter

Opprett en ny fil i `_recipes/` mappen med følgende format:

```markdown
---
title: Oppskriftens navn
category: Middag
tid: 30 min
portion: 4
difficulty: Lett
description: Kort beskrivelse av oppskriften
tags: [tag1, tag2, tag3]
---

# Oppskriftens navn

Beskrivelse av oppskriften.

## Ingredienser

- Ingrediens 1
- Ingrediens 2

## Fremgangsmåte

1. Steg 1
2. Steg 2

## Tips

- Tips og råd
```

## Kategorier

Oppskriftene kan kategoriseres med følgende veganske kategorier:
- **Frokost** - Energirike morgenmåltider
- **Lunsj** - Mettende lunsjretter
- **Middag** - Hovedmåltider  
- **Dessert** - Søte veganske retter
- **Snacks** - Veganske mellommåltider
- **Smoothies** - Sunne drikker og smoothie bowls
- **Bakevarer** - Veganske kaker og bakverk
- **Proteiner** - Proteinrike plantebaserte retter

Du kan legge til flere kategorier i `_config.yml` under `recipe_categories`.

## Deployment

### GitHub Pages

1. Push koden til et GitHub repository
2. Gå til repository Settings > Pages
3. Velg "Deploy from a branch" og "main" branch
4. Siden vil være tilgjengelig på `https://[username].github.io/[repository-name]`

### Netlify

1. Koble repository til Netlify
2. Build command: `bundle exec jekyll build`
3. Publish directory: `_site`

## Tilpassing

### Farger og styling

Du kan tilpasse farger og styling ved å legge til CSS i filene eller ved å override theme-variabler.

### Nye felter for oppskrifter

Du kan legge til nye metadatafelter i frontmatter-delen av oppskriftene og vise dem i templates.

## Bidrag

For å bidra med nye oppskrifter eller forbedringer:

1. Fork repositoryet
2. Opprett en ny branch
3. Legg til oppskrifter eller gjør endringer
4. Send inn en pull request

## Lisens

Dette prosjektet bruker jekyll-theme-recipe som er lisensiert under MIT-lisensen.
