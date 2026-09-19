# 🌴 Météo La Réunion — Dashboard Temps Réel

> **Dashboard météo interactif et responsive** pour les 24 communes de La Réunion, avec plus de **40 variables météorologiques**, **6 indices calculés** (chaleur, confort, risque cyclonique, risque incendie…) et une interface tricolore moderne.

![Version](https://img.shields.io/badge/version-2.0-blue)
![Licence](https://img.shields.io/badge/licence-MIT-red)
![Statut](https://img.shields.io/badge/statut-production-success)
![Responsive](https://img.shields.io/badge/responsive-mobile%20%7C%20tablette%20%7C%204K-informational)

---

## 📖 Table des matières

- [Aperçu](#-aperçu)
- [Fonctionnalités](#-fonctionnalités)
- [Indices calculés](#-indices-calculés)
- [Captures d'écran](#-captures-décran)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Structure du projet](#-structure-du-projet)
- [Sources de données](#-sources-de-données)
- [Compatibilité](#-compatibilité)
- [Personnalisation](#-personnalisation)
- [Contribuer](#-contribuer)
- [Licence](#-licence)
- [Remerciements](#-remerciements)

---

## 🌟 Aperçu

Ce dashboard affiche en **temps réel** les conditions météorologiques des **24 communes de La Réunion**, réparties en **5 zones** géographiques :

| Zone | Communes |
|------|----------|
| 🔵 **Nord** | Saint-Denis, Sainte-Marie, Sainte-Suzanne, La Possession |
| 🔴 **Ouest** | Saint-Paul, Le Port, Les Trois-Bassins, Saint-Leu |
| 🔵 **Sud** | Saint-Pierre, Saint-Louis, L'Étang-Salé, Les Avirons, Petite-Île, Saint-Joseph, Saint-Philippe |
| 🔴 **Est** | Saint-André, Saint-Benoît, Bras-Panon, Sainte-Rose, La Plaine-des-Palmistes |
| ⚪ **Intérieur** | Le Tampon, Cilaos, Salazie, L'Entre-Deux |

Le tout dans une **interface tricolore** aux couleurs de La Réunion et de la France, **entièrement responsive** (du mobile 320 px à l'écran 4K).

---

## ✨ Fonctionnalités

### 📡 Données météo en temps réel
- **40+ variables** récupérées via l'API Open-Meteo (gratuit, sans clé API)
- **Cache intelligent** de 10 minutes pour limiter les appels réseau
- **Actualisation automatique** configurable (1 à 15 minutes)
- **Filtrage dynamique** par zone géographique

### 🎨 Interface moderne
- Thème **bleu-blanc-rouge** (couleurs La Réunion / France)
- **4 onglets** : Vue d'ensemble · Carte · Indices · Données
- **Design responsive** avec typographie fluide (`clamp()`)
- **Sidebar accordéon** sur mobile, fixe sur desktop
- **Animations fluides** et effets de survol
- **Accessibilité** : ARIA, navigation clavier, `prefers-reduced-motion`

### 🗺️ Visualisations interactives
- **Carte Leaflet** avec marqueurs colorés selon la température
- **Graphiques Plotly** : températures, vents, humidité, UV par zone
- **Tableau détaillé** avec barres de progression colorées
- **Alertes dynamiques** (canicule, vent fort, pluie, incendie, cyclone)

### 📊 Statistiques en direct
- Commune la plus chaude / fraîche / ventée / arrosée
- Meilleur confort / UV le plus élevé
- Moyennes globales calculées en temps réel

---

## 🔥 Indices calculés

Le dashboard calcule **6 indices** à partir des données brutes :

| Indice | Description | Formule |
|--------|-------------|---------|
| 🔥 **Indice de chaleur** | Température ressentie par forte chaleur | Formule de Rothfusz (Heat Index) |
| ❄️ **Wind Chill** | Refroidissement éolien | Formule canadienne officielle |
| 😊 **Indice de confort** | Score 0-10 basé sur T + humidité + vent | Algorithme pondéré |
| 🔥 **Risque incendie** | 5 niveaux (Faible → Extrême) | T + humidité + vent + pluie |
| 🌀 **Risque cyclonique** | 5 niveaux (Aucun → Violet) | Rafales + cumul pluie (grille officielle) |
| ☀️ **UV effectif** | UV pondéré par la couverture nuageuse | `UV × (1 - nuages/100)` |

---

## 📸 Captures d'écran

> *(Ajoutez vos propres captures dans le dossier `/screenshots`)*

| Vue d'ensemble | Carte interactive |
|:--------------:|:-----------------:|
| `screenshots/overview.png` | `screenshots/map.png` |

| Indices | Données détaillées |
|:-------:|:------------------:|
| `screenshots/indices.png` | `screenshots/data.png` |

---

## 🚀 Installation

### Prérequis
Aucun — le dashboard est **100 % client-side** (HTML + CSS + JavaScript pur).

### Étapes

1. **Télécharger** le fichier `meteo-reunion.html`

2. **Ouvrir** dans un navigateur moderne :
   ```bash
   # Depuis un terminal
   open meteo-reunion.html    # macOS
   start meteo-reunion.html   # Windows
   xdg-open meteo-reunion.html # Linux
   ```

3. **Ou héberger** sur GitHub Pages, Netlify, Vercel, etc.

### Hébergement local (optionnel)

```bash
# Avec Python
python -m http.server 8000

# Avec Node.js
npx serve

# Puis ouvrir http://localhost:8000/meteo-reunion.html
```

---

## 💡 Utilisation

### Navigation

| Onglet | Contenu |
|--------|---------|
| 📊 **Vue d'ensemble** | Métriques globales + cartes des 24 communes |
| 🗺️ **Carte** | Carte interactive + graphiques par zone |
| 📈 **Indices** | Indices calculés + alertes + comparatifs |
| 📋 **Données** | Tableau complet des 40+ variables |

### Filtres

- **Par zone** : cliquer sur les tags dans la sidebar (Nord, Ouest, Sud, Est, Intérieur)
- **Par commune** : filtrer le tableau via le sélecteur de zone
- **Auto-refresh** : activer/désactiver + choisir la fréquence (1 à 15 min)

### Interactions

- 🖱️ **Clic sur un marqueur** : affiche les détails complets
- 🖱️ **Survol d'une carte commune** : effet visuel
- 📱 **Sur mobile** : sidebar en accordéon (cliquer sur ⚙️ Configuration)

---

## 📁 Structure du projet

```
meteo-reunion/
├── meteo-reunion.html      # Dashboard complet (fichier unique)
├── README.md               # Ce fichier
├── LICENSE                 # Licence MIT
└── screenshots/            # Captures d'écran (optionnel)
    ├── overview.png
    ├── map.png
    ├── indices.png
    └── data.png
```

**Architecture du code (dans `meteo-reunion.html`)** :

```
├── <head>
│   ├── Styles CSS (variables, thème, responsive)
│   └── CDN (Plotly + Leaflet)
├── <body>
│   ├── Loader
│   ├── Header tricolore
│   ├── Sidebar (configuration + filtres)
│   └── Contenu principal
│       ├── Onglets
│       ├── Onglet 1 : Vue d'ensemble
│       ├── Onglet 2 : Carte
│       ├── Onglet 3 : Indices
│       └── Onglet 4 : Données
└── <script>
    ├── Données communes + zones
    ├── API Open-Meteo (fetch + cache)
    ├── Calcul des indices
    ├── Rendu (métriques, cartes, graphiques)
    └── Événements (onglets, filtres, auto-refresh)
```

---

## 🌐 Sources de données

| Source | Type | Lien |
|--------|------|------|
| **Open-Meteo** | Météo temps réel (modèles Météo-France AROME) | [open-meteo.com](https://open-meteo.com) |
| **OpenStreetMap** | Fond de carte Leaflet | [openstreetmap.org](https://www.openstreetmap.org) |
| **Météo-France Réunion** | Référence cyclonique | [meteofrance.re](https://meteofrance.re) |

### Variables récupérées (extrait)

```javascript
temperature_2m, relative_humidity_2m, apparent_temperature,
dewpoint_2m, precipitation, rain, showers, cloud_cover,
wind_speed_10m, wind_direction_10m, wind_gusts_10m,
pressure_msl, surface_pressure, uv_index,
wet_bulb_temperature_2m, vapour_pressure_deficit,
cape, convective_inhibition, freezing_level_height,
visibility, weather_code
```

---

## 📱 Compatibilité

### Navigateurs supportés

| Navigateur | Version minimale |
|------------|------------------|
| Chrome / Edge | 90+ |
| Firefox | 88+ |
| Safari | 14+ |
| Opera | 76+ |

### Écrans supportés

| Type | Largeur | Comportement |
|------|---------|--------------|
| 📱 Mobile | 320 – 639 px | 1-2 colonnes, sidebar accordéon |
| 📱 Mobile XL | 640 – 767 px | 4 colonnes métriques |
| 💻 Tablette | 768 – 1023 px | Graphiques empilés |
| 🖥️ Desktop | 1024 – 1599 px | Sidebar fixe + contenu |
| 🖥️ Grand écran | 1600 – 1919 px | Layout élargi |
| 🖥️ 4K | 1920 px+ | Grille étendue |

---

## 🎨 Personnalisation

### Modifier les couleurs

Dans le `<style>`, modifiez les variables CSS :

```css
:root {
  --bleu: #0055A4;      /* Bleu France */
  --rouge: #EF4135;     /* Rouge France */
  --blanc: #FFFFFF;     /* Blanc */
}
```

### Ajouter une commune

Dans `COMMUNES_REUNION`, ajoutez :

```javascript
{
  nom: "Nouvelle-Commune",
  lat: -21.0000,
  lon: 55.5000,
  altitude: 100,
  zone: "Nord"  // Doit exister dans ZONES
}
```

### Modifier la fréquence d'actualisation

```javascript
const CACHE_DURATION = 600000; // 10 minutes en ms
```

### Changer le fond de carte

```javascript
L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
  attribution: "© OpenStreetMap"
}).addTo(state.map);
```

Alternatives : CartoDB, Stamen, Esri…

---

## 🤝 Contribuer

Les contributions sont les bienvenues !

1. **Fork** le projet
2. **Créer** une branche (`git checkout -b feature/nouvelle-fonctionnalite`)
3. **Commit** (`git commit -m 'Ajout nouvelle fonctionnalité'`)
4. **Push** (`git push origin feature/nouvelle-fonctionnalite`)
5. **Ouvrir** une Pull Request

### Idées d'amélioration

- [ ] Prévisions à 7 jours (Open-Meteo forecast_days)
- [ ] Données marines (hauteur vagues, température mer)
- [ ] Qualité de l'air (PM2.5, O₃, pollen)
- [ ] Alertes cycloniques officielles Météo-France
- [ ] Mode sombre
- [ ] Export PDF/CSV
- [ ] PWA (Progressive Web App)
- [ ] Notifications push

---

## 📄 Licence

Ce projet est sous licence **MIT** — voir le fichier [LICENSE](LICENSE) pour plus de détails.

```
MIT License

Copyright (c) 2025 Météo La Réunion Dashboard

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 Remerciements

- **[Open-Meteo](https://open-meteo.com)** — API météo gratuite et open-source
- **[Météo-France](https://meteofrance.re)** — Modèles AROME et référence cyclonique
- **[OpenStreetMap](https://www.openstreetmap.org)** — Fond de carte libre
- **[Plotly.js](https://plotly.com/javascript/)** — Graphiques interactifs
- **[Leaflet](https://leafletjs.com)** — Cartes interactives légères
- **La Réunion** 🌴 et ses 24 communes

---

<div align="center">

**🌴 Fait avec ❤️ pour La Réunion 🌴**

[⬆ Retour en haut](#-météo-la-réunion--dashboard-temps-réel)

</div>

---

<div align="center">

### 🇫🇷 Gunout · 2026

![Made in France](https://img.shields.io/badge/Made_in-France-002395?style=flat-square&labelColor=FFFFFF&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA5MDAgNjAwIj48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzAwMjM5NSIvPjxyZWN0IHdpZHRoPSI5MDAiIGhlaWdodD0iNDAwIiB5PSIxMDAiIGZpbGw9IiNmZmYiLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjIwMCIgeT0iNDAwIiBmaWxsPSIjZWQyOTM5Ii8+PC9zdmc+)
![GitHub](https://img.shields.io/badge/GitHub-gunout-181717?style=flat-square&logo=github&logoColor=white)
![Year](https://img.shields.io/badge/2026-ED2939?style=flat-square&labelColor=FFFFFF)

<sub>© 2026 <strong>Gunout</strong> — Tous droits réservés.</sub>

</div>
