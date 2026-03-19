---
date: 2026-03-19
description: Apprenez comment **supprimer les pages XPS** des documents et **supprimer
  la page à l’index** en utilisant Aspose.Page pour .NET – un guide complet étape
  par étape avec les prérequis, des exemples de code et une FAQ.
linktitle: Remove Page from XPS Document
second_title: Aspose.Page .NET API
title: Supprimer une page du document XPS avec Aspose.Page pour .NET
url: /fr/net/page-manipulation/remove-page-from-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Supprimer une page d'un document XPS avec Aspose.Page pour .NET

## Introduction

Si vous devez **remove page xps** des fichiers de manière programmatique, Aspose.Page pour .NET vous offre une méthode propre et fiable pour le faire. Dans ce tutoriel, nous parcourrons les étapes exactes nécessaires pour supprimer une page spécifique d'un document XPS, expliquerons pourquoi cette opération est importante, et vous montrerons comment enregistrer le fichier mis à jour sur le disque.

## Quick Answers
- **Que signifie “remove page xps” ?** Il s'agit de supprimer une page unique d'un document XPS (XML Paper Specification).  
- **Quelle méthode supprime une page ?** Utilisez `RemovePageAt(index)` où l'index commence à zéro.  
- **Puis-je supprimer une page à n'importe quelle position ?** Oui – vous pouvez **delete page at index** 0, 1, 2, etc., selon les besoins.  
- **Ai-je besoin d'une licence pour Aspose.Page ?** Une licence temporaire est requise pour les tests ; une licence complète est nécessaire pour la production.  
- **Le code est‑il compatible avec .NET 6 ?** Absolument – Aspose.Page prend en charge .NET Framework, .NET Core et .NET 5/6.

## What is “remove page xps”?
Supprimer une page d'un document XPS signifie retirer l'une des pages du document tout en préservant le reste du contenu, la mise en page et les métadonnées. Cette opération est utile lorsque vous devez réduire des PDF, générer des rapports personnalisés ou respecter des limites de taille de document.

## Why use Aspose.Page for .NET?
- **Aucune dépendance externe** – bibliothèque pure .NET.  
- **Haute fidélité** – conserve les graphiques vectoriels et la précision de la mise en page.  
- **Cross‑platform** – fonctionne sous Windows, Linux et macOS.  
- **API simple** – un appel de méthode unique (`RemovePageAt`) gère le travail lourd.

## Prerequisites

Avant de plonger dans le code, assurez‑vous d'avoir :

- **Aspose.Page for .NET** – téléchargez‑le depuis la [documentation Aspose.Page for .NET](https://reference.aspose.com/page/net/).  
- Un **environnement de développement .NET** (Visual Studio, VS Code ou tout IDE de votre choix).  
- Un **document XPS d'exemple** (par ex. `Sample.xps`) placé dans un dossier que vous pouvez référencer depuis votre projet.

## Import Namespaces

Ajoutez les espaces de noms requis en haut de votre fichier C# afin que le compilateur sache où trouver les classes XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step 1: Set the Document Directory

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Astuce :** Utilisez `Path.Combine` pour la construction de chemins multiplateforme.

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument(dataDir + "Sample.xps");
// ExEnd:4
```

Cette ligne charge le fichier XPS existant (`Sample.xps`) dans un objet `XpsDocument`, prêt à être manipulé.

## Step 3: Delete Page at Index

```csharp
// ExStart:5
// Remove the first page (at index 1).
doc.RemovePageAt(1);
// ExEnd:5
```

La méthode `RemovePageAt` **supprime la page à l'index spécifié**. N'oubliez pas que l'indexation commence à 0, ainsi `1` supprime la deuxième page. Ajustez l'index pour cibler la page que vous devez supprimer.

## Step 4: Save the Resultant XPS Document

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "Sample_out.xps");
// ExEnd:6
```

Après la suppression, le document est enregistré sous `Sample_out.xps`. Vous pouvez maintenant ouvrir ce fichier pour vérifier que la page indésirable a disparu.

## Common Issues and Solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| **Index hors limites** | Tentative de suppression d'une page qui n'existe pas. | Vérifiez le nombre de pages avec `doc.Pages.Count` avant d'appeler `RemovePageAt`. |
| **Fichier verrouillé** | Le fichier XPS est ouvert dans un autre programme. | Fermez les visionneuses ou assurez‑vous que le fichier n'est pas utilisé avant d'exécuter le code. |
| **Licence non appliquée** | Utilisation de la bibliothèque sans licence valide en production. | Appliquez une licence temporaire ou permanente en utilisant `License license = new License(); license.SetLicense("Aspose.Page.lic");` |

## Frequently Asked Questions

**Q1 : Puis‑je supprimer plusieurs pages à la fois avec Aspose.Page pour .NET ?**  
R1 : Oui, il suffit d'appeler `RemovePageAt` à plusieurs reprises ou de parcourir une liste d'indices (n'oubliez pas de supprimer du plus grand au plus petit indice pour que les indices restants restent valides).

**Q2 : Aspose.Page est‑il compatible avec le dernier framework .NET ?**  
R2 : Aspose.Page est régulièrement mis à jour pour prendre en charge les dernières versions de .NET, y compris .NET 6 et .NET 7.

**Q3 : Puis‑je utiliser Aspose.Page pour des applications commerciales ?**  
R3 : Absolument. Pour les détails de licence, consultez la page [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q4 : Où puis‑je trouver un support supplémentaire et des discussions sur Aspose.Page ?**  
R4 : Rejoignez la communauté sur le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour des astuces, des exemples et de l'aide au dépannage.

**Q5 : Ai‑je besoin d'une licence temporaire pour tester Aspose.Page ?**  
R5 : Oui, vous pouvez obtenir une [licence temporaire](https://purchase.aspose.com/temporary-license/) pour évaluer la bibliothèque avant l'achat.

**Q6 : Comment préserver les métadonnées du document après la suppression d'une page ?**  
R6 : La méthode `RemovePageAt` conserve automatiquement les métadonnées originales. Si vous devez les modifier, utilisez la collection `doc.DocumentProperties`.

## Conclusion

Vous avez maintenant appris comment **remove page xps** des documents et **delete page at index** avec Aspose.Page pour .NET. Cette approche concise vous permet d'intégrer la logique de suppression de pages directement dans vos applications .NET, vous offrant un contrôle total sur le contenu des documents XPS.

---

**Dernière mise à jour :** 2026-03-19  
**Testé avec :** Aspose.Page 24.12 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}