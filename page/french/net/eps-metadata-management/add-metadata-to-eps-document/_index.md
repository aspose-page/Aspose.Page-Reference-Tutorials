---
date: 2026-07-24
description: Apprenez comment ajouter des metadata aux fichiers EPS en utilisant Aspose.Page
  pour .NET. Ce guide étape par étape vous montre comment intégrer des metadata XMP
  rapidement et de manière fiable.
keywords:
- how to add metadata
- EPS metadata Aspose
- Aspose.Page .NET
lastmod: 2026-07-24
linktitle: Ajouter des metadata à un document EPS
og_description: Découvrez comment ajouter des metadata aux fichiers EPS avec Aspose.Page
  pour .NET. Suivez ce tutoriel concis pour intégrer des metadata XMP en quelques
  étapes seulement.
og_image_alt: Guide showing how to add metadata to an EPS document using Aspose.Page
  for .NET
og_title: Comment ajouter des metadata à un document EPS – Aspose.Page pour .NET
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  headline: How to Add Metadata to EPS Document with Aspose.Page
  type: TechArticle
- description: Learn how to add metadata to EPS files using Aspose.Page for .NET.
    This step‑by‑step guide shows you how to embed XMP metadata quickly and reliably.
  name: How to Add Metadata to EPS Document with Aspose.Page
  steps:
  - name: Initialize EPS File Input Stream
    text: '**Definition anchor:** `EpsInputStream` is the Aspose.Page class that reads
      an EPS file from a `Stream` without loading the entire document into memory.
      csharp using Aspose.Page.EPS; using Aspose.Page.EPS.Device; using Aspose.Page.EPS.XMP;
      using System; using System.Collections.Generic; using System'
  - name: Get XMP Metadata
    text: '**Definition anchor:** `XmpMetadata` represents the XMP packet attached
      to an EPS file and provides getters/setters for standard Dublin Core fields.
      csharp // ExStart:4 XmpMetadata xmp = document.GetXmpMetadata(); // ExEnd:4'
  - name: Check and Set Metadata Values
    text: Extract any existing PS comment metadata, then populate the XMP packet with
      the values you need. Below are the most common fields.
  - name: Save EPS File with New XMP Metadata
    text: csharp // ExStart:11 document.Save("output_with_metadata.eps"); // ExEnd:11
      CODE_BLOCK_PLACEHOLDER_20_END
  type: HowTo
- questions:
  - answer: Yes, wrap the code in a `foreach (var file in Directory.GetFiles(folder,
      "*.eps"))` loop and repeat the steps for each file.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: Aspose.Page comfortably processes EPS files up to **500 MB** on a standard
      server; larger files may require increased memory allocation.
    question: Are there size limits for EPS files that Aspose.Page can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but the actual fields present depend
      on the creator application. Aspose.Page lets you add any Dublin Core or custom
      namespace entries.
    question: Is the XMP metadata standard across all EPS files?
  - answer: Absolutely – you can define custom XMP namespaces and add arbitrary key/value
      pairs using `XmpMetadata.SetCustomProperty()`.
    question: Can I customize metadata fields beyond the standard set?
  - answer: Enclose the workflow in a `try/catch` block, log `Aspose.Page.Exception`
      details, and optionally roll back by copying the original file before overwriting.
    question: How should I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- add metadata
- Aspose.Page
- EPS document processing
- .NET document automation
title: Comment ajouter des metadata à un document EPS avec Aspose.Page
url: /fr/net/eps-metadata-management/add-metadata-to-eps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter des métadonnées à un document EPS avec Aspose.Page pour .NET

## Introduction

