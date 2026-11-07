# The Cartographer's Quill

Une plume dessine, trait après trait, une carte de monde fantastique sur un vieux parchemin : cadre et rose des vents, côtes, lavis d'aquarelle, rivières, montagnes, forêts, routes, villes et châteaux, noms des royaumes et des mers, navires, serpent de mer, puis le titre dans son bandeau.

Chaque monde est généré aléatoirement (relief, noms, placement), le tout dans un seul fichier HTML sans dépendance, à part la police « IM Fell English » chargée depuis Google Fonts.

## Utilisation

Ouvrir `index.html` dans un navigateur.

- **Pause** / **1× 2× 4×** / **Redraw** (même carte) / **New world** (nouvelle carte)
- Raccourcis : `Espace` pause, `R` redessiner, `N` nouveau monde
- Le numéro après `#` dans l'adresse identifie la carte : `index.html#4242` redessine toujours le même monde.

---

# 17 Octobre : défends la boutique

Beat'em up en 3D (vue de dessus, esprit arène) dans le dossier `17-octobre/`. Tu incarnes le Responsable d'une boutique Micromania à Nice, la nuit des émeutes du 17 octobre, et tu défends le magasin contre des vagues de casseurs.

## Utilisation

Ouvrir `17-octobre/index.html` dans un navigateur récent (connexion requise : Three.js r128 et ses modules de post-traitement sont chargés depuis cdnjs et jsDelivr, les polices depuis Google Fonts). Jouable au clavier sur PC et au tactile sur mobile (joystick + boutons).

| Action | Clavier | Tactile |
| --- | --- | --- |
| Se déplacer | ZQSD / WASD / flèches | joystick (moitié gauche) |
| Frapper / lancer | Espace ou J | FRAPPER |
| Prendre / lâcher | K | PRENDRE |
| Esquive | Maj ou L | ESQUIVE |
| Appel CRS | C | CRS |
| Pause | Échap ou P | PAUSE |

## Graphismes

- Rendu physique (PBR) : textures générées au lancement (bitume mouillé avec flaques, dalles de trottoir, carrelage brillant, tissus, jean, cheveux, métal brossé).
- Nuit : clair de lune avec ombres portées douces, lampadaires au sodium, néons de la boutique, feux (poubelle, voiture brûlée) qui vacillent, gyrophares lors de l'appel aux CRS, reflets d'environnement.
- Post-traitement en mode **Ultra** : bloom, tone mapping ACES, étalonnage, vignette, grain, légère aberration chromatique, FXAA. Le mode **Performance** (par défaut sur mobile) coupe le post-traitement et réduit les ombres ; bouton « Graphismes » sur l'écran titre et dans le menu pause.
- Personnages articulés (épaules, coudes, hanches, genoux) avec marche, coups, projections, chutes et toux sous les gaz.

## Gameplay

- **Vagues** de casseurs de plus en plus nombreuses ; toutes les 5 vagues, le **Chef des casseurs** (casque, panneau STOP, charges) arrive. Le battre déclenche une livraison (+3 par rayon, vitrines réparées).
- **Casseurs** : casseurs (parfois armés d'une barre de fer ou d'une batte, cassent les vitrines), voleurs rapides (foncent sur les consoles et les cartes), lanceurs de pavés.
- **Armes** : désarme les casseurs et ramasse leurs barres, battes et pavés ; lance manettes, PC portables ou consoles (chaque console lancée coûte 1 en stock) ; soulève chaises, barrières, poubelles et présentoirs.
- **Appel CRS** : 2 au départ, des grenades lacrymogènes dispersent tous les casseurs touchés (ils lâchent armes et butin).
- **Bonus** : café (soin), mode rage (dégâts ×1,8), appel CRS supplémentaire.
- **Vols** : un casseur qui sort avec un produit le fait perdre définitivement ; frappe-le avant pour qu'il le lâche, puis ramasse-le.
- **Défaite** : dès qu'un des trois rayons (Jeux vidéo, Consoles, Cartes Pokémon) est vide et qu'aucun produit volé n'est encore récupérable.

Musique et bruitages sont synthétisés en direct (WebAudio). Le record est gardé dans le navigateur.
