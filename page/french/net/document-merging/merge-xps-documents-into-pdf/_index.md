---
date: 2026-01-20
description: Ajoutez facilement des numéros de page aux PDF tout en fusionnant des
  documents XPS en PDF de haute qualité avec Aspose.Page pour .NET. Suivez notre guide
  étape par étape pour convertir XPS en PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Ajouter des numéros de page PDF – Fusionner XPS en PDF avec Aspose.Page
url: /fr/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des numéros de page PDF – Fusionner XPS en PDF avec Aspose.Page

## Introduction

Si vous devez **ajouter des numéros de page PDF** lors de la fusion de fichiers XPS, Aspose.Page pour .NET rend le processus indolore. Dans ce tutoriel, nous parcourrons un exemple complet, prêt pour la production, qui convertit un document XPS en PDF de haute qualité, vous permet de contrôler la compression des images, et insère automatiquement les numéros de page dans le PDF final. À la fin, vous disposerez d’un extrait réutilisable que vous pourrez intégrer dans n’importe quel projet C#.

## Quick Answers
- **Puis-je ajouter des numéros de page lors de la fusion de XPS en PDF ?** Oui – la propriété `PdfSaveOptions.PageNumbers` fait exactement cela.  
- **Quelle bibliothèque gère la conversion ?** Aspose.Page pour .NET.  
- **Ai-je besoin d’une licence pour une utilisation en production ?** Une licence valide d’Aspose.Page est requise ; une licence temporaire est disponible pour les tests.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6+.  
- **Est‑il possible d’obtenir une sortie d’image de haute qualité ?** Absolument – définissez `JpegQualityLevel` à 100 et choisissez `PdfImageCompression.Jpeg`.

## Prerequisites

Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants en place :

- Aspose.Page pour .NET : Assurez‑vous d’avoir la bibliothèque Aspose.Page installée. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).

- Fichiers de document : Ayez le document XPS (`input.xps`) prêt dans le répertoire que vous avez spécifié.

## Import Namespaces

Dans votre projet .NET, incluez les espaces de noms nécessaires pour travailler avec Aspose.Page :

```csharp
using Aspose.Page.XPS;
```

Cette étape garantit que vous avez accès aux classes et méthodes requises pour la conversion du document.

## How to add page numbers PDF when merging XPS documents

Comment ajouter des numéros de page PDF lors de la fusion de documents XPS ?

La collection `PdfSaveOptions.PageNumbers` vous permet de spécifier exactement quelles pages (ou plages de pages) doivent apparaître dans le PDF de sortie. En la remplissant avec les numéros de page souhaités, Aspose.Page insère automatiquement la numérotation correcte.

### Step 1: Initialize Streams

Étape 1 : Initialiser les flux

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Cette étape consiste à configurer les flux d’entrée et de sortie pour les fichiers XPS et PDF. Assurez‑vous que les chemins et noms de fichiers sont corrects.

### Step 2: Load XPS Document

Étape 2 : Charger le document XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Ici, nous chargeons le document XPS dans l’objet `XpsDocument`, le préparant pour le traitement ultérieur.

### Step 3: Initialize Save Options (merge xps to pdf)

Étape 3 : Initialiser les options d’enregistrement (fusion XPS en PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Personnalisez l’objet `PdfSaveOptions` selon vos préférences, en spécifiant des paramètres tels que la compression d’image, la compression du texte, et les **numéros de page** que vous souhaitez voir apparaître dans le PDF final. Définir `JpegQualityLevel` à 100 garantit des **images PDF de haute qualité**.

### Step 4: Create Rendering Device

Étape 4 : Créer le dispositif de rendu

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` est l’outil responsable du rendu du document XPS au format PDF.

### Step 5: Save the Document (c# xps to pdf)

Étape 5 : Enregistrer le document (C# XPS en PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Enfin, enregistrez le document en utilisant le dispositif de rendu et les options spécifiées. Le PDF de sortie contiendra les pages sélectionnées avec les numéros de page ajoutés automatiquement.

## Why use Aspose.Page for this conversion?

Pourquoi utiliser Aspose.Page pour cette conversion ?

- **Fiabilité** – Gère les fonctionnalités complexes de XPS sans perte de fidélité.  
- **Performance** – Le traitement basé sur les flux évite de charger des fichiers entiers en mémoire.  
- **Flexibilité** – Contrôle granulaire sur la qualité d’image, la compression et la numérotation des pages.  
- **Cross‑platform** – Fonctionne sous Windows, Linux et macOS avec .NET Core.

## Common Issues and Solutions

Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **Le PDF de sortie est vide** | Vérifiez que le chemin du fichier XPS est correct et que le fichier n’est pas corrompu. |
| **Les numéros de page n’apparaissent pas** | Assurez‑vous que `PageNumbers` est défini avec les indices de page basés sur zéro corrects (par ex., `new int[] {1,2,6}`). |
| **Images de basse qualité** | Augmentez `JpegQualityLevel` et choisissez `PdfImageCompression.Jpeg`. |
| **Les gros fichiers XPS provoquent une pression mémoire** | Traitez le XPS par morceaux plus petits ou augmentez la limite de mémoire de l’application. |

## Frequently Asked Questions

### Q1: Can I merge multiple XPS files into a single PDF?

**Q1 :** Puis‑je fusionner plusieurs fichiers XPS en un seul PDF ?

**R1 :** Oui, vous pouvez. Ajustez simplement le paramètre `PageNumbers` dans `PdfSaveOptions` pour inclure les pages souhaitées provenant de différents fichiers XPS, ou chargez chaque XPS séquentiellement et appelez `document.Save` sur le même `PdfDevice`.

### Q2: Is a temporary license available for Aspose.Page for .NET?

**Q2 :** Une licence temporaire est‑elle disponible pour Aspose.Page pour .NET ?

**R2 :** Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/) à des fins de test.

### Q3: Are there any limitations on file size when using Aspose.Page for document conversion?

**Q3 :** Existe‑t‑il des limitations de taille de fichier lors de l’utilisation d’Aspose.Page pour la conversion de documents ?

**R3 :** Aspose.Page pour .NET n’impose pas de limitations strictes de taille de fichier, mais des performances optimales sont obtenues avec des fichiers de taille raisonnable. Pour des documents XPS très volumineux, envisagez de les traiter en flux afin de réduire la consommation de mémoire.

### Q4: Can I customize the output PDF further, such as adding watermarks or annotations?

**Q4 :** Puis‑je personnaliser davantage le PDF de sortie, par exemple en ajoutant des filigranes ou des annotations ?

**R4 :** Oui, Aspose.Page pour .NET offre de nombreuses fonctionnalités pour la manipulation de PDF. Après la conversion, vous pouvez utiliser la bibliothèque Aspose.PDF pour ajouter des filigranes, des annotations ou d’autres améliorations.

### Q5: Does Aspose.Page for .NET support cross‑platform development?

**Q5 :** Aspose.Page pour .NET prend‑il en charge le développement multiplateforme ?

**R5 :** Oui, Aspose.Page pour .NET est conçu pour fonctionner de manière transparente sur diverses plateformes, y compris Windows, Linux et macOS, lorsqu’il est utilisé avec .NET Core ou .NET 5/6.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}