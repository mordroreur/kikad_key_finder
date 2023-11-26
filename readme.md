
# Key-Finder design

Ce repos est le travaille de Laurencot Mathieu pour la cinquième scéance de du cours de "Design à deux balles" mis en place par M. Marchand et M. Petit.
Le but de ce cour est de créer la carte électronque qui pourrait être implémenté dans le key-Finder. 
Vous trouverez donc tout les fichier de mon travaille.

## Information

Le travaille à été fait en utilisant le logiciel KiCad7.0.
Il suffit donc de cloner le projet, puis de l'ouvrir avec le logiciel kikad.
Le but estait de partir d'une base du composant nrf52 et de lui ajouter les fonctionnalité qe nous avons vue dans les cours précédents.

### Les fonctionnalités

La liste des fonctionnalité est disponnible sur le schéma ci-dessous

![shéma des fonctions ajoutés](schema_fonction.png)

Pour récapituler le shéma, nous avons ajouté un buzzer relié à la pin 06 de la puce, une led verte relié à la pin 12 et un bouton relié à la pin 04. Il y a aussi, le bouton reset, reliéa la pin 21 aussi nommé pin de reset et une batterie relié au vcc et au ground. Enfin il y a un connecteur de programmation(peut-être voué à disparaitre pour la version finale) qui est relié aux pins du swdio, swdclk, la pin de reset(inversé) et les pins 22, 23 et 24. 

## Limitation

Lors de ce travaille, je me suis heurté à de nombreux problèmes dont quelques un qui ne sont actuellement pas réglé.
Tout d'abord, même en copiant le VDD initialement présent, kikad n'as jamais accepté de les fusioner, il y a donc deux circuit electrique sur la puce, et des chevelux que kikad refuse de connecter.

Ensuite, mettre la pile d'un coté de la carte empêche de cabler l'autre coté de la carte, c'est pour cela que j'ai due agrandir la carte pour faire passer la pile à coté du reste. 



