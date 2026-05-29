# FDDS Editor Webapp v0.5

Éditeur web séparé du site public. Il se connecte au dépôt GitHub du site, lit les contenus structurés du dossier `content/`, permet de les modifier, puis republie le site généré en un seul commit.

## Nouveautés v0.4

- Correction de l’édition du contenu d’article.
- Séparation plus nette entre article général et article personnage.
- Extraction automatique des anciennes cartes personnage `aside.infobox` lors du chargement des contenus existants.
- Ajout d’un template « Article personnage » avec carte structurée : image, type, activité, entourage, ennemi de, première apparition, état.
- Les champs de la carte acceptent du HTML et des liens.
- Ajout d’une fenêtre de création de lien : sélectionnez du texte, cliquez sur « Lien » ou « Créer un lien sur la sélection », puis renseignez la cible.
- La génération conserve le style public existant des cartes personnage.

## Test recommandé

1. Ouvrir `index.html` avec Live Server dans VS Code.
2. Charger le dépôt GitHub de test.
3. Ouvrir un article de catégorie Personnage, par exemple Vega ou Jacques Homme Doré.
4. Vérifier que la carte personnage est affichée dans les champs structurés.
5. Modifier un champ, par exemple « État ».
6. Modifier un paragraphe dans le corps de l’article.
7. Prévisualiser la génération.
8. Publier.
9. Vérifier le site public.

## Remarque de structure

À partir de cette version, les articles peuvent contenir :

```json
{
  "template": "character",
  "characterCard": {
    "enabled": true,
    "image": "assets/images/...",
    "caption": "...",
    "type": "...",
    "activity": "...",
    "entourage": "...",
    "enemyOf": "...",
    "firstAppearance": "...",
    "status": "..."
  },
  "bodyHtml": "<p>Contenu principal de l’article.</p>"
}
```

Le site public continue d’être généré dans `pages/`, `data/` et `index.html`.


## Correctifs v0.5

- Les champs de carte personnage apparaissent dès que le type « Article personnage » est sélectionné.
- Une case « Créer une carte personnage » permet d’activer explicitement la carte.
- Les articles de catégorie « Personnage » affichent automatiquement les champs spécifiques au chargement.
- Les anciennes cartes personnage présentes dans le HTML sont extraites vers les champs structurés.

## Aides contextuelles

Cette version ajoute des aides contextuelles dans l’interface. Les champs et actions principales disposent d’un bouton `?`. Un clic ouvre une bulle d’aide superposée à l’interface. La bulle se ferme avec la croix, avec la touche Échap, ou en cliquant ailleurs dans la page.
