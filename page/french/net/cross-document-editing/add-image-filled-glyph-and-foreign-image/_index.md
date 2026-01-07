---
date: 2026-01-07
description: Apprenez à créer un document XPS .NET avec Aspose.Page. Ce guide montre
  comment ajouter des glyphes remplis d’images et des images externes pour enrichir
  les visuels du document.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Créer un document XPS .NET avec Aspose.Page – Glyphe rempli d’image et image
  étrangère
url: /fr/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS .NET avec Aspose.Page – Glyphe rempli d'image & Image étrangère

## Introduction

Si vous devez **créer des documents XPS .NET** qui ont l'air soignés et professionnels, Aspose.Page vous fournit les outils pour intégrer des images directement dans les glyphes et réutiliser les ressources graphiques entre plusieurs documents. Dans ce tutoriel, nous allons créer deux fichiers XPS, remplir des glyphes avec un pinceau d'image, puis réutiliser ce pinceau dans un second document. À la fin, vous comprendrez pourquoi cette approche économise de la mémoire, simplifie le style et ouvre des possibilités créatives pour les rapports, factures ou tout contenu imprimable.

## Réponses rapides
- **Que couvre ce tutoriel ?** Ajout de glyphes remplis d'image et réutilisation de ceux‑ci dans des documents XPS avec Aspose.Page pour .NET.  
- **Quel mot‑clé principal est ciblé ?** `create xps document .net`.  
- **Pré‑requis ?** Environnement de développement .NET, Aspose.Page pour .NET, et un dossier pour vos fichiers XPS.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un prototype fonctionnel.  
- **Puis‑je utiliser d'autres formats d'image ?** Oui – tout format pris en charge par `System.Drawing.Image` de .NET.

## Pré‑requis

Avant de plonger dans le code, assurez‑vous d'avoir les éléments suivants prêts :

- **Aspose.Page pour .NET** – téléchargez la dernière bibliothèque [ici](https://releases.aspose.com/page/net/).  
- **Environnement de développement** – Visual Studio 2022 (ou tout IDE supportant .NET 6+).  
- **Répertoire de documents** – créez un dossier sur votre machine qui contiendra les images d’entrée et les fichiers XPS générés ; nous le désignerons **Your Document Directory** dans les extraits.

## Importer les espaces de noms

Commencez par inclure les espaces de noms nécessaires pour travailler avec les objets XPS et les utilitaires de dessin.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Guide étape par étape

### Étape 1 : Créer le premier document XPS

Nous commençons par instancier un document XPS vide qui accueillera le glyphe rempli d'image.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Étape 2 : Ajouter des glyphes au premier document

Ensuite, ajoutez un glyphe (un caractère texte) que nous remplirons plus tard avec un pinceau d'image.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Étape 3 : Remplir les glyphes avec un pinceau d'image

Ici, nous créons un `ImageBrush` à partir d'un fichier TIFF situé dans notre répertoire de données et l'appliquons au glyphe. Le pinceau est configuré en mode tuile afin que l'image se répète si la zone du glyphe dépasse la taille de l'image.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Étape 4 : Créer le second document XPS

Nous créons maintenant un second document XPS qui réutilisera le style de glyphe et le pinceau d'image du premier.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Étape 5 : Ajouter des glyphes avec la police du premier document

Nous ajoutons un glyphe au second document, en réutilisant exactement l'objet police du premier document. Cela garantit une cohérence visuelle entre les deux fichiers.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Étape 6 : Créer un pinceau d'image à partir du remplissage du premier document

Au lieu de charger à nouveau l'image, nous clonons le pinceau depuis `glyphs1` et l'assignons à `glyphs2`. Cela montre comment vous pouvez **créer des documents XPS .NET** avec des flux de travail partageant efficacement les ressources.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Étape 7 : Enregistrer les documents

Enfin, persistez les deux fichiers XPS sur le disque. Vous pouvez maintenant les ouvrir avec n’importe quel visualiseur XPS pour voir l’effet du glyphe rempli d'image.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Pourquoi utiliser des glyphes remplis d'image lorsque vous créez un document XPS .NET ?

- **Impact visuel** – Transformez du texte simple en éléments riches graphiquement sans rasteriser toute la page.  
- **Réutilisation des ressources** – Partagez pinceaux et polices entre plusieurs documents, réduisant l’empreinte mémoire.  
- **Flexibilité** – Tile, stretch ou rotate le pinceau d'image pour obtenir des motifs personnalisés ou du branding.

## Problèmes courants et astuces

- **Erreurs de chemin de fichier** – Assurez‑vous que `dataDir` se termine par un séparateur de chemin (`\` ou `/`) adapté à votre OS.  
- **Formats d'image non pris en charge** – Aspose.Page fonctionne de préférence avec TIFF, PNG et JPEG. Convertissez les autres formats avant utilisation.  
- **TileMode non appliqué** – Vérifiez que vous castiez en `XpsImageBrush` avant de définir `TileMode` ; sinon la propriété est ignorée.

## Questions fréquentes

### Q1 : Puis‑je utiliser différents formats d'image pour remplir les glyphes ?

**R :** Oui, Aspose.Page prend en charge TIFF, PNG, JPEG, BMP et GIF. Il suffit de fournir la bonne extension de fichier dans l’appel `CreateImageBrush`.

### Q2 : Comment puis‑je personnaliser davantage l’apparence des glyphes ?

**R :** Explorez les propriétés supplémentaires de `XpsGlyphs` telles que `Opacity`, `RenderTransform` et `Stroke` pour affiner le rendu.

### Q3 : Aspose.Page est‑il adapté à la gestion de grands ensembles de documents ?

**R :** Absolument. La bibliothèque est optimisée pour des scénarios haute performance et peut traiter des milliers de fichiers XPS en batch.

### Q4 : Puis‑je appliquer différents styles à des glyphes individuels ?

**R :** Oui. Chaque instance de `XpsGlyphs` peut avoir son propre remplissage, contour et transformation, vous offrant un contrôle granulaire.

### Q5 : Quels sont les avantages d’utiliser Aspose.Page par rapport à d’autres outils de traitement de documents ?

**R :** Aspose.Page propose une API complète, sans licence, pour la création, la manipulation et la conversion XPS, avec une documentation exhaustive et un support 24/7.

---

**Dernière mise à jour :** 2026-01-07  
**Testé avec :** Aspose.Page 24.12 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}