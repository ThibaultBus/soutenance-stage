---
# You can also start simply with 'default'
theme: academic
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
class: text-white
layout: cover
coverBackgroundUrl: '/ovh-background.jpg'
transition: slide-left
themeConfig:
  paginationPagesDisabled: [13]
  paginationX: 'r'
  paginationY: 't'


coverDate: ""
---

<div class="absolute top-10">
  <h1>Soutenance de stage</h1>
  <p>Automatisation de la configuration de composants d'une infrastructure <i>cloud</i> isolée par une approche GitOps</p>
</div>

<div class="absolute bottom-10">
  <span class="font-700">
    Thibault Bustarret, Mardi 2 Juillet 2024
  </span>
</div>

---
# layout: table-of-contents
hideInToc: true
---

# Sommaire

<Toc minDepth="1" maxDepth="1"></Toc>



---
layout: intro
---

# L'entreprise et l'équipe

---
layout: figure-side
figureUrl: "/map-pop.webp"

---

<style>
.footnotes-sep {
  @apply mt-5 opacity-10;
}
.footnotes {
  @apply text-sm fixed bottom-10 left-10 right-0 p-4;
}
.footnote-backref {
  display: none;
}
</style>

## OVHcloud 

<!-- <img src="/map-pop.webp" alt="" class="float-right w-1/2 mr-4" /> -->
<br/>
<br/>

* Spécialisé dans le _cloud computing_, mais aussi FAI et opérateur
* Premier fournisseur de cloud européen
* 2900 salariés [^1]
* 897 millions d'euros de chiffre d'affaires [^1]
* 43 _datacenters_
* Acteur majeur de la souveraineté européenne

[^1]: [1. Données de 2023]

---
layout: figure-side
figureUrl: '/octave.webp'
figureX: 'l'
---

## L'histoire d'OVHcloud

* 1999 : Création d'OVH, par Octave Klaba
* Années 2000 : Rapide évolution d'OVH. L'entreprise se démarque en construisant ses serveurs, et utilise du refroidissement par eau.
* 2010 : L'entreprise entre dans le monde du _cloud_
* 2019 : OVH devient OVHcloud
* 2021 : OVHcloud fait son entrée en bourse

---
layout: center
---
## Organigramme

<img src="/organigramme.png">


---
layout: statement
---
## L'équipe Gold-ô-Rack
 
<br/>

<div class="grid grid-cols-2 gap-40 pt-4 -mb-6 place-items-center">
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Yann Degat </p>
  </div>
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Vicent Casse </p>
  </div>
</div>

<br/>

<div class="grid grid-cols-3 gap-40 pt-4 -mb-6">
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Victor Coutellier </p>
  </div>
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Olivier Bedouet </p>
  </div>
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Damien Rannou </p>
  </div>
</div>

<br/>

<div class="grid grid-cols-3 gap-40 pt-4 -mb-6">
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Riad El Hajjaji </p>
  </div>
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Alexandre Arents </p>
  </div>
  <div class="flex flex-col items-center">
    <solar-user-bold-duotone class="text-4xl" />
    <p> Bruno David </p>
  </div>
</div>

---
layout: intro
---

# Le projet

---

## Objectif de Gold-ô-Rack
<br/>
<br />

<div class="flex flex-col items-center">
  <b> Des critiques à apporter au <i>cloud</i> : </b>
  <p> Pas d'isolation de l'extérieur, éloignement géographique du client (latence, bande passante...) </p>
  <solar-arrow-down-bold class="text-4xl" />
  <b> Une solution : </b>
  <p> Une pile technologique permettant permettant de construire un <i>cloud</i> isolé </p>
  <solar-arrow-down-bold class="text-4xl" />
  <b> Deux produits : </b>
  <p> <i> Baremetal pod </i> et <i> Datacenter-as-a-Service </i> </p>
</div>

---

<img src="/seed.png">

---
layout: center
---

<div class="flex">
  <div class="h-110 w-96">
    <img src="/gor-controller-arch.png" class="object-contain">
  </div>
</div>

---

<div class="flex flex-col">
  <div>
  <h2> Problème de post-installation </h2>

  Plusieurs applications avec des configurations gérées sub-optimalement :
  * Pas de configuration post-installation possible (ou trop simpliste)
  * Aucune assurance sur l'équivalence avec la configuration de la source de vérité
  <solar-arrow-right-bold /> <span>  </span> Gestion de la configuration suivant les principes du GitOps
  </div>
</div>

---
layout: figure
figureUrl: "/gitops.png"
class: "bg-white text-black"
---

<Pagination classNames="text-black"> </Pagination>

