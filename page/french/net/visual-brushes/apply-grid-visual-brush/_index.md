---
title: Appliquer un pinceau visuel de grille avec Aspose.Page pour .NET
linktitle: Appliquer le pinceau visuel de grille
second_title: API Aspose.Page .NET
description: Explorez le monde dynamique du traitement de documents dans .NET avec Aspose.Page. Apprenez à appliquer un Grid Visual Brush pour des documents visuellement époustouflants.
weight: 10
url: /fr/net/visual-brushes/apply-grid-visual-brush/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Appliquer un pinceau visuel de grille avec Aspose.Page pour .NET

## Introduction

Dans le monde du développement .NET, Aspose.Page s'impose comme un outil puissant pour gérer les tâches de traitement de documents. Une fonctionnalité fascinante qu'il offre est la possibilité d'appliquer un Grid Visual Brush, apportant une nouvelle dimension à vos documents. Ce didacticiel vous guidera étape par étape tout au long du processus de mise en œuvre d'un pinceau visuel Magenta Grid à l'aide d'Aspose.Page pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les prérequis suivants :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque est installée et configurée dans votre environnement .NET. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

- Environnement de développement : disposez d'un environnement de développement .NET fonctionnel et d'une compréhension de base de la programmation C#.

- Répertoire de documents : créez un répertoire pour vos documents dans lequel les fichiers traités seront enregistrés.

## Importer des espaces de noms

Dans votre code C#, vous devez importer les espaces de noms nécessaires pour utiliser efficacement les fonctionnalités d'Aspose.Page :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Maintenant, décomposons l'exemple en plusieurs étapes.

## Étape 1 : initialiser XpsDocument

```csharp
// ExDébut : 3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExFin : 3
```

 Ici, nous créons une instance de`XpsDocument` pour travailler avec des documents XPS.

## Étape 2 : Créer une géométrie de grille magenta

```csharp
// ExDébut : 4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExFin : 4
```

Cette étape consiste à créer une géométrie de chemin pour la grille magenta.

## Étape 3 : Concevoir VisualBrush à grille magenta

```csharp
// ExDébut : 5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExFin : 5
```

Ici, nous concevons l'aspect visuel de la grille magenta à l'aide de graphiques vectoriels.

## Étape 4 : Appliquer VisualBrush à la grille

```csharp
// ExDébut : 6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExFin : 6
```

Appliquez le pinceau visuel sur le chemin de la grille, en vous assurant qu'il est correctement carrelé.

## Étape 5 : ajouter une grille au canevas

```csharp
// ExDébut : 7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExFin : 7
```

Ajoutez la grille au canevas, en spécifiant les transformations nécessaires.

## Étape 6 : Améliorer avec le rectangle rouge

```csharp
// ExDébut : 8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f;
// ExFin : 8
```

Améliorez l'attrait visuel en ajoutant un rectangle transparent rouge.

## Étape 7 : Enregistrez le document

```csharp
// ExDébut : 9
doc.Save(dataDir + "AddGrid_out.xps");
// ExFin : 9
```

Enregistrez le document XPS résultant dans votre répertoire spécifié.

## Conclusion

Toutes nos félicitations! Vous avez appliqué avec succès un Grid Visual Brush à votre document à l’aide d’Aspose.Page pour .NET. Cette technique peut améliorer considérablement les éléments visuels de vos documents, offrant une expérience utilisateur dynamique et engageante.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET dans les applications Web et de bureau ?

A1 : Oui, Aspose.Page pour .NET est polyvalent et peut être utilisé dans différents types d'applications.

### Q2 : Existe-t-il une version d'essai disponible avant l'achat ?

 A2 : Absolument, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).

### Q3 : Où puis-je trouver une assistance supplémentaire ou des discussions communautaires ?

 A3 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour des échanges et du soutien.

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A4 : Vous pouvez acquérir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Quelle autre documentation est disponible pour Aspose.Page pour .NET ?

 A5 : Explorez la documentation complète[ici](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
