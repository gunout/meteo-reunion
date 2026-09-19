# 🌴 Météo La Réunion — Dashboard Temps Réel v3.0

> **Dashboard météo interactif et responsive** pour les 24 communes de La Réunion, avec **prévisions 7 jours**, **données marines**, **qualité de l'air**, **6 indices calculés** (chaleur, confort, risque cyclonique, risque incendie…), **mode sombre** et **export CSV**.

[![GitHub repo](https://img.shields.io/badge/GitHub-gunout%2Fmeteo--reunion-blue?logo=github)](https://github.com/gunout/meteo-reunion/)
[![Version](https://img.shields.io/badge/version-3.0-blue)](https://github.com/gunout/meteo-reunion/)
[![Licence](https://img.shields.io/badge/licence-MIT-red)](https://github.com/gunout/meteo-reunion/blob/main/LICENSE)
[![Statut](https://img.shields.io/badge/statut-production-success)](https://github.com/gunout/meteo-reunion/)
[![Responsive](https://img.shields.io/badge/responsive-mobile%20%7C%20tablette%20%7C%204K-informational)](https://github.com/gunout/meteo-reunion/)
[![Dark Mode](https://img.shields.io/badge/dark%20mode-%E2%9C%93-black)](https://github.com/gunout/meteo-reunion/)
[![PWA Ready](https://img.shields.io/badge/PWA-ready-purple)](https://github.com/gunout/meteo-reunion/)

---

## 🔗 Liens rapides

| Ressource | Lien |
|-----------|------|
| 📦 **Dépôt GitHub** | [github.com/gunout/meteo-reunion](https://github.com/gunout/meteo-reunion/) |
| 🌐 **Démo en ligne (GitHub Pages)** | [gunout.github.io/meteo-reunion](https://gunout.github.io/meteo-reunion/) |
| 📄 **Code source direct** | [index.html](https://github.com/gunout/meteo-reunion/blob/main/index.html) |
| 🐛 **Signaler un bug** | [Issues](https://github.com/gunout/meteo-reunion/issues) |
| 💡 **Proposer une idée** | [Discussions](https://github.com/gunout/meteo-reunion/discussions) |
| ⭐ **Mettre une étoile** | [Star le repo](https://github.com/gunout/meteo-reunion/) |

---

## 📖 Table des matières

- [Aperçu](#-aperçu)
- [Nouveautés v3.0](#-nouveautés-v30)
- [Fonctionnalités](#-fonctionnalités)
- [Indices calculés](#-indices-calculés)
- [Captures d'écran](#-captures-décran)
- [Installation](#-installation)
- [Déploiement](#-déploiement)
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

👉 **Voir la démo en direct** : [gunout.github.io/meteo-reunion](https://gunout.github.io/meteo-reunion/)

---

## 🆕 Nouveautés v3.0

- 📅 **Prévisions 7 jours** — Graphiques de tendance + détail par commune
- 🌊 **Données marines** — Vagues, houle, température de mer (4 spots de surf)
- 🌫️ **Qualité de l'air** — AQI européen, PM2.5, PM10, O₃, NO₂, pollen
- 🌀 **Alertes cycloniques** — Widget avec liens officiels Météo-France Réunion
- 🌙 **Mode sombre** — Toggle manuel + détection OS + persistance
- 📤 **Export CSV** — Toutes les données en un clic
- 📊 **Nouveaux onglets** — Prévisions, Environnement

---

## ✨ Fonctionnalités

### 📡 Données météo temps réel
- **40+ variables** via l'API Open-Meteo (gratuit, sans clé API)
- **Cache intelligent** de 10 minutes
- **Actualisation automatique** configurable (1 à 15 minutes)
- **Filtrage dynamique** par zone géographique

### 📅 Prévisions 7 jours
- Graphique multi-zones (températures max moyennes)
- Détail par commune (max, min, précipitations)
- Mini-barres de tendance dans chaque carte commune

### 🌊 Données marines
- Hauteur et période des vagues
- Hauteur, période et direction de la houle
- Température de surface de la mer
- 4 spots : Saint-Leu, Saint-Pierre, L'Étang-Salé, Le Port

### 🌫️ Qualité de l'air
- **AQI européen** (0-100+) avec code couleur
- PM2.5, PM10, O₃, NO₂, CO
- Pollen (graminées)
- 8 communes principales

### 🎨 Interface moderne
- Thème **bleu-blanc-rouge** (couleurs La Réunion / France)
- **Mode sombre** avec détection auto (`prefers-color-scheme`)
- **6 onglets** : Vue d'ensemble · Prévisions · Carte · Indices · Environnement · Données
- **Design responsive** avec typographie fluide (`clamp()`)
- **Sidebar accordéon** sur mobile, fixe sur desktop
- **Accessibilité** : ARIA, navigation clavier, `prefers-reduced-motion`

### 🗺️ Visualisations interactives
- **Carte Leaflet** avec marqueurs colorés par température
- **Graphiques Plotly** : températures, vents, humidité, UV, chaleur, confort
- **Tableau détaillé** avec barres de progression
- **Alertes dynamiques** (canicule, vent, pluie, incendie, cyclone)

### 📊 Statistiques en direct
- Commune la plus chaude / fraîche / ventée / arrosée
- Meilleur confort / UV le plus élevé
- Moyennes globales calculées en temps réel

---

## 🔥 Indices calculés

| Indice | Description | Formule |
|--------|-------------|---------|
| 🔥 **Indice de chaleur** | Température ressentie par forte chaleur | Formule de Rothfusz (Heat Index) |
| ❄️ **Wind Chill** | Refroidissement éolien | Formule canadienne officielle |
| 😊 **Indice de confort** | Score 0-10 basé sur T + humidité + vent | Algorithme pondéré |
| 🔥 **Risque incendie** | 5 niveaux (Faible → Extrême) | T + humidité + vent + pluie |
| 🌀 **Risque cyclonique** | 5 niveaux (Aucun → Violet) | Rafales + cumul pluie (grille officielle Météo-France) |
| ☀️ **UV effectif** | UV pondéré par la couverture nuageuse | `UV × (1 - nuages/100)` |

---

## 📸 Captures d'écran

> *(Ajoutez vos propres captures dans le dossier `/screenshots` du dépôt)*

| Vue d'ensemble | Prévisions 7 jours |
|:--------------:|:------------------:|
| ![Vue d'ensemble](screenshots/overview.png) | ![Prévisions](screenshots/forecast.png) |

| Carte interactive | Indices calculés |
|:-----------------:|:----------------:|
| ![Carte](screenshots/map.png) | ![Indices](screenshots/indices.png) |

| Environnement (Marine + Air) | Données détaillées |
|:----------------------------:|:------------------:|
| ![Environnement](screenshots/environment.png) | ![Données](screenshots/data.png) |

| Mode sombre |
|:-----------:|
| ![Dark](screenshots/dark-mode.png) |

---

## 🚀 Installation

### Prérequis
Aucun — le dashboard est **100 % client-side** (HTML + CSS + JavaScript pur).

### Option 1 : Cloner le dépôt

```bash
git clone https://github.com/gunout/meteo-reunion.git
cd meteo-reunion
```

Puis ouvrez `index.html` dans votre navigateur.

### Option 2 : Télécharger directement

Téléchargez le fichier [index.html](https://github.com/gunout/meteo-reunion/blob/main/index.html) depuis GitHub et ouvrez-le dans un navigateur moderne.

### Option 3 : Hébergement local

```bash
# Avec Python
python -m http.server 8000

# Avec Node.js
npx serve

# Puis ouvrir http://localhost:8000
```

---

## 🚢 Déploiement

Le projet est **100 % statique** (un seul fichier `index.html`), il peut être déployé sur n'importe quelle plateforme d'hébergement statique.

### ⭐ GitHub Pages (recommandé — déjà configuré)

Le déploiement est **automatique** à chaque `push` sur la branche `main`.

**URL de production** : [https://gunout.github.io/meteo-reunion/](https://gunout.github.io/meteo-reunion/)

Pour activer GitHub Pages manuellement :
1. Aller dans **Settings** → **Pages** du dépôt
2. Source : **Deploy from a branch**
3. Branch : `main` / `/ (root)`
4. Cliquer sur **Save**

### ▲ Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/gunout/meteo-reunion)

```bash
# Via CLI
npm i -g vercel
vercel
```

### 🟢 Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/gunout/meteo-reunion)

```bash
# Via CLI
npm i -g netlify-cli
netlify deploy --prod
```

### ☁️ Cloudflare Pages

1. Aller sur [pages.cloudflare.com](https://pages.cloudflare.com)
2. Connecter votre compte GitHub
3. Sélectionner `gunout/meteo-reunion`
4. Build command : *(laisser vide)*
5. Output directory : `/`
6. Cliquer sur **Save and Deploy**

### 📦 Autres options

| Plateforme | Commande |
|------------|----------|
| **Surge.sh** | `npx surge` |
| **Render** | [render.com](https://render.com) |
| **Firebase Hosting** | `firebase deploy` |
| **GitLab Pages** | Miroir du repo sur GitLab |

---

## 💡 Utilisation

### Navigation

| Onglet | Contenu |
|--------|---------|
| 📊 **Vue d'ensemble** | Widget cyclone + métriques + cartes des 24 communes |
| 📅 **Prévisions 7j** | Graphique multi-zones + détail par commune |
| 🗺️ **Carte** | Carte interactive + graphiques par zone |
| 📈 **Indices** | 6 indices + alertes + comparatifs |
| 🌊 **Environnement** | Données marines + qualité de l'air |
| 📋 **Données** | Tableau complet + Export CSV + statistiques |

### Filtres

- **Par zone** : cliquer sur les tags dans la sidebar (Nord, Ouest, Sud, Est, Intérieur)
- **Par commune** : filtrer le tableau via le sélecteur de zone
- **Auto-refresh** : activer/désactiver + choisir la fréquence (1 à 15 min)

### Boutons spéciaux

- 🌙 **Mode sombre** : dans la sidebar
- 📥 **Export CSV** : dans l'onglet Données

### Interactions

- 🖱️ **Clic sur un marqueur** : détails complets
- 🖱️ **Survol d'une carte commune** : effet visuel
- 📱 **Sur mobile** : sidebar en accordéon (cliquer sur ⚙️ Configuration)

---

## 📁 Structure du projet

```
meteo-reunion/
├── index.html              # Dashboard complet (fichier unique)
├── README.md               # Ce fichier
├── LICENSE                 # Licence MIT
└── screenshots/            # Captures d'écran (optionnel)
    ├── overview.png
    ├── forecast.png
    ├── map.png
    ├── indices.png
    ├── environment.png
    ├── data.png
    └── dark-mode.png
```

**Architecture du code (dans `index.html`)** :

```
├── <head>
│   ├── Styles CSS (variables, thème, responsive, dark mode)
│   └── CDN (Plotly + Leaflet)
├── <body>
│   ├── Loader
│   ├── Header tricolore
│   ├── Sidebar (config + filtres + toggle dark)
│   └── Contenu principal
│       ├── 6 onglets
│       └── Vue d'ensemble + Prévisions + Carte
│       └── Indices + Environnement + Données
└── <script>
    ├── Données communes + zones + spots marins
    ├── API Open-Meteo (météo + marine + air quality)
    ├── Calcul des indices
    ├── Gestion du thème (dark/light + localStorage)
    ├── Export CSV
    ├── Rendu (métriques, cartes, graphiques, alertes)
    └── Événements (onglets, filtres, auto-refresh)
```

---

## 🌐 Sources de données

| Source | Type | Lien |
|--------|------|------|
| **Open-Meteo Forecast** | Météo temps réel + prévisions 7j | [open-meteo.com](https://open-meteo.com) |
| **Open-Meteo Marine** | Vagues, houle, température mer | [marine-api.open-meteo.com](https://marine-api.open-meteo.com) |
| **Open-Meteo Air Quality** | AQI, PM2.5, PM10, O₃, pollen | [air-quality-api.open-meteo.com](https://air-quality-api.open-meteo.com) |
| **OpenStreetMap** | Fond de carte Leaflet | [openstreetmap.org](https://www.openstreetmap.org) |
| **Météo-France Réunion** | Alertes cycloniques officielles | [meteofrance.re](https://meteofrance.re/fr/cyclone) |

### Variables récupérées

**Météo actuelle** :
```javascript
temperature_2m, relative_humidity_2m, apparent_temperature,
dewpoint_2m, precipitation, cloud_cover,
wind_speed_10m, wind_gusts_10m, wind_direction_10m,
pressure_msl, surface_pressure, uv_index,
wet_bulb_temperature_2m, vapour_pressure_deficit,
cape, visibility, weather_code
```

**Prévisions 7 jours** :
```javascript
temperature_2m_max, temperature_2m_min,
precipitation_sum, precipitation_probability_max,
wind_speed_10m_max, wind_gusts_10m_max,
uv_index_max, weather_code, sunrise, sunset
```

**Marine** :
```javascript
wave_height, wave_period, wave_direction,
swell_wave_height, swell_wave_period,
swell_wave_direction, sea_surface_temperature
```

**Qualité de l'air** :
```javascript
pm10, pm2_5, carbon_monoxide, nitrogen_dioxide,
ozone, european_aqi, us_aqi, grass_pollen
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

/* Mode sombre */
html.dark-mode {
  --bleu: #4A9EFF;
  --rouge: #FF6B5B;
  /* ... */
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

### Ajouter un spot de surf

Dans `SPOTS_MARINS`, ajoutez :

```javascript
{
  nom: "Nouveau-Spot",
  lat: -21.2000,
  lon: 55.3000
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

1. **Fork** le projet : [github.com/gunout/meteo-reunion/fork](https://github.com/gunout/meteo-reunion/fork)
2. **Créer** une branche (`git checkout -b feature/nouvelle-fonctionnalite`)
3. **Commit** (`git commit -m 'Ajout nouvelle fonctionnalité'`)
4. **Push** (`git push origin feature/nouvelle-fonctionnalite`)
5. **Ouvrir** une Pull Request

### Idées d'amélioration

- [ ] Alertes cycloniques officielles via scraping Météo-France
- [ ] Notifications push pour les alertes
- [ ] PWA (Progressive Web App) avec service worker
- [ ] Export PDF avec mise en page
- [ ] Widgets embarquables pour sites tiers
- [ ] Historique et comparaison avec les normales saisonnières
- [ ] Carte des précipitations radar (si disponible)
- [ ] Intégration marées (Pointe des Galets, Piton Saint-Leu)

---

## 📄 Licence

Ce projet est sous licence **MIT** — voir le fichier [LICENSE](https://github.com/gunout/meteo-reunion/blob/main/LICENSE) pour plus de détails.

```
MIT License

Copyright (c) 2025-2026 Gunout

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
- **[Open-Meteo Marine](https://marine-api.open-meteo.com)** — Données marines
- **[Open-Meteo Air Quality](https://air-quality-api.open-meteo.com)** — Qualité de l'air
- **[Météo-France Réunion](https://meteofrance.re)** — Modèles AROME et référence cyclonique
- **[OpenStreetMap](https://www.openstreetmap.org)** — Fond de carte libre
- **[Plotly.js](https://plotly.com/javascript/)** — Graphiques interactifs
- **[Leaflet](https://leafletjs.com)** — Cartes interactives légères
- **La Réunion** 🌴 et ses 24 communes

---

## 📞 Contact

- **GitHub** : [@gunout](https://github.com/gunout)
- **Issues** : [github.com/gunout/meteo-reunion/issues](https://github.com/gunout/meteo-reunion/issues)
- **Discussions** : [github.com/gunout/meteo-reunion/discussions](https://github.com/gunout/meteo-reunion/discussions)

---

<div align="center">

**🌴 Fait pour La Réunion 🌴**

[⬆ Retour en haut](#-météo-la-réunion--dashboard-temps-réel)


---

<div align="center">

### 🇫🇷 Gunout · 2026

![Made in France](https://img.shields.io/badge/Made_in-France-002395?style=flat-square&labelColor=FFFFFF&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA5MDAgNjAwIj48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjYwMCIgZmlsbD0iIzAwMjM5NSIvPjxyZWN0IHdpZHRoPSI5MDAiIGhlaWdodD0iNDAwIiB5PSIxMDAiIGZpbGw9IiNmZmYiLz48cmVjdCB3aWR0aD0iOTAwIiBoZWlnaHQ9IjIwMCIgeT0iNDAwIiBmaWxsPSIjZWQyOTM5Ii8+PC9zdmc+)
![GitHub](https://img.shields.io/badge/GitHub-gunout-181717?style=flat-square&logo=github&logoColor=white)
![Year](https://img.shields.io/badge/2026-ED2939?style=flat-square&labelColor=FFFFFF)

<sub>© 2026 <strong>Gunout</strong> — Tous droits réservés.</sub>

</div>
