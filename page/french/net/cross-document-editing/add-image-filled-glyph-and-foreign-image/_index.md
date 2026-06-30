---
date: 2026-06-30
description: Apprenez à créer un document XPS .NET et à ajouter des glyphes remplis
  d'image ou des images étrangères en utilisant Aspose.Page pour .NET en quelques
  étapes simples.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Ajouter un glyphe rempli d'image et une image étrangère
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Créer un document XPS .NET – Ajouter un glyphe rempli d'image et une image
  étrangère avec Aspose.Page
url: /fr/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS .NET – Ajouter un glyphe rempli d'image et une image étrangère avec Aspose.Page

## Introduction

Dans le développement .NET, les tâches de **création de document XPS .NET** sont courantes lorsque vous avez besoin de graphiques de haute qualité, indépendants de la résolution. Aspose.Page pour .NET rend cela simple et vous permet d’enrichir les fichiers XPS avec des glyphes remplis d'image ou d'importer des images depuis un autre document XPS. À la fin de ce tutoriel, vous saurez comment créer deux documents XPS, remplir des glyphes avec des images et réutiliser ces images entre les documents — idéal pour générer des factures, des certificats ou tout autre rendu visuel riche.

## Réponses rapides
- **Qu'est-ce que Aspose.Page prend en charge ?** Plus de 25 formats d'image et la capacité de traiter des fichiers XPS jusqu'à 500 Mo sans chargement complet en mémoire.  
- **Combien de lignes de code pour ajouter un glyphe rempli d'image ?** Deux lignes seulement : créez un `ImageBrush` et assignez‑le à un `Glyph`.  
- **Ai-je besoin d'une licence pour la production ?** Oui, une licence commerciale supprime les filigranes d'évaluation.  
- **Quelles versions de .NET sont compatibles ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis-je réutiliser les polices d'un autre XPS ?** Absolument – vous pouvez importer la collection de polices du premier document dans le second.

## Comment créer un document XPS en utilisant Aspose.Page .NET ?

