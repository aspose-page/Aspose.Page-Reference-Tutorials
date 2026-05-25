---
date: 2026-01-20
description: Apprenez à créer un document XPS, ajouter un rectangle et enregistrer
  le fichier XPS à l’aide d’Aspose.Page pour .NET dans ce guide étape par étape.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Créer un document XPS : ajouter un rectangle avec Aspose.Page pour .NET'
url: /fr/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS : ajouter un rectangle avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel, vous **créerez des fichiers de document XPS** et dessinerez un rectangle à l'intérieur en utilisant la bibliothèque Aspose.Page pour .NET. Ajouter des formes comme des rectangles est une exigence courante lorsque vous devez générer des factures, des rapports ou des graphiques personnalisés de manière programmatique. Suivez les étapes ci-dessous et vous disposerez d'un fichier XPS prêt à l'emploi en quelques minutes.

## Quick Answers
- **Que puis‑je générer ?** Documents XPS avec graphiques vectoriels et texte.  
- **Quelle bibliothèque ?** Aspose.Page pour .NET (essai gratuit disponible).  
- **Combien de temps cela prend‑il ?** Environ 5‑10 minutes pour implémenter et exécuter.  
- **Ai‑je besoin d'une licence ?** Une licence temporaire est requise pour une utilisation en production.  
- **Puis‑je enregistrer le résultat sous forme de fichier XPS ?** Oui – la méthode `Save` écrit un **fichier XPS** sur le disque.

## What is “create XPS document”?

Créer un document XPS signifie construire programmétiquement une description de page au format XML Paper Specification. Le fichier résultant est indépendant de la résolution, idéal pour l'impression et l'affichage haute qualité sur toutes les plateformes.

## Why use Aspose.Page to create XPS document?

- **Support complet .NET** – fonctionne avec .NET Framework, .NET Core et .NET 5/6+.  
- **API de dessin riche** – inclut la géométrie de chemin, les pinceaux, les stylos et la gestion du texte.  
- **Aucune dépendance externe** – tout s'exécute en‑processus sans nécessiter Office ou Acrobat.  

## Prerequisites

Avant de commencer, assurez‑vous d'avoir les éléments suivants :

1. **Aspose.Page pour .NET** – téléchargez‑le [ici](https://releases.aspose.com/page/net/).  
2. **Un dossier accessible en écriture** où les fichiers XPS générés seront stockés.

## Import Namespaces

Dans votre projet .NET, importez les espaces de noms requis :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : définir le répertoire du document

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Astuce :** Utilisez un chemin absolu ou `Path.Combine` pour éviter les problèmes de séparateur de chemin sur différents systèmes d'exploitation.

## Étape 2 : créer un nouveau document XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

À ce stade, vous avez **créé un objet document XPS** qui contiendra tous les éléments de dessin.

## Étape 3 : ajouter un rectangle (en utilisant create path geometry)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

L’appel `CreatePathGeometry` **crée une géométrie de chemin** qui définit le contour du rectangle. Vous pouvez modifier la chaîne de commandes de type SVG pour dessiner d’autres formes.

## Étape 4 : enregistrer le document (fichier XPS)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

L’appel à `Save` écrit le **fichier XPS** à l’emplacement que vous avez spécifié.

Félicitations ! Vous avez réussi à **créer un document XPS**, ajouter un rectangle et enregistrer le fichier.

## Problèmes courants et solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| `FileNotFoundException` on `doc.Save` | `dataDir` pointe vers un dossier inexistant | Assurez‑vous que le répertoire existe ou créez‑le avec `Directory.CreateDirectory(dataDir)`. |
| Rectangle non visible | Profil de couleur de trait manquant ou géométrie de chemin malformée | Vérifiez le chemin du fichier ICC et la chaîne de géométrie (`M … Z`). |
| Ralentissement des performances sur de gros documents | Trop d’appels individuels à `AddPath` | Regroupez les opérations de dessin ou réutilisez les objets pinceaux/stylos. |

## Questions fréquentes

**Q : Aspose.Page est‑il compatible avec toutes les applications .NET ?**  
R : Oui, Aspose.Page est conçu pour fonctionner de manière transparente avec toutes les applications .NET.

**Q : Où puis‑je trouver la documentation d’Aspose.Page pour .NET ?**  
R : La documentation est disponible [ici](https://reference.aspose.com/page/net/).

**Q : Puis‑je essayer Aspose.Page pour .NET gratuitement avant d’acheter ?**  
R : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?**  
R : Visitez [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire.

**Q : Où puis‑je obtenir du support communautaire ou poser des questions liées à Aspose.Page pour .NET ?**  
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

**Dernière mise à jour :** 2026-01-20  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}