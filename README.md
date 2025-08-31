# 🛠️ Guide d'Optimisation Minecraft (Fabric, Forge & Paper)

Ce guide utilise les descriptions officielles publiées par Alexis sur MineStrator pour vous offrir un aperçu technique et détaillé de chaque mod recommandé.

---

## 🟢 Partie 1 – Mods Fabric (descriptions issues du forum)

| Mod                      | Impact | Description technique |
|--------------------------|--------|------------------------|
| **Sodium**              | 🟢 VERT | Remplace le moteur de rendu graphique de Minecraft pour augmenter significativement les FPS sans altérer la qualité visuelle. L’un des mods les plus rapides et compatibles. |
| **Indium**              | 🟠 ORANGE | Add‑on pour Sodium (versions <0.6, MC ≤ 1.20) permettant le rendu via Indigo : nécessaire pour la compatibilité avec les mods visuels (shaders, lighting, textures). |
| **Sodium Extra**         | 🟠 ORANGE | Complément à Sodium : offre un menu vidéo enrichi (tri des paramètres, zoom, toggles particules/entités) pour affiner le rendu. |
| **ImmediatelyFast**      | 🟠 ORANGE | Optimise le pipeline de rendu OpenGL “immediat mode” (UI, entités, particules) en batchant et limitant les appels coûteux. |
| **Enhanced Block Entities (EBE)** | 🟠 ORANGE | Remplace le rendu traditionnel des block entities (coffres, têtes…) par des modèles « baked », réduisant fortement l’impact FPS tout en conservant animations/lumière. |
| **Entity Culling**       | 🟢 VERT | (Fabric) Utilise un algorithme asynchrone pour cacher entités et blocs hors champ, améliorant les performances graphiques. |
| **More Culling**         | 🟠 ORANGE | Étend le culling interne à des composants invisibles (feuilles internes, entités hors champ, etc.), réduisant le rendu GPU. |
| **Lithium**              | 🟢 VERT | Optimise la physique, le tick des entités/mobs/redstone ; gain de 50 % de temps de tick serveur/solo. |
| **Starlight**            | 🟢 VERT | Refonte complète du moteur de lumière : +90 % plus rapide que Vanilla, corrige bugs d’éclairage. |
| **Phosphor**             | 🟠 ORANGE | Ancien mod d’éclairage remplaçable par Starlight sur les versions récentes. |
| **Krypton**              | 🟢 VERT | Optimisation du réseau (Netty), transfert plus efficace des paquets, réduction de la latence et des pics réseau. |
| **LazyDFU**              | 🟠 ORANGE | Décale l'initialisation du DataFixerUpper pour accélérer le démarrage des mondes récents. |

---

## 🟣 Partie 2 – Mods Forge (descriptions issues du forum)

