<div align="center">

# 🎧 CYBERDASH V2

### HTTP & YouTube Player — Dashboard cyberpunk par Gleaphe

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/docs/Web/JavaScript)
[![JSZip](https://img.shields.io/badge/JSZip-3.10.1-00ffff)](https://stuk.github.io/jszip/)
[![No Backend](https://img.shields.io/badge/backend-none-00ff66)](#)
[![Made in Réunion](https://img.shields.io/badge/made%20in-La%20R%C3%A9union%20%F0%9F%87%B7%F0%9F%87%AA-ff69b4)](#)

**Scannez, écoutez et archivez des bibliothèques MP3 entières depuis une seule page HTML.**

### 🚀 [**Essayer la démo live →**](https://gunout.github.io/CyberDash_V2/)

[✨ Fonctionnalités](#-fonctionnalités) · [🚀 Installation](#-installation) · [📖 Utilisation](#-utilisation) · [🛠️ Stack](#️-stack-technique) · [🔐 Sécurité](#-sécurité) · [🤝 Contribution](#-contribution)

</div>

---

## 📋 Table des matières

- [Présentation](#-présentation)
- [Démo live](#-démo-live)
- [Fonctionnalités](#-fonctionnalités)
- [Aperçu](#-aperçu)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Stack technique](#️-stack-technique)
- [Architecture](#-architecture)
- [Sécurité](#-sécurité)
- [Performance](#-performance)
- [Roadmap](#-roadmap)
- [Contribution](#-contribution)
- [Licence](#-licence)
- [Auteur](#-auteur)

---

## 🎯 Présentation

**CYBERDASH V2** *(interface : « BEATSTREET SECURE EDITION »)* est un dashboard web **single-page** au style cyberpunk qui permet d'explorer récursivement une arborescence web, de détecter les fichiers `.mp3`, de les lire en streaming et de les télécharger en une archive ZIP — le tout **sans backend**, **sans clé API**, et **sans installation**.

Il combine :

- 🕸️ **Un crawler récursif** avec gestion de profondeur, filtrage de domaine et throttling anti-ban
- 🎵 **Un lecteur multimédia intégré** (YouTube + streaming audio HTML5)
- 📦 **Un générateur ZIP côté client** propulsé par un Web Worker (JSZip)
- 🎨 **Une UI cyberpunk** immersive (néons cyan, scanlines, particules animées)
- 🔐 **Sécurité renforcée** (protection XSS, CSP, validation d'URL)

---

## 🚀 Démo live

> **Aucune installation requise** — teste directement dans ton navigateur :

### 👉 **[https://gunout.github.io/CyberDash_V2/](https://gunout.github.io/CyberDash_V2/)**

Fonctionne immédiatement. Pour le **Direct Mode** (bypass CORS), installe une extension navigateur — voir [Installation](#-installation).

---

## ✨ Fonctionnalités

| Fonctionnalité | Description |
|---|---|
| 🕷️ **Deep Scan récursif** | Explore automatiquement les sous-dossiers jusqu'à 10 niveaux |
| 🎯 **Détection MP3** | Repère tous les fichiers `.mp3` et reconstruit l'arborescence |
| 🎧 **Lecteur audio intégré** | Streaming direct via `<audio>` + visualiseur de waveform |
| 📺 **Lecteur YouTube** | Support natif des liens YouTube avec extraction d'ID |
| 📦 **ZIP côté navigateur** | Génération d'archive par Web Worker (pas de blocage UI) |
| 🔀 **3 proxies CORS** | Fallback automatique : corsproxy.io / allorigins / codetabs |
| 🎛️ **Proxy personnalisé** | Possibilité de coller sa propre URL de proxy CORS |
| ⚡ **Direct Mode** | Bypass CORS via extension navigateur (le plus rapide) |
| 🐌 **Scan Speed réglable** | Steady (safe) ou Fast (risqué) |
| 🎚️ **Multi-sélection** | Checkboxes cyber pour choisir les fichiers à archiver |
| 🔍 **Filtre live** | Champ de recherche instantané sur la playlist |
| 💾 **Persistance locale** | Playlist sauvegardée dans `localStorage` |
| ⌨️ **Raccourcis clavier** | `Espace` play/pause · `←` précédent · `→` suivant |
| 🔔 **Notifications toast** | Feedback visuel non-bloquant |
| 📊 **Stats en temps réel** | Compteur trouvés / visités / en attente pendant le scan |
| 🛡️ **Sécurité intégrée** | XSS-proof, CSP meta, validation d'URL |

---

## 📸 Aperçu

> *Ajoute une capture dans `docs/preview.png` et décommente la ligne ci-dessous :*

<!-- ![Aperçu du dashboard](docs/preview.png) -->

```
┌──────────────────────────────────────────────────────────────────┐
│  BEATSTREET SECURE EDITION          ● ONLINE  ● SAFE MODE       │
├──────────────┬────────────────────────────┬──────────────────────┤
│ DATA STREAM  │  [URL input]   [LOAD]      │  CONTROLS            │
│ [12/48]      │  ┌──────────────────────┐  │  [DEEP SCAN]         │
│ 🔍 Filtrer…  │  │  ▶  YOUTUBE PLAYER   │  │  [CLEAR ALL]         │
│ ☑ track1.mp3 │  │                      │  │                      │
│ ☐ track2.mp3 │  └──────────────────────┘  │                      │
│ ☑ track3.mp3 │  ⏮  ⏯  ⏭    [GET MP3]    │                      │
├──────────────┤                            │                      │
│ ZIP SELECTED │                            │                      │
│ FAST TEST    │                            │                      │
│ DOWNLOAD ALL │                            │                      │
└──────────────┴────────────────────────────┴──────────────────────┘
```

---

## 🚀 Installation

### Option 1 — Utilisation directe (recommandé)

Ouvre simplement la démo live :

### 👉 **[https://gunout.github.io/CyberDash_V2/](https://gunout.github.io/CyberDash_V2/)**

### Option 2 — En local

```bash
# 1. Clone le dépôt
git clone https://github.com/gunout/CyberDash_V2.git
cd CyberDash_V2

# 2. Ouvre simplement le fichier HTML
open index.html      # macOS
start index.html     # Windows
xdg-open index.html  # Linux
```

### Prérequis

- Un **navigateur moderne** : Chrome / Edge / Firefox / Safari (dernières versions)
- *(Optionnel)* Une extension de désactivation CORS pour le **Direct Mode** :
  - **Chrome / Edge** : [Allow CORS](https://chrome.google.com/webstore/detail/allow-cors-access-control/lhobafahddgcelffkeicbaginigeejlf)
  - **Firefox** : [CORS Everywhere](https://addons.mozilla.org/firefox/addon/cors-everywhere/)

**Aucune dépendance à installer. Aucun serveur à lancer.** 🎉

---

## 📖 Utilisation

### 1️⃣ Charger un média directement

Colle une URL YouTube ou un lien direct `.mp3` dans le champ en haut, puis clique **LOAD**.

- URL YouTube → `https://www.youtube.com/watch?v=dQw4w9WgXcQ`
- Lien direct MP3 → `https://example.com/track.mp3`

### 2️⃣ Lancer un Deep Scan

1. Clique sur **DEEP SCAN** (panneau de droite)
2. Colle l'URL de base à explorer, ex :
   ```
   https://example.com/music/albums/
   ```
3. Choisis tes options :
   - **Custom Proxy URL** — si tu as un proxy privé
   - **Direct Mode** — active si tu as une extension CORS
   - **Scan Speed** — `Steady` (recommandé) ou `Fast`
4. Clique **START CRAWL**

### 3️⃣ Télécharger un ZIP

- **ZIP SELECTED** → archive les fichiers cochés
- **FAST TEST (10 FILES)** → teste avec 10 fichiers
- **DOWNLOAD ALL AUDIO** → sélectionne et archive tous les MP3

### 4️⃣ Raccourcis clavier

| Touche | Action |
|---|---|
| `Espace` | Play / Pause |
| `←` | Piste précédente |
| `→` | Piste suivante |

---

## 🛠️ Stack technique

| Couche | Technologie |
|---|---|
| **UI** | HTML5 sémantique + CSS3 (Grid, Flexbox, variables, animations) |
| **Logique** | JavaScript Vanilla ES2020+ |
| **Polices** | Orbitron + Rajdhani (Google Fonts) |
| **Icônes** | Font Awesome 6 |
| **Archive** | [JSZip 3.10.1](https://stuk.github.io/jszip/) |
| **Concurrence** | Web Worker (offload du téléchargement + ZIP) |
| **Réseau** | Fetch API + AbortController + retry/backoff |
| **Stockage** | localStorage |
| **Sécurité** | CSP meta + DOM API strict (no innerHTML user-content) |
| **Hébergement** | GitHub Pages |
| **Backend** | **Aucun** ✅ |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      MAIN THREAD                            │
│                                                             │
│   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐   │
│   │   Scanner    │   │   Playlist   │   │    Player    │   │
│   │  (crawler)   │◄──┤   (state)    │──►│  (audio/YT)  │   │
│   └──────┬───────┘   └──────┬───────┘   └──────────────┘   │
│          │                  │                              │
│          │                  ▼                              │
│          │          ┌──────────────┐                       │
│          │          │  localStorage │                       │
│          │          └──────────────┘                       │
│          │                                                 │
│          │   postMessage()                                 │
│          ▼                                                 │
│   ┌────────────────────────────────────────┐              │
│   │         ZIP WEB WORKER                 │              │
│   │  ─ JSZip                                │              │
│   │  ─ 3 proxies CORS en fallback           │              │
│   │  ─ Concurrency: 2 + jitter 300ms        │              │
│   │  ─ Retry/backoff exponentials           │              │
│   │  ─ Content-Type validation              │              │
│   └────────────────────────────────────────┘              │
└─────────────────────────────────────────────────────────────┘
```

---

## 🔐 Sécurité

| Protection | Implémentation |
|---|---|
| **XSS** | Rendu 100 % via DOM API (`createElement`, `textContent`) — jamais d'`innerHTML` sur du contenu utilisateur |
| **CSP** | Meta `Content-Security-Policy` restrictive dans le `<head>` |
| **URL validation** | Blocage des protocoles non-HTTP(S), IPs privées (10.x, 192.168.x, 172.16-31.x, 127.x) |
| **SSRF local** | Rejet de `localhost` comme cible de scan |
| **Worker isolation** | Le code de téléchargement tourne dans un Web Worker sandboxé |
| **Blob cleanup** | `URL.revokeObjectURL()` au `beforeunload` pour éviter les fuites mémoire |

---

## ⚡ Performance

- **Log en O(1)** — `appendLog()` avec plafond de 500 entrées (évite l'explosion de la RAM)
- **Debounce de rendu** — `scheduleRender()` limite les re-renders à 4/sec maximum
- **Toggle ciblé** — Cocher/décocher ne re-render que l'élément concerné
- **Concurrency réduite** — 2 téléchargements simultanés + jitter pour éviter les bans
- **Retry progressif** — Backoff de 800 ms × tentative avant de passer au proxy suivant
- **Timeout portable** — `AbortController` + `setTimeout` (compatible tous navigateurs)

---

## 🗺️ Roadmap

- [x] Crawler récursif avec gestion de profondeur
- [x] Web Worker pour ZIP non-bloquant
- [x] 3 proxies CORS en fallback
- [x] Fix XSS + CSP
- [x] Filtre playlist + localStorage
- [x] Raccourcis clavier
- [x] Déploiement GitHub Pages
- [ ] Export de la playlist en JSON / CSV
- [ ] Support `.m4a`, `.flac`, `.wav`
- [ ] Mode sombre / clair
- [ ] Internationalisation (FR / EN)
- [ ] Plugin navigateur (bypass CORS natif)
- [ ] Progressive Web App (offline)

---

## 🤝 Contribution

Les contributions sont **les bienvenues** ! 🎉

```bash
# 1. Fork le projet
# 2. Crée ta branche
git checkout -b feature/ma-super-feature

# 3. Commit tes changements
git commit -m "feat: ajout d'une super feature"

# 4. Push
git push origin feature/ma-super-feature

# 5. Ouvre une Pull Request
```

**Conventions de commit** : [Conventional Commits](https://www.conventionalcommits.org/)

- `feat:` nouvelle fonctionnalité
- `fix:` correction de bug
- `docs:` documentation
- `style:` formatage
- `refactor:` refactoring
- `perf:` performance
- `chore:` maintenance

---

## 📄 Licence

Distribué sous licence **MIT**. Voir le fichier [LICENSE](LICENSE) pour plus d'informations.

---

## 👤 Auteur

**Gleaphe** — *Gunout*

- GitHub : [@gunout](https://github.com/gunout)
- Projet : [CyberDash_V2](https://github.com/gunout/CyberDash_V2)
- 🌐 Démo live : [gunout.github.io/CyberDash_V2](https://gunout.github.io/CyberDash_V2/)

---

<div align="center">

**🇷🇪 Fait avec ❤️ pour La Réunion 🇷🇪**

[⬆ Retour en haut](#-reunion-monitor--dashboard-des-travaux-numériques-réunion)

### Gunout · 2026

© 2026 **Gunout** — Tous droits réservés.

</div>


