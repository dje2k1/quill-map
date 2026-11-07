# The Cartographer's Quill

Une plume dessine, trait après trait, une carte de monde fantastique sur un vieux parchemin : cadre et rose des vents, côtes, lavis d'aquarelle, rivières, montagnes, forêts, routes, villes et châteaux, noms des royaumes et des mers, navires, serpent de mer, puis le titre dans son bandeau.

Chaque monde est généré aléatoirement (relief, noms, placement), le tout dans un seul fichier HTML sans dépendance, à part la police « IM Fell English » chargée depuis Google Fonts.

## Utilisation

Ouvrir `index.html` dans un navigateur.

- **Pause** / **1× 2× 4×** / **Redraw** (même carte) / **New world** (nouvelle carte)
- Raccourcis : `Espace` pause, `R` redessiner, `N` nouveau monde
- Le numéro après `#` dans l'adresse identifie la carte : `index.html#4242` redessine toujours le même monde.

---

# 16 Octobre : défends la boutique

Beat'em up en 3D (vue de dessus, esprit arène) dans le dossier `16-octobre/`. Tu incarnes le Responsable du Microsoft Store de Nice et tu défends la boutique contre des vagues de casseurs.

## Utilisation

Ouvrir `16-octobre/index.html` dans un navigateur (connexion requise pour charger Three.js r128 depuis cdnjs et les polices Google). Jouable au clavier sur PC et au tactile sur mobile (joystick + boutons).

| Action | Clavier | Tactile |
| --- | --- | --- |
| Se déplacer | ZQSD / WASD / flèches | joystick (moitié gauche) |
| Frapper / lancer | Espace ou J | FRAPPER |
| Prendre / lâcher | K | PRENDRE |
| Esquive | Maj ou L | ESQUIVE |
| Appel CRS | C | CRS |
| Pause | Échap ou P | PAUSE |

## Gameplay

- **Vagues** de casseurs de plus en plus nombreuses ; toutes les 5 vagues, le **Chef des casseurs** (panneau STOP, charges) arrive. Le battre déclenche une livraison (+3 par rayon, vitrines réparées).
- **Casseurs** : casseurs (parfois armés d'une barre de fer ou d'une batte, cassent les vitrines), voleurs rapides (foncent sur les consoles et les cartes), lanceurs de pavés.
- **Armes** : désarme les casseurs et ramasse leurs barres, battes et pavés ; lance manettes, Surface Laptop ou consoles (chaque console lancée coûte 1 en stock) ; soulève chaises, barrières, poubelles et présentoirs.
- **Appel CRS** : 2 au départ, des grenades lacrymogènes dispersent tous les casseurs touchés (ils lâchent armes et butin).
- **Bonus** : café (soin), mode rage (dégâts ×1,8), appel CRS supplémentaire.
- **Vols** : un casseur qui sort avec un produit le fait perdre définitivement ; frappe-le avant pour qu'il le lâche, puis ramasse-le.
- **Défaite** : dès qu'un des trois rayons (Jeux Xbox, Consoles, Cartes Pokémon) est vide et qu'aucun produit volé n'est encore récupérable.

Musique et bruitages sont synthétisés en direct (WebAudio). Le record est gardé dans le navigateur.
