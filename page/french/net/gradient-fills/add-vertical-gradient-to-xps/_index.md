---
title: Ajouter un dégradé vertical à XPS avec Aspose.Page pour .NET
linktitle: Ajouter un dégradé vertical à XPS
second_title: API Aspose.Page .NET
description: Découvrez comment améliorer les documents XPS avec des dégradés verticaux à l'aide d'Aspose.Page pour .NET. Suivez notre guide étape par étape pour une intégration transparente.
weight: 15
url: /fr/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé vertical à XPS avec Aspose.Page pour .NET

## Introduction

Bienvenue dans ce didacticiel étape par étape expliquant comment ajouter un dégradé vertical à un document XPS à l'aide d'Aspose.Page pour .NET. Aspose.Page est une API puissante qui vous permet de travailler avec des fichiers XPS (XML Paper Spécification) dans vos applications .NET. Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un nouveau document XPS, d'ajout d'un dégradé vertical à un tracé et d'enregistrement du résultat.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :

-  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

- Environnement de développement : configurez un environnement de développement .NET avec votre IDE préféré, tel que Visual Studio.

Commençons maintenant par ajouter un dégradé vertical à un document XPS à l'aide d'Aspose.Page pour .NET.

## Importer des espaces de noms

Dans votre application .NET, incluez les espaces de noms nécessaires pour accéder aux classes et méthodes Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Étape 1 : Configurez votre répertoire de documents

Avant de commencer, définissez le chemin d'accès à votre répertoire de documents dans lequel vous souhaitez enregistrer le document XPS résultant.

```csharp
// ExDébut : 3
string dataDir = "Your Document Directory";
// ExFin : 3
```

## Étape 2 : Créer un nouveau document XPS

Initialisez un nouveau document XPS à l'aide du code suivant :

```csharp
// ExDébut : 4
XpsDocument doc = new XpsDocument();
// ExFin : 4
```

## Étape 3 : Définir les arrêts de dégradé

Créez une liste de points de dégradé, en spécifiant la couleur et la position de chaque point. Dans cet exemple, nous définissons un dégradé vertical avec cinq arrêts.

```csharp
// ExDébut : 5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExFin : 5
```

## Étape 4 : Créer un chemin avec dégradé

Définissez un tracé en spécifiant sa géométrie et appliquez-lui un pinceau dégradé linéaire.

```csharp
// ExDébut : 6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExFin : 6
```

## Étape 5 : Enregistrez le document XPS résultant

Enregistrez le document XPS modifié dans votre répertoire spécifié.

```csharp
// ExDébut : 7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExFin : 7
```

Toutes nos félicitations! Vous avez ajouté avec succès un dégradé vertical à un document XPS à l'aide d'Aspose.Page pour .NET.

## Conclusion

Dans ce didacticiel, nous avons exploré comment exploiter Aspose.Page pour .NET pour améliorer les documents XPS avec des dégradés verticaux. Aspose.Page simplifie les tâches complexes, offrant aux développeurs un moyen transparent de manipuler les fichiers XPS dans leurs applications .NET.

## FAQ

### Q1 : Aspose.Page est-il compatible avec Visual Studio 2019 ?

A1 : Oui, Aspose.Page est compatible avec Visual Studio 2019. Assurez-vous que la version correcte de la bibliothèque est installée.

### Q2 : Puis-je utiliser Aspose.Page pour des projets commerciaux ?

 A2 : Oui, Aspose.Page peut être utilisé pour des projets commerciaux. Visite[ici](https://purchase.aspose.com/buy) pour explorer les options de licence.

### Q3 : Existe-t-il un essai gratuit disponible ?

 A3 : Oui, vous pouvez obtenir un essai gratuit d'Aspose.Page[ici](https://releases.aspose.com/).

### Q4 : Où puis-je trouver la documentation Aspose.Page ?

 A4 : La documentation est disponible[ici](https://reference.aspose.com/page/net/).

### Q5 : Comment puis-je obtenir de l'aide ou poser des questions ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
