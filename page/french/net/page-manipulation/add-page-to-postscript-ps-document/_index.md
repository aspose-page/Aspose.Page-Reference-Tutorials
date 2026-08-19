---
date: 2026-03-03
description: Apprenez à définir une taille de page personnalisée et à ajouter une
  deuxième page PS à un document PostScript en utilisant Aspose.Page pour .NET.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Définir une taille de page personnalisée dans un document PS avec Aspose.Page
url: /fr/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une page à un document PostScript (PS) avec Aspose.Page

## Introduction

Dans le développement .NET, pouvoir **set custom page size** et **add second PS page** à un document PostScript (PS) vous donne un contrôle précis sur la mise en page des impressions, rapports ou graphiques générés. Aspose.Page pour .NET rend cette tâche simple grâce à une API propre et orientée objet. Dans ce tutoriel, vous apprendrez à créer un fichier PS multi‑pages, à définir une taille personnalisée pour chaque page et à enregistrer le résultat — le tout en quelques lignes de code C#.

## Réponses rapides
- **Puis-je définir une taille de page personnalisée ?** Oui – il suffit de fournir la largeur et la hauteur lors de l'ouverture d'une page.  
- **Comment ajouter une deuxième page PS ?** Appelez `document.OpenPage(width, height)` une deuxième fois.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ai-je besoin d'une licence ?** Une licence temporaire suffit pour les tests ; une licence complète est requise en production.  
- **Où puis-je télécharger Aspose.Page ?** Depuis la page de téléchargement officielle ci‑dessous.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d'avoir les prérequis suivants :

- Une connaissance pratique du développement .NET.  
- Visual Studio installé sur votre machine.  
- La bibliothèque Aspose.Page pour .NET, que vous pouvez télécharger [ici](https://releases.aspose.com/page/net/).  
- Votre répertoire de documents préféré pour les tests.

## Importer les espaces de noms

Assurez‑vous d’inclure les espaces de noms nécessaires dans votre projet pour accéder aux fonctionnalités fournies par Aspose.Page. Dans l’exemple donné, les espaces de noms sont implicitement inclus, mais il est essentiel de vérifier et d’ajuster selon la structure de votre projet.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Configurer votre projet

Créez un nouveau projet .NET dans Visual Studio et configurez les paramètres nécessaires. Veillez à référencer la bibliothèque Aspose.Page dans votre projet.

## Définir une taille de page personnalisée et ajouter une deuxième page PS

Cette section montre exactement comment **set custom page size** pour chaque page et comment **add second ps page** au même document.

### Étape 2 : Initialiser le document

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### Étape 3 : Ajouter la première page (taille par défaut)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### Étape 4 : Ajouter la deuxième page avec une taille différente (personnalisée)

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### Étape 5 : Enregistrer le document

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

Suivez ces étapes méticuleusement, et vous réussirez à **set custom page size** et à ajouter une **second PS page** à un document PostScript en utilisant Aspose.Page pour .NET.

## Pourquoi c'est important

- **Precision Layout** – Les dimensions de page personnalisées vous permettent d'adapter les spécifications de l'imprimante ou de créer des formats de brochure uniques.  
- **Multiple Pages** – Ajouter une deuxième page (ou plus) permet des rapports multi‑pages sans outils de fusion externes.  
- **Cross‑Platform** – Le fichier PS généré peut être rendu sur n'importe quel appareil compatible PostScript ou converti en PDF ultérieurement.

## Pièges courants et dépannage

- **Incorrect Path** – Assurez‑vous que `dataDir` se termine par un séparateur de chemin ou utilisez `Path.Combine`.  
- **License Issues** – Sans licence valide, la bibliothèque peut ajouter un filigrane ou limiter le nombre de pages.  
- **Unit Confusion** – La largeur et la hauteur sont mesurées en points (1 point = 1/72 pouce). Ajustez en conséquence.

## Questions fréquemment posées

**Q1 : Aspose.Page est‑il compatible avec différents formats de documents ?**  
R1 : Aspose.Page se concentre principalement sur la manipulation de documents PostScript. Pour d'autres formats, vous pouvez explorer les bibliothèques Aspose adaptées à des besoins spécifiques.

**Q2 : Puis‑je personnaliser la taille de la page dans Aspose.Page ?**  
R2 : Absolument ! Comme démontré dans le tutoriel, vous pouvez spécifier différentes tailles pour chaque page selon vos besoins.

**Q3 : Où puis‑je trouver plus d'exemples et de documentation ?**  
R3 : Consultez la [documentation](https://reference.aspose.com/page/net/) pour des informations complètes et de nombreux exemples.

**Q4 : Comment obtenir une licence temporaire pour Aspose.Page ?**  
R4 : Rendez‑vous sur [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire à des fins de test.

**Q5 : Où puis‑je obtenir du support communautaire ou poser des questions ?**  
R5 : Rejoignez le [forum communautaire Aspose.Page](https://forum.aspose.com/c/page/39) pour entrer en contact avec d'autres développeurs, partager des expériences et demander de l'aide.

---

**Dernière mise à jour :** 2026-03-03  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}