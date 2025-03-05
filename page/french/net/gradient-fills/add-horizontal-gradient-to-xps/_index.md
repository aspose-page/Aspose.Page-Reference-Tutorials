---
title: Ajouter un dégradé horizontal à XPS avec Aspose.Page pour .NET
linktitle: Ajouter un dégradé horizontal à XPS
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter de superbes dégradés horizontaux à vos documents XPS à l'aide d'Aspose.Page pour .NET. Améliorez l’attrait visuel sans effort.
type: docs
weight: 13
url: /fr/net/gradient-fills/add-horizontal-gradient-to-xps/
---
## Introduction

Dans ce didacticiel, nous explorerons comment améliorer les documents XPS en ajoutant un dégradé horizontal à l'aide d'Aspose.Page pour .NET. Aspose.Page pour .NET est une bibliothèque puissante qui permet une gestion transparente des documents XPS (XML Paper Spécification) dans les applications .NET. L'ajout de dégradés peut apporter un attrait visuel à vos documents, et ce guide vous guidera pas à pas tout au long du processus.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez le télécharger depuis le[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/).

2. Environnement de développement : configurez un environnement de développement adapté, comprenant un éditeur de code comme Visual Studio.

## Importer des espaces de noms

Commencez par importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms sont essentiels pour travailler avec Aspose.Page pour .NET :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes.

## Étape 1 : Définir le chemin du répertoire de documents

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

## Étape 3 : initialiser les arrêts de dégradé

```csharp
// ExDébut : 5
// Initialiser la liste de XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExFin : 5
```

## Étape 4 : Créer un nouveau chemin

```csharp
// ExDébut : 6
//Créez un nouveau chemin en définissant la géométrie sous forme d'abréviation
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExFin : 6
```

## Étape 5 : Enregistrez le document XPS résultant

```csharp
// ExDébut : 7
// Enregistrer le document XPS résultant
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExFin : 7
```

Vous avez maintenant ajouté avec succès un dégradé horizontal à votre document XPS à l'aide d'Aspose.Page pour .NET.

## Conclusion

L'amélioration de vos documents XPS avec des dégradés améliore non seulement leur attrait visuel, mais offre également une expérience utilisateur plus attrayante. Aspose.Page for .NET simplifie ce processus, vous permettant d'obtenir des résultats professionnels sans effort.

## FAQ

### Q1 : Où puis-je trouver la documentation Aspose.Page pour .NET ?

 A1 : Vous pouvez trouver la documentation[ici](https://reference.aspose.com/page/net/).

### Q2 : Comment télécharger Aspose.Page pour .NET ?

 A2 : Vous pouvez télécharger la bibliothèque à partir du[Aspose.Page pour la page de téléchargement .NET](https://releases.aspose.com/page/net/).

### Q3 : Où puis-je acheter Aspose.Page pour .NET ?

 A3 : Vous pouvez acheter Aspose.Page pour .NET à partir du[page d'achat](https://purchase.aspose.com/buy).

### Q4 : Existe-t-il un essai gratuit ?

 A4 : Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/).

### Q5 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A5 : Vous pouvez obtenir une licence temporaire auprès de[ce lien](https://purchase.aspose.com/temporary-license/).