
# 🛠️ Guide d'Optimisation Minecraft (Fabric, Forge & Paper)

Ce guide compile les meilleures pratiques issues de MineStrator pour optimiser les performances de serveurs Minecraft : Fabric, Forge et Paper/Spigot.

---

## 🟢 Partie 1 – Mods Fabric : Impact et détails

| Mod                           | Impact         | Description détaillée |
|------------------------------|----------------|-------------------------|
| **Sodium**                   | 🟢 VERT        | Moteur de rendu ultra-performant (GPU-driven rendering). Augmentation massive des FPS. |
| **Sodium Extra**             | 🟠 ORANGE      | Réglages graphiques avancés pour Sodium. |
| **Indium**                   | 🟠 ORANGE      | Nécessaire pour Indigo avec Sodium <0.6. |
| **ImmediatelyFast**          | 🟠 ORANGE      | Réduction du coût CPU/GPU sur le rendu d'entités. |
| **Enhanced Block Entities**  | 🟠 ORANGE      | Modèles pré-baked pour les block entities (coffres, pancartes). |
| **More Culling**             | 🟠 ORANGE      | Masquage des faces non visibles, améliore les FPS. |
| **Lithium**                  | 🟢 VERT        | Optimise le tick serveur : IA, collisions, redstone. |
| **Starlight**                | 🟢 VERT        | Refonte du système de lumière : ultra rapide. |
| **FerriteCore**              | 🟢 VERT        | Réduction mémoire (blockstates, modèles). |
| **Smooth Boot**              | 🟠 ORANGE      | Répartit mieux les threads au démarrage. |
| **ModernFix**                | 🟠 ORANGE      | Optimisations mémoire et chargement. |
| **DashLoader**               | 🟠 ORANGE      | Cache les ressources au lancement. |
| **Krypton** (réseau)         | 🟢 VERT        | Amélioration du réseau client/serveur. |

---

## 🟣 Partie 2 – Mods Forge : Impact et détails

| Mod                  | Impact     | Description |
|----------------------|------------|-------------|
| **Rubidium**         | 🟢 VERT    | Port Forge de Sodium. |
| **Oculus**           | 🟠 ORANGE  | Ajoute les shaders à Rubidium. |
| **Entity Culling**   | 🟢 VERT    | Cache les entités non visibles. |
| **Pluto**            | 🟢 VERT    | Optimise le netcode Forge. |
| **Clumps**           | 🟠 ORANGE  | Fusionne les orbes d'XP. |
| **In Control!**      | 🟠 ORANGE  | Contrôle avancé des spawns. |
| **Magnum Torch**     | 🟠 ORANGE  | Empêche le spawn dans une large zone. |

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
