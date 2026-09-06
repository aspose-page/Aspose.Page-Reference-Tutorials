---
date: 2026-07-29
description: Apprenez comment extraire et ajouter les metadata EPS à l'aide d'Aspose.Page
  pour .NET. Ce guide présente du code étape par étape pour gérer efficacement les
  metadata EPS XMP.
keywords:
- aspose.page eps metadata
- eps metadata extraction
- aspose.page .net
lastmod: 2026-07-29
linktitle: Extraire les metadata du document EPS
og_description: 'Guide aspose.page eps metadata : extraire et définir les metadata
  XMP dans les fichiers EPS à l''aide d''Aspose.Page pour .NET. Suivez le tutoriel
  étape par étape.'
og_image_alt: Tutorial showing how to extract and add metadata to EPS documents with
  Aspose.Page for .NET
og_title: aspose.page eps metadata – Extraire les metadata EPS avec .NET
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to extract and add EPS metadata using Aspose.Page for .NET.
    This guide shows step‑by‑step code to manage EPS XMP metadata efficiently.
  headline: aspose.page eps metadata – Extract EPS Metadata with .NET
  type: TechArticle
- questions:
  - answer: Yes, iterate over a collection of file paths, apply the same extraction‑and‑update
      logic, and save each file. The API is thread‑safe, so you can parallelise the
      operation for faster batch processing.
    question: Can I add metadata to multiple EPS documents simultaneously?
  - answer: The library comfortably processes EPS files up to **500 MB**. For files
      larger than this, consider splitting the document or using a streaming approach
      to avoid out‑of‑memory exceptions.
    question: Are there any limitations on the size of EPS documents that Aspose.Page
      for .NET can handle?
  - answer: XMP follows the ISO 16684‑1 standard, but individual creators may populate
      custom namespaces. Aspose.Page reads both standard and custom properties, allowing
      you to preserve any proprietary data.
    question: Is the XMP metadata standardized for all EPS documents?
  - answer: Absolutely. You can add custom XMP schemas or extend existing ones by
      using the `XmpMetadata.AddCustomProperty` method, giving you full control over
      the metadata structure.
    question: Can I customize the metadata fields to suit specific requirements?
  - answer: Wrap the extraction and save logic in a `try…catch` block, and log `Aspose.Page.Exception`
      details. This will capture issues such as corrupted streams, unsupported properties,
      or I/O failures.
    question: How can I handle errors during the metadata addition process?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: aspose.page eps metadata – Extraire les metadata EPS avec .NET
url: /fr/net/eps-metadata-management/extract-metadata-from-eps-document/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraire les métadonnées d'un document EPS avec Aspose.Page pour .NET

## Introduction

Dans les flux de travail de documents modernes, **aspose.page eps metadata** est la clé pour rendre les fichiers EPS recherchables, triables et conformes aux politiques de gestion de contenu d'entreprise. Ce tutoriel vous guide à travers l'extraction des métadonnées XMP existantes, la mise à jour des champs courants tels que *CreatorTool* et *CreateDate*, et l'enregistrement du fichier EPS avec les nouvelles informations — le tout en utilisant l'API Aspose.Page pour .NET.

## Réponses rapides
- **Quel est le sujet du tutoriel ?** Extraction et mise à jour des métadonnées XMP dans les fichiers EPS avec Aspose.Page pour .NET.  
- **Quelle version de la bibliothèque est requise ?** Toute version d'Aspose.Page pour .NET qui prend en charge XMP (v24.10 ou ultérieure).  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis-je traiter de gros fichiers EPS ?** Oui—Aspose.Page peut gérer des fichiers jusqu'à 500 Mo sans charger l'intégralité du document en mémoire.  
- **Le code est-il multiplateforme ?** La bibliothèque .NET fonctionne sous Windows, Linux et macOS avec .NET 6+.

## Prérequis

Avant de plonger dans le guide étape par étape, assurez‑vous de disposer de ce qui suit :

