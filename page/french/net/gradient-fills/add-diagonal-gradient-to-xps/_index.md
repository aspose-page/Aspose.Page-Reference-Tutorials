---
title: Ajoutez un dégradé diagonal à XPS avec Aspose.Page pour .NET
linktitle: Ajouter un dégradé diagonal à XPS
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter des dégradés diagonaux captivants aux documents XPS à l'aide d'Aspose.Page pour .NET. Élevez vos présentations visuelles sans effort.
weight: 11
url: /fr/net/gradient-fills/add-diagonal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajoutez un dégradé diagonal à XPS avec Aspose.Page pour .NET

## Introduction

Dans le domaine du traitement de documents, Aspose.Page pour .NET se distingue comme une boîte à outils puissante qui permet aux développeurs de manipuler facilement les documents XPS. Une fonctionnalité intéressante qu'il offre est la possibilité d'ajouter des dégradés diagonaux, vous permettant d'améliorer l'attrait visuel de vos documents. Ce didacticiel vous guidera étape par étape tout au long du processus, vous montrant comment incorporer des dégradés diagonaux dans des fichiers XPS à l'aide d'Aspose.Page pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

2. Environnement de développement : configurez votre environnement de développement préféré pour travailler avec .NET.

Commençons maintenant par ajouter des dégradés diagonaux à XPS à l'aide d'Aspose.Page pour .NET.

## Importer des espaces de noms

Dans votre projet .NET, incluez les espaces de noms nécessaires de la bibliothèque Aspose.Page pour accéder aux classes et méthodes requises. Ajoutez les espaces de noms suivants au début de votre code :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Étape 1 : Définir le répertoire des documents

Commencez par spécifier le chemin d'accès à votre répertoire de documents. C'est ici que le document XPS résultant avec le dégradé diagonal sera enregistré.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer un nouveau document XPS

Initialisez un nouveau XpsDocument à l'aide de la bibliothèque Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Étape 3 : Définir les couleurs du dégradé

Créez une liste d'objets XpsGradientStop, chacun représentant une couleur dans le dégradé diagonal.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Répétez pour les autres couleurs
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Étape 4 : ajouter un dégradé diagonal à un chemin

Créez un nouveau chemin avec une géométrie définie et appliquez-y le dégradé diagonal. Ajustez la transformation de rendu et les propriétés de remplissage selon vos besoins.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Étape 5 : Enregistrez le document XPS résultant

Enfin, enregistrez le document XPS modifié dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Vous avez maintenant ajouté avec succès un dégradé diagonal à un document XPS à l'aide d'Aspose.Page pour .NET. Expérimentez avec différentes couleurs et géométries pour créer des effets visuels époustouflants.

## Conclusion

Aspose.Page pour .NET simplifie le processus d'amélioration des documents XPS avec des dégradés diagonaux. Ce didacticiel vous a guidé à travers les étapes, depuis la configuration des prérequis jusqu'à l'enregistrement du document final. Explorez d’autres possibilités et améliorez la présentation de vos documents.

## FAQ

### Q1 : Puis-je appliquer plusieurs dégradés à différentes parties du document ?

A1 : Oui, vous pouvez créer plusieurs chemins et appliquer des dégradés distincts à chacun.

### Q2 : Existe-t-il des styles de dégradé prédéfinis ?

A2 : Aspose.Page permet des dégradés personnalisés, vous donnant un contrôle total sur les transitions de couleurs.

### Q3 : Puis-je utiliser Aspose.Page pour .NET avec d’autres formats de document ?

A3 : Aspose.Page se concentre principalement sur la manipulation de documents XPS.

### Q4 : Comment puis-je gérer les erreurs liées au traitement des documents ?

 A4 : Reportez-vous au[Documentation](https://reference.aspose.com/page/net/)pour les meilleures pratiques de gestion des erreurs.

### Q5 : Existe-t-il une version d'essai disponible avant l'achat ?

 A5 : Oui, vous pouvez explorer le[essai gratuit](https://releases.aspose.com/) pour découvrir Aspose.Page pour .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
