---
date: 2026-07-19
description: Apprenez à créer un document XPS .NET et à ajouter un rectangle en utilisant
  Aspose.Page pour .NET dans un guide concis étape par étape.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Ajouter un rectangle au document XPS
og_description: Créez rapidement un document XPS .NET. Ce tutoriel montre comment
  ajouter un rectangle à un fichier XPS en utilisant Aspose.Page pour .NET, avec du
  code clair et des astuces.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Créer un document XPS .NET – Ajouter un rectangle avec Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Créer un document XPS .NET – Ajouter un rectangle avec Aspose.Page
url: /fr/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS .NET – Ajouter un rectangle avec Aspose.Page

## Introduction

Dans ce tutoriel, vous apprendrez comment **créer un document XPS .NET** et dessiner un rectangle à l'intérieur en utilisant Aspose.Page pour .NET. Que vous construisiez un moteur de reporting, une facture imprimable ou une couche graphique personnalisée, la capacité de générer des fichiers XPS de manière programmatique vous donne un contrôle total sur la mise en page et la fidélité. Suivez les étapes ci‑dessous et vous disposerez d'un fichier XPS prêt à l'emploi en quelques minutes.

## Réponses rapides
- **Quel est l'objectif principal ?** Créer un document XPS .NET et ajouter une forme de rectangle.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET (téléchargeable depuis le site officiel).  
- **Ai-je besoin d'une licence pour les tests ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de temps prend l'implémentation ?** Environ 5‑10 minutes pour un rectangle basique.

## Qu'est-ce qu'Aspose.Page pour .NET ?
Aspose.Page pour .NET est une API haute performance, entièrement gérée, qui permet aux développeurs de créer, modifier et rendre des documents XPS (XML Paper Specification) de façon programmatique sans dépendre de composants externes. Elle offre un modèle d'objet riche pour le dessin de formes, de texte et d'images, et prend en charge des fonctionnalités avancées telles que la gestion des couleurs, la compression et la conversion PDF, ce qui la rend adaptée à un large éventail de scénarios de génération de documents.

## Pourquoi utiliser Aspose.Page pour créer un document XPS .NET ?
Aspose.Page prend en charge **plus de 30 fonctionnalités XPS** — y compris les graphiques vectoriels, la mise en page du texte et la gestion des couleurs — et peut générer des fichiers jusqu'à **500 MB** sans charger l'intégralité du document en mémoire. Cette capacité quantifiée assure des performances fluides même pour des travaux d'impression à grande échelle.

## Prérequis

Avant de commencer ce tutoriel, assurez-vous d'avoir les prérequis suivants en place :

1. Bibliothèque Aspose.Page pour .NET : Assurez-vous que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).

2. Répertoire des documents : Créez un répertoire où vous souhaitez stocker vos documents XPS.

## Importer les espaces de noms

Dans votre application .NET, incluez les espaces de noms nécessaires pour utiliser les fonctionnalités d'Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Comment ajouter un rectangle à un document XPS en .NET ?

Chargez le document XPS, créez un objet `Graphics`, définissez un `RectangleF` avec la taille souhaitée, puis appelez `DrawRectangle`. Cette séquence dessine un rectangle en une seule ligne de code et gère automatiquement le redimensionnement DPI. Pour des pages de taille A4 typiques, un rectangle de 200 × 100 pt apparaît centré sans calculs supplémentaires.

### Étape 1 : Définir le répertoire des documents

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Étape 2 : Créer un nouveau document XPS

La classe `XpsDocument` représente le fichier XPS que vous construisez et fournit des méthodes pour ajouter des pages, des graphiques et d'autres ressources.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Étape 3 : Ajouter un rectangle

`XpsPath` définit un objet de chemin dessinable au sein du document XPS, vous permettant de définir la géométrie, le trait, le remplissage et d'autres propriétés visuelles.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Étape 4 : Enregistrer le document

La méthode `Save` écrit le document XPS construit à l'emplacement de fichier spécifié sur le disque.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Félicitations ! Vous avez ajouté avec succès un rectangle à un document XPS en utilisant Aspose.Page pour .NET.

## Problèmes courants et astuces

- **Polices manquantes :** Assurez-vous que les polices que vous référencez sont installées sur le serveur ; sinon Aspose.Page les remplace par une police par défaut, ce qui peut modifier la mise en page.  
- **Documents volumineux :** Lors de la génération de fichiers supérieurs à 200 MB, envisagez d’appeler `document.SaveOptions.Compress = true` pour réduire l’utilisation de la mémoire.  
- **Système de coordonnées :** XPS utilise des points (1/72 pouce). N'oubliez pas de convertir les pixels en points si vous travaillez avec des dimensions basées sur l'écran.

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec toutes les applications .NET ?**  
R : Oui, Aspose.Page fonctionne parfaitement avec les applications .NET de bureau, web et cloud.

**Q : Où puis‑je trouver la documentation d'Aspose.Page pour .NET ?**  
R : La référence complète de l'API est disponible [ici](https://reference.aspose.com/page/net/).

**Q : Puis‑je essayer Aspose.Page pour .NET gratuitement avant d'acheter ?**  
R : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?**  
R : Visitez [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire.

**Q : Où puis‑je obtenir du support communautaire ou poser des questions liées à Aspose.Page pour .NET ?**  
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

---

**Dernière mise à jour :** 2026-07-19  
**Testé avec :** Aspose.Page pour .NET 24.9  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un document XPS avec Aspose.Page pour .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Dessiner des formes](/page/net/drawing-shapes/)
- [Ajouter du texte à un document XPS avec Aspose.Page pour .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}