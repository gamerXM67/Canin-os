🐾 Documentation Technique - Salon de Toilettage Canin-OS
Ce document détaille l'architecture technique, les choix technologiques et les instructions de maintenance pour le site vitrine du salon de toilettage Canin-OS.

📋 Table des Matières

Aperçu du Projet
Stack Technique
Architecture du Code
Fonctionnalités Clés
Design System & CSS
Installation et Démarrage
Déploiement


1. Aperçu du Projet
Ce projet est une Single Page Application (SPA) statique développée pour présenter les services, tarifs et informations du salon de toilettage de Ludovic, artisan toiletteur basé à Niederschaeffolsheim (67420, Alsace).
L'objectif principal est de proposer un site léger, performant et sans backend, entièrement navigable via des ancres HTML (#Presentation, #Services, #Tarifs…) pour une expérience fluide sans rechargement de page. Le site est déjà compilé (dossier dist/ présent) et prêt à être hébergé.

2. Stack Technique
Cœur du Système
Vue.js 3 (Composition API) : Framework JavaScript progressif utilisé pour sa réactivité et son système de composants modulaire. L'API de Composition (<script setup lang="ts">) est utilisée dans tous les composants pour une meilleure organisation logique et un typage statique natif.
Vite : Outil de build de nouvelle génération offrant un démarrage de serveur quasi-instantané et un Hot Module Replacement (HMR) ultra-rapide grâce à l'utilisation native des modules ES (ESM).
TypeScript : Typage statique sur l'ensemble du projet (~5.9.3). Garantit la fiabilité du code et facilite la maintenance. Note : Galerie.vue est le seul composant qui ne l'utilise pas encore — à corriger.
Qualité du Code
ESLint + OxLint : Double couche de linting. OxLint est un linter ultra-rapide écrit en Rust qui complète ESLint pour détecter davantage d'erreurs potentielles.
Prettier : Formatage automatique et cohérent de tout le code source (src/).
Déploiement
Le projet génère un bundle statique (HTML + CSS + JS) dans /dist. Il peut être hébergé sans serveur applicatif sur Vercel, Netlify ou GitHub Pages.

3. Architecture du Code
La structure suit les standards Vue.js :
canin-os/
├── components/          # Composants Vue de chaque section de page
│   ├── Navbar.vue       # Navigation fixe + menu burger mobile
│   ├── Index.vue        # Section hero (accueil)
│   ├── Presentation.vue # Biographie de Ludovic
│   ├── Services.vue     # Grille des 3 prestations
│   ├── Tarifs.vue       # Grille tarifaire par gabarit
│   ├── Galerie.vue      # Slider photos avec navigation
│   ├── Avis.vue         # Avis clients (non implémenté)
│   ├── Faq.vue          # Accordéon FAQ interactif
│   └── Contact.vue      # Coordonnées + formulaire
├── src/
│   ├── App.vue          # Composant racine — assemble tous les composants
│   ├── main.ts          # Point d'entrée de l'application
│   └── assets/          # Images WebP (photos chiens, logo, réseaux sociaux)
├── public/
│   └── favicon.ico      # Icône de l'onglet navigateur
├── dist/                # Build de production (déjà généré)
├── index.html           # HTML racine (chargement police Nunito)
├── vite.config.ts
├── tsconfig.json
└── package.json
Choix d'Architecture
SPA sans routeur : Le site n'utilise pas Vue Router. La navigation se fait exclusivement via des ancres HTML (href="#Services"). Ce choix simplifie l'architecture et suffit amplement pour un site vitrine mono-page.
Composants de section : Chaque partie du site (Hero, Services, Tarifs…) est isolée dans son propre composant. Cela permet de modifier, masquer ou réordonner une section sans impacter le reste. L'ordre d'affichage est contrôlé directement dans App.vue.
Scoped Styles : Tout le CSS est scoped dans chaque composant .vue pour éviter les conflits de style entre sections. Il n'y a pas de feuille de style globale — les variables et resets sont définis dans App.vue.

4. Fonctionnalités Clés
Système de Navigation (Navbar.vue)
La barre de navigation est fixée en haut de page (position: fixed, z-index: 1000) et entièrement responsive :

Sur Desktop : Menu horizontal avec 8 liens d'ancrage et 4 icônes réseaux sociaux.
Sur Mobile (breakpoint < 1150px) : Bouton burger qui déclenche l'ouverture d'un volet latéral coulissant depuis la droite. L'état est géré réactivement avec ref<boolean>.

ts// Navbar.vue — gestion de l'état du menu mobile
const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
Le bouton burger s'anime en croix (×) lorsqu'il est actif, via des transformations CSS pures :
css.burger.is-active span:nth-child(1) { transform: translateY(9px) rotate(45deg); }
.burger.is-active span:nth-child(2) { opacity: 0; }
.burger.is-active span:nth-child(3) { transform: translateY(-9px) rotate(-45deg); }
Galerie Photos (Galerie.vue)
Un slider minimaliste avec navigation circulaire. La logique est entièrement gérée avec des ref Vue sans dépendance externe :
js// Navigation circulaire avec modulo
const next = () => {
  currentIndex.value = (currentIndex.value + 1) % images.value.length
}
const prev = () => {
  currentIndex.value = (currentIndex.value - 1 + images.value.length) % images.value.length
}
La transition entre les images utilise le système natif <transition> de Vue avec un effet fade (opacité) :
html<transition name="fade" mode="out-in">
  <img :key="currentIndex" :src="images[currentIndex].url" />
