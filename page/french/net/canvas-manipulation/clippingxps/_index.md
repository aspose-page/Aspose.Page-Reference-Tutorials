---
title: Découpage de XPS avec Aspose.Page pour .NET
linktitle: Découpage XPS
second_title: API Aspose.Page .NET
description: Découvrez la puissance d'Aspose.Page pour .NET dans ce guide étape par étape sur le découpage de documents XPS. Créez, manipulez et enregistrez des fichiers XPS sans effort.
weight: 11
url: /fr/net/canvas-manipulation/clippingxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Découpage de XPS avec Aspose.Page pour .NET

## Introduction

Bienvenue dans ce didacticiel complet sur le découpage de XPS à l'aide d'Aspose.Page pour .NET ! Dans ce guide, nous vous guiderons tout au long du processus de création, de manipulation et d'enregistrement de documents XPS à l'aide d'Aspose.Page pour .NET. XPS, ou XML Paper Spécification, est un format de document standardisé et ouvert, et Aspose.Page pour .NET fournit des outils puissants pour travailler avec des documents XPS dans vos applications .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :

- Visual Studio installé sur votre ordinateur.
-  Bibliothèque Aspose.Page pour .NET ajoutée à votre projet. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).
- Connaissance de base du langage de programmation C#.

## Importer des espaces de noms

Afin d'utiliser Aspose.Page pour les fonctionnalités .NET, vous devez importer les espaces de noms requis dans votre projet. Suivez ces étapes:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Maintenant, décomposons l'exemple de code que vous avez fourni en plusieurs étapes.

## Étape 1 : définissez le chemin du répertoire du document.

```csharp
string dataDir = "Your Document Directory";
```

Assurez-vous de remplacer « Votre répertoire de documents » par le chemin réel d'accès à votre répertoire de documents.

## Étape 2 : Créez un nouveau document XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

Cela crée un nouveau document XPS avec lequel vous travaillerez.

## Étape 3 : Créez le canevas principal.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Cette étape crée le canevas principal, commun à tous les éléments de la page.

## Étape 4 : définissez les décalages gauche et supérieur dans le canevas principal.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Ajustez les décalages gauche et supérieur selon vos besoins.

## Étape 5 : Créez une géométrie de chemin rectangulaire.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Cela crée une géométrie de chemin pour un rectangle.

## Étape 6 : Créez un remplissage pour les rectangles.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Définissez la couleur de remplissage des rectangles.

## Étape 7 : Ajoutez un autre canevas avec clip au canevas principal.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Cette étape ajoute un autre canevas au canevas principal.

## Étape 8 : Créez une géométrie de cercle pour le clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Cela crée une géométrie de clip circulaire et l'applique au deuxième canevas.

## Étape 9 : Créez un rectangle dans la deuxième toile et remplissez-le.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Cette étape crée un rectangle dans le deuxième canevas et le remplit.

## Étape 10 : Ajoutez la deuxième toile avec un rectangle tracé à la toile principale.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Cela ajoute un autre canevas au canevas principal.

## Étape 11 : Créez un rectangle dans la troisième toile et tracez-le.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Cela crée un rectangle dans le troisième canevas et lui applique un trait.

## Étape 12 : Enregistrez le document XPS résultant.

```csharp
doc.Save(dataDir + "output2.xps");
```

Cela enregistre le document XPS dans le répertoire spécifié.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment découper XPS à l’aide d’Aspose.Page pour .NET. Ce guide fournit une présentation détaillée des étapes impliquées dans le processus.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET avec d’autres formats de document ?

A1 : Aspose.Page pour .NET se concentre principalement sur les documents XPS, mais Aspose fournit d'autres bibliothèques pour différents formats de documents.

### Q2 : Aspose.Page pour .NET convient-il aux débutants ?

A2 : Oui, Aspose.Page pour .NET est conçu pour être convivial et les débutants peuvent rapidement comprendre ses fonctionnalités avec une documentation appropriée.

### Q3 : Où puis-je trouver plus d’exemples et de ressources ?

 A3 : Visitez le[Documentation](https://reference.aspose.com/page/net/) et[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour des ressources et des exemples complets.

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A4 : Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Existe-t-il un essai gratuit disponible pour Aspose.Page pour .NET ?

 A5 : Oui, vous pouvez explorer l'essai gratuit[ici](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
