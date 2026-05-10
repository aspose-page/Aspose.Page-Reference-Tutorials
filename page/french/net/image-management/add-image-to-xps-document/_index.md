---
date: 2026-02-28
description: Apprenez à créer un document XPS .NET et à ajouter une image en utilisant
  Aspose.Page pour .NET. Suivez ce guide étape par étape pour une expérience de développement
  fluide.
linktitle: Add Image to XPS Document
second_title: Aspose.Page .NET API
title: Créer un document XPS .NET – Ajouter une image avec Aspose.Page
url: /fr/net/image-management/add-image-to-xps-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une image à un document XPS avec Aspose.Page pour .NET

Dans ce tutoriel, vous apprendrez comment **create XPS document .NET** et intégrer une image à l'aide de la puissante bibliothèque Aspose.Page. Que vous génériez des rapports, des factures ou des graphiques personnalisés, l'ajout d'éléments visuels aux fichiers XPS est une exigence fréquente pour les développeurs .NET.

## Introduction

Dans le monde du développement .NET, l'incorporation d'images dans les documents XPS est une exigence courante. Aspose.Page pour .NET simplifie ce processus, offrant une boîte à outils puissante pour manipuler et améliorer les documents XPS sans effort. Ce tutoriel vous guidera à travers les étapes d'ajout d'une image à un document XPS à l'aide d'Aspose.Page pour .NET.

## Réponses rapides
- **De quoi traite ce tutoriel ?** Ajout d'une image à un document XPS avec Aspose.Page pour .NET.  
- **Quel mot‑clé principal est ciblé ?** *create xps document .net*  
- **Ai‑je besoin d'une licence ?** Un essai gratuit est disponible ; une licence est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** Fonctionne avec .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de temps prend l'implémentation ?** Environ 5‑10 minutes pour une insertion d'image basique.

## Qu'est‑ce que “create XPS document .NET” ?

Créer un document XPS en .NET signifie générer de façon programmatique un fichier XML Paper Specification (XPS) — un format de document à mise en page fixe — en utilisant C# ou VB.NET. Aspose.Page fournit une API fluide qui abstrait les détails de bas niveau, vous permettant de vous concentrer sur le contenu tel que le texte, les formes et les images.

## Pourquoi utiliser Aspose.Page pour ajouter une image ?

- **Contrôle total** sur le positionnement, le redimensionnement et le rognage des images.  
- **Aucune dépendance externe** – la bibliothèque gère le décodage des images en interne.  
- **Prise en charge multiplateforme** pour les environnements Windows et Linux.  
- **Rendu haute fidélité** qui préserve la qualité de l'image dans le fichier XPS final.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d'avoir les prérequis suivants en place :

1. Bibliothèque Aspose.Page pour .NET : téléchargez et installez la bibliothèque depuis [Aspose.Page .NET Documentation](https://reference.aspose.com/page/net/).
2. Environnement de développement : configurez un environnement de développement .NET, tel que Visual Studio.
3. Image d'exemple : disposez d'un fichier image d'exemple (par ex., « QL_logo_color.tif ») que vous souhaitez ajouter au document XPS.

## Importer les espaces de noms

Commencez par importer les espaces de noms nécessaires dans votre projet .NET. Ces espaces de noms sont essentiels pour exploiter les fonctionnalités fournies par Aspose.Page pour .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Ajouter une image à un document XPS avec Aspose.Page

Ci-dessous, nous parcourons chaque étape nécessaire pour **create XPS document .NET** et intégrer une image.

### Étape 1 : Définir le répertoire du document

Commencez par spécifier le chemin de votre répertoire de documents. Cette étape garantit que votre projet sait où localiser et enregistrer les fichiers.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// ExEnd:1
```

### Étape 2 : Créer un document XPS

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// ExEnd:1
```

### Étape 3 : Ajouter une image au document XPS

Maintenant, ajoutons l'image au document XPS. Dans cet exemple, nous utiliserons une image d'exemple nommée « QL_logo_color.tif ».

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExEnd:1
```

### Étape 4 : Enregistrer le document XPS résultant

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExEnd:1
```

Vous avez maintenant ajouté avec succès une image à un document XPS en utilisant Aspose.Page pour .NET !

## Problèmes courants et solutions

- **Erreur fichier introuvable** – Vérifiez que `dataDir` pointe vers le bon dossier et que le nom du fichier image correspond exactement, y compris la sensibilité à la casse sous Linux.
- **L'image apparaît déformée** – Ajustez les facteurs d'échelle de `CreateMatrix` ou les paramètres de `RectangleF` pour contrôler la taille et le ratio d'aspect.
- **Format d'image non pris en charge** – Aspose.Page prend en charge les formats raster courants (PNG, JPEG, TIFF). Convertissez les formats non pris en charge avant d'utiliser `CreateImageBrush`.

## Questions fréquemment posées

### Q1 : Aspose.Page pour .NET est‑il compatible avec les dernières versions du framework .NET ?

R1 : Aspose.Page pour .NET est conçu pour être compatible avec un large éventail de versions du framework .NET, y compris les dernières versions. Consultez la [documentation](https://reference.aspose.com/page/net/) pour plus de détails.

### Q2 : Puis‑je utiliser Aspose.Page pour .NET à la fois sous Windows et Linux ?

R2 : Oui, Aspose.Page pour .NET est indépendant de la plateforme, ce qui le rend adapté à une utilisation à la fois sous Windows et Linux.

### Q3 : Existe‑t‑il des options de licence pour Aspose.Page pour .NET ?

R3 : Oui, vous pouvez explorer les options de licence et effectuer un achat [ici](https://purchase.aspose.com/buy).

### Q4 : Une version d'essai gratuite est‑elle disponible pour Aspose.Page pour .NET ?

R4 : Oui, vous pouvez essayer Aspose.Page pour .NET gratuitement en accédant à l'[essai gratuit](https://releases.aspose.com/).

### Q5 : Où puis‑je obtenir de l'aide ou interagir avec la communauté pour Aspose.Page pour .NET ?

R5 : Visitez le [forum Aspose.Page pour .NET](https://forum.aspose.com/c/page/39) pour rejoindre la communauté et obtenir de l'aide.

## Conclusion

Dans ce tutoriel, nous avons exploré comment exploiter Aspose.Page pour .NET afin d'intégrer de manière fluide des images dans les documents XPS. Ce guide étape par étape garantit un processus d'intégration fluide, améliore vos capacités de développement .NET et vous aide à **create XPS document .NET** avec une richesse visuelle.

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** Aspose.Page for .NET 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}