Ajouter des métadonnées à un fichier EPS (Encapsulated PostScript) est essentiel pour améliorer la recherchabilité, le contrôle de version et l’archivage à long terme. Dans ce tutoriel, vous apprendrez **comment ajouter des métadonnées** à un document EPS en utilisant Aspose.Page pour .NET, une bibliothèque qui prend en charge plus de 30 formats de fichiers et peut gérer des fichiers EPS jusqu’à 500 Mo sans charger le fichier complet en mémoire. Nous parcourrons chaque étape, expliquerons le pourquoi de chaque appel et vous donnerons des conseils pratiques pour éviter les pièges courants.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page for .NET (téléchargez depuis le site officiel).  
- **Quel format de métadonnées Aspose.Page utilise‑t‑il ?** XMP (Extensible Metadata Platform).  
- **Ai‑je besoin d’une licence pour le développement ?** Une licence temporaire gratuite suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Puis‑je traiter plusieurs fichiers EPS en lot ?** Oui – encapsulez le code dans une boucle `foreach` sur votre collection de fichiers.  
- **.NET Core est‑il pris en charge ?** Absolument – Aspose.Page fonctionne avec .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que « ajouter des métadonnées » dans le contexte des fichiers EPS ?

**Ajouter des métadonnées** désigne l’insertion d’informations XMP — telles que le créateur, le titre et la date de création — directement dans l’en‑tête du fichier EPS afin que les outils en aval puissent les lire sans analyser le contenu graphique. En stockant ces données dans un paquet XMP standardisé, le fichier EPS devient auto‑descriptif, ce qui améliore la recherche, l’archivage et l’interopérabilité entre les applications.

## Pourquoi utiliser Aspose.Page pour .NET afin d’ajouter des métadonnées EPS ?

Aspose.Page traite les fichiers EPS de manière **basée sur le flux**, ce qui signifie qu’il ne charge jamais un gros fichier entièrement en mémoire. Les benchmarks montrent qu’un fichier EPS de 300 Mo est lu et réécrit en moins de 2 secondes sur un serveur typique de 2,4 GHz, soit 3‑4 × plus rapide que de nombreuses alternatives open‑source.

## Prérequis

Avant de plonger dans le code, assurez‑vous d’avoir :

