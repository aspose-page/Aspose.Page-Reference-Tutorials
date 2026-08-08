---
date: 2026-08-08
description: Apprenez à créer un EPS avec des métadonnées XMP et à ajouter des valeurs
  nommées en utilisant Aspose.Page pour .NET. Guide étape par étape avec des espaces
  réservés de code.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Ajouter une valeur nommée
og_description: Créer un EPS avec des métadonnées XMP dans .NET en utilisant Aspose.Page.
  Ce guide montre comment ajouter des valeurs nommées aux fichiers EPS rapidement
  et de manière fiable.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Créer un EPS avec XMP – ajouter une valeur nommée avec Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Créer un EPS avec XMP – ajouter une valeur nommée avec Aspose.Page
url: /fr/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-container >}}
{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un EPS avec XMP – ajouter une valeur nommée à l'aide d'Aspose.Page

## Introduction

Dans ce tutoriel, vous apprendrez comment **créer un EPS avec des métadonnées XMP** et injecter une valeur nommée à l'aide de la bibliothèque Aspose.Page pour .NET. Que vous construisiez une chaîne de traitement par lots ou que vous deviez enrichir des fichiers EPS avec des balises XMP personnalisées, les étapes ci‑dessous vous guident depuis la configuration du projet jusqu'à la persistance du fichier modifié. Aspose.Page peut gérer des documents EPS jusqu'à **500 pages** sans charger le fichier complet en mémoire, ce qui le rend adapté aux scénarios à haut volume.

## Réponses rapides
- **Quel est l'objectif principal ?** Ajouter une valeur XMP nommée à un fichier EPS existant.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET.  
- **Ai‑je besoin d'une licence ?** Une licence commerciale est requise pour la production ; un essai gratuit est disponible.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Combien de temps prend l'implémentation ?** Environ 10–15 minutes pour un cas d'utilisation basique.

## Comment créer un EPS avec des métadonnées XMP en .NET ?

Chargez le fichier EPS cible, obtenez (ou créez) son objet de métadonnées XMP, ajoutez la valeur nommée requise, puis enregistrez le document sur le disque. Ce flux de travail ne nécessite que quelques appels de méthode et fonctionne de manière cohérente sur toutes les versions EPS prises en charge. L'approche préserve également le contenu des pages existantes et les autres structures XMP, vous permettant de chaîner en toute sécurité plusieurs mises à jour de métadonnées.

## Prérequis

Avant de commencer, assurez‑vous de disposer de :

- Connaissances de base en C# et en structure de projet .NET.  
- Visual Studio 2022 (ou tout IDE compatible).  
- Bibliothèque Aspose.Page pour .NET. Si vous ne l’avez pas encore, téléchargez‑la depuis la **page de téléchargement Aspose.Page pour .NET**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Importer les espaces de noms

Les espaces de noms suivants donnent accès aux classes de gestion EPS, de sortie d’appareil et aux métadonnées XMP d’Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Étape 1 : initialiser le flux d'entrée du fichier EPS

Créez un `FileStream` pour le fichier EPS source et instanciez un objet `PsDocument` afin de travailler avec le document.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Étape 2 : obtenir les métadonnées XMP

Récupérez l'objet `XmpMetadata` du document ; cet objet représente le paquet XMP intégré.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Étape 3 : modifier les valeurs des métadonnées XMP

Utilisez la méthode `AddNamedValue` de `XmpMetadata` pour insérer une nouvelle valeur nommée dans la structure XMP spécifiée.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Étape 4 : enregistrer le fichier EPS avec les métadonnées XMP modifiées

Enregistrez le document modifié en l’écrivant dans un nouveau `FileStream`.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Pourquoi utiliser Aspose.Page pour les métadonnées EPS ?

Aspose.Page prend en charge **plus de 50 schémas XMP** et peut traiter des fichiers EPS jusqu’à **500 pages** tout en maintenant une utilisation mémoire inférieure à **30 Mo** pour les documents typiques. La bibliothèque ne dépend d’aucun outil externe ni de code natif, garantissant un comportement cohérent sous Windows, Linux et macOS.

## Problèmes courants et dépannage

- **Paquet XMP manquant :** Si `GetXmpMetadata()` renvoie `null`, le fichier EPS ne contient pas de bloc XMP. La bibliothèque en créera automatiquement un, mais assurez‑vous que le fichier n’est pas corrompu.  
- **Conflits d’espaces de noms :** Lors de l’ajout de valeurs nommées personnalisées, utilisez un URI d’espace de noms unique pour éviter les collisions avec les schémas existants.  
- **Fichiers volumineux :** Pour les fichiers EPS supérieurs à 200 Mo, envisagez de diffuser la sortie afin d’éviter une consommation excessive de mémoire.

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec différentes versions de fichiers EPS ?**  
R : Aspose.Page prend en charge les versions EPS 3.0 à 3.3, assurant une large compatibilité avec les fichiers anciens et modernes.

**Q : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Oui, une licence commerciale est requise pour une utilisation en production. Vous pouvez acheter une licence sur la **[page d’achat de licence Aspose.Page](https://purchase.aspose.com/buy)**.

**Q : Un essai gratuit est‑il disponible ?**  
R : Oui, un essai pleinement fonctionnel peut être téléchargé sur la **[page de téléchargement d’essai gratuit Aspose.Page](https://releases.aspose.com/)**.

**Q : Comment obtenir du support ou rejoindre la communauté ?**  
R : Visitez le **[forum Aspose.Page](https://forum.aspose.com/c/page/39)** pour poser des questions et partager vos expériences.

**Q : Qu’est‑ce qu’une licence temporaire et comment en obtenir une ?**  
R : Une licence temporaire vous permet d’évaluer le produit pendant une courte période. Vous pouvez en demander une sur la **[page de demande de licence temporaire](https://purchase.aspose.com/temporary-license/)**.

---

**Dernière mise à jour :** 2026-08-08  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Ajouter des métadonnées à un document EPS avec Aspose.Page pour .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Modifier une valeur nommée avec Aspose.Page pour .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Extraire les métadonnées d’un document EPS avec Aspose.Page pour .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/pf/main-wrap-class >}}