[README.md](https://github.com/user-attachments/files/32433439/README.md)
# QR Generator — Dark Glass Edition

Générateur de QR Code moderne, rapide et responsive, conçu pour transformer une URL en QR Code téléchargeable et imprimable directement depuis le navigateur.

Le projet adopte une direction artistique Dark Glass / Midnight Tech, inspirée des interfaces macOS/iOS (composants en verre semi-translucide, effets d'ombre profonds et typographie système).

---

## Fonctionnalités

- Formatage d'URL intelligent : Ajout automatique du protocole https:// si l'utilisateur saisit un nom de domaine simple (ex: google.fr).
- Génération instantanée : Création du QR Code en temps réel côté client.
- Confidentialité garantie : Aucune donnée n'est envoyée vers un serveur intermédiaire.
- Téléchargement optimisé (Blob) : Export PNG rapide compatible PC et mobile.
- Impression sur 1 page : Fenêtre d'impression isolée garantissant un rendu propre et sans débordement.
- Compatibilité In-App (Instagram/Facebook) : Détection des navigateurs intégrés et affichage d'une bannière explicative pour l'utilisateur.
- Responsive Design : Interface fluide s'adaptant sur mobile, tablette et ordinateur.
- Balises Open Graph : Cartes de partage optimisées pour WhatsApp, iMessage, Instagram et X (Twitter).

---

## Direction Artistique & UI

L'application utilise des variables CSS dédiées pour maintenir la cohérence de la charte graphique :

| Élément | Valeur CSS | Rendu |
| :--- | :--- | :--- |
| Background Principal | #05070D | Fond sombre profond |
| Background Secondaire | #080D16 | Dégradé subtil |
| Effet Glassmorphism | rgba(255, 255, 255, 0.055) | Surface translucide |
| Bordure Glass | rgba(255, 255, 255, 0.12) | Contour fin |
| Couleur Accent (Primary) | #8B9CFF | Boutons et faits saillants |
| Succès / Impression | #5EE6A8 | Indicateur d'état et actions |

---

## Structure du Projet

```text
qr-generator/
├── index.html          # Structure HTML, styles CSS et scripts JS
├── qrcodefavicon.png   # Favicon du site (format carré 512x512 px recommandé)
├── og-image.png        # Image d'aperçu pour les réseaux sociaux (1200x630 px)
└── README.md           # Documentation du projet
