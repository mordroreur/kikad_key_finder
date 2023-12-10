
# Key-Finder design

Ce repos est le travaille de Laurencot Mathieu pour la cinq, six et septième scéance du cours de "Design à deux balles" mis en place par M. Marchand et M. Petit.
Le but de ce cour est de créer un objet concurent au [mini traceur gps de
action](https://www.action.com/fr-fr/p/2579654/mini-traceur-gps/). Pour cela,
nous avons travaillés sur la carte électronque qui pourrait être implémenté dans
le key-Finder, ainsi que sur le designe de l'objet. 
Vous trouverez donc tout les fichier de mon travaille dans se repos.

## Information

Le travaille à été fait en utilisant les logiciels KiCad7.0 et fusion360.
Il suffit donc de cloner le projet, puis de l'ouvrir avec le logiciel kikad. Et
d'importer le fichier Design_key_finder.f3z dans l'application fusion 360.
Le but était de partir d'une base du composant nrf52 et de lui ajouter les
fonctionnalité que nous avons observé sur le key-finder de action lors des cours précédents.

### Les fonctionnalités standard

La liste des fonctionnalité est disponnible sur le schéma ci-dessous

![shéma des fonctions ajoutés](schema_fonction.png)

Pour récapituler le shéma, nous avons ajouté un buzzer relié à la pin 06 de la
puce, une led verte relié à la pin 09 et un bouton relié à la pin 04. Il y a
aussi, le bouton reset, reliéa la pin 21 aussi nommé pin de reset et une
batterie relié au vcc et au ground. Enfin il y a un connecteur de
programmation(qui peut-être voué à disparaitre pour la version finale) qui est relié
aux pins du swdio, swdclk, la pin de reset(inversé) et les pins 22, 23 et 24.

### Le petit plus

De plus, j'ai fais le choix de mettre un microphone. C'est une fonctionnalité
qui est annoncé sur le packaging du keyfinder de action mais qui n'est pas sur la
carte éléctronique, et qui n'existe donc pas.
J'ai donc décidé de mettre un microphone qui pourrais assez facilement avoir les
fonctions suivantes :
- Sonner à une commande de voix précise (pour éviter à l'utilisateur de devoir
  chercher son téléphone pour ensuite chercher ses clés).
- Pouvoir configurer la commande vocale necessaire pour sonner (pour éviter
  d'utiliser un mot anglais assez rare en france donc qui n'active jamais le
  key-finder sans raison, mais qui si l'on part en voyage à l'étranger se
  retrouve à s'activer fréquement sans raison.)
- Utiliser une commande vocale pour envoyer une commande au téléphone, par
  exemple déclencher la prise d'une photo.

### Le designe

Ce projet étant mon premier projet sur Fusion, vous remarquerez que les formes
sont assez basique, mais pourtant efficaces. 
Le designe est fait sur le modèle du key-finder de action, donc on retrouve une
boucle pratique pour accroccher le key-finder à un porte clés par exemple, un
bouton pour allumer et éteindre l'objet, ou encore pour demander à l'objet
d'envoyer un signal au téléphone. Il y a aussi un capuchon qui protège la pile
(facilement enlevable, ce qui permet de changer la pile si besoins) et enfin un
trou traversant en face de la led de sorte à voire quand la led s'allume des
deux cotés de l'objet.

De plus, contrairement à l'objet d'action, j'ai fais le choix d'augmenté la
porté du son du buzzer en ne bloquant pas le son. Pour cela, j'ai fais queleques
sorties sur les coques. Un groupe de sortie est situé au dessus du buzzer, et un
groupe est situé en dessous du microphone.
L'inconvenient de se choix est la perte de la résistance à l'eau, mais vue qu'il
ny a aucun joint sur l'objet originale et qu'il y a un trou pour la lumière de
la led je ne penses pas avoir beaucoup deterioré cet aspet.

## Limitation

### Electronique

Lors de ce travaille, je me suis heurté à de nombreux problèmes éléctroniques
dont quelques un qui ne sont actuellement pas réglé, ce qui fait que dans l'état
la carte n'est pas utilisibale. Nous pouvons notemment citer le fait que la pin
reset du JTAG est sensé être inversé mais ne connaissant pas les inverseur, je
n'ai pas put le faire.
On peu aussi citer les routes lors du tracage qui ont quelques angles un peu
aigue, ce qui risquerait de créer des résonances et donc  poser des problèmes
avec la norme CE. De plus l'antenne n'est surement pas faite exactement au 
centieme de millimetre près.
Enfin, certains des composants sont surement mal cablé du à mon manque de
connaissance et de temps de recherche sur ce domaine en particuler.

### Designe

Pour la partie designe, pas trop de problème, il faudrais juste pour améliorer le 
designe avoir des connaissances en physique supplémentaire pour connaitre la taille 
minimal d'un trou  que peu utiliser de l'eau pour s'infiltrer ou encore la 
disposition adéquate pour que des trous laissent passer le son le mieux possible.
De plus il est possible que le designe manque de calle en haut et en bas pour 
bloquer le pcb, mais comme le pcb est sensé s'emboiter parfaitement, c'est à mon 
avis un test à réaliser.

## Conclusion

Ce repos est la conclusion d'un semestre de travail sur un key-finder. Ce
travailles pourrait être amélioré par des connaissances en physiques plus importantes. 
Ou encore des testes avec des objets physiques, mais le resultat de ce travaille est 
globalement réalisable, il n'y aurait plus qu'a y intégrer le code.  


