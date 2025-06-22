
# 🛠️ Guide d'Optimisation Minecraft (Fabric & Paper)

Ce guide compile les meilleures pratiques et recommandations techniques issues des forums MineStrator pour améliorer les performances (FPS, TPS, mémoire, réseau) d'un serveur Minecraft moddé ou Vanilla.

---

## 🟢 Partie 1 – Mods Fabric : Impact et détails

| Mod                           | Impact         | Description détaillée |
|------------------------------|----------------|-------------------------|
| **Sodium**                   | 🟢 VERT        | Moteur de rendu alternatif ultra-performant utilisant des techniques avancées de culling et rendu GPU. Augmente fortement les FPS. |
| **Sodium Extra**             | 🟠 ORANGE      | Ajoute des options graphiques et des contrôles supplémentaires à Sodium pour affiner les performances selon les besoins. |
| **Indium**                   | 🟠 ORANGE      | API de compatibilité pour rendre Sodium compatible avec les mods visuels utilisant Indigo. |
| **ImmediatelyFast**          | 🟠 ORANGE      | Réduit les appels OpenGL redondants, notamment lors du rendu d’interfaces et d’entités, allégeant le GPU. |
| **Enhanced Block Entities**  | 🟠 ORANGE      | Transforme les block entities complexes (coffres, pancartes) en modèles statiques plus légers pour le rendu. |
| **More Culling**             | 🟠 ORANGE      | Optimise le rendu en éliminant les faces de blocs invisibles. Réduction du travail GPU. |
| **Lithium** (client/serveur) | 🟢 VERT        | Optimise les calculs serveur : IA, redstone, collisions. Réduction du temps de tick jusqu'à 50 %. |
| **Starlight**                | 🟢 VERT        | Réécriture complète du moteur de lumière Vanilla. Génération de lumière quasi-instantanée. |
| **FerriteCore**              | 🟢 VERT        | Optimise l’utilisation mémoire en réduisant les objets dupliqués comme les blockstates ou modèles. |
| **Smooth Boot / ThreadTweak**| 🟠 ORANGE      | Améliore le démarrage du jeu en répartissant mieux la charge sur plusieurs threads. |
| **ModernFix**                | 🟠 ORANGE      | Corrige des inefficacités dans le code de chargement des ressources, accélère l’ouverture du jeu. |
| **DashLoader**               | 🟠 ORANGE      | Met en cache les ressources du jeu (textures, sons, modèles) pour un chargement plus rapide au démarrage. |
| **Krypton** (réseau)         | 🟢 VERT        | Optimise le netcode Minecraft. Réduction de la latence réseau, meilleur en multi. |

---

## 🟡 Partie 2 – Optimisation Serveur Paper/Spigot

### 2.1. Prégénération de la map

- **Chunky** (plugin ou mod) – 🟢 VERT  
  Générez les chunks avant l’arrivée des joueurs pour éviter les ralentissements en exploration.

### 2.2. Réglages `.yml`

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

### 2.3. Plugins utiles

- **Insight** – 🟠 ORANGE  
  Analyse les entités/tile-entities par chunk. Détection des zones surchargées.

---

## 🧠 Partie 3 – Conseils Généraux

- Utiliser **Paper** plutôt que Vanilla ou Spigot – 🟢 VERT  
- Préférer **Java OpenJ9** sur machine à faible RAM – 🟠 ORANGE  
- Toujours **mettre à jour les plugins/mods/datapacks** – 🟠 ORANGE  
- **Réduire view-distance** à 6–10 selon la puissance – 🟠 ORANGE  
- **Prégénérer les mondes** – 🟢 VERT  
- **Utiliser Spark** pour profiler le serveur – 🟢 VERT

---

# 🧪 TUTO Spark – Profilage de performances

### 1. Installation

Placez `spark.jar` dans `/plugins` (Spigot/Paper) ou `/mods` (Fabric/Forge) et redémarrez.

### 2. Vérification rapide

```bash
/spark tps
```

Affiche les TPS, MSPT, CPU. Permet de vérifier la stabilité du serveur.

### 3. Profilage complet

```bash
/spark profiler --timeout 30
```

Crée un profil sur 30 secondes. Idéal pour les lags persistants.

### 4. Détection des ticks lents

```bash
/spark tickmonitor
/spark profiler --only-ticks-over 100
```

Cible uniquement les ticks > 100 ms.

### 5. Analyse graphique (via spark viewer)

- **Timeline** : pic de TPS/MSPT
- **Arbre d'exécution** : fonctions responsables du lag
- **World/Entity/Chunk** : surcharge locale d’entités

### 6. Actions recommandées

- Identifier le code ou plugin fautif  
- Localiser la zone problématique  
- Adapter la configuration, supprimer ou corriger  

---

## ✅ Légende Impact

| Couleur | Signification |
|--------|---------------|
| 🟢 VERT | Impact très positif, recommandé |
| 🟠 ORANGE | Impact modéré ou situationnel |
| 🔴 ROUGE | Non utilisé ici (peut avoir effets secondaires) |

---

Avec ce guide, vous pouvez optimiser efficacement un serveur Minecraft moddé ou vanilla en adaptant votre environnement à vos ressources.
