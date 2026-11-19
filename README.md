# Mloka Crew

Site statique + une Netlify Function (`/api/votes`) qui garde les votes dans Netlify Blobs (la base de donnees integree a Netlify, rien a configurer).

```
public/index.html                 le site
netlify/functions/votes.mjs       GET = lire les totaux, POST {"key":"ninja"} = ajouter un vote
netlify.toml, package.json        config (dependance: @netlify/blobs)
```

## Mettre en ligne, etape par etape (GitHub + Netlify)

1. Dezipi `mloka-netlify.zip`. Khass tla9a: `public/`, `netlify/`, `netlify.toml`, `package.json`.
2. Sir l github.com, dir compte (wla dkhol), o dir **New repository** (smiyto `mloka-crew`, Public wla Private, bla README).
3. F page dyal l'repo jdid, clik **uploading an existing file**. Jbed l'fichiers kamlin (b dossiers dyalhom: `public`, `netlify`, `netlify.toml`, `package.json`) o 7etthom f l'page. 3ref bli `netlify/functions/votes.mjs` khasso ybqa f had l'path. Clik **Commit changes**.
4. Sir l app.netlify.com, **Sign up with GitHub**.
5. **Add new project** > **Import an existing project** > **GitHub** > khtar `mloka-crew`. Netlify ghadi y3ti lik settings jahzin (netlify.toml kayqoul publish = `public`). Ma tbeddel walo, clik **Deploy**.
6. Tsenna 1 la 2 d'dqayeq 7ta tchouf **Published**. Clik 3la l'link li ytl3 (b7al `xxxx.netlify.app`).
7. Jarreb: clik "+1 khra" 3la chi smiya, 3awed l'page: khasso yb9a l'3dad. 7el l'link 3la telephone o chouf bli l'3dad nafs chi.
8. Bach tbddel smiyt l'link: Site configuration > **Change site name**. Dir lia `mloka-crew` wla 3ndek.
9. Siftou l sa7abek.

## Tari9a CLI (bla GitHub)
```
npm install
npx netlify-cli login
npx netlify-cli deploy --prod --build
```
(`--build` dar bach l'function t'bundla m3a `@netlify/blobs`.) Drag-and-drop dyal l'folder f Netlify ma kaydmanch Functions m3a dependencies.

## Test local
```
npx netlify-cli dev
```
Kat7el http://localhost:8888.

## Notes
- Chi wa7ed 3ndou l'link y9der ysawet (bla login). Ila bghiti t7made mn spam, zid rate limit f `votes.mjs`.
- Bach t'reset: mse7 l'blobs mn Netlify UI (Blobs, store `mloka`).
