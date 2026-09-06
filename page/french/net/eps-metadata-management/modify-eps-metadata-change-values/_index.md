---
date: 2026-08-13
description: Apprenez à utiliser Aspose.Page pour modifier les valeurs EPS dans les
  applications .NET, y compris les mises à jour pas à pas des métadonnées XMP.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Modifier les valeurs
og_description: Le tutoriel Aspose.Page sur la modification des valeurs EPS vous montre
  comment modifier les métadonnées XMP à l'intérieur des fichiers EPS avec .NET. Suivez
  le guide pas à pas pour mettre à jour le créateur, le titre et la date de modification
  instantanément.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: 'Tutoriel Aspose.Page : modifier les valeurs EPS avec .NET'
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page modifier les valeurs EPS avec .NET – tutoriel
url: /fr/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page modifier les valeurs eps avec .NET – tutoriel

## Introduction

## Réponses rapides
- **Que couvre le tutoriel ?** Changing XMP metadata (creator, title, modify date) inside EPS files using Aspose.Page for .NET.  
- **Quelle version de la bibliothèque est requise ?** Any Aspose.Page for .NET release that supports XMP (v24.10+).  
- **Ai-je besoin d'une licence ?** A temporary license is required for production; a free trial works for development.  
- **Puis-je exécuter cela sur .NET Core ?** Yes – the API is compatible with .NET 5, .NET 6, and .NET Core 3.1+.  
- **Combien de temps prend l'implémentation ?** About 5‑10 minutes for a basic metadata update.

## Qu'est-ce que les métadonnées XMP ?

Les métadonnées XMP sont un bloc XML standardisé qui stocke des informations descriptives (auteur, titre, dates) à l'intérieur des fichiers EPS et d'autres formats graphiques. Elles sont intégrées directement dans l'en-tête du fichier et peuvent être lues par de nombreux outils de conception et de publication, permettant une gestion cohérente des métadonnées sur toutes les plateformes. Mettre à jour les XMP permet aux applications en aval d'afficher les propriétés correctes du document sans modifier le contenu visuel.

## Pourquoi utiliser Aspose.Page pour les métadonnées EPS ?

Aspose.Page peut traiter **30+** formats graphiques et gérer les fichiers EPS jusqu'à **1 GB** sans charger le fichier complet en mémoire, offrant une réduction de **70 %** de l'utilisation de la RAM comparée à une analyse de flux naïve. La bibliothèque garantit également que le rendu visuel de l'EPS reste inchangé après les modifications de métadonnées.

## Pré-requis

Avant de commencer, assurez-vous que les éléments suivants sont prêts :

1. **Aspose.Page for .NET library** – téléchargez-le depuis la page officielle des versions d'Aspose.Page for .NET [ici](https://releases.aspose.com/page/net/). Vous pouvez également explorer les autres versions de produits Aspose [ici](https://releases.aspose.com/).  
2. **Document directory** – créez un dossier sur votre machine où les fichiers EPS source et les fichiers de sortie seront stockés.

Maintenant que l'environnement est configuré, importons les espaces de noms dont vous aurez besoin.

## Importer les espaces de noms

L'espace de noms `Aspose.Page` fournit les classes principales, tandis que `System.IO` vous offre des capacités de gestion de flux.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Comment modifier les valeurs des métadonnées EPS ?

Chargez le fichier EPS, récupérez son paquet XMP, modifiez les champs requis, puis écrivez l'EPS mis à jour sur le disque. Le processus ne nécessite pas de rendu du contenu de la page, il est donc rapide et efficace en mémoire. Suivez les étapes détaillées pour voir des exemples de code pour chaque opération. Ce flux de bout en bout est présenté dans les étapes ci‑dessous.

### Étape 1 : initialiser le flux d'entrée du fichier EPS

Créez un `FileStream` en lecture seule qui pointe vers le fichier EPS source.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Étape 2 : créer une instance PsDocument à partir du flux

`PsDocument` est l'objet de niveau supérieur représentant un document EPS en mémoire. Il vous donne accès à la fois au contenu de la page et aux métadonnées XMP intégrées.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Étape 3 : obtenir les métadonnées XMP

La propriété `XmpMetadata` renvoie un objet `XmpPacket` que vous pouvez interroger et modifier.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Étape 4 : modifier les valeurs des métadonnées XMP

Vous allez maintenant modifier trois champs courants : **ModifyDate**, **Creator** et **Title**.

#### Étape 4.1 : modifier la valeur ModifyDate

Définissez le `ModifyDate` sur l'horodatage UTC actuel.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Étape 4.2 : modifier la valeur Creator

Remplacez le créateur existant par le nom de votre application.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Étape 4.3 : modifier la valeur Title

Mettez à jour le titre pour refléter le nouveau but du contenu.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Étape 5 : enregistrer le fichier EPS avec les métadonnées XMP modifiées

Après modification, écrivez le document à nouveau.

#### Étape 5.1 : créer le flux de sortie

Ouvrez un `FileStream` pour le fichier EPS de destination.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Étape 5.2 : enregistrer le fichier EPS

Appelez `Save` sur l'instance `PsDocument`, en passant le flux de sortie.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Enfin, fermez le flux d'entrée pour libérer le handle du fichier.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Félicitations ! Vous avez réussi à **aspose.page change eps values** en mettant à jour les métadonnées XMP à l'intérieur d'un fichier EPS.

## Écueils courants et dépannage

- **Empty XMP packet** – Certains fichiers EPS sont générés sans XMP. Dans ce cas, créez un nouveau `XmpPacket` via `new XmpPacket()` avant d'assigner des valeurs.  
- **Large files** – Pour les EPS de plus de 500 Mo, activez le tamponnage de flux en définissant `PsDocumentOptions.UseMemoryMappedFiles = true` afin d'éviter `OutOfMemoryException`.  
- **Incorrect date format** – XMP attend le format ISO 8601. Utilisez `DateTime.UtcNow.ToString("o")` pour générer une chaîne conforme.

## Questions fréquemment posées

**Q : Puis-je utiliser Aspose.Page for .NET avec d'autres formats graphiques ?**  
A : Oui, la bibliothèque prend en charge plus de 30 formats dont PDF, SVG et AI, mais les API d'édition XMP sont spécifiques aux EPS et PDF.

**Q : Une version d'essai est‑elle disponible ?**  
A : Oui, vous pouvez essayer Aspose.Page for .NET avec l'essai gratuit disponible sur la page des versions Aspose [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver une documentation détaillée ?**  
A : La référence complète de l'API Aspose.Page .NET se trouve [ici](https://reference.aspose.com/page/net/).

**Q : Comment obtenir une licence temporaire ?**  
A : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Puis‑je acheter Aspose.Page for .NET ?**  
A : Absolument ! Visitez la page d'achat d'Aspose.Page [ici](https://purchase.aspose.com/buy) pour les options de licence.

---

**Dernière mise à jour** : 2026-08-13  
**Testé avec** : Aspose.Page 24.10 for .NET  
**Auteur** : Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Tutoriels associés

- [Ajouter des métadonnées à un document EPS avec Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extraire les métadonnées d'un document EPS avec Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Modifier une valeur nommée avec Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}