Chargez la bibliothèque Aspose.Page, créez une instance d'`XpsDocument`, ajoutez une page et appelez `Save` – c’est le flux complet en trois instructions concises. L'API gère automatiquement la taille de la page, le DPI et la gestion des ressources, vous n’avez donc pas besoin de gérer les structures XPS de bas niveau vous-même. Cette approche passe d’un flyer d’une seule page à des catalogues de plusieurs centaines de pages.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Aspose.Page for .NET** – téléchargez‑le depuis [here](https://releases.aspose.com/page/net/).  
- **Un IDE .NET** – Visual Studio, Rider ou VS Code avec l'extension C#.  
- **Un dossier pour vos documents** – nous le désignerons comme **Your Document Directory** dans les extraits de code.

## Importer les espaces de noms

Le namespace `Aspose.Page.XPS` fournit les classes principales de documents XPS, tandis que `Aspose.Page.XPS.XpsModel` contient les éléments du modèle tels que les glyphes et les pinceaux. Importez‑les en haut de votre fichier :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Qu'est-ce qu'un glyphe rempli d'image ?

Un glyphe est une forme vectorielle qui peut être rendue avec une couleur unie, un dégradé ou un pinceau d'image. Lorsque vous appliquez un `ImageBrush`, l'intérieur du glyphe est peint avec l'image fournie, permettant des effets visuels complexes sans rasteriser toute la page.

## Étape 1 : Créer le premier document XPS

`XpsDocument` représente un paquet XPS et constitue le point d'entrée pour créer et enregistrer des fichiers XPS. Commencez par créer le premier document XPS qui hébergera les glyphes remplis d'image.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Étape 2 : Ajouter des glyphes au premier document

`XpsGlyphs` définit une collection de glyphes (caractères texte) qui peuvent être placés sur une page. Ajoutez des glyphes au premier document en spécifiant la police, la taille, le style et la position.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Étape 3 : Remplir les glyphes avec un pinceau d'image

`ImageBrush` peint une zone avec une image, permettant à des motifs ou des photos de remplir des formes. Remplissez les glyphes avec un pinceau d'image en utilisant une image de votre répertoire de données.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Étape 4 : Créer le deuxième document XPS

`XpsDocument` est utilisé pour créer un nouveau fichier XPS pouvant contenir des pages, des ressources et du contenu. Créez maintenant le deuxième document XPS qui incorporera les glyphes du premier document.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Étape 5 : Ajouter des glyphes avec la police du premier document

`Font` représente une police utilisée pour rendre du texte dans un document XPS. Ajoutez des glyphes au deuxième document en utilisant la police extraite du premier document. En partageant la collection de polices, vous maintenez la taille du fichier faible et assurez la cohérence visuelle.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Étape 6 : Créer un pinceau d'image à partir du remplissage du premier document

`ImageBrush` peut être créé à partir d'un remplissage existant pour réutiliser la même image entre plusieurs documents. Créez un pinceau d'image à partir du remplissage du premier document et utilisez‑le pour remplir les glyphes du deuxième document. Cette technique d'« image étrangère » vous permet de réutiliser des illustrations sans dupliquer le fichier source.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Étape 7 : Enregistrer les documents

`Save` écrit le paquet XPS dans un fichier, en intégrant toutes les ressources. Enregistrez les premier et deuxième documents XPS dans le dossier de sortie. La méthode `Save` écrit le paquet XPS, intègre toutes les ressources et préserve les glyphes remplis d'image.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Image non affichée à l'intérieur du glyphe** | Le `ImageBrush` a été créé avec une URI incorrecte ou la taille de l'image dépasse les limites du glyphe. | Vérifiez le chemin de l'image et, éventuellement, définissez `ImageBrush.Stretch = Stretch.Uniform`. |
| **Polices manquantes dans le deuxième document** | Les ressources de police n'ont pas été exportées depuis le premier XPS. | Utilisez `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` avant d'ajouter les glyphes. |
| **Ralentissement des performances sur de gros fichiers** | Chargement de grandes images en mémoire pour chaque glyphe. | Réutilisez une seule instance de `ImageBrush` pour tous les glyphes, ou réduisez la résolution de l'image avant utilisation. |

## Questions fréquemment posées

### Q1 : Puis-je utiliser différents formats d'image pour remplir les glyphes ?

A1 : Oui, Aspose.Page prend en charge PNG, JPEG, BMP, GIF, TIFF, et plus — plus de 25 formats au total.

### Q2 : Comment puis‑je personnaliser davantage l'apparence des glyphes ?

A2 : Explorez des propriétés comme `Glyph.Stroke`, `Glyph.FillOpacity` et `Glyph.Transform` pour ajuster les contours, la transparence et la rotation.

### Q3 : Aspose.Page est‑il adapté à la gestion de grands ensembles de documents ?

A3 : Absolument. La bibliothèque traite des fichiers XPS de plusieurs centaines de pages en utilisant le streaming, maintenant l'utilisation de la mémoire sous 100 Mo même pour des documents de 500 pages.

### Q4 : Puis‑je appliquer différents styles à des glyphes individuels ?

A4 : Oui, chaque instance de `Glyph` possède ses propres propriétés `Fill`, `Stroke` et `Transform`, permettant une stylisation par glyphe.

### Q5 : Quels sont les avantages d'utiliser Aspose.Page par rapport aux autres outils XPS ?

A5 : Aspose.Page prend en charge plus de 25 formats d'image, traite des fichiers jusqu'à 500 Mo sans chargement complet en mémoire, et offre une API 100 % native .NET — éliminant le besoin d'interopérabilité COM ou d'outils externes.

**Dernière mise à jour** : 2026-06-30  
**Testé avec** : Aspose.Page 24.11 for .NET  
**Auteur** : Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Créer un document XPS – Aspose.Page for .NET](/page/net/document-creation/)
- [Ajouter une image au document XPS avec Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Ajouter un clone de glyphe et changer la couleur avec Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}