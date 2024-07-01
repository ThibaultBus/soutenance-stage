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

<Toc minDepth="1" maxDepth="2"></Toc>

---
layout: bullets
---
# OVHcloud

* Spécialisé dans le cloud computing, mais aussi FAI et opérateur
* Premier fournisseur de cloud européen
* 2900 salariés

<img src="map-pop.webp" alt="" class="float-right w-1/2 mr-4" />

---
layout: intro-image-right
image: '/octave.webp'
imageSize: contain
---

## L'histoire d'OVHcloud

* 1999 : Création sous le nom d'OVH, par Octave Klaba
* Années 2000 : OVH se démarque en construisant ses propres serveurs et en mettant en place un système de refroidissement par eau innovant
* 2010 : D'abord hébergeur, OVH, entre dans le monde du cloud

---
# Test

````md magic-move
```js
console.log(`Step ${1}`)
```
```js
console.log(`Step ${2 + 1}`)
```
```ts
console.log(`Step ${3}` as string)
```
````