# Some definitions

- DOM = Document Object Model
- Virtual DOM = Virtual Document Object Model

# VueJS DOM updating

Chaque propiété que l'on instancie dans vue possède son propre watcher. Qui va regarder chaque changement de la propriete.  
On pourrait croire que a chaque changement que le watcher detecte ca effectue un changement mais non ! par exemple on ne veux pas reacceder au DOM si on change une valeur d'une propriete par une valeur similaire.  
Cela propovoque un gros probleme de performance -> acceder au DOM est tres couteux !  
Pour eviter ca on va donc utiliser le VDOM
C'est une copie parser en JavaScrip, cést bien plus rapide dy acceder  
Vue js crer le VDOM grace aux watchers et watch ensuite les changement sur les proprietees watcher dans le VDOM  
On rcreer alors le VDOM a chaque changement et on met a jour le DOM via le VDOM seulement la ou il y a eu du changement entre l'instance vue et le vDom

# Memo

Pourquoi le VDOM est cheep ? -> Il n'y a pas de rendu a chaque modifications
Le module de compilation est executer au runtime et au build
Mettre des liens sur les différentes définitions

Pour l'attribution correcte des props par vue 3 dans la fonction h voici comment sa fonctionne :
On check si la key (ex: id) existe sur le noeud actuel (ex: div) en tant que propriété si c'est le cas ça le set en propriété sinon en attribue

# Plan

Ce qu'on va faire :

Deux parties :

- Explication / Définition
- Live Coding

  ## Explication / Definition

  - Définition du Dom
  - Pourquoi c'est un probleme (talk vdom react)
    - Exemple immeuble et démolission
  - Définition VDOM
  - Son fonctionnement 3 step etc ..

  ## Live Demo

  - Attention faire un exemple a coté pour copier le code

  ## Peach

  ### Slide 1

  Ajourd'hui nous allons tenté de comprendre les rouages du virtual dom.
  pour cela nous diviserons cette présentation en deux parties :

  ### Slide 2

  - Théorie :
    Nous allons définir les diférents concepts autour du virtual DOM et son fonctionnement au sein du framework VUE JS.

  ### Slide 3

  - Pratique :
    Nous allons créer une version simplifié du virtual DOM de vue en javascript.

  ### Slide 4

  Avant de jouer les aprenties Evan You , on va s'assurer de connaitre les bases.
  Qu'est ce que le DOM ?
  _Lecture des Définition_

  ### Slide 6

  Le DOM possède nez en moins des limites. Anthony l'explique très bien dans ton Talk sur les navigateurs web les opération dans le DOM sont très lourdes.
  Exemple du Batiment :
  \_On veux changer le mobilier de la salle ADA, Est-ce que c'est mieux de tout démolir et de reconstruire avec notre nouveau mobilier ou bien on fait un plan on regarde ce qu'on jette ce qu'on garde et ne change que ça ?

  ### Slide 7

  C'est la qu'intervient le VDOM.
  C'est quoi le VDOM
  _Lecture des définitions_

  Alors que ce passe-t-il sous le capot lors de cette 'synchronisation magique ?'
  _Lecture du slide_
  Sur le compiler module a savoir : il s'execute au Runtime et au build

  ### Slide 12

  _Explication de la pipeline de rendu_ -> Seulement si on a le temps

  ### Slide 16

  Ok mais concrètement sa donne quoi ? on veux du code !
  Pour h pour représenter le hyperscript - Javascript qui produit du HTML
  Cette fonction prends en paramètre 3 valeur :

  - le type
  - les props
  - le children - simple texte / object / tableau d'objet (on restera sur texte ou tableau d'objet pour plus de facilité )

  ### slide 18 - 20

  - Première exemple assez basique
  - Deuxième exemple on vois du nested on passe un tableau en tan que children
  - Troisème exemple vue 3 choisi automatiquement la bonne méthode d'attribution des props (Voir mémo)
