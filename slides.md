---
# You can also start simply with 'default'
theme: apple-basic
# some information about your slides (markdown enabled)
# title: Welcome to Slidev
# info: |
#   ## Slidev Starter Template
#   Presentation slides for developers.

#   Learn more at [Sli.dev](https://sli.dev)
# # https://sli.dev/custom/highlighters.html
# highlighter: shiki
# # https://sli.dev/guide/drawing
# drawings:
#   persist: false
# # slide transition: https://sli.dev/guide/animations#slide-transitions
# transition: slide-left
# # enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
layout: intro-image
image: '/ovh-background-darken.jpg'
transition: slide-left
---

<div class="absolute top-10">
  <h1>Soutenance de mi-parcours</h1>
  <p>Configuration post-setup d'applications avec une approche GitOps</p>
</div>

<div class="absolute bottom-10">
  <span class="font-700">
    Thibault Bustarret, Mardi 2 Juillet 2024
  </span>
</div>

---
hideInToc: true
---

# Sommaire

<Toc minDepth="1" maxDepth="1"></Toc>



---
layout: section
---

# L'entreprise et le projet

---
layout: bullets
---

<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm fixed bottom-10 left-10 right-0 p-4 bg-white;
}
.footnote-backref {
  display: none;
}
</style>

## OVHcloud 

<img src="/map-pop.webp" alt="" class="float-right w-1/2 mr-4" />

* Spécialisé dans le cloud computing, mais aussi FAI et opérateur
* Premier fournisseur de cloud européen
* 2900 salariés [^1]
* 897 millions d'euros de chiffre d'affaires [^1]

[^1]: [1. Données de 2023]

---
layout: intro-image-right
image: '/octave.webp'
imageSize: contain
---

## L'histoire d'OVHcloud

* 1999 : Création sous le nom d'OVH, par Octave Klaba
* Années 2000 : OVH se démarque en construisant ses propres serveurs et en mettant en place un système de refroidissement par eau innovant
* 2010 : D'abord hébergeur, OVH entre dans le monde du cloud

---
layout: statement
---
## Organigramme

<img src="/organigramme.png">

---
layout: intro-image-right
image: '/goldorak.png'
---
## L'équipe Gold-ô-Rack

* Équipe R&D
* Reproduire L'orchestration d'un cloud industriel sur une simple machine
* Objectif : Datacenter en tant que service

---
layout: statement
---
## Les membres de l'équipe

<br/>

<div>
  <solar-user-bold-duotone class="text-4xl" />
  <p> Yann Degat </p>
</div>

<br/>

<div class="grid grid-cols-3 gap-40 pt-4 -mb-6">
  <div>
    <solar-user-bold-duotone class="text-4xl" />
    <p> Victor Coutellier </p>
  </div>
  <div>
    <solar-user-bold-duotone class="text-4xl" />
    <p> Olivier Bedouet </p>
  </div>
  <div>
    <solar-user-bold-duotone class="text-4xl" />
    <p> Damien Rannou </p>
  </div>
</div>

<br/>

<div class="grid grid-cols-3 gap-40 pt-4 -mb-6">
  <div>
    <solar-user-bold-duotone class="text-4xl" />
    <p> Riad El Hajjaji </p>
  </div>
  <div>
    <solar-user-bold-duotone class="text-4xl" />
    <p> Alexandre Arents </p>
  </div>
  <div>
    <solar-user-bold-duotone class="text-4xl" />
    <p> Vincent Casse </p>
  </div>
</div>

---

## Mon rôle dans l'équipe

Plusieurs applications avec des configurations gérées sub-optimalement :
* Pas de post-setup possible (ou trop simpliste)
* Aucune assurance sur l'équivalence avec la configuration de la source de vérité

<img src="/gitops.jpeg" alt="" class="float-right w-1/2 mr-4" />

<solar-arrow-right-bold /> <span>  </span> Gestion de la configuration suivant les principes du GitOps

---
layout: section
---

# Tâches Accomplies
---

## Contexte

<br />

<style>
  ol {
    list-style: decimal;
  }
</style>

> Comment mettre en place un système qui assure la cohérence des configurations avec la source de vérité ?

<br/>

1. Définir l'étendue des éléments de configuration concernés
   <span class="text-gray-500 italic text-sm"><br/>Il est inutile de prendre en charge des éléments inutiles.</span>