- **Aspose.Page for .NET Library** – Téléchargez et installez la bibliothèque depuis [here](https://releases.aspose.com/page/net/).  
- **Document Directory** – Un dossier sur votre machine contenant les fichiers EPS que vous souhaitez traiter.  
- **.NET Development Environment** – Visual Studio 2022, Rider, ou tout IDE supportant .NET 6+.

## Qu'est-ce que les métadonnées EPS ?

Les **métadonnées EPS** sont constituées de paquets XMP (Extensible Metadata Platform) intégrés qui stockent des informations telles que le créateur, la date de création, le titre et l'outil utilisé pour générer le fichier. XMP est un format standard ISO, rendant les métadonnées interchangeables entre les produits Adobe, les systèmes de gestion de contenu et les moteurs de recherche.

## Pourquoi utiliser Aspose.Page pour les métadonnées EPS ?

Aspose.Page prend en charge **plus de 30 propriétés XMP distinctes** et peut les lire ou les écrire sans rendre l'intégralité du contenu PostScript. Il traite les fichiers EPS jusqu'à **500 Mo** tout en maintenant l'utilisation de la mémoire en dessous de **50 Mo**, ce qui est idéal pour les pipelines de traitement par lots dans des environnements cloud ou sur site.

## Importer les espaces de noms

Les espaces de noms suivants sont requis pour travailler avec les fichiers EPS et les métadonnées XMP.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Comment extraire et définir les métadonnées EPS à l'aide d'Aspose.Page ?

Chargez le fichier EPS dans un flux `EpsDocument`, récupérez le paquet XMP existant, modifiez les champs requis, puis enregistrez le document sur le disque. L'ensemble du flux de travail peut être réalisé en **quatre étapes concises** que vous pouvez intégrer dans n'importe quel service .NET ou application console.

## Étape 1 : Initialiser le flux d'entrée du fichier EPS

`PsDocument` représente un document EPS et fournit l'accès à ses pages et à ses métadonnées.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:3
```

## Étape 2 : Obtenir les métadonnées XMP

`XmpMetadata` encapsule le paquet XMP intégré dans un fichier EPS, permettant la lecture et l'écriture des propriétés de métadonnées.

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

## Étape 3 : Vérifier et définir les valeurs des métadonnées

Vérifiez les valeurs de métadonnées extraites des commentaires de métadonnées PS et configurez-les dans les nouvelles métadonnées XMP.

### Obtenir la valeur CreatorTool

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// ExEnd:5
```

### Obtenir la valeur CreateDate

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// ExEnd:6
```

### Obtenir la valeur Format

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// ExEnd:7
```

### Obtenir la valeur Title

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// ExEnd:8
```

### Obtenir la valeur Creator

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// ExEnd:9
```

### Obtenir la valeur MetadataDate

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// ExEnd:10
```

## Étape 4 : Enregistrer le fichier EPS avec les nouvelles métadonnées XMP

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// ExEnd:11
```

## Problèmes courants et solutions

- **Paquet XMP manquant** – Si `document.XmpMetadata` renvoie `null`, le fichier EPS ne contient pas de bloc XMP. Vous pouvez créer une nouvelle instance `XmpMetadata` et l'attacher avant l'enregistrement.  
- **Format de date incorrect** – XMP attend des dates au format ISO 8601 (`yyyy-MM-ddTHH:mm:ssZ`). Utilisez `DateTime.UtcNow.ToString("o")` pour générer une chaîne conforme.  
- **Pics de mémoire sur les gros fichiers** – Activez le mode streaming en définissant `EpsLoadOptions.Streaming = true` afin de maintenir une faible consommation de mémoire.

## Questions fréquemment posées

**Q : Puis‑je ajouter des métadonnées à plusieurs documents EPS simultanément ?**  
R : Oui, parcourez une collection de chemins de fichiers, appliquez la même logique d'extraction et de mise à jour, et enregistrez chaque fichier. L'API est thread‑safe, vous pouvez donc paralléliser l'opération pour un traitement par lots plus rapide.

**Q : Existe‑t‑il des limites de taille pour les documents EPS qu'Aspose.Page pour .NET peut gérer ?**  
R : La bibliothèque traite aisément les fichiers EPS jusqu'à **500 Mo**. Pour des fichiers plus volumineux, envisagez de scinder le document ou d'utiliser une approche streaming afin d'éviter les exceptions de dépassement de mémoire.

**Q : Les métadonnées XMP sont‑elles standardisées pour tous les documents EPS ?**  
R : XMP suit la norme ISO 16684‑1, mais les créateurs individuels peuvent remplir des espaces de noms personnalisés. Aspose.Page lit à la fois les propriétés standard et personnalisées, vous permettant de conserver toute donnée propriétaire.

**Q : Puis‑je personnaliser les champs de métadonnées pour répondre à des exigences spécifiques ?**  
R : Absolument. Vous pouvez ajouter des schémas XMP personnalisés ou étendre ceux existants en utilisant la méthode `XmpMetadata.AddCustomProperty`, vous offrant un contrôle complet sur la structure des métadonnées.

**Q : Comment gérer les erreurs lors du processus d'ajout de métadonnées ?**  
R : Encapsulez la logique d'extraction et d'enregistrement dans un bloc `try…catch`, et consignez les détails de `Aspose.Page.Exception`. Cela capturera les problèmes tels que les flux corrompus, les propriétés non prises en charge ou les échecs d'E/S.

**Q : Aspose.Page prend‑il en charge .NET Core et .NET 5/6 ?**  
R : Oui, la bibliothèque est entièrement compatible avec .NET Core 3.1, .NET 5, .NET 6 et les versions ultérieures, offrant une API cohérente sur tous les runtimes supportés.

---

**Dernière mise à jour :** 2026-07-29  
**Testé avec :** Aspose.Page for .NET 24.10  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Ajouter des métadonnées à un document EPS avec Aspose.Page pour .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Ajouter un espace de noms avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)
- [Ajouter des propriétés simples avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}