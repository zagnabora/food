# Hurtigstart Guide 🚀

## For å komme i gang raskt

### 1. Installer Ruby og Jekyll

**Windows - Raskeste måte:**
1. Gå til [RubyInstaller.org](https://rubyinstaller.org/downloads/)
2. Last ned "Ruby+Devkit" (nyeste versjon)
3. Kjør installeren og følg instruksjonene
4. Åpne "Start Command Prompt with Ruby" fra startmenyen
5. Skriv: `gem install jekyll bundler`

### 2. Kjør nettsiden

```bash
cd c:\Users\aurbjo\Dev\food
bundle install
bundle exec jekyll serve
```

Nettsiden åpnes på: http://localhost:4000/food

## Hvis du ikke vil installere Ruby

Du kan også bruke GitHub Pages for automatisk hosting:

1. Push koden til GitHub
2. Gå til repository Settings > Pages
3. Velg "Deploy from a branch" og "main"
4. Nettsiden blir tilgjengelig på `https://[brukernavn].github.io/food`

## Eksisterende veganske oppskrifter

Jeg har laget følgende eksempeloppskrifter:

- **Vegansk Lasagne** (Middag) - Med linser og cashewsaus
- **Vegansk Tofu Wok** (Middag) - Asiatisk inspirert wok
- **Veganske Pannekaker** (Dessert) - Med havrmelk og linfrø
- **Vegansk Caesar Salat** (Lunsj) - Med cashew-dressing
- **Kraftig Vegansk Chili** (Middag) - Med tre typer bønner
- **Gourmet Avokado Toast** (Frokost) - Med fermenterte grønnsaker
- **Vegansk Pizza** (Middag) - Med hjemmelaget cashew-ost
- **Buddha Bowl** (Lunsj) - Med tahinsaus
- **Hjemmelaget Hummus** (Snacks) - Med kreative toppings
- **Grønn Smoothie Bowl** (Frokost) - Med superfood

## Funksjoner som er implementert

✅ **100% Veganske oppskrifter**: Alle retter er plantebaserte
✅ **Kategorier**: Frokost, Lunsj, Middag, Dessert, Smoothies, Bakevarer, Proteiner
✅ **Navigasjon**: Dropdown-meny med veganske kategorier
✅ **Søkefunksjon**: På "Alle oppskrifter" siden
✅ **Metadatafelter**: Tid, porsjoner, vanskelighetsgrad
✅ **Tags**: For enkel gruppering av veganske oppskrifter
✅ **Responsive design**: Fungerer på mobile enheter
✅ **Theme**: Bruker jekyll-theme-recipe
✅ **Næringsinfo**: Fokus på plantebaserte næringsstoffer

## Neste steg

1. **Legg til flere oppskrifter** i `_recipes/` mappen
2. **Tilpass farger** ved å endre CSS i layouts
3. **Legg til bilder** ved å opprette en `assets/images/` mappe
4. **Sett opp automatisk deployment** med GitHub Pages eller Netlify

Trenger du hjelp? Se `README.md` for mer detaljerte instruksjoner!