2. Concevoir et mettre en œuvre un système de réconciliation continue des configurations par rapport à la source de vérité
  <span class="text-gray-500 italic text-sm"><br/>Cela implique d'avoir un système capable de lire les états des configurations déployées, de les comparer à la source de vérité et de les mettre à jour si besoin.</span>
3. S’assurer que l’ensemble des primitives de configuration de chaque service, identifiées à l’étape 1,
puissent être contrôlées par le système défini à l’étape 2.

4. Implémenter la gestion des primitives le cas échéant
---
layout: image
image: "/gantt-past.png"
backgroundSize: contain
---

<div class="absolute top-10">
  <h2 text-black>Tâches accomplies</h2>
</div>

---

## Premiers pas
<ul>
  <br/>
  <li> Tests de déploiements Kubernetes (2 semaines)
  <span class="text-gray-500 italic text-sm"><br/>Déploiement sur Kubernetes d'une application simple en 5 approches différentes.</span>
  <br/>
  <br/>
  </li>
  <li> Semaine d'intégration OVHcloud (1 semaine)
  <span class="text-gray-500 italic text-sm"><br/>Une semaine de présentation des activités, équipes et fonctionnements internes d'OVHcloud.</span>
  <br/>
  <br/>
  </li>
</ul>

<div class="fixed bottom-10 left-0 right-0 mx-auto w-11/12 rounded-md border border-gray-600 p-2 text-sm">
  Compétences liées :
  <ul>
    <li>CC1 : S'intégrer dans la structure d'accueil </li>
  </ul>
</div>
---

## Recherche préliminaire
<br/>

<div class="bg-teal-100 border-t-4 border-teal-500 rounded-b text-teal-900 px-4 py-3 shadow-md" role="alert">
  <div class="flex">
    <div class="py-4"><svg class="fill-current h-6 w-6 text-teal-500 mr-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M2.93 17.07A10 10 0 1 1 17.07 2.93 10 10 0 0 1 2.93 17.07zm12.73-1.41A8 8 0 1 0 4.34 4.34a8 8 0 0 0 11.32 11.32zM9 11V9h2v6H9v-4zm0-6h2v2H9V5z"/></svg></div>
    <div>
      <p class="font-bold">Rappel</p>
      <p class="text-sm">Nous voulons concevoir un système capable de lire les états des configurations déployées, de les comparer à la source de vérité et de les mettre à jour si besoin.</p>
      <p class="text-sm">Celui-ci doit gérer le plus grand nombre de primitives de configuration possible, pour minimiser l'effort de développement.</p>
    </div>
  </div>
</div>

<br/>
<br/>

<div class="grid grid-cols-3 gap-40 pt-4 mb-6 text-center">
  <div>
    <logos-crossplane-icon class="text-5xl" />
    <p> Crossplane </p>
  </div>
  <div>
    <logos-kubernetes class="text-5xl" />
    <p> Opérateurs <br/>Kubernetes </p>
  </div>
  <div>
    <logos-terraform-icon class="text-5xl" />
    <p> Terraform & Tofu-controller </p>
  </div>
</div>

---

## <logos-crossplane-icon class="text-2xl" /> Crossplane
<br/>
<div>
  Crossplane est un plan de contrôle universel. <br/>
  Il est possible de générer un provider Crossplane, <br/>
  à partir d'un provider Terraform.

  <br/>
  <br/>
  <img src="/crossplane.webp" alt="" class="float-right w-4/7 mr-4" />

  <div class="w-1/3">
      <div class="border border-green-500 bordertext-green-600 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Pros: </bold> </br>
        <ul>
          <li>Bénéficie de l'écosystème Terraform</li>
          <li>Utilise un langage répandu (YAML)</li>
        </ul>
      </div> 
      <br/>
      <div class="border border-red-500 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Cons: </bold>
        </br>
        <ul>
          <li>La génération de provider Crossplane est complexe</li>
          <li>Le YAML à écrire a des subtilités pouvant avoir de fortes conséquences</li>
        </ul>
      </div> 
  </div>
</div>

---

