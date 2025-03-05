---
title: Transformations XPS avec Aspose.Page pour .NET
linktitle: Transformation XPS
second_title: API Aspose.Page .NET
description: Transformez des documents XPS sans effort avec Aspose.Page pour .NET. Suivez notre guide étape par étape pour des transformations fluides.
type: docs
weight: 13
url: /fr/net/canvas-manipulation/transformationsxps/
---
## Introduction

Bienvenue dans le monde d'Aspose.Page pour .NET, une bibliothèque puissante qui vous permet d'effectuer diverses transformations sur des documents XPS sans effort. Dans ce didacticiel, nous allons plonger dans le processus de transformation de documents XPS à l'aide d'Aspose.Page pour .NET. Que vous soyez un développeur chevronné ou débutant, ce guide vous guidera à travers chaque étape, vous assurant de comprendre facilement les concepts.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants en place :

-  Aspose.Page pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir de[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/).

- Environnement de développement : configurez un environnement de développement compatible, tel que Visual Studio ou tout autre outil de développement .NET.

- Votre répertoire de documents : remplacez l'espace réservé dans le code par le chemin réel d'accès à votre répertoire de documents.

Passons maintenant au tutoriel !

## Importer des espaces de noms

Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires pour rendre les fonctionnalités Aspose.Page for .NET disponibles dans votre code. Ajoutez les espaces de noms suivants au début de votre script :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Créer un nouveau document XPS

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";

// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
```

## Étape 2 : Créer un canevas principal

```csharp
// Créer un canevas principal, commun à tous les éléments de la page
XpsCanvas canvas1 = doc.AddCanvas();

// Effectuer des décalages vers la gauche et le haut dans le canevas principal
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Étape 3 : Créer une géométrie de chemin rectangulaire

```csharp
// Créer une géométrie de chemin rectangulaire
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Étape 4 : ajouter un remplissage pour les rectangles

```csharp
// Créer un remplissage pour les rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Étape 5 : Ajouter un nouveau canevas sans transformations

```csharp
// Ajouter un nouveau canevas sans aucune transformation au canevas principal
XpsCanvas canvas2 = canvas1.AddCanvas();

// Créez un rectangle dans ce canevas et remplissez-le
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Étape 6 : Ajouter un nouveau canevas avec la transformation Translate

```csharp
// Ajouter un nouveau canevas avec transformation de traduction au canevas principal
XpsCanvas canvas3 = canvas1.AddCanvas();

// Traduisez ce canevas pour positionner un nouveau rectangle en dessous du rectangle précédent
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Traduisez ce canevas sur le côté droit de la page
canvas3.RenderTransform.Translate(500, 0);

// Créez un rectangle dans ce canevas et remplissez-le
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Étape 7 : Ajouter un nouveau canevas avec une transformation à double échelle

```csharp
//Ajouter un nouveau canevas avec une transformation à double échelle au canevas principal
XpsCanvas canvas4 = canvas1.AddCanvas();

// Traduisez ce canevas pour positionner un nouveau rectangle en dessous du rectangle précédent
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Mettez à l'échelle cette toile
canvas4.RenderTransform.Scale(2, 2);

// Créez un rectangle dans ce canevas et remplissez-le
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Étape 8 : Ajouter un nouveau canevas avec rotation autour d'une transformation ponctuelle

```csharp
// Ajouter un nouveau canevas avec rotation autour d'une transformation ponctuelle au canevas principal
XpsCanvas canvas5 = canvas1.AddCanvas();

// Traduisez ce canevas pour positionner un nouveau rectangle en dessous du rectangle précédent
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Faites pivoter cette toile autour d'un point à 45 degrés
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Créez un rectangle dans ce canevas et remplissez-le
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Étape 9 : Enregistrer le document XPS résultant

```csharp
// Enregistrer le document XPS résultant
doc.Save(dataDir + "output1.xps");
// ExFin : 1
```

## Conclusion

Toutes nos félicitations! Vous avez transformé avec succès un document XPS à l'aide d'Aspose.Page pour .NET. Ce guide couvrait les étapes essentielles, de la mise en place des prérequis à la réalisation de diverses transformations. Expérimentez ces techniques et libérez tout le potentiel d’Aspose.Page pour .NET dans vos projets.

## FAQ

### Q1 : Aspose.Page pour .NET est-il compatible avec tous les environnements de développement .NET ?

A1 : Oui, Aspose.Page pour .NET est conçu pour fonctionner de manière transparente avec divers environnements de développement .NET, y compris Visual Studio.

### Q2 : Où puis-je trouver des exemples et de la documentation supplémentaires pour Aspose.Page pour .NET ?

 A2 : Visitez le[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/) pour une documentation complète et des exemples.

### Q3 : Puis-je essayer Aspose.Page pour .NET avant d'acheter ?

 A3 : Oui, vous pouvez explorer une version d'essai gratuite en visitant[Essai gratuit d'Aspose.Page](https://releases.aspose.com/).

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A4 : Obtenez un permis temporaire en visitant[Permis temporaire](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis-je acheter Aspose.Page pour .NET ?

 A5 : Achetez Aspose.Page pour .NET sur[Aspose.Page Acheter](https://purchase.aspose.com/buy).