# Personnage 3D – Three.js

## Contenu
- `index.html` — la scène Three.js complète (fond `#95A8C8`, particules, flottement, rotation, responsive)
- `assets/character.fbx` — le personnage (version PBR, texturé)
- `assets/texture_diffuse.png`, `texture_normal.png`, `texture_metallic.png`, `texture_roughness.png` — les textures PBR appliquées manuellement au modèle

## Lancer le projet
Les navigateurs bloquent le chargement de fichiers locaux (FBX/textures) en ouvrant `index.html` directement (`file://`). Il faut donc servir le dossier via un petit serveur local :

**Avec Node.js :**
```
npx serve .
```

**Avec Python :**
```
python3 -m http.server 8000
```
puis ouvrir `http://localhost:8000` dans le navigateur.

## Ce que fait la scène
- Fond uni `#95A8C8`
- Personnage chargé depuis `base_basic_pbr.fbx`, texturé avec les 4 cartes PBR fournies, centré et mis à l'échelle automatiquement
- Rotation à la souris / au doigt (glisser-déposer) via `OrbitControls`, avec une légère rotation automatique quand on n'y touche pas
- Léger mouvement de flottement (haut/bas + oscillation) sur le personnage
- ~260 particules brillantes autour du personnage, avec un léger scintillement et une dérive lente
- Entièrement responsive : le canvas s'adapte à la taille de l'écran, la caméra recule légèrement en mode portrait pour garder le personnage dans le cadre, le zoom tactile natif est désactivé pour une meilleure expérience mobile

## Personnalisation rapide
Tout se règle en haut du script dans `index.html` :
- `BACKGROUND_COLOR` — couleur de fond
- `PARTICLE_COUNT` — nombre de particules
- `targetHeight` — taille du personnage à l'écran
- `controls.autoRotateSpeed` — vitesse de rotation automatique
