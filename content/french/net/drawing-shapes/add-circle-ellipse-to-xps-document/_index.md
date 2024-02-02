---
title: Ajouter Circle Ellipse au document XPS avec Aspose.Page pour .NET
linktitle: Ajouter Circle Ellipse au document XPS
second_title: API Aspose.Page .NET
description: Améliorez les documents XPS avec des dégradés radiaux éclatants à l'aide d'Aspose.Page pour .NET. Suivez notre guide étape par étape pour des effets visuels époustouflants.
type: docs
weight: 11
url: /fr/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## Introduction

La création de documents XPS visuellement attrayants est une exigence courante dans diverses applications. Aspose.Page pour .NET fournit un ensemble puissant de fonctionnalités pour manipuler efficacement les documents XPS. Dans ce didacticiel, nous nous concentrerons sur l'ajout d'une ellipse circulaire à un document XPS à l'aide d'Aspose.Page pour .NET. Suivez les étapes ci-dessous pour améliorer vos documents XPS avec des dégradés radiaux éclatants.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Installation de la bibliothèque Aspose.Page pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).
- Un environnement de développement, de préférence Visual Studio ou tout autre outil de développement .NET.
- Connaissance de base de la programmation C#.

## Importer des espaces de noms

Pour commencer, incluez les espaces de noms nécessaires dans votre code C# :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Maintenant, décomposons l'exemple en plusieurs étapes :

## Étape 1 : Configurer le document

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
```

Ici, nous initialisons un nouveau document XPS à l'aide d'Aspose.Page pour .NET.

## Étape 2 : Définir l'ellipse de dégradé radial

```csharp
// Ellipse à dégradé radial en bas à gauche
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

Cette étape consiste à définir une ellipse de dégradé radial avec différents arrêts de couleur.

## Étape 3 : définir le pinceau dégradé radial

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

Ici, nous définissons le trait de l'ellipse sur un pinceau à dégradé radial, en lui fournissant les paramètres nécessaires.

## Étape 4 : Ajuster l'épaisseur du trait

```csharp
path.StrokeThickness = 12f;
```

Cette étape consiste à ajuster l’épaisseur du trait pour une meilleure visualisation.

## Étape 5 : Enregistrez le document XPS résultant

```csharp
// Enregistrer le document XPS résultant
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// ExFin : 1
```

Enfin, enregistrez le document XPS modifié à l'emplacement souhaité.

## Conclusion

Toutes nos félicitations! Vous avez ajouté avec succès une ellipse circulaire avec des dégradés radiaux à votre document XPS à l'aide d'Aspose.Page pour .NET. Expérimentez avec différents paramètres et couleurs pour obtenir les effets visuels souhaités dans vos documents.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET avec d’autres formats de document ?

A1 : Aspose.Page pour .NET traite spécifiquement de la manipulation de documents XPS. Pour les autres formats, pensez à utiliser les bibliothèques Aspose associées.

### Q2 : Une licence temporaire est-elle disponible à des fins de test ?

 A2 : Oui, vous pouvez obtenir une licence temporaire pour tester en visitant[ce lien](https://purchase.aspose.com/temporary-license/).

### Q3 : Où puis-je trouver de l'aide et des discussions supplémentaires ?

 A3 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien et les discussions de la communauté.

### Q4 : Existe-t-il des exemples de documents disponibles à titre de référence ?

 A4 : Explorez le[Documentation](https://reference.aspose.com/page/net/) pour des exemples et des lignes directrices complets.

### Q5 : Puis-je acheter Aspose.Page pour .NET ?

 A5 : Oui, vous pouvez acheter la bibliothèque[ici](https://purchase.aspose.com/buy).