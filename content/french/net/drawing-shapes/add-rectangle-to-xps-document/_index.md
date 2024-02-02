---
title: Ajouter un rectangle au document XPS avec Aspose.Page pour .NET
linktitle: Ajouter un rectangle au document XPS
second_title: API Aspose.Page .NET
description: Améliorez la création de documents avec Aspose.Page pour .NET. Découvrez comment ajouter des rectangles aux documents XPS dans ce didacticiel étape par étape.
type: docs
weight: 13
url: /fr/net/drawing-shapes/add-rectangle-to-xps-document/
---
## Introduction

Aspose.Page pour .NET est une bibliothèque puissante qui offre une variété de fonctionnalités pour travailler avec des documents XPS (XML Paper Spécification) dans les applications .NET. Dans ce didacticiel, nous nous concentrerons sur l'ajout d'un rectangle à un document XPS à l'aide d'Aspose.Page pour .NET. Suivez ce guide étape par étape pour améliorer votre processus de création de documents.

## Conditions préalables

Avant de commencer ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

2. Répertoire de documents : configurez un répertoire dans lequel vous souhaitez stocker vos documents XPS.

## Importer des espaces de noms

Dans votre application .NET, incluez les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Définir le répertoire des documents

```csharp
// ExDébut : 3
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// ExFin : 3
```

## Étape 2 : Créer un nouveau document XPS

```csharp
// ExDébut : 4
// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
// ExFin : 4
```

## Étape 3 : ajouter un rectangle

```csharp
// ExDébut : 5
// Rectangle quadrillé de couleur unie CMJN (bleu) en bas à gauche
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExFin : 5
```

## Étape 4 : Enregistrez le document

```csharp
// ExDébut : 6
// Enregistrer le document XPS résultant
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExFin : 6
```

Toutes nos félicitations! Vous avez ajouté avec succès un rectangle à un document XPS à l'aide d'Aspose.Page pour .NET.

## Conclusion

Aspose.Page for .NET simplifie les tâches de manipulation de documents, permettant aux développeurs de créer et de modifier des documents XPS sans effort. Ce guide étape par étape montre comment ajouter un rectangle à votre document XPS, fournissant ainsi une base solide pour une exploration plus approfondie.

## FAQ

### Q1 : Aspose.Page est-il compatible avec toutes les applications .NET ?

A1 : Oui, Aspose.Page est conçu pour fonctionner de manière transparente avec toutes les applications .NET.

### Q2 : Où puis-je trouver la documentation d’Aspose.Page pour .NET ?

 A2 : La documentation est disponible[ici](https://reference.aspose.com/page/net/).

### Q3 : Puis-je essayer Aspose.Page pour .NET gratuitement avant d'acheter ?

 A3 : Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/).

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A4 : Visite[ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir un permis temporaire.

### Q5 : Où puis-je rechercher l'assistance de la communauté ou poser des questions relatives à Aspose.Page pour .NET ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien de la communauté.