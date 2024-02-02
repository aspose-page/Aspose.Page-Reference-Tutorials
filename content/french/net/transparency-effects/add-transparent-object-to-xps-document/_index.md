---
title: Ajouter un objet transparent au document XPS avec Aspose.Page
linktitle: Ajouter un objet transparent au document XPS
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter des objets transparents aux documents XPS dans .NET à l'aide d'Aspose.Page. Améliorez l’attrait visuel avec des conseils étape par étape.
type: docs
weight: 11
url: /fr/net/transparency-effects/add-transparent-object-to-xps-document/
---
## Introduction

Dans ce didacticiel, nous allons explorer comment ajouter des objets transparents à un document XPS à l'aide d'Aspose.Page pour .NET. La transparence des documents XPS peut améliorer l'attrait visuel et transmettre les informations de manière efficace. Nous diviserons le processus en étapes gérables, garantissant clarté et facilité de compréhension.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée. Vous pouvez le télécharger depuis[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/).

## Importer des espaces de noms

Pour commencer, incluez les espaces de noms nécessaires dans votre projet :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Passons maintenant au guide étape par étape.

## Étape 1 : Créer un nouveau document XPS

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
```

Ce code initialise un nouveau document XPS à l'aide d'Aspose.Page pour .NET.

## Étape 2 : faire preuve de transparence

```csharp
// Juste pour faire preuve de transparence
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

Ces lignes créent des chemins transparents pour mettre en valeur l'effet de transparence dans le document.

## Étape 3 : Créer un chemin avec une géométrie de rectangle fermé

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Ici, nous créons un chemin avec une géométrie de rectangle fermé, définissons un pinceau solide bleu pour le remplir et l'ajoutons à la page actuelle.

## Étape 4 : Manipuler les chemins et les couleurs

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

Cette étape montre comment les chemins peuvent être manipulés et les couleurs peuvent être modifiées.

## Étape 5 : Cloner et transformer les chemins

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

Clonez et transformez les chemins, en décalant et en changeant la couleur du chemin cloné.

## Étape 6 : Répéter et modifier les chemins

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

Répétez le processus en créant un nouveau chemin basé sur le précédent, avec des modifications.

## Étape 7 : Gérer l'opacité

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

Démontrez comment l’opacité peut être gérée indépendamment pour différents chemins.

## Étape 8 : Enregistrez le document XPS

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

Enfin, enregistrez le document XPS résultant avec la transparence appliquée.

## Conclusion

L'ajout d'objets transparents aux documents XPS à l'aide d'Aspose.Page pour .NET offre un moyen polyvalent d'améliorer les présentations visuelles. Expérimentez avec différentes géométries, couleurs et opacités pour obtenir l'effet souhaité.

## FAQ

### Q1 : Puis-je appliquer de la transparence à n’importe quel objet dans un document XPS ?

R1 : Oui, la transparence peut être appliquée à divers objets tels que des tracés, des formes et des images dans un document XPS.

### Q2 : Comment puis-je ajuster l’opacité d’un élément spécifique ?

A2 : Vous pouvez définir la propriété d'opacité du remplissage ou du contour pour ajuster la transparence d'un élément spécifique.

### Q3 : Aspose.Page est-il compatible avec .NET Core ?

A3 : Oui, Aspose.Page prend en charge .NET Core, permettant le développement multiplateforme.

### Q4 : Puis-je exporter des documents XPS vers d’autres formats à l’aide d’Aspose.Page ?

A4 : Aspose.Page fournit des fonctionnalités permettant d'exporter des documents XPS vers différents formats, notamment PDF et images.

### Q5 : Où puis-je trouver du soutien supplémentaire et des discussions communautaires ?

 A5 : Pour obtenir un soutien supplémentaire et des discussions communautaires, visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39).