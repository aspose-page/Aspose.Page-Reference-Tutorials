---
date: 2026-02-25
description: Apprenez à créer un dégradé XPS avec un remplissage horizontal en utilisant
  Aspose.Page pour .NET. Rehaussez l’attrait visuel de vos documents sans effort.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Créer un dégradé XPS : remplissage horizontal avec Aspose.Page pour .NET'
url: /fr/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un dégradé XPS – Ajouter un dégradé horizontal à XPS avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel, vous allez **créer des remplissages en dégradé XPS** qui s’étendent horizontalement sur vos pages. Ajouter un dégradé horizontal peut immédiatement donner à un document XPS un aspect plus soigné et attrayant, notamment pour les rapports, les brochures ou tout rendu visuel riche. Nous parcourrons l’ensemble du processus avec Aspose.Page pour .NET, depuis la configuration de l’environnement jusqu’à l’enregistrement du fichier XPS final.

## Quick Answers
- **Que couvre ce tutoriel ?** Ajouter un dégradé horizontal à un document XPS avec Aspose.Page pour .NET.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET (toute version récente).  
- **Ai‑je besoin d’une licence ?** Une version d’essai suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Combien de temps prend l’implémentation ?** Environ 5–10 minutes pour un dégradé de base.  
- **Puis‑je changer la direction du dégradé ?** Oui – modifiez les points de départ/arrivée du `LinearGradientBrush`.

## How to create XPS gradient with Aspose.Page for .NET

Vous trouverez ci‑dessous un guide étape par étape qui explique **pourquoi** chaque ligne de code existe, et pas seulement **ce que** fait chaque ligne. N’hésitez pas à suivre dans Visual Studio ou votre éditeur .NET préféré.

## Prerequisites

Avant de commencer, assurez‑vous d’avoir les prérequis suivants :

1. Bibliothèque Aspose.Page pour .NET : Vérifiez que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez la télécharger depuis la [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. Environnement de développement : Configurez un environnement de développement adapté, incluant un éditeur de code comme Visual Studio.

## Import Namespaces

Commencez par importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms sont essentiels pour travailler avec Aspose.Page pour .NET :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Now, let's break down the provided example into multiple steps.

## Step 1: Set the Document Directory Path

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Initialize Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Step 4: Create a New Path

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Vous avez maintenant ajouté avec succès un dégradé horizontal à votre document XPS en utilisant Aspose.Page pour .NET.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| Le dégradé apparaît comme une couleur unie | Les arrêts du dégradé n’ont pas été ajoutés correctement | Assurez‑vous que `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` est exécuté après la définition du pinceau. |
| Le fichier enregistré est vide | `dataDir` pointe vers un dossier inexistant | Vérifiez que le dossier existe ou utilisez un chemin absolu. |
| Erreur de compilation sur `PointF` | Référence `System.Drawing` manquante | Ajoutez une référence à `System.Drawing.Common` (pour .NET Core/5+). |

## FAQ's

### Q1 : Où puis‑je trouver la documentation Aspose.Page pour .NET ?

A1 : Vous pouvez consulter la documentation [ici](https://reference.aspose.com/page/net/).

### Q2 : Comment télécharger Aspose.Page pour .NET ?

A2 : Vous pouvez télécharger la bibliothèque depuis la [page de téléchargement Aspose.Page pour .NET](https://releases.aspose.com/page/net/).

### Q3 : Où puis‑je acheter Aspose.Page pour .NET ?

A3 : Vous pouvez acheter Aspose.Page pour .NET sur la [page d’achat](https://purchase.aspose.com/buy).

### Q4 : Existe‑t‑il un essai gratuit ?

A4 : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

### Q5 : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?

A5 : Vous pouvez obtenir une licence temporaire via [ce lien](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q : Puis‑je utiliser cette technique de dégradé avec des documents XPS contenant déjà des images ?**  
R : Absolument. Le dégradé est appliqué à un calque de chemin, les images existantes restent intactes.

**Q : Est‑il possible de créer un dégradé vertical à la place ?**  
R : Oui. Modifiez les points de départ et d’arrivée du `LinearGradientBrush` pour avoir des coordonnées Y différentes tout en conservant X constant.

**Q : Aspose.Page prend‑il en charge .NET Core ?**  
R : La bibliothèque est entièrement compatible avec .NET Core, .NET 5 et les versions ultérieures.

**Q : Comment réutiliser le même dégradé sur plusieurs pages ?**  
R : Créez le `XpsLinearGradientBrush` une fois, stockez‑le dans une variable, puis assignez‑le aux chemins de chaque page.

## Conclusion

Enrichir vos documents XPS avec des dégradés améliore non seulement l’esthétique visuelle mais offre également une expérience utilisateur plus engageante. Avec Aspose.Page pour .NET, vous pouvez **créer des remplissages en dégradé XPS** rapidement et de manière fiable, donnant à vos rapports, brochures ou e‑books une finition professionnelle.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-02-25  
**Testé avec :** Aspose.Page pour .NET 24.11  
**Auteur :** Aspose  

---