</transition>
FAQ Accordéon (Faq.vue)
L'accordéon gère l'ouverture exclusive d'une seule entrée à la fois. Un clic sur une entrée déjà ouverte la referme :
ts// Faq.vue — une seule entrée ouverte à la fois
const openIndex = ref<number | null>(null)

function toggle(index: number) {
  openIndex.value = openIndex.value === index ? null : index
}
L'animation d'ouverture/fermeture est gérée par une transition Vue slide-fade combinant translateY et opacity pour un effet fluide.
Formulaire de Contact (Contact.vue)
Le formulaire utilise la validation HTML5 native (attributs required, type="email", type="tel") et @submit.prevent pour intercepter la soumission.

⚠️ Important : Le formulaire ne fait actuellement rien lors de la soumission. Un service d'envoi d'email (ex : EmailJS) est à connecter dans le handler @submit.prevent.

Les labels sont masqués visuellement mais restent accessibles aux lecteurs d'écran via la classe .sr-only :
css.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}

5. Design System & CSS
Le design repose sur une identité visuelle cohérente définie dans chaque composant. Les valeurs clés sont :
css/* Palette principale — répétée dans tous les composants */
#dc8c82   /* Corail principal — badges, CTA, prix, icônes actives */
#ca7b71   /* Corail hover — états :hover et :active uniquement    */
#2c3e50   /* Bleu nuit — tous les titres H1/H2                    */
#6a6a6a   /* Gris — corps de texte standard                       */
#fffdf6   /* Blanc crème — fond de la navbar                      */

/* Fond global — App.vue */
body {
  font-family: 'Nunito', sans-serif;
  background: radial-gradient(circle, rgba(255,255,255,1) 0%, rgba(224,238,255,1) 100%);
}

Pourquoi ne pas utiliser de variables CSS globales ? Le projet n'a pas de feuille de style globale avec :root. Les valeurs sont répétées dans chaque composant scoped. Cela fonctionne bien pour un petit site, mais migrer vers des variables CSS globales dans un futur style.css faciliterait un éventuel rebranding.

Pattern Glassmorphism
Un effet de transparence douce est appliqué à toutes les cartes du site pour créer une profondeur visuelle légère :
css.card {
  background: rgba(255, 255, 255, 0.5);
  border: 1px solid rgba(255, 255, 255, 0.6);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
  backdrop-filter: blur(10px); /* Utilisé sur les tarifs */
  border-radius: 24px;
}
Typographie
Police unique : Nunito chargée via Google Fonts dans index.html. Choisie pour sa rondeur en accord avec l'univers animalier du salon.
ÉlémentTailleGraisseTitre H1 hero2.8rem700Titre H1 sections2.4rem700–800Corps de texte1–1.1rem400Badge0.8rem700, uppercasePrix1.05rem800
Responsive Design
Le site est adapté pour mobile, tablette et desktop via des @media queries dans chaque composant :
BreakpointComportement< 600pxGrilles en 1 colonne, titres réduits< 768–900pxGrilles en 1–2 colonnes< 992–1024pxTarifs en 2 colonnes< 1150pxMenu burger mobile activé

6. Installation et Démarrage
Prérequis

Node.js : ^20.19.0 ou >=22.12.0 (contrainte définie dans package.json)
npm : inclus avec Node.js

Procédure
Cloner le dépôt :
bashgit clone https://github.com/gamerXM67/Canin-os.git
cd Canin-os
Installer les dépendances :
bashnpm install
Cette commande télécharge Vue 3, Vite et tous les outils de développement dans node_modules/.
Lancer le serveur de développement :
bashnpm run dev
Le site est accessible sur http://localhost:5173 avec rechargement automatique à chaque modification de fichier (HMR).
Scripts disponibles
CommandeActionnpm run devServeur de développement avec HMRnpm run buildBuild de production (type-check + Vite en parallèle)npm run previewPrévisualisation du build dist/ en localnpm run lintLinting ESLint + OxLint avec auto-fixnpm run formatFormatage Prettier sur src/

7. Déploiement
Compiler le projet
bashnpm run build
Vite optimise, minifie et compile tout le code dans le dossier /dist. Le build effectue également une vérification TypeScript complète (vue-tsc) avant de compiler.

💡 Le dossier dist/ est déjà présent dans le dépôt — le site peut être déployé immédiatement sans recompilation.

Hébergement
Le contenu de /dist est purement statique (HTML, CSS, JS, images WebP). Il peut être hébergé sur :

Vercel / Netlify (recommandé) : Déploiement automatique depuis GitHub, HTTPS gratuit, CDN mondial, zéro configuration.
GitHub Pages : Gratuit pour les repos publics. Nécessite d'ajouter base: '/Canin-os/' dans vite.config.ts.
Apache / Nginx : Copier le contenu de /dist dans le répertoire web du serveur.


Documentation rédigée pour le projet Canin-OS — Mars 2026
