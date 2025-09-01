# ⚡ Optimisations côté Client (FPS & rendu)

Améliorez vos performances graphiques dans Minecraft grâce à des mods Fabric ou Forge optimisés.  
Ces mods **n’impactent pas le gameplay**, ils optimisent uniquement le rendu visuel et la fluidité.

👉 Légende d’impact :  
🟩 **Fort** — Gain majeur de FPS / réduction de lag  
🟧 **Moyen** — Gain notable selon votre configuration  
🟥 **Faible** — Amélioration plus spécifique ou situationnelle  

---

# 🧵 Fabric

## 🟩 Sodium  
🔗 [Modrinth – Sodium](https://modrinth.com/mod/sodium)  
**Versions :** 1.16.1 → 1.21.x  
**Dépendances :** Aucune (Indium requis uniquement pour 1.16–1.20).  

- Réécrit le moteur de rendu OpenGL de Minecraft.  
- Boost de FPS **spectaculaire** (souvent ×2 ou ×3).  
- Compatible shaders via **Iris** (équivalent Fabric d’Oculus).  
- Depuis la 0.6.0, **Indium est intégré**.  

💡 **Combo conseillé :** Sodium + Sodium Extra + ImmediatelyFast.

---

## 🟧 Indium  
🔗 [Modrinth – Indium](https://modrinth.com/mod/indium)  
**Versions :** 1.16.5 → 1.20.x  
**Dépendances :** Sodium.  

- Fournissait le support Fabric Renderer (Indigo).  
- Utile pour mods visuels (Connected Textures, Lumières dynamiques…).  
- ❌ Obsolète en 1.21+ (inclus dans Sodium).

---

## 🟩 Sodium Extra  
🔗 [Modrinth – Sodium Extra](https://modrinth.com/mod/sodium-extra)  
**Versions :** 1.16.5 → 1.21.x  
**Dépendances :** Sodium.  

- Menu graphique enrichi (zoom, tri, réglages détaillés).  
- Désactivation des particules / ajustement entités.  
- Permet un réglage **fin du rendu** pour gratter encore plus de FPS.

---

## 🟩 ImmediatelyFast  
🔗 [Modrinth – ImmediatelyFast](https://modrinth.com/mod/immediatelyfast)  
**Versions :** 1.18.2 → 1.21.x  
**Dépendances :** Aucune.  

- Optimise les appels de rendu OpenGL (entités, particules, UI).  
- Compatible Sodium & mods graphiques.  
- **Plug-and-play** : installation → FPS plus fluides.

---

## 🟩 Enhanced Block Entities (EBE)  
🔗 [Modrinth – EBE](https://modrinth.com/mod/ebe)  
**Versions :** 1.16.2 → 1.21.x  
**Dépendances :** Fabric API.  

- Remplace le rendu lourd des block entities (coffres, panneaux, spawners…).  
- Rend ces blocs **beaucoup moins coûteux** en FPS.  
- Compatible Sodium 0.6+ sans Indium.  

---

## 🟩 Entity Culling  
🔗 [Modrinth – EntityCulling](https://modrinth.com/mod/entityculling)  
**Versions :** 1.16 → 1.21.x  
**Dépendances :** Aucune.  

- Cache les entités & blocs **invisibles** (derrière un mur, hors champ).  
- Réduit charge GPU/CPU, surtout dans zones chargées.  
- Configurable via fichier ou [Mod Menu](https://modrinth.com/mod/modmenu).

---

## 🟧 More Culling  
🔗 [Modrinth – MoreCulling](https://modrinth.com/mod/moreculling)  
**Versions :** 1.18 → 1.21.x  
**Dépendances :** Cloth Config + Fabric API recommandé.  

- Étend le culling vanilla : feuilles, faces internes, entités spécifiques.  
- Similaire à l’option “Smart Leaves” d’OptiFine.  
- Peut être couplé avec **MoreCullingExtra** pour aller plus loin.  

---

## 🟥 Dynamic FPS  
🔗 [Modrinth – Dynamic FPS](https://modrinth.com/mod/dynamic-fps)  
**Versions :** 1.14.4 → 1.21.x  
**Dépendances :** Aucune (optionnel : Cloth Config + Mod Menu).  

- Réduit automatiquement FPS & consommation GPU/CPU **quand Minecraft est en arrière-plan**.  
- Idéal sur portable (gain d’autonomie).  
- Aucun impact direct en jeu → plutôt un **confort utilisateur**.

---

# 🛠 Forge / NeoForge

## 🟩 Rubidium  
🔗 [CurseForge – Rubidium](https://www.curseforge.com/minecraft/mc-mods/rubidium)  
**Versions :** 1.16.5 → 1.20.x  
**Dépendances :** Aucune.  

- Portage de Sodium pour Forge.  
- Grosse amélioration FPS, rendu fluide, optimisation VRAM.  
- Alternative principale à OptiFine.  
- 💡 Peut être couplé avec Rubidium Extra pour plus de réglages.

---

## 🟩 Embeddium  
🔗 [CurseForge – Embeddium](https://www.curseforge.com/minecraft/mc-mods/embeddium)  
**Versions :** 1.19+  
**Dépendances :** Aucune.  

- Fork de Rubidium, jugé plus stable et compatible.  
- Recommandé si Rubidium cause des bugs avec certains mods.  
- Même philosophie que Sodium → FPS massivement améliorés.

---

## 🟧 Rubidium Extra / Embeddium Extra  
🔗 [CurseForge – Rubidium Extra](https://www.curseforge.com/minecraft/mc-mods/rubidium-extra)  
**Versions :** 1.16.5 → 1.20.x  
**Dépendances :** Rubidium ou Embeddium.  

- Ajoute un menu d’options graphiques avancées (particules, animations, FPS counter…).  
- Approche proche de Sodium Extra côté Forge.  

---

## 🟧 Oculus  
🔗 [CurseForge – Oculus](https://www.curseforge.com/minecraft/mc-mods/oculus)  
**Versions :** 1.16.5 → 1.20.x  
**Dépendances :** Rubidium / Embeddium.  

- Equivalent Forge de **Iris** (support des shaders).  
- Ne booste pas les FPS → sert uniquement à activer les shaders.  

---

## 🟩 Entity Culling  
🔗 [CurseForge – Entity Culling](https://www.curseforge.com/minecraft/mc-mods/entityculling)  
**Versions :** 1.6.3 → 1.21.5  
**Dépendances :** Aucune.  

- Même principe que sur Fabric : ne rend pas ce qui est caché.  
- Compatible Rubidium / Embeddium.

---

## 🟧 Cull Less Leaves Reforged  
🔗 [CurseForge – Cull Less Leaves Reforged](https://www.curseforge.com/minecraft/mc-mods/cull-less-leaves-reforged)  
**Versions :** 1.18.2 → 1.20.2  
**Dépendances :** Aucune.  

- Variante de “Smart Leaves”.  
- Supprime le rendu des faces cachées des feuilles pour gagner ~10% de FPS en forêts.  

---

## 🟧 Entity Collision FPS Fix  
🔗 [CurseForge – Entity Collision FPS Fix](https://www.curseforge.com/minecraft/mc-mods/entity-collision-fps-fix)  
**Versions :** 1.18.2 → 1.19.2  
**Dépendances :** Aucune.  

- Désactive certains calculs inutiles de collision côté client.  
- Améliore les FPS dans les zones avec beaucoup d’entités rapprochées.  

---

## 🟧 Better Biome Blend  
🔗 [CurseForge – Better Biome Blend](https://www.curseforge.com/minecraft/mc-mods/better-biome-blend)  
**Versions :** 1.12.2 → 1.19  
**Dépendances :** Aucune.  

- Améliore le rendu des transitions de biomes (plus lisses et plus rapides).  
- FPS plus stables en exploration.  

---

# ✅ Recommandations

- **Fabric minimal** : Sodium + ImmediatelyFast + EBE  
- **Fabric complet** : Sodium + Sodium Extra + EBE + Entity/More Culling  
- **Forge minimal** : Embeddium (ou Rubidium) + Entity Culling  
- **Forge complet** : Embeddium + Embeddium Extra + Oculus + Cull Less Leaves  

---

# 📊 Impact général

### Fabric
- Sodium = **indispensable** 🟩  
- EBE, ImmediatelyFast, Entity Culling = **très recommandés** 🟩  
- Sodium Extra, More Culling = **bon plus** 🟧  
- Indium = utile uniquement ≤1.20 🟧  
- Dynamic FPS = confort mais pas vital 🟥  

### Forge
- Embeddium/Rubidium = **indispensable** 🟩  
- Entity Culling = **très recommandé** 🟩  
- Embeddium Extra / Rubidium Extra, Cull Less Leaves, Better Biome Blend = **bons plus** 🟧  
- Oculus = utile uniquement si shaders 🟧  
- Entity Collision FPS Fix = situationnel 🟧  
