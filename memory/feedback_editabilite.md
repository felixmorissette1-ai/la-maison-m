---
name: feedback-editabilite
description: Tous les textes et photos doivent toujours être éditables depuis l'admin Shopify
metadata:
  type: feedback
---

Toujours rendre les textes et les photos éditables depuis l'admin Shopify via les settings de section (`{% schema %}`).

**Why:** L'utilisateur ne veut pas dépendre du dev pour changer du contenu — il veut tout contrôler lui-même.

**How to apply:** Pour chaque section ou snippet, exposer dans le schema : tous les textes (titres, sous-titres, descriptions, labels), toutes les images, et toutes les options configurables. Utiliser `section.settings.*` plutôt que du texte codé en dur. Pour les snippets (qui ne supportent pas `{% schema %}`), passer les variables depuis la section parente.