| Mod                        | Impact | Description technique |
|---------------------------|--------|------------------------|
| **Adaptive Performance Tweaks (APT)** | 🟢 VERT | Ensemble de tweaks modulables ajustant dynamiquement entités et rendu selon la charge système pour maintenir un TPS stable. |
| **AI Improvements**        | 🟢 VERT | Rend l'IA des mobs moins gourmande en CPU (pathfinding, navigation), limitant le lag en présence de nombreux entités. |
| **Performant**            | 🟠 ORANGE | Pack d’optimisations serveur (1.14–1.16) améliorant le TPS via des modifications internes (mobs, tâches, etc.). |
| **Canary (Lithium for Forge)** | 🟢 VERT | Port non officiel de Lithium sur Forge, apportant les optimisations de physique et gestion du monde. |
| **Radium Reforged**       | 🟢 VERT | Alternative à Canary, port Lithium pour Forge/NeoForge, optimisant TPS/mécanismes serveur. |
| **Alternate Current**     | 🟢 VERT | Refonte du système redstone pour réduire les mises à jour redondantes sans modifier le gameplay. |
| **Smooth Chunk Save**     | 🟠 ORANGE | Répartit les opérations d’écrire disque sur plusieurs ticks pour éviter les freezes lors de l’autosave. |
| **Chunk Sending**         | 🟢 VERT    | Optimise l’envoi des données de chunk aux joueurs en espaçant les envois sur plusieurs ticks. |
| **Connectivity**          | 🟢 VERT    | Améliore la gestion réseau côté Forge (timeouts, taille paquets, limites), réduisant latence/erreurs. |
| **Pluto**                 | 🟢 VERT    | Portage Forge de Krypton : améliore netcode, compression, buffer de paquets en multijoueur. |
| **Clumps**                | 🟠 ORANGE | Fusionne les orbes XP pour réduire le nombre d’entités actives, limitant les lags dans les fermes/workflows intensifs. |
| **In Control!**           | 🟠 ORANGE | Configuration précise du spawn des mobs (zones, fréquence), pour éviter les pics d’IA/follow-up impact serveur. |
| **Magnum Torch**          | 🟠 ORANGE | Permet de placer des méga-torches empêchant les spawns hostiles dans une zone élargie, allégeant la charge CPU. |
| **Saturn**                | 🟠 ORANGE | Optimise la mémoire (buffers, cache) pour réduire l’empreinte moddé sur client et serveur. |
| **FoamFix**               | 🟠 ORANGE | Optimise structures de données pour les versions 1.8–1.12.2, réduisant la RAM et accélérant le chargement modpacks. |
| **CullLessLeaves Reforged** | 🟠 ORANGE | Culls intelligemment les faces cachées des feuilles, offrant +5–10 % FPS dans les zones boisées denses. |
| **Entity Collision FPS Fix** | 🟠 ORANGE | Désactive les collisions entité–entité côté client pour alléger la charge CPU sur les scènes pleines d’entités. |
| **Better Biome Blend**     | 🟠 ORANGE | Rend les transitions de biome plus efficaces (multithread) avec un rendu fluide et moins gourmand. |
| **Chunk Pregenerator (Forge/Chunky)** | 🟢 VERT | Génère à l’avance les chunks pour éviter les lag spikes en exploration. |

---

## 🟡 Partie 3 – Optimisation Serveur Paper/Spigot

### 3.1. Réglages `.yml`

**bukkit.yml**
```yaml
spawn-limits:
  monsters: 50
  animals: 8
chunk-gc:
  period-in-ticks: 400
ticks-per:
  monster-spawns: 5
  water-spawns: 11
```

**spigot.yml**
```yaml
save-user-cache-on-stop-only: true
```

**paper.yml**
```yaml
hopper:
  disable-move-event: true
view-distance: 4
paper:
  world-settings:
    default:
      view-distance: 8
      use-faster-eigencraft-redstone: true
```

### 3.2. Plugins utiles

- **Insight** – 🟠 ORANGE : analyse les entités/tile-entities par chunk.

---

## 🌍 Partie 4 – Tuto Prégénération avec Chunky

### 1. Installer Chunky

- Téléchargez le plugin Chunky compatible avec votre version serveur.
- Placez-le dans le dossier `plugins/` et redémarrez le serveur.

### 2. Définir la zone à générer

```bash
/chunky center
/chunky radius 5000
/chunky shape square
```

### 3. Démarrer la génération

```bash
/chunky start
```

### 4. Astuces

- Utilisez `/chunky pause` pour stopper temporairement.
- Vérifiez la progression avec `/chunky status`.

---

## 🧠 Partie 5 – Conseils Généraux

- Utilisez **Paper** : économie mémoire et meilleures performances.
- **Prégénérez** la map avec Chunky ou Chunk Pregenerator.
- Tenez **à jour** tous les mods/plugins.
- **Baissez la view-distance** (6–10).
- Préférez **Java OpenJ9** sur VPS à faibles ressources.
- Analysez les lags avec **Spark**.

---

# 🧪 TUTO Spark – Analyse de performance

### Installation

- Ajoutez `spark.jar` à vos `plugins/` ou `mods/`.

### Commandes utiles

```bash
/spark tps
/spark profiler --timeout 30
/spark tickmonitor
/spark profiler --only-ticks-over 100
/spark heap
```

### Lecture des résultats

- **Timeline** : mesure de stabilité.
- **Flamegraph** : identifie les sources de lag.
- **World/Chunk** : entités ou redstone excessives.

---

## ✅ Légende Impact

| Couleur | Signification |
|--------|---------------|
| 🟢 VERT | Impact très positif, recommandé |
| 🟠 ORANGE | Impact modéré, selon contexte |
| 🔴 ROUGE | À éviter ou instable |

---

Avec ce guide, vous disposez d’une base complète pour booster les performances de vos serveurs Minecraft (moddés ou non) tout en maintenant une excellente jouabilité.
