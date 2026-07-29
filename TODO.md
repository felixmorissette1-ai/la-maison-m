# À faire — La Maison M. (Shopify)

## Contenu (admin Shopify / rédaction — pas du code)
- [ ] Créer l'histoire et le fil narratif de la page d'accueil (textes + photos)
- [ ] Ajouter les 8 produits dans l'admin Shopify avec vrais prix, descriptions, tissu, origine
- [ ] Ajouter les photos des complets (page produit + cartes collection)
- [ ] Ajouter les photos de tissus (swatches sur les cartes et pages produit)

## Configurateur
- [x] Page configurateur sur mesure (choix de canevas → étapes) — construit (`configurateur-style`, `-tissu`, `-lining`, `-boutons`, `-construction`, `-resume`)
- [ ] Ajouter les vraies photos de chaque type de canevas (Fused, Half, Full) — le système est prêt (metaobjects avec champ `photo`, voir `sections/configurateur-construction.liquid:18-19`), il manque juste l'upload des photos dans l'admin

## Mensurations
- [x] Metafields de mensurations sur le profil client (`custom.mensurations`, utilisé activement pour débloquer le paiement — voir `sections/cart.liquid`)
- [ ] Vérifier que les couturières remplissent bien les mesures détaillées (tour de poitrine, tour de taille, longueur d'épaule, etc.) dans le profil client au premier rendez-vous — process humain à confirmer, pas du code
- [x] Les mesures sont automatiquement disponibles sur les commandes futures (logique de gating déjà en place dans le panier)

## Commandes en boutique
- [ ] Former la couturière à créer des draft orders depuis l'admin Shopify
- [ ] Prévoir une tablette/ordi en boutique pour que le client se connecte à son compte La Maison M.
- [ ] Documenter le flux : client se connecte → couturière crée le draft → client voit et paie

## Prise de rendez-vous
- [x] Système de réservation en place — **intégré via Cal.com** (pas Calendly comme prévu à l'origine), directement dans le header et la modale de localisation/couturière (`sections/header.liquid`), avec sync automatique des metafields rdv via `llm-backend/api/cal-sync.js` et `cal-webhook.js`
- [x] Champ de réglage "Lien Calendly" retiré du schema de `sections/page.liquid` (obsolète depuis le passage à Cal.com)

## Futur
- [ ] Option de basculer le site complet en anglais (bilingue FR/EN)
- [ ] Page "Choisis le nom que tu veux faire coudre dans la manche" (monogramme/broderie personnalisée)
- [ ] Livraison : définir les délais, et voir si un suivi de commande est possible (avec quel transporteur ?)
- [ ] Comptabilité : comprendre comment Shopify gère la comptabilité (taxes, rapports de vente, etc.) — recherche à faire avec Felix, pas du code
- [ ] Esthétique + adaptabilité mobile/tablette — révision visuelle générale du site sur tous les appareils

## Branding / liens à corriger
- [ ] Mettre le bon logo partout sur le site (actuellement incohérent ou manquant à certains endroits)
- [ ] Le bouton/lien "Voir la collection" doit pointer vers la vraie page de collection (actuellement incorrect)
- [ ] Footer : le lien actuellement nommé "Magasine" (`sections/footer.liquid:221-224`, réglage `magasine_url`) est une coquille pour "Magasiner" (Shop) — à corriger. Felix veut aussi des liens footer distincts pour "Personnalisé", "Collection", et "Chemise" qui mènent chacun vers la bonne page.

## Déjà construit (retiré de la liste "à construire")
- [x] Navigation principale (`sections/header.liquid` — Accueil / Collection / Personnalisé)
- [x] Footer (`sections/footer.liquid` + `footer-group.json`)
