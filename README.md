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

Beat'em up en 3D (caméra à la troisième personne) dans le dossier `17-octobre/`. Tu incarnes le Responsable d'une boutique Micromania à Nice, la nuit des émeutes du 17 octobre, et tu défends le magasin contre des vagues de casseurs.

## Utilisation

Ouvrir `17-octobre/index.html` dans un navigateur récent compatible WebGL 2 (Chrome, Edge, Firefox, Safari 15+). Connexion requise : le moteur Three.js r186 et ses modules de post-traitement sont chargés depuis jsDelivr, les polices depuis Google Fonts. Tout le reste (personnages, textures, décor, sons) est fabriqué par le programme au lancement, ce qui prend quelques secondes. Jouable au clavier, à la manette et au tactile (joystick + boutons).

| Action | Clavier | Manette PS4 | Tactile |
| --- | --- | --- | --- |
| Se déplacer | ZQSD / WASD / flèches | stick gauche / croix | joystick |
| Frapper / lancer | J ou clic gauche | □ | FRAPPER |
| Sauter (puis frapper = plongeon) | Espace | ✕ | SAUT |
| Prendre un objet / saisir un casseur | K ou clic droit | △ | PRENDRE |
| Esquive (puis frapper = charge d'épaule) | Maj ou L | ○ | ESQUIVE |
| Colère du gérant (jauge pleine) | F ou I | R1 / R2 | SPÉCIAL |
| Appel CRS | C | L1 / L2 | CRS |
| Pause | Échap ou P | Options | PAUSE |

La manette vibre à chaque impact (navigateurs compatibles).

## Combat

- **Enchaînement** : direct, direct, uppercut (envoie le casseur en l'air, on peut le jongler), puis **coup de bide** qui le projette au loin.
- **Plongeon** : saut puis frappe, onde de choc à l'atterrissage, touche aussi les casseurs au sol.
- **Charge d'épaule** : frappe juste après une esquive, renverse tout sur son passage.
- **Saisie** : on soulève un casseur au-dessus de sa tête et on le projette sur les autres.
- **Combo** : compteur de coups (multiplicateur de score), cassé quand on encaisse.
- **Colère du gérant** : la jauge se remplit en frappant ; une fois pleine, le Responsable bondit et retombe dans une énorme onde de choc, avec ralenti, zoom, éclairs et sol fissuré.
- Les casseurs tournent autour du joueur et n'attaquent qu'à deux à la fois.

## Graphismes

- **Moteur** : Three.js r186 (WebGL 2), rendu HDR avec anticrénelage MSAA, occlusion ambiante (GTAO), bloom, étalonnage ACES, profondeur de champ, aberration chromatique, vignette et grain.
- **Personnages** : le Responsable, les casseurs, les voleurs et le Chef sont sculptés par le programme au lancement (champs de distance transformés en maillages lissés, puis squelette et déformation de peau) : corps, visages, mains, plis des vêtements, capuches, cagoules, casque. Shaders de tissu (molleton, jersey, jean, nylon, cuir), de peau (la lumière diffuse sous la surface, barbe, sourcils) et de cheveux ; liseré de contre-jour pour détacher les silhouettes de la rue. Cheveux et ventre du gérant bougent par ressorts.
- **Décor** : une avenue niçoise la nuit, sous la pluie. Textures en relief calculées sur la carte graphique (dalles, bitume, crépi, béton, métal, rideaux de fer) ; sol mouillé avec flaques, ondes de pluie et reflets en temps réel ; boutique vitrée (rayonnages, gondoles, écrans de démo, sol poli) ; immeubles à persiennes et balcons en fer forgé, pharmacie, tabac, palmiers, rails du tramway, voiture brûlée.
- **Lumières** : intensités physiques, clair de lune, lampadaires au sodium et leur cône dans la brume, lumière de la boutique projetée sur le trottoir avec l'ombre des piliers, néons qui grésillent, feux qui vacillent, gyrophares de l'appel aux CRS, éclairs d'orage à l'arrivée du Chef, reflets d'ambiance photographiés dans la scène.
- **Effets spéciaux** : étincelles et éclairs électriques aux impacts, traînées lumineuses des coups, ondes de choc qui déforment l'image, fissures incandescentes au sol, poussière et gaz lacrymogène éclairés par la rue, éclats de verre, flammes, braises, fumée, pluie, flou radial, bandes cinéma et ralenti sur les coups spéciaux.
- **Qualité** : **Ultra**, **Élevé** ou **Performance** (bouton « Graphismes » sur l'écran titre et dans le menu pause, ou `?q=ultra`, `?q=high`, `?q=perf` dans l'adresse). Ultra par défaut sur ordinateur, Performance sur mobile. Si l'affichage passe sous 27 images par seconde, le jeu descend lui-même d'un cran.
- **Caméra** : troisième personne, elle se rapproche quand la bagarre est serrée, recule quand les casseurs arrivent de loin, plonge dans la boutique quand on y entre (la façade s'efface) et zoome sur les coups spéciaux.
- **Le Responsable** : forte corpulence, cheveux longs bruns, barbe. Tous les réglages d'apparence sont dans l'objet `GERANT` en haut du script (teint, cheveux et leur longueur, barbe, t-shirt et logo, jean, chaussures, corpulence, taille).

## Gameplay

- **Vagues** de casseurs de plus en plus nombreuses ; toutes les 5 vagues, le **Chef des casseurs** (casque, panneau STOP, charges) arrive sous l'orage. Le battre déclenche une livraison (+3 par rayon, vitrines réparées).
- **Casseurs** : casseurs (parfois armés d'une barre de fer ou d'une batte, cassent les vitrines), voleurs rapides (foncent sur les consoles et les cartes), lanceurs de pavés.
- **Armes** : désarme les casseurs et ramasse leurs barres, battes et pavés ; lance manettes, PC portables ou consoles (chaque console lancée coûte 1 en stock) ; soulève chaises, barrières, poubelles et présentoirs.
- **Appel CRS** : 2 au départ, des grenades lacrymogènes dispersent tous les casseurs touchés (ils lâchent armes et butin).
- **Bonus** : café (soin), mode rage (dégâts ×1,8), appel CRS supplémentaire.
- **Vols** : un casseur qui sort avec un produit le fait perdre définitivement ; frappe-le avant pour qu'il le lâche, puis ramasse-le.
- **Défaite** : dès qu'un des trois rayons (Jeux vidéo, Consoles, Cartes Pokémon) est vide et qu'aucun produit volé n'est encore récupérable.

Musique et bruitages sont synthétisés en direct (WebAudio). Le record est gardé dans le navigateur.
