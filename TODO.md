# À faire — La Maison M. (Shopify)

## Gestion des stocks
- [x] Stock illimité tant que Felix ne bloque pas manuellement un item — appliqué aux 5 variantes existantes (Chemise en coton ×4 couleurs, Complet pure laine test) : suivi de quantité désactivé (`inventory_management: null`) sur chaque variante.
- **Pour les futurs produits** : ne pas activer "Suivre la quantité" dans Shopify Admin (section Inventaire de la variante) — laissé désactivé, le produit reste toujours achetable. Le contrôle manuel de Felix se fait en passant le produit à "Brouillon" (Draft) ou en le désactivant, pas via une quantité qui tombe à zéro.

## Contenu à ajouter — photos & descriptions (admin Shopify / rédaction, pas du code)
- [ ] Créer l'histoire et le fil narratif de la page d'accueil (textes + photos)
- [ ] Ajouter les 8 produits dans l'admin Shopify avec vrais prix, descriptions, tissu, origine

**1. Collection**
- [ ] Photos des items de la collection
- [ ] Information / description des items de la collection
- [ ] Photos Fused, Half, Full canvas
- [ ] Description Fused, Half, Full canvas
- [ ] Photos liées aux pantalons
- [ ] Descriptions liées aux pantalons
- [ ] Photos 2 pièces / 3 pièces

**2. Personnalisé** (photos supplémentaires)
- [ ] Photos Styles
- [ ] Photos Tissus
- [ ] Photos Lining
- [ ] Photos Boutons

**3. Chemises**
- [ ] Photos tissus chemises

## Configurateur
- [x] Page configurateur sur mesure (choix de canevas → étapes) — construit (`configurateur-style`, `-tissu`, `-lining`, `-boutons`, `-construction`, `-resume`)
- [ ] Ajouter les vraies photos de chaque type de canevas (Fused, Half, Full) — le système est prêt (metaobjects avec champ `photo`, voir `sections/configurateur-construction.liquid:18-19`), il manque juste l'upload des photos dans l'admin (même item que "Photos Fused, Half, Full canvas" ci-dessus)

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
- [x] Page monogramme (nom brodé à l'intérieur du veston) — ajoutée à la fin des parcours Collection et Personnalisé, 20$.
- [ ] Livraison : définir les délais, et voir si un suivi de commande est possible (avec quel transporteur ?)
- [ ] Comptabilité : comprendre comment Shopify gère la comptabilité (taxes, rapports de vente, etc.) — recherche à faire avec Felix, pas du code
- [ ] Esthétique + adaptabilité mobile/tablette — révision visuelle générale du site sur tous les appareils

## Branding / liens à corriger
- [ ] Mettre le bon logo partout sur le site (actuellement incohérent ou manquant à certains endroits)
- [x] Le bouton/lien "Voir la collection" pointe maintenant vers `/collections/frontpage` (même page que le lien "Collection" du header/footer)
- [x] Footer : "Magasine" corrigé en "Magasiner", avec 3 liens distincts (Personnalisé, Collection, Chemise) menant chacun vers la bonne page.

## Déjà construit (retiré de la liste "à construire")
- [x] Navigation principale (`sections/header.liquid` — À propos / Collection / Personnalisé / Chemise, logo = retour accueil)
- [x] Footer (`sections/footer.liquid` + `footer-group.json`)
- [x] Distinction couturière vendeuse (livres de tissus) vs mensurations seulement — pastille dorée dédiée sur la carte, légende, toggle de filtre, texte clair sur chaque carte (`sections/header.liquid`, champ `vendeuse` sur le metaobjet `couturiere`). Felix doit cocher "vendeuse" sur ses vraies couturières concernées dans l'Admin Shopify.
- [x] Classe `.lmm-btn-primary` unifiée dans `snippets/css-variables.liquid` — corrige un vrai bug où les boutons "Continuer" de tout le parcours Collection (pieces/pantalon/ourlet/monogramme/page.liquid) étaient non stylés (la seule définition existante était locale à `home-hero.liquid`, renommée `.lmm-btn-hero-light` pour éviter la collision).
- [x] Étape monogramme (Personnalisé) et récapitulatif final réutilisent maintenant le même bouton partagé du panneau preview (`#lmm-prev-btn-next` dans `snippets/sm-preview.liquid`) au lieu de boutons locaux non stylés/incohérents. Le texte "un membre de notre équipe vous contactera" a été retiré du récapitulatif.
