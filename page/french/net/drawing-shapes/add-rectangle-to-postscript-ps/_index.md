---
date: 2026-01-18
description: Apprenez à créer un document PostScript .NET et à ajouter des rectangles
  en utilisant Aspose.Page pour .NET. Guide étape par étape avec des exemples de code.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Créer un document PostScript .NET – Ajouter un rectangle avec Aspose.Page
url: /fr/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un rectangle à PostScript (PS) avec Aspose.Page pour .NET

## Introduction

Si vous cherchez à **créer un document PostScript .NET**, Aspose.Page offre une solution puissante pour gérer les fichiers PostScript. Dans ce tutoriel, nous vous guiderons pour ajouter des rectangles à un document PostScript en utilisant Aspose.Page pour .NET, vous offrant une base solide pour la génération de graphiques plus riches.

## Quick Answers
- **Quelle bibliothèque faut‑il ?** Aspose.Page pour .NET.
- **Puis‑je créer un document PostScript à partir de zéro ?** Oui – l’API vous permet de générer des fichiers PS programmatiquement.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.
- **Combien de temps prend l’implémentation ?** Généralement moins de 10 minutes pour des formes de base.

## What is creating a postscript document .net?
Créer un document PostScript en .NET signifie générer programmatiquement un fichier .ps qui décrit le contenu d’une page — texte, graphiques ou formes — en utilisant l’API Aspose.Page. Cette approche est idéale pour la génération de graphiques côté serveur, la création de rapports automatisés, ou tout scénario nécessitant un contrôle précis du format de sortie.

## Why use Aspose.Page for .NET?
- **Contrôle complet sur les graphiques** – dessinez des formes, définissez des couleurs et appliquez des traits sans gérer la syntaxe PS de bas niveau.
- **Cross‑platform** – fonctionne sur les environnements Windows, Linux et macOS.
- **Aucune dépendance externe** – la bibliothèque gère toute la génération PS en interne.
- **Documentation riche & exemples** – démarrez rapidement.

## Prerequisites

- **Bibliothèque Aspose.Page pour .NET** – téléchargez et installez depuis [here](https://releases.aspose.com/page/net/).
- **Environnement de développement** – Visual Studio, VS Code, ou tout IDE compatible .NET.

## Import Namespaces

Avant de commencer à coder, importez les espaces de noms qui exposent les classes requises :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Passons maintenant à la décomposition de l’exemple en étapes claires et numérotées.

## Step 1: Set up Your Document Directory

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le dossier où vous souhaitez enregistrer le fichier PS résultant.

## Step 2: Create Output Stream for the PostScript Document

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ce flux pointe vers **AddRectangle_outPS.ps**. N’hésitez pas à renommer le fichier ou à modifier l’emplacement selon vos besoins.

## Step 3: Set Save Options and Create the PS Document

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ici nous indiquons à Aspose.Page d’utiliser le format de page A4 et de créer un document d’une seule page.

## Step 4: Add a Filled Rectangle

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Nous définissons un rectangle à (250, 100) avec une largeur de 150 et une hauteur de 100, définissons un pinceau orange, et remplissons la forme.

## Step 5: Add an Outlined Rectangle

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Un second rectangle est créé plus bas sur la page, cette fois avec un trait rouge de 3 points.

## Step 6: Close the Page and Save the Document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

La fermeture de la page finalise le dessin, et `Save()` écrit le fichier PS sur le disque.

## Common Issues & Tips

- **Chemin de fichier incorrect** – assurez‑vous que `dataDir` se termine par un séparateur de chemin (`\\` ou `/`) ou utilisez `Path.Combine`.
- **Licence manquante** – dans un environnement de production, appliquez votre licence Aspose avant de créer le document afin d’éviter les filigranes d’évaluation.
- **Visibilité des couleurs** – si le rectangle apparaît vide, vérifiez que les couleurs du pinceau ou du stylo contrastent avec le fond de la page.

## Frequently Asked Questions

**Q :** Puis‑je personnaliser les couleurs des rectangles ?  
**R :** Absolument. Modifiez les valeurs `Color.Orange` ou `Color.Red` dans les constructeurs `SolidBrush` et `Pen` avec n’importe quel `System.Drawing.Color` de votre choix.

**Q :** Aspose.Page est‑il compatible avec d’autres formats de documents ?  
**R :** Oui. En plus de PostScript, Aspose.Page prend également en charge la génération XPS et EPS.

**Q :** Comment ajouter du texte au même document ?  
**R :** Utilisez la classe `TextFragment` pour placer du texte aux coordonnées souhaitées, puis appelez `document.Draw(textFragment)`.

**Q :** Où puis‑je trouver des exemples supplémentaires et la référence complète de l’API ?  
**R :** Explorez la documentation [here](https://reference.aspose.com/page/net/) et rejoignez la communauté sur le [forum Aspose.Page](https://forum.aspose.com/c/page/39).

**Q :** Puis‑je essayer Aspose.Page avant d’acheter ?  
**R :** Oui, téléchargez un essai gratuit [here](https://releases.aspose.com/). Pour une évaluation prolongée, envisagez une [licence temporaire](https://purchase.aspose.com/temporary-license/).

---

**Dernière mise à jour** : 2026-01-18  
**Testé avec** : Aspose.Page 24.12 for .NET  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}