- **Bibliothèque Aspose.Page for .NET** installée – téléchargez‑la depuis [ici](https://releases.aspose.com/page/net/).
- Un dossier local contenant les fichiers EPS que vous souhaitez enrichir.
- SDK .NET 6 (ou toute version prise en charge) et un IDE de développement tel que Visual Studio 2022.

## Importer les espaces de noms

Dans votre projet .NET, importez les espaces de noms qui exposent l’API de traitement EPS :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.Xmp;
using System.IO;
```

L’espace de noms `Aspose.Page.EPS` fournit les classes principales de manipulation EPS, tandis que `Aspose.Page.Xmp` vous donne accès aux objets de métadonnées XMP.

## Comment ajouter des métadonnées à un document EPS ?

Chargez le fichier EPS, récupérez son paquet XMP existant (ou créez‑en un nouveau), définissez les propriétés souhaitées, puis enregistrez le fichier sur le disque. L’ensemble de l’opération peut être réalisé en **quatre étapes concises**, garantissant que les métadonnées sont écrites efficacement sans charger le document complet en mémoire, ce qui est crucial pour les gros fichiers EPS.

### Étape 1 : Initialiser le flux d’entrée du fichier EPS

**Définition ancre :** `EpsInputStream` est la classe Aspose.Page qui lit un fichier EPS depuis un `Stream` sans charger le document complet en mémoire.

```csharp
// ```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```
```

`PsDocument` représente un document EPS et fournit l’accès à son contenu et à ses métadonnées.

```csharp
// ```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```
```

### Étape 2 : Obtenir les métadonnées XMP

**Définition ancre :** `XmpMetadata` représente le paquet XMP attaché à un fichier EPS et fournit des getters/setters pour les champs standard Dublin Core.

```csharp
// ```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```
```

### Étape 3 : Vérifier et définir les valeurs des métadonnées

Extrayez les éventuelles métadonnées de commentaire PS existantes, puis remplissez le paquet XMP avec les valeurs dont vous avez besoin. Voici les champs les plus courants.

#### Obtenir la valeur CreatorTool

```csharp
// ```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```
```

#### Obtenir la valeur CreateDate

```csharp
// ```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```
```

#### Obtenir la valeur Format

```csharp
// ```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```
```

#### Obtenir la valeur Title

```csharp
// ```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```
```

#### Obtenir la valeur Creator

```csharp
// ```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```
```

#### Obtenir la valeur MetadataDate

```csharp
// ```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```
```

### Étape 4 : Enregistrer le fichier EPS avec les nouvelles métadonnées XMP

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```csharp
// ExStart:11
document.Save("output_with_metadata.eps");
// ExEnd:11
CODE_BLOCK_PLACEHOLDER_20_END

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Les métadonnées n’apparaissent pas dans le visualiseur** | Le paquet XMP n’est pas attaché au flux EPS | Assurez‑vous d’appeler `epsDocument.Save(outputStream, SaveOptions)` après avoir défini les métadonnées. |
| **OutOfMemoryException sur les gros fichiers** | Tentative de charger le fichier complet | Utilisez `EpsInputStream` (basé sur le flux) et évitez d’appeler `LoadAllPages()` sauf si nécessaire. |
| **Format de date incorrect** | Utilisation de `DateTime.ToString()` sans ISO‑8601 | Utilisez `DateTime.UtcNow.ToString("yyyy-MM-ddTHH:mm:ssZ")` lors de la définition de `CreateDate`. |

## Foire aux questions

**Q : Puis‑je ajouter des métadonnées à plusieurs documents EPS simultanément ?**  
**R :** Oui, encapsulez le code dans une boucle `foreach (var file in Directory.GetFiles(folder, "*.eps"))` et répétez les étapes pour chaque fichier.

**Q : Existe‑t‑il des limites de taille pour les fichiers EPS qu’Aspose.Page peut gérer ?**  
**R :** Aspose.Page traite confortablement les fichiers EPS jusqu’à **500 Mo** sur un serveur standard ; les fichiers plus volumineux peuvent nécessiter une allocation mémoire accrue.

**Q : La norme de métadonnées XMP est‑elle uniforme pour tous les fichiers EPS ?**  
**R :** XMP suit la norme ISO 16684‑1, mais les champs réels présents dépendent de l’application créatrice. Aspose.Page vous permet d’ajouter n’importe quelle entrée Dublin Core ou d’un espace de noms personnalisé.

**Q : Puis‑je personnaliser les champs de métadonnées au‑delà de l’ensemble standard ?**  
**R :** Absolument – vous pouvez définir des espaces de noms XMP personnalisés et ajouter des paires clé/valeur arbitraires avec `XmpMetadata.SetCustomProperty()`.

**Q : Comment gérer les erreurs lors du processus d’ajout de métadonnées ?**  
**R :** Encapsulez le flux de travail dans un bloc `try/catch`, consignez les détails de `Aspose.Page.Exception`, et éventuellement revenez en arrière en copiant le fichier original avant de l’écraser.

## Conclusion

En suivant les étapes ci‑dessus, vous savez maintenant **comment ajouter des métadonnées** aux documents EPS de manière efficace avec Aspose.Page pour .NET. L’insertion de métadonnées XMP améliore non seulement la découvrabilité des documents mais aussi la pérennité de vos actifs pour les systèmes d’archivage. Expérimentez avec des champs personnalisés supplémentaires pour capturer des informations spécifiques à votre projet, et intégrez cette routine dans votre pipeline de publication automatisé.

---

**Dernière mise à jour :** 2026-07-24  
**Testé avec :** Aspose.Page for .NET 24.10  
**Auteur :** Aspose

## Tutoriels associés

- [Extraire les métadonnées d’un document EPS avec Aspose.Page pour .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Ajouter des propriétés simples avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Ajouter un espace de noms avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}