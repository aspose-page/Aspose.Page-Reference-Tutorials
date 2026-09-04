---
date: 2026-06-30
description: Apprenez comment créer un document postscript .NET et ajouter des rectangles
  en utilisant Aspose.Page pour .NET. Guide étape par étape avec des exemples de code.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Ajouter un rectangle à PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Créer un document PostScript .NET – Ajouter un rectangle Aspose.Page
url: /fr/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un rectangle à PostScript (PS) avec Aspose.Page pour .NET

## Introduction

Aspose.Page pour .NET est une bibliothèque qui permet la création et la manipulation de fichiers PostScript, EPS et XPS de manière programmatique. Si vous cherchez à **create postscript document .net**, ce tutoriel vous guide pas à pas pour ajouter des rectangles à un document PostScript à l’aide d’Aspose.Page, vous offrant une base solide pour la génération de graphiques plus riches.

## Réponses rapides
- **Quelle bibliothèque me faut‑il ?** Aspose.Page pour .NET.  
- **Puis‑je créer un document PostScript à partir de zéro ?** Oui – l’API vous permet de créer des fichiers PS programmatique.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production.  
- **Combien de temps prend l’implémentation ?** Typiquement moins de 10 minutes pour des formes de base.

## Qu’est‑ce que la création d’un document postscript .net ?
Créer un document PostScript en .NET signifie générer de façon programmatique un fichier `.ps` qui décrit le contenu d’une page — texte, graphiques ou formes — en utilisant l’API Aspose.Page. Cette approche est idéale pour la génération de graphiques côté serveur, la création automatisée de rapports, ou tout scénario nécessitant un contrôle précis du format de sortie.

## Pourquoi utiliser Aspose.Page pour .NET ?
Aspose.Page prend en charge **plus de 30 primitives graphiques** et peut générer des fichiers jusqu’à **500 Mo** sans charger l’ensemble du document en mémoire, offrant un rendu haute performance sous Windows, Linux et macOS. Elle vous donne un contrôle total sur les formes, les couleurs et les traits tout en éliminant le besoin d’écrire du code PostScript de bas niveau.

- **Contrôle complet sur les graphiques** – dessinez des formes, définissez des couleurs et appliquez des traits sans gérer la syntaxe PS de bas niveau.  
- **Cross‑platform** – fonctionne sur les environnements Windows, Linux et macOS.  
- **Aucune dépendance externe** – la bibliothèque gère toute la génération PS en interne.  
- **Documentation riche & exemples** – démarrez rapidement.

## Prérequis

- **Bibliothèque Aspose.Page pour .NET** – téléchargez et installez depuis [here](https://releases.aspose.com/page/net/).  
- **Environnement de développement** – Visual Studio, VS Code ou tout IDE compatible .NET.

## Importer les espaces de noms

L’espace de noms `Aspose.Page` expose les classes principales dont vous aurez besoin, telles que `Document`, `Page`, `SolidBrush` et `Pen`. Importez‑le avant de commencer à coder.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Maintenant, décomposons l’exemple en étapes numérotées claires.

## Étape 1 : Configurer le répertoire de votre document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le dossier où vous souhaitez enregistrer le fichier PS résultant.

## Étape 2 : Créer le flux de sortie pour le document PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ce flux pointe vers **AddRectangle_outPS.ps**. N’hésitez pas à renommer le fichier ou à changer l’emplacement selon vos besoins.

## Étape 3 : Définir les options d’enregistrement et créer le document PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ici, nous indiquons à Aspose.Page d’utiliser le format de page A4 et de créer un document d’une seule page.

## Étape 4 : Ajouter un rectangle rempli

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Nous définissons un rectangle en (250, 100) avec une largeur de 150 et une hauteur de 100, appliquons un pinceau orange et remplissons la forme.

## Étape 5 : Ajouter un rectangle contouré

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

## Étape 6 : Fermer la page et enregistrer le document

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Fermer la page finalise le dessin, et `Save()` écrit le fichier PS sur le disque.

## Comment créer un document postscript .net ?
`Document` est la classe principale représentant un fichier PostScript dans Aspose.Page. `SaveOptions` spécifie des paramètres tels que la taille de page et le format de sortie du document. Chargez l’objet `Document`, configurez `SaveOptions` pour une page A4, dessinez vos formes avec `SolidBrush` ou `Pen`, puis appelez `document.Save()` — le flux de travail complet ne nécessite que quelques lignes de code et fonctionne sur tout runtime .NET pris en charge. Cette méthode vous permet de générer des fichiers PostScript entièrement conformes sans toucher à la syntaxe PS brute.

## Comment générer un fichier postscript
Utilisez la classe `SaveOptions` d’Aspose.Page pour spécifier le format de sortie en PostScript (`SaveFormat.PS`). La bibliothèque diffuse le contenu directement vers un fichier ou un flux mémoire, vous permettant de générer de gros documents efficacement sans consommation excessive de mémoire.

## Problèmes courants & conseils

- **Chemin de fichier incorrect** – assurez‑vous que `dataDir` se termine par un séparateur de chemin (`\\` ou `/`) ou utilisez `Path.Combine`.  
- **Licence manquante** – dans un environnement de production, appliquez votre licence Aspose avant de créer le document pour éviter les filigranes d’évaluation.  
- **Visibilité des couleurs** – si le rectangle apparaît vide, vérifiez que les couleurs du pinceau ou du stylo contrastent avec le fond de la page.

## Questions fréquemment posées

**Q :** Puis‑je personnaliser les couleurs des rectangles ?  
**R :** Absolument. Modifiez les valeurs `Color.Orange` ou `Color.Red` dans les constructeurs `SolidBrush` et `Pen` avec n’importe quelle `System.Drawing.Color` de votre choix.

**Q :** Aspose.Page est‑il compatible avec d’autres formats de documents ?  
**R :** Oui. En plus de PostScript, Aspose.Page prend également en charge la génération XPS et EPS.

**Q :** Comment ajouter du texte au même document ?  
**R :** Utilisez la classe `TextFragment` pour placer du texte aux coordonnées souhaitées, puis appelez `document.Draw(textFragment)`.

**Q :** Où puis‑je trouver des exemples supplémentaires et la référence complète de l’API ?  
**R :** Explorez la documentation [here](https://reference.aspose.com/page/net/) et rejoignez la communauté sur le [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q :** Puis‑je essayer Aspose.Page avant d’acheter ?  
**R :** Oui, téléchargez un essai gratuit [here](https://releases.aspose.com/). Pour une évaluation prolongée, envisagez une [licence temporaire](https://purchase.aspose.com/temporary-license/).

**Dernière mise à jour :** 2026-06-30  
**Testé avec :** Aspose.Page 24.12 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment créer un document PostScript avec Aspose.Page pour .NET](/page/net/document-creation/create-postscript-document/)
- [Ajouter une image à un document PostScript (PS) avec Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Ajouter du texte à un document PostScript (PS) avec Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}