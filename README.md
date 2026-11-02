# 🎬 Motion Studio v4 — PWA

Studio de motion design IA qui tourne entièrement dans le navigateur.

## 🚀 Déploiement en 3 minutes

### Option A — GitHub Pages (recommandé)

1. Crée un repo GitHub public (ex: `motion-studio`)
2. Dépose les 5 fichiers : `index.html`, `manifest.json`, `sw.js`, `icon.svg`, `README.md`
3. **Settings → Pages → Source : `main` / `root`** → Save
4. Attends 30 secondes. Ton app est en ligne sur :
   ```
   https://TON_USERNAME.github.io/motion-studio/
   ```

### Option B — Netlify / Vercel (drag & drop)

1. Glisse le dossier entier sur **https://app.netlify.com/drop**
2. C'est en ligne, HTTPS automatique.

## 📱 Installer en PWA

### Sur Android (Chrome)
1. Ouvre l'URL en HTTPS
2. Menu ⋮ → **« Installer l'application »** ou **« Ajouter à l'écran d'accueil »**
3. Une icône Motion Studio apparaît sur ton écran d'accueil, en plein écran

### Sur iPhone (Safari)
1. Ouvre l'URL dans **Safari** (pas Chrome)
2. Bouton Partager ↑ → **« Sur l'écran d'accueil »**
3. L'app se lance en plein écran sans barre Safari

### Sur Desktop (Chrome/Edge)
- Icône ⊕ dans la barre d'adresse → **Installer**

## 🔑 Configuration API

Au premier lancement, ajoute :

- **Clé Agnes** (obligatoire) : [platform.agnes-ai.com](https://platform.agnes-ai.com)
- **Clé Mystral** (optionnel) : [console.mistral.ai](https://console.mistral.ai)

Les clés sont stockées dans `localStorage` (chiffré par le navigateur). Elles ne quittent jamais ton appareil sauf vers les APIs Agnes/Mistral.

## ✨ Fonctionnalités

- 🚀 **Mode Auto IA** — décris une vidéo, l'IA crée tout
- 📷 **Photos de référence** — guide l'IA avec tes images
- 🎙️ **Voix off IA** — 10 voix Agnes
- 🤖 **Fournisseur LLM** — Agnes par défaut, Mystral optionnel
- ⬇️ **Export vidéo** — WebM/MP4 avec ou sans voix
- 💾 **Projets sauvegardables** en JSON

## ⚠️ Limites PWA connues

| Fonctionnalité | Chrome Android | Safari iOS |
|---|---|---|
| Export vidéo WebM | ✅ | ⚠️ MP4 seulement |
| Audio dans l'export | ✅ | ⚠️ Peut échouer |
| Voix navigateur (fallback) | ✅ | ⚠️ Limité |
| Installation écran d'accueil | ✅ | ✅ (manuel) |
| Offline (UI seulement) | ✅ | ✅ |

**Astuce iOS** : si l'export vidéo plante, décoche « voix off » avant d'exporter, ou utilise un iPhone/Android.

## 🧪 Debug

- Chrome DevTools → Application → Service Workers
- Console : `[MS] Platform: web/PWA` et `[PWA] Service Worker enregistré` doivent apparaître

## 🔄 Mise à jour

Modifie `index.html` et incrémente `CACHE_VERSION` dans `sw.js` (ex: `v4.0.1`), push sur GitHub. Les utilisateurs reçoivent la mise à jour au prochain lancement.

## 📦 Passer en APK/iOS plus tard

Ce code est **100% compatible Capacitor** grâce au `native-bridge` intégré. Si tu veux plus tard produire un APK/iOS natif :
1. Suis les instructions Capacitor fournies précédemment
2. Copie ce même `index.html` dans `www/`
3. Le pont détectera automatiquement l'environnement natif

## 📄 Licence

Usage personnel et commercial autorisé. Attribution appréciée.
