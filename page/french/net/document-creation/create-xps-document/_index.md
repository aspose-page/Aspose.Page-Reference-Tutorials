---
date: 2026-01-12
description: Apprenez à créer un document XPS avec Aspose.Page pour .NET – un guide
  étape par étape pour générer des documents électroniques de haute qualité.
linktitle: Create XPS Document
second_title: Aspose.Page .NET API
title: Créer un document XPS avec Aspose.Page pour .NET
url: /fr/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS avec Aspose.Page pour .NET

## Introduction

Bienvenue dans notre guide étape par étape sur **comment créer un document XPS** en utilisant Aspose.Page pour .NET. Dans ce tutoriel, nous explorerons le processus de génération de fichiers XPS, un format largement utilisé pour les documents électroniques. Que vous soyez un développeur chevronné ou que vous débutiez avec Aspose.Page, ce guide est conçu pour vous aider à créer des documents XPS de manière fluide avec des exemples clairs et des explications détaillées.

## Quick Answers
- **Quelle bibliothèque faut‑il ?** Aspose.Page for .NET  
- **Puis‑je l’exécuter sur .NET Core ?** Yes, the library fully supports .NET Core and .NET 5/6  
- **Combien de lignes de code ?** Less than 20 lines to produce a basic XPS file  
- **Ai‑je besoin d’une licence pour les tests ?** A free trial is available; a license is required for production  
- **Quel format a la sortie ?** XPS (XML Paper Specification)  

## How to create XPS document using Aspose.Page for .NET

Vous trouverez ci‑dessous tout ce dont vous avez besoin avant de commencer à coder, suivi d’un guide concis, numéroté.

## Prerequisites

Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants en place :

1. **Bibliothèque Aspose.Page pour .NET :** Téléchargez et installez la bibliothèque Aspose.Page depuis le [lien de téléchargement](https://releases.aspose.com/page/net/).

2. **Votre répertoire de documents :** Choisissez ou créez un répertoire sur votre système où vous souhaitez enregistrer les fichiers XPS de sortie.

Passons maintenant au tutoriel !

## Import Namespaces

Afin d’utiliser Aspose.Page pour .NET, vous devez importer les espaces de noms nécessaires dans votre projet. Suivez ces étapes :

### Step 1: Add Reference to Aspose.Page

Dans votre projet, ajoutez une référence à la bibliothèque Aspose.Page for .NET. Vous pouvez trouver le DLL requis dans le package téléchargé.

### Step 2: Import Namespaces

Include the following namespaces in your code file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Maintenant que nous avons configuré les prérequis et importé les espaces de noms nécessaires, décomposons le processus de création d’un document XPS en plusieurs étapes.

## Step 1: Set Document Directory

```csharp
string dir = "Your Document Directory";
```

Assurez‑vous de remplacer `"Your Document Directory"` par le chemin réel où vous souhaitez enregistrer le fichier XPS de sortie.

## Step 2: Create XPS Document

```csharp
XpsDocument xDocs = new XpsDocument();
```

Initialisez un nouveau document XPS en utilisant la classe `XpsDocument`.

## Step 3: Add Glyphs to the Document

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Utilisez la méthode `AddGlyphs` pour ajouter des glyphes (texte) au document. Personnalisez la police, la taille, le style et la position selon vos besoins.

## Step 4: Set Glyph Fill Color

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

Spécifiez la couleur de remplissage pour les glyphes ajoutés. Dans cet exemple, nous utilisons le noir, mais vous pouvez choisir n’importe quelle couleur.

## Step 5: Save the Result

```csharp
xDocs.Save(dir + "output.xps");
```

Enfin, enregistrez le document XPS dans le répertoire spécifié avec le nom de fichier souhaité. Le fichier XPS résultant contiendra le texte « Hello World! ».

Félicitations ! Vous avez créé avec succès un document XPS en utilisant Aspose.Page for .NET.

## Common Tips & Gotchas

- **Chemin du répertoire** – Utilisez `Path.Combine(dir, "output.xps")` pour éviter les séparateurs de chemin manquants sur différents systèmes d’exploitation.  
- **Disponibilité de la police** – La police que vous spécifiez doit être installée sur la machine où le code s’exécute ; sinon, Aspose remplacera par une police par défaut.  
- **Pages multiples** – Pour créer des fichiers XPS multi‑pages, instanciez des objets `XpsPage` supplémentaires et ajoutez du contenu à chaque page avant d’enregistrer.

## Conclusion

Dans ce tutoriel, nous avons parcouru le processus de création de documents XPS en utilisant Aspose.Page pour .NET. Cette bibliothèque puissante offre un moyen fluide de générer des documents électroniques avec facilité. Expérimentez avec différentes polices, styles et contenus pour adapter vos fichiers XPS à vos besoins spécifiques.

## FAQ's

### Q1: Puis‑je utiliser des polices personnalisées dans mon document XPS ?

R1 : Oui, vous pouvez spécifier la famille de police et la taille lors de l’ajout de glyphes à votre document XPS.

### Q2: Aspose.Page est‑il compatible avec .NET Core ?

R2 : Oui, Aspose.Page prend en charge .NET Core, vous permettant de l’utiliser dans des applications multiplateformes.

### Q3: Comment ajouter des images à un document XPS ?

R3 : Aspose.Page fournit des méthodes pour ajouter des images à votre document XPS. Consultez la documentation pour des exemples détaillés.

### Q4: Puis‑je créer des documents XPS multi‑pages ?

R4 : Absolument ! Vous pouvez ajouter plusieurs pages à un document XPS en utilisant la bibliothèque Aspose.Page.

### Q5: Une version d’essai est‑elle disponible ?

R5 : Oui, vous pouvez explorer les fonctionnalités d’Aspose.Page en téléchargeant l’[essai gratuit](https://releases.aspose.com/).

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}