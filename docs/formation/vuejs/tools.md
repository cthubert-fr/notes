---
layout: default
title: "Outils - VueJS"
permalink: /formation/vuejs/tools/
lang: fr
my_menu: menu-vuejs.html
---

## Outils pour développer en VueJS

L'ensemble des outils cités ici aident aux développements VueJS.

Note : *cette liste est loin d'être exhaustive, je la mettrais d'ailleurs bientôt à jour*.

<h3 id="main-tools-title" class="mt-4" >Outils principaux</h3>

<div class="accordion" id="main-tools">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingnode">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#node" aria-expanded="false" aria-controls="node">
        NodeJS
      </button>
    </h2>
    <div id="node" class="accordion-collapse collapse text-dark" aria-labelledby="headingnode" data-bs-parent="#main-tools">
      <div class="accordion-body">
        Environnement d'exécution JavaScript. Il permet de faire fonctionner différents services utiles pour le développement de composants Vue. Et c'est grâce au gestionnaire de paquets npm, installé en même temps que NodeJS, que nous installerons notamment Vue.
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingvsc">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#vsc" aria-expanded="false" aria-controls="vsc">
        Visual Studio Code (aka VS Code)
      </button>
    </h2>
    <div id="vsc" class="accordion-collapse collapse text-dark" aria-labelledby="headingvsc" data-bs-parent="#main-tools">
      <div class="accordion-body">
        Editeur de code développé par Microsoft et multiplateformes.
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headinggc">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#gc" aria-expanded="false" aria-controls="gc">
        Google Chrome
      </button>
    </h2>
    <div id="gc" class="accordion-collapse collapse text-dark" aria-labelledby="headinggc" data-bs-parent="#main-tools">
      <div class="accordion-body">
        Navigateur Web utilisé pour visualiser le résultat des développements.
      </div>
    </div>
  </div>
</div>

<h3 id="vsc-addons-title" class="mt-4" >Extensions pour VS Code</h3>

<div class="accordion" id="vsc-addons">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingvetur">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#vetur" aria-expanded="false" aria-controls="vetur">
        Vetur
      </button>
    </h2>
    <div id="vetur" class="accordion-collapse collapse text-dark" aria-labelledby="headingvetur" data-bs-parent="#vsc-addons">
      <div class="accordion-body">
        Extension permettant notamment d'avoir de l'autocomplétion pour les développements de composants VueJS.
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingthunder">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#thunder" aria-expanded="false" aria-controls="thunder">
        Thunder Client
      </button>
    </h2>
    <div id="thunder" class="accordion-collapse collapse text-dark" aria-labelledby="headingthunder" data-bs-parent="#vsc-addons">
      <div class="accordion-body">
        Extension permettant de requêter une API REST.
      </div>
    </div>
  </div>
</div>

<h3 id="gc-addons-title" class="mt-4" >Extensions pour Google Chrome</h3>

<div class="accordion" id="gc-addons">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingvuedevtools">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#vuedevtools" aria-expanded="false" aria-controls="vuedevtools">
        Vue DevTools
      </button>
    </h2>
    <div id="vuedevtools" class="accordion-collapse collapse text-dark" aria-labelledby="headingvuedevtools" data-bs-parent="#gc-addons">
      <div class="accordion-body">
        Extension utile pour visualiser le contenu de ces composants VueJS, notamment l'arborescence de ces composants, mais également le contenu (à savoir les props).
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingreduxdevtools">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#reduxdevtools" aria-expanded="false" aria-controls="reduxdevtools">
        Redux DevTools
      </button>
    </h2>
    <div id="reduxdevtools" class="accordion-collapse collapse text-dark" aria-labelledby="headingreduxdevtools" data-bs-parent="#gc-addons">
      <div class="accordion-body">
        Extension permettant de débugger le gestionnaire d'état Vuex.
      </div>
    </div>
  </div>
</div>