## <logos-kubernetes class="text-2xl" /> Opérateurs Kubernetes
<br/>
<div>
  Écriture d'un opérateur Kubernetes pour chacune de nos apps.<br/>
  Réutilisation d'opérateur existant lorsque cela est possible (notamment pour OpenStack).

  <br/>
  <br/>
  <img src="/openstack.svg" alt="" class="float-right w-1/3 mr-4" />

  <div class="w-1/3">
      <div class="border border-green-500 bordertext-green-600 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Pros: </bold> </br>
        <ul>
          <li>Granularité fine</li>
          <li>Les opérateurs OpenStack pourraient être grandement utiles</li>
        </ul>
      </div> 
      <br/>
      <div class="border border-red-500 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Cons: </bold>
        </br>
        <ul>
          <li>La création d'un opérateur est une tâche très complexe</li>
          <li>Les opérateurs OpenStack ne semblent pas prêts pour la production</li>
        </ul>
      </div> 
  </div>
</div>

---

## <logos-terraform-icon class="text-2xl" /> Terraform & tofu-controller
<br/>
<div>
  Terraform est un outil d'infrastructure-as-code (dont Tofu est le fork open-source). <br/>
  Le tofu-controller de Flux permet de jouer un plan Terraform en continu. <br/>
  <br/>
  <br/>
  <img src="/terraform.avif" alt="" class="float-right w-4/7 mr-4" />

  <div class="w-1/3">
      <div class="border border-green-500 bordertext-green-600 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Pros: </bold> </br>
        <ul>
          <li>Très grand écosystème de provider</li>
          <li>HCL est un langage simple mais puissant</li>
        </ul>
      </div> 
      <br/>
      <div class="border border-red-500 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Cons: </bold>
        </br>
        <ul>
          <li>Peut être lent à la réconciliation</li>
          <li>Granularité peut-être pas tout à fait assez fine pour certains usages</li>
        </ul>
      </div> 
  </div>
</div>

---

## Choix final
<br/>

* La génération de provider Crossplane est trop complexe, Crossplane est donc écarté.
<br/>
* La création d'un opérateur pour chaque application est un chantier bien trop colossal.
<br/>
* Terraform et le tofu-controller devient notre unique option

<div class="fixed bottom-10 left-0 right-0 mx-auto w-11/12 rounded-md border border-gray-600 p-2 text-sm">
  Compétences liées :
  <ul>
    <li>CST1 : Analyser et comprendre un problème </li>
    <li>CST2 : Concevoir et formaliser une solution </li>
    <li>CST4 : Trouver l'information pertinente et l'exploiter </li>
    <li>CM2 : Communiquer par une synthèse écrite </li>
  </ul>
</div>

---

## Netbox

Netbox est un outil de gestion des infrastructures réseau.

Sa configuration est défini uniquement à la création à partir d'un fichier YAML.

<br/>

<span class="font-bold">Mes tâches :</span>

<ul>
  <li> Contributions au provider Terraform
  <br/>
  </li>
  <li> Test de performance Netbox & Terraform
  <br/>
  </li>
  <li> Écriture d'une recette Terraform
  <span class="text-gray-500 italic text-sm"><br/>Celle-ci devait être capable de lire les données du fichier YAML déjà utilisé !</span>
  <br/>
  </li>
  <li> Migration la configuration Netbox vers cette approche
  <br/>
  </li>
</ul>


---

## Objectif final

<br/>
<br/>
<br/>

Example d'une conversion YAML vers Terraform :
````md magic-move

```js
asns.yml: |
    - asn: 65100
      rir: Goldorack
```

```js
resource "netbox_asn" "asns" {
  asn      = 65100
  rir_id   = netbox_rir.rirs["Goldorack"].id
}
```

```js
resource "netbox_asn" "asns" {
  for_each = { for asn in local.netbox_items["asns"] : asn.asn => merge(local.asn_schema, asn) }
  asn      = each.value.asn
  rir_id   = netbox_rir.rirs[each.value.rir].id
}
```
````

<div class="fixed bottom-10 left-0 right-0 mx-auto w-11/12 rounded-md border border-gray-600 p-2 text-sm">
  Compétences liées :
  <ul>
    <li>CST3 : Mettre en oeuvre et formaliser une solution </li>
    <li>CM4 : Acquérir de nouvelles connaissance et savoirs-faire </li>
  </ul>
</div>

---
layout: section
---

# Tâches à venir

---
layout: image
image: "/gantt-future.png"
backgroundSize: contain
---

<div class="absolute top-10">
  <h2 text-black>Tâches à venir</h2>
</div>

---
layout: statement
---

# Conclusion

---
layout: statement
hideInToc: true
---

<h1>Des Questions ?</h1>