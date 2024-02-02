---
title: Ajouter un glyphe rempli d'image et une image étrangère avec Aspose.Page .NET
linktitle: Ajouter un glyphe rempli d'image et une image étrangère
second_title: API Aspose.Page .NET
description: Libérez la puissance du traitement des documents dans .NET avec Aspose.Page. Ajoutez facilement des glyphes remplis d’images. Améliorez les visuels et rationalisez votre flux de travail.
type: docs
weight: 11
url: /fr/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---
## Introduction

Dans le monde du développement .NET, Aspose.Page se distingue comme une puissante boîte à outils pour gérer les tâches de traitement de documents. Ce didacticiel vous guidera tout au long du processus d'ajout de glyphes remplis d'images et d'incorporation d'images étrangères à l'aide d'Aspose.Page pour .NET. À la fin de ce guide, vous aurez une solide compréhension de la manière d'améliorer vos capacités de traitement de documents.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page est installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).

- Environnement de développement : configurez un environnement de développement .NET fonctionnel avec Visual Studio ou tout autre IDE préféré.

- Répertoire de documents : créez un répertoire dans lequel vous stockerez vos documents. Ceci sera appelé « Votre répertoire de documents » dans les exemples de code.

## Importer des espaces de noms

Dans votre application .NET, commencez par importer les espaces de noms nécessaires pour accéder aux classes et méthodes fournies par Aspose.Page :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Créer le premier document XPS

Commencez par créer le premier document XPS à l'aide d'Aspose.Page. Ce document servira de base pour l'ajout de glyphes remplis d'images.

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";

// Créer le premier document XPS
XpsDocument doc1 = new XpsDocument();
```

## Étape 2 : ajouter des glyphes au premier document

Ajoutez des glyphes au premier document, en spécifiant la police, la taille, le style et la position.

```csharp
// Ajouter des glyphes au premier document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Étape 3 : remplir les glyphes avec un pinceau à image

Remplissez les glyphes avec un pinceau d'image, en utilisant une image de votre répertoire de données.

```csharp
// Remplissez les glyphes avec un pinceau d'image
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Étape 4 : Créer le deuxième document XPS

Créez maintenant le deuxième document XPS qui incorporera les glyphes du premier document.

```csharp
// Créez le deuxième document XPS
XpsDocument doc2 = new XpsDocument();
```

## Étape 5 : ajouter des glyphes avec la police du premier document

Ajoutez des glyphes au deuxième document, en utilisant la police du premier document.

```csharp
// Ajouter des glyphes avec la police du premier document au deuxième document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Étape 6 : Créer un pinceau d'image à partir du remplissage du premier document

Créez un pinceau d'image à partir du remplissage du premier document et utilisez-le pour remplir les glyphes du deuxième document.

```csharp
// Créez un pinceau d'image à partir du remplissage du premier document et remplissez les glyphes dans le deuxième document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Étape 7 : Enregistrez les documents

Enregistrez le premier et le deuxième documents XPS.

```csharp
// Enregistrez le premier document XPS
doc1.Save(dataDir + "out1.xps");

// Enregistrez le deuxième document XPS
doc2.Save(dataDir + "out2.xps");
// ExFin : 1
```

## Conclusion

Toutes nos félicitations! Vous avez ajouté avec succès des glyphes remplis d'images et incorporé des images étrangères à l'aide d'Aspose.Page pour .NET. Ce didacticiel fournit une base pour améliorer vos capacités de traitement de documents, ouvrant de nouvelles possibilités pour des documents créatifs et visuellement attrayants.

## FAQ

### Q1 : Puis-je utiliser différents formats d’image pour remplir les glyphes ?

A1 : Oui, Aspose.Page prend en charge différents formats d'image. Assurer la compatibilité avec le format d’image choisi.

### Q2 : Comment puis-je personnaliser davantage l’apparence des glyphes ?

A2 : Explorez la documentation Aspose.Page pour connaître des propriétés et des méthodes supplémentaires permettant d'affiner l'apparence des glyphes.

### Q3 : Aspose.Page est-il adapté à la gestion de grands ensembles de documents ?

A3 : Aspose.Page est conçu pour gérer efficacement des ensembles de documents petits et grands.

### Q4 : Puis-je appliquer différents styles à des glyphes individuels ?

A4 : Oui, vous pouvez personnaliser les styles de chaque glyphe indépendamment, offrant ainsi un haut niveau de flexibilité.

### Q5 : Quels sont les avantages de l’utilisation d’Aspose.Page par rapport à d’autres outils de traitement de documents ?

A5 : Aspose.Page offre un ensemble complet de fonctionnalités, d'excellentes performances et une documentation complète, ce qui en fait un choix privilégié pour de nombreux développeurs.