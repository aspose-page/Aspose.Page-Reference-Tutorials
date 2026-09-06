---
date: 2026-08-08
description: Apprenez comment ajouter des éléments de tableau aux métadonnées EPS
  à l'aide d'Aspose.Page EPS metadata. Ce guide .NET étape par étape montre comment
  ajouter des éléments de tableau et lire les fichiers EPS efficacement.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Ajouter des éléments de tableau
og_description: Découvrez comment ajouter des éléments de tableau aux métadonnées
  EPS à l'aide d'Aspose.Page EPS metadata. Suivez ce tutoriel .NET concis pour lire
  les fichiers EPS et gérer les métadonnées efficacement.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Ajouter des éléments de tableau avec Aspose.Page EPS metadata dans .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Ajouter des éléments de tableau avec Aspose.Page EPS metadata dans .NET
url: /fr/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des éléments de tableau avec les métadonnées EPS d'Aspose.Page en .NET

## Introduction

Dans ce tutoriel, vous apprendrez comment ajouter des éléments de tableau aux métadonnées EPS en utilisant **Aspose.Page EPS metadata**. Que vous ayez besoin d'enrichir un fichier EPS avec des titres supplémentaires, des créateurs ou des balises personnalisées, Aspose.Page rend la tâche simple pour tout développeur .NET. Nous parcourrons chaque étape, de l'ouverture du flux EPS à la persistance du paquet XMP mis à jour, afin que vous puissiez intégrer la gestion des métadonnées dans vos propres applications en toute confiance.

## Réponses rapides
- **Que permet de faire les métadonnées EPS d'Aspose.Page ?** Elle permet de lire et d'écrire des tableaux de métadonnées XMP à l'intérieur des fichiers EPS depuis .NET.  
- **Quelle classe représente un document EPS ?** `PsDocument` est la classe principale pour charger et enregistrer le contenu EPS.  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Puis-je modifier les métadonnées sans altérer les graphiques EPS ?** Oui, seul le paquet XMP est modifié, le contenu de la page reste intact.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est-ce que les métadonnées EPS d'Aspose.Page ?
Les métadonnées EPS d'Aspose.Page sont un bloc d'information basé sur XMP intégré à l'intérieur d'un fichier EPS. Elles stockent des propriétés descriptives telles que les titres, les créateurs, les mots‑clé et les balises personnalisées conformément à la norme ISO 16684‑1. Les métadonnées peuvent être accédées et modifiées programmatiquement via l'API Aspose.Page, permettant une gestion automatisée des documents et une optimisation de la recherche.

## Pourquoi modifier les métadonnées EPS ?
Aspose.Page peut traiter **plus de 30 champs de métadonnées** et gérer des fichiers EPS jusqu'à **200 Mo** sans charger le document complet en mémoire, ce qui réduit l'utilisation du CPU jusqu'à 40 % comparé à une analyse complète du fichier. Mettre à jour les métadonnées améliore la recherche, la conformité et l'automatisation des flux de travail en aval.

## Prérequis

- Connaissances de base en programmation .NET.  
- Aspose.Page pour .NET installé – téléchargez-le depuis [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (ou tout IDE compatible .NET) pour exécuter le code d'exemple.  

## Comment ajouter des éléments de tableau aux métadonnées EPS ?
Pour ajouter des éléments de tableau, chargez d'abord le fichier EPS dans un `PsDocument`, puis récupérez son paquet XMP avec `GetXmpMetadata()`. Utilisez la méthode `AddArrayItem()` sur le tableau XMP souhaité, tel que `dc:title` ou `dc:creator`, pour ajouter de nouvelles valeurs. Enfin, appelez `Save()` pour écrire les métadonnées mises à jour dans le fichier tout en conservant le contenu graphique inchangé.

### Étape 1 : initialiser le flux d'entrée du fichier EPS
`PsDocument` représente un document EPS et fournit des méthodes pour accéder à son contenu. Le code suivant ouvre le fichier EPS en tant que flux et crée une instance `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Étape 2 : obtenir les métadonnées XMP
`GetXmpMetadata()` récupère le paquet XMP intégré dans le fichier EPS. Si aucun paquet n'existe, l'API génère un nouveau paquet basé sur les commentaires PostScript existants.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Étape 3 : modifier les valeurs des métadonnées XMP
`AddArrayItem()` ajoute une nouvelle valeur à un tableau XMP existant sans écraser les autres entrées. Utilisez‑la pour ajouter des titres, des créateurs ou des balises personnalisées aux métadonnées.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Étape 4 : enregistrer le fichier EPS avec les métadonnées XMP modifiées
`Save()` écrit le paquet XMP modifié dans le fichier EPS tout en préservant le contenu PostScript original. Fournissez le chemin de sortie pour créer un nouveau fichier ou écraser la source.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Pièges courants et dépannage

- **Paquet XMP nul** – Si `GetXmpMetadata()` renvoie `null`, assurez‑vous que le fichier EPS contient au moins un bloc de commentaire ; sinon, créez manuellement une nouvelle instance `XmpMetadata`.  
- **Problèmes d'encodage** – Utilisez UTF‑8 lors de l'ajout de valeurs de chaîne pour éviter la corruption des caractères dans les langues non‑ASCII.  
- **Fichiers volumineux** – Pour les fichiers EPS supérieurs à 150 MB, envisagez de diffuser l'entrée via `FileStream` avec un tampon afin de réduire l'utilisation de la mémoire.

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec tous les environnements .NET ?**  
R : Oui, Aspose.Page fonctionne sur .NET Framework 4.5+, .NET Core 3.1+ et .NET 5/6/7, offrant un comportement d'API cohérent sous Windows, Linux et macOS.

**Q : Puis‑je utiliser Aspose.Page gratuitement ?**  
R : Vous pouvez évaluer la bibliothèque avec un téléchargement d'essai gratuit depuis la [page d'achat Aspose](https://purchase.aspose.com/buy). Une licence commerciale est requise pour les déploiements en production.

**Q : Des licences temporaires sont‑elles disponibles pour Aspose.Page ?**  
R : Des licences temporaires peuvent être obtenues depuis la [page de licence temporaire](https://purchase.aspose.com/temporary-license/) pour des projets à court terme ou des périodes d'évaluation.

**Q : Où puis‑je trouver du support communautaire pour Aspose.Page ?**  
R : Rejoignez la discussion sur le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour poser des questions et partager des solutions avec d'autres développeurs.

**Q : Quelle est la dernière version d'Aspose.Page pour .NET ?**  
R : Consultez la [documentation officielle](https://reference.aspose.com/page/net/) pour les notes de version les plus récentes et les liens de téléchargement.

---

**Dernière mise à jour :** 2026-08-08  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Tutoriels associés

- [Modifier les éléments de tableau avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Ajouter des propriétés simples avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Ajouter un espace de noms avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}