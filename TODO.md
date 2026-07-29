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

## Déjà construit (retiré de la liste "à construire")
- [x] Navigation principale (`sections/header.liquid` — Accueil / Collection / Personnalisé)
- [x] Footer (`sections/footer.liquid` + `footer-group.json`)