---
layout: intro
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
layout: figure
figureUrl: "/gantt1.png"
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
    <li>CST1 : Analyser et comprendre un problème </li>
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
        <bold class="font-bold">Avantages: </bold> </br>
        <ul>
          <li>Bénéficie de l'écosystème Terraform</li>
          <li>Utilise un langage répandu (YAML)</li>
        </ul>
      </div> 
      <br/>
      <div class="border border-red-500 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Inconvénients: </bold>
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
        <bold class="font-bold">Avantages: </bold> </br>
        <ul>
          <li>Granularité fine</li>
          <li>Les opérateurs OpenStack pourraient être grandement utiles</li>
        </ul>
      </div> 
      <br/>
      <div class="border border-red-500 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Inconvénients: </bold>
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
        <bold class="font-bold">Avantages: </bold> </br>
        <ul>
          <li>Très grand écosystème de provider</li>
          <li>HCL est un langage simple mais puissant</li>
        </ul>
      </div> 
      <br/>
      <div class="border border-red-500 py-2 px-4 rounded text-sm">
        <bold class="font-bold">Inconvénients: </bold>
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
    <li>CM1 : ’organiser et planifier le travai </li>
    <li>CM4 : Acquérir de nouvelles connaissance et savoirs-faire </li>
    <li>CST3 : Mettre en oeuvre et formaliser une solution </li>
    <li>CST4 : Trouver l’information pertinente et l’exploite </li>
  </ul>
</div>

---
layout: section
---

# Tâches à venir


<!-- 

Exemple neutron:

BM_NET_NAME=physnet1
ADMIN_NET_VLAN=200
ADMIN_NET_NAME=adminnet
ADMIN_SUBNET_NAME=admin_net
ADMIN_NET_CIDR={{ admin_net_prefix }}
ADMIN_NET_START_IP={{ admin_net_prefix | ansible.utils.nthhost(5) }}
ADMIN_NET_END_IP={{ admin_net_prefix | ansible.utils.nthhost(-5) }}
DISCOVERY_NET_VLAN=199
DISCOVERY_NET_NAME=discovery
EXTERNAL_NET_VLAN=201
EXTERNAL_NET_NAME=extnet
EXTERNAL_SUBNET_NAME=external_subnet

echo >&2 Configuring neutron admin network
if ! openstack network show -c id -f value "${ADMIN_NET_NAME}" > /dev/null; then
    openstack network create --project admin "${ADMIN_NET_NAME}" \
        --provider-segment "${ADMIN_NET_VLAN}" \
        --disable-port-security \
        --provider-network-type vlan --provider-physical-network "${BM_NET_NAME}"
fi

--------------------------------------------------------

resource "openstack_networking_network_v2" "admin" {
  tenant_id             = data.openstack_identity_project_v3.admin.id
  name                  = var.admin_net_name
  port_security_enabled = false

  segments {
    physical_network = var.bm_net_name
    network_type     = "vlan"
    segmentation_id  = var.admin_net_vlan
  }
}
 -->


 <!-- Exemple nova
 
 # 40 instances
openstack quota set --instances 40 ${ADMIN_PROJECT_ID}

# 40 cores
openstack quota set --cores 400 ${ADMIN_PROJECT_ID}

# 96GB ram
openstack quota set --ram 96000 ${ADMIN_PROJECT_ID}
 
 
 resource "openstack_compute_quotaset_v2" "quotaset_1" {
  for_each = {} # TODO: add support for var.quota_sets

resource "openstack_compute_quotaset_v2" "quotaset_admin" {
  project_id           = data.openstack_identity_project_v3.admin.id
  cores                = each.value.cores
  fixed_ips            = each.value.fixed_ips
  floating_ips         = each.value.floating_ips
  instances            = each.value.instances
  key_pairs            = each.value.key_pairs
  metadata_items       = each.value.metadata_items
  ram                  = each.value.ram
  security_group_rules = each.value.security_group_rules
  security_groups      = each.value.security_groups
  server_group_members = each.value.server_group_members
  server_groups        = each.value.server_groups
  cores                = var.quota_sets.cores
  fixed_ips            = var.quota_sets.fixed_ips
  floating_ips         = var.quota_sets.floating_ips
  instances            = var.quota_sets.instances
  key_pairs            = var.quota_sets.key_pairs
  metadata_items       = var.quota_sets.metadata_items
  ram                  = var.quota_sets.ram
  security_group_rules = var.quota_sets.security_group_rules
  security_groups      = var.quota_sets.security_groups
  server_group_members = var.quota_sets.server_group_members
  server_groups        = var.quota_sets.server_groups
} 
 
  -->

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