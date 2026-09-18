# QR

Générateur de QR Code simple, rapide et responsive permettant de
transformer une URL en QR Code directement depuis le navigateur.

Le projet est conçu selon une direction artistique **Dark Glass /
Midnight Tech** : interface sombre, minimaliste, élégante et inspirée
des interfaces iOS/macOS.

------------------------------------------------------------------------

## ✨ Fonctionnalités

-   🔗 Saisie d'une URL
-   ⚡ Génération instantanée du QR Code
-   ✅ Vérification de l'URL avant génération
-   🔒 Génération côté navigateur
-   📥 Téléchargement du QR Code en PNG
-   🖨️ Impression directe du QR Code
-   📱 Interface responsive
-   💻 Adaptation automatique PC / tablette / mobile
-   🚫 Aucun défilement vertical ou horizontal sur l'interface
    principale
-   🌙 Interface Dark Glass / Midnight Tech
-   ♿ Interface simple et lisible

------------------------------------------------------------------------

## 🎨 Direction artistique

Le site utilise une esthétique **Dark Glass / Midnight Tech**.

### Couleurs principales

  Élément                 Couleur
  ----------------------- --------------------------
  Background              `#05070D`
  Background secondaire   `#080D16`
  Glass                   `rgba(255,255,255,.055)`
  Glass hover             `rgba(255,255,255,.08)`
  Border                  `rgba(255,255,255,.12)`
  Texte principal         `#F5F7FA`
  Texte secondaire        `#8B93A1`
  Texte muted             `#555D69`
  Primary                 `#8B9CFF`
  Secondary               `#6EE7F9`
  Success                 `#5EE6A8`
  Warning                 `#F5C86B`
  Danger                  `#FF6B7A`

### Principes UI

-   Glassmorphism très subtil
-   `backdrop-filter: blur(...)`
-   Bordures fines
-   Coins arrondis
-   Ombres diffuses
-   Beaucoup d'espace négatif
-   Animations courtes et discrètes
-   Typographie système / Inter / SF Pro
-   Aucun style cyberpunk ou gaming
-   Aucun néon excessif

------------------------------------------------------------------------

## 📱 Responsive Design

L'interface est pensée comme une **petite application dédiée**, et non
comme une longue page web.

### Ordinateur

L'écran affiche deux zones :

``` text
┌───────────────────────────────┬──────────────────────┐
│                               │                      │
│       Saisie de l'URL         │     Aperçu QR        │
│                               │                      │
│       Informations            │     QR Code          │
│       fonctionnalités         │                      │
│                               │   Télécharger        │
│                               │     Imprimer         │
└───────────────────────────────┴──────────────────────┘
```

### Mobile

La mise en page passe automatiquement en colonne et privilégie les
éléments essentiels :

``` text
┌──────────────────────┐
│     QR Generator     │
│                      │
│     Un lien.         │
│     Un QR.           │
│                      │
│  ┌────────────────┐  │
│  │ URL            │  │
│  └────────────────┘  │
│      Générer         │
│                      │
│      ┌──────┐        │
│      │  QR  │        │
│      │ CODE │        │
│      └──────┘        │
│                      │
│ Télécharger Imprimer │
└──────────────────────┘
```

Le viewport est verrouillé afin d'éviter le défilement horizontal et
vertical sur l'interface principale.

------------------------------------------------------------------------

## ⚙️ Fonctionnement

Le QR Code est généré directement dans le navigateur à partir de l'URL
saisie.

Exemple :

``` text
https://www.instagram.com/enzo.rae/
```

devient :

``` text
URL
 ↓
QRCode.js
 ↓
QR Code
 ↓
PNG / Impression
```

Le QR Code contient directement l'URL fournie.

### QR Code statique

Le projet utilise un fonctionnement de **QR Code statique**.

Cela signifie que :

-   aucune base de données n'est nécessaire ;
-   aucune URL intermédiaire n'est utilisée ;
-   aucun compte utilisateur n'est nécessaire ;
-   le QR Code n'expire pas ;
-   le QR Code continue de fonctionner indépendamment du site
    générateur, tant que l'URL encodée existe toujours.

Deux utilisateurs qui saisissent la même URL peuvent donc obtenir un QR
Code identique. Ce n'est pas un conflit : les deux QR Codes encodent
exactement la même donnée.

Deux URLs différentes produisent des données QR différentes.

------------------------------------------------------------------------

## 🧩 Technologies

Le projet utilise :

-   **HTML5**
-   **CSS3**
-   **JavaScript**
-   **QRCode.js**

La bibliothèque QRCode.js est chargée depuis CDN :

``` html
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
```

Une connexion Internet est donc nécessaire au chargement initial de la
bibliothèque.

------------------------------------------------------------------------

## 📂 Structure

Structure minimale recommandée :

``` text
qr-code-generator/
│
├── createyourqr.html
├── favicon.png
└── README.md
```

### `index.html`

Fichier principal contenant :

-   la structure HTML ;
-   les styles CSS ;
-   le JavaScript ;
-   la génération du QR Code ;
-   le téléchargement PNG ;
-   l'impression ;
-   le responsive design.

### `favicon.png`

Icône utilisée comme favicon du site.

Dans le `<head>` :

``` html
<link rel="icon" type="image/png" href="favicon.png">
```

Le fichier doit se trouver dans le même dossier que `index.html`.

### `README.md`

Documentation du projet.

------------------------------------------------------------------------

## 🚀 Installation

Aucune installation complexe n'est nécessaire.

### Méthode simple

1.  Télécharger les fichiers du projet.
2.  Placer `index.html` et `favicon.png` dans le même dossier.
3.  Ouvrir `index.html` avec un navigateur moderne.
4.  Coller une URL.
5.  Cliquer sur **Générer**.

### Hébergement

Le projet peut être hébergé sur pratiquement n'importe quel hébergement
statique :

-   GitHub Pages
-   Netlify
-   Vercel
-   Cloudflare Pages
-   serveur Apache/Nginx
-   hébergement web classique

Aucun backend n'est nécessaire pour le fonctionnement actuel.

------------------------------------------------------------------------

## 🖨️ Impression

Le bouton **Imprimer** utilise :

``` javascript
window.print();
```

Une feuille de style `@media print` masque l'interface et conserve
uniquement le QR Code afin d'obtenir une impression propre.

------------------------------------------------------------------------

## 📥 Téléchargement

Le QR Code généré est récupéré depuis le canvas puis converti en PNG :

``` javascript
canvas.toDataURL("image/png");
```

Le fichier est téléchargé sous le nom :

``` text
qr-code.png
```

------------------------------------------------------------------------

## 🔐 Confidentialité

La génération est réalisée côté client.

L'URL saisie n'est pas envoyée à un serveur appartenant au projet pour
générer le QR Code.

La seule ressource externe utilisée par la page est la bibliothèque
**QRCode.js** chargée depuis le CDN.

------------------------------------------------------------------------

## 🔄 Évolutions possibles

Le projet peut évoluer vers une version plus complète avec :

-   personnalisation de la couleur du QR Code ;
-   modification de la taille ;
-   choix du niveau de correction ;
-   export SVG ;
-   export PDF ;
-   ajout d'un logo ;
-   QR Codes avec couleurs personnalisées ;
-   historique local des QR Codes ;
-   génération de QR Codes pour texte, Wi-Fi, e-mail, téléphone, etc. ;
-   mode QR Code dynamique avec identifiant unique ;
-   statistiques de scans ;
-   comptes utilisateurs ;
-   base de données pour les QR Codes dynamiques.

Ces fonctionnalités nécessiteraient certaines modifications de
l'architecture actuelle.

------------------------------------------------------------------------

## 📄 Licence

Projet personnel / expérimental.

La bibliothèque QRCode.js utilisée par le projet possède sa propre
licence et ses propres conditions d'utilisation.
