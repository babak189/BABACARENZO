# BABACARENZO
MINI JEUX
EADME — Mini Brigitte Game (libGDX)
# MiniSoulKnight

A [libGDX](https://libgdx.com/) project generated with [gdx-liftoff](https://github.com/libgdx/gdx-liftoff).

This project was generated with a template including simple application launchers and an `ApplicationAdapter` extension that draws libGDX logo.

## Platforms

- `core`: Main module with the application logic shared by all platforms.
- `lwjgl3`: Primary desktop platform using LWJGL3; was called 'desktop' in older docs.

## Gradle

This project uses [Gradle](https://gradle.org/) to manage dependencies.
The Gradle wrapper was included, so you can run Gradle tasks using `gradlew.bat` or `./gradlew` commands.
Useful Gradle tasks and flags:

- `--continue`: when using this flag, errors will not stop the tasks from running.
- `--daemon`: thanks to this flag, Gradle daemon will be used to run chosen tasks.
- `--offline`: when using this flag, cached dependency archives will be used.
- `--refresh-dependencies`: this flag forces validation of all dependencies. Useful for snapshot versions.
- `build`: builds sources and archives of every project.
- `cleanEclipse`: removes Eclipse project data.
- `cleanIdea`: removes IntelliJ project data.
- `clean`: removes `build` folders, which store compiled classes and built archives.
- `eclipse`: generates Eclipse project data.
- `idea`: generates IntelliJ project data.
- `lwjgl3:jar`: builds application's runnable jar, which can be found at `lwjgl3/build/libs`.
- `lwjgl3:run`: starts the application.
- `test`: runs unit tests (if any).

Note that most tasks that are not specific to a single project can be run with `name:` prefix, where the `name` should be replaced with the ID of a specific project.
For example, `core:clean` removes `build` folder only from the `core` project.


Présentation du projet:

Mini Brigitte Game est un jeu 2D développé en Java avec le framework libGDX.
Le jeu propose une arène dans laquelle le joueur incarne un personnage devant éviter des monstres, atteindre un coffre et progresser à travers plusieurs vagues de difficulté croissante.

Le projet a été développé avec une approche progressive, en mettant l’accent sur la gestion correcte des collisions,l’adaptation à différentes tailles d’écran,la structuration propre du code et l’équilibrage du gameplay.

Technologies utilisées
Langage : Java
Framework : libGDX (LWJGL3)
Gestion de projet : Gradle
Outil de mapping : Tiled (.tmx)
Architecture : ApplicationAdapter (libGDX)

Structure du projet
Le projet est organisé selon la structure standard libGDX :
core/
Contient toute la logique du jeu (rendu, collisions, gameplay, entités).
lwjgl3/
Module desktop permettant l’exécution du jeu sur PC.
assets/
Contient les ressources graphiques et la carte Tiled 

Carte et collisions (Tiled)
La carte du jeu a été conçue avec Tiled et exportée au format .tmx.
Layer de collisions
Une couche nommée Collisions contient des rectangles invisibles.
Ces rectangles définissent les murs, bordures et limites physiques du jeu.
Les collisions ne sont pas basées sur la taille de l’écran, mais sur la carte elle-même.
Cela garantit que :
-le comportement est identique en plein écran ou en fenêtre,
-les entités ne sortent jamais de la zone jouable,
-la logique est propre et extensible.




Joueur
Le joueur est contrôlé au clavier (ZQSD / WASD / flèches),possède une vitesse définie et est bloqué par les collisions Tiled,
La collision du joueur est calculée avant le déplacement, afin d’éviter tout chevauchement avec le décor.




Monstres (ennemis)
Les monstres sont générés à chaque vague,se déplacent librement dans l’arène,poursuivent le joueur lorsqu’il entre dans un rayon donné,voient leur vitesse et agressivité augmenter à chaque vague.
La difficulté progresse naturellement grâce à l’augmentation de la vitesse, à un rayon de poursuite plus large, à une pression constante sur le joueur.




Coffre 
Le coffre est positionné à un endroit stratégique de la carte et se déplace verticalement dans une zone définie,




Système de vagues
Le jeu est structuré autour de vagues successives
Chaque vague augmente la difficulté,réinitialise les ennemis,conserve le score et les vies.
Une fois la dernière vague terminée :
le joueur gagne la partie,
le jeu se fige correctement (aucun déplacement en arrière-plan).




Vies et score
Le joueur dispose d’un nombre limité de vies.
Une collision avec un monstre = retire une vie,
replace le joueur à son point de départ.
Lorsque les vies tombent à zéro la partie est perdue,
Un écran GAME OVER s’affiche.
Le score et les informations de jeu sont affichés en permanence à l’écran.




Gestion de l’affichage et du redimensionnement
Le jeu utilise une caméra monde pour le rendu du jeu,Une caméra UI séparée pour les textes (score, vies, messages).
Grâce à cela les textes restent visibles en petit écran et en plein écran,l’interface reste lisible quelle que soit la résolution.




Lancement du jeu
Depuis la racine du projet :
./gradlew lwjgl3:run
ou sous Windows :
gradlew.bat lwjgl3:run




Auteurs
Projet réalisé par :
Enzo Thureau Mensah L3 ST
Ababacar Khalifa Diouf L3 ST
