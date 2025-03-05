---
title: Ajouter une image en mosaïque au document XPS avec Aspose.Page pour .NET
linktitle: Ajouter une image en mosaïque au document XPS
second_title: API Aspose.Page .NET
description: Découvrez l'ajout d'images en mosaïque aux documents XPS sans effort avec Aspose.Page pour .NET. Améliorez l’attrait visuel et créez des documents époustouflants.
type: docs
weight: 12
url: /fr/net/image-management/add-tiled-image-to-xps-document/
---
## Introduction

Cherchez-vous à améliorer vos documents XPS en ajoutant des images en mosaïque visuellement attrayantes ? Aspose.Page pour .NET permet aux développeurs d'y parvenir de manière transparente. Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'ajout d'une image en mosaïque à un document XPS à l'aide d'Aspose.Page pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page est installée. Vous pouvez trouver une documentation détaillée et télécharger la bibliothèque[ici](https://reference.aspose.com/page/net/).
- Environnement de développement : configurez votre environnement de développement .NET préféré, tel que Visual Studio.

## Importer des espaces de noms

Pour commencer, importez les espaces de noms nécessaires dans votre projet. Cela garantit que vous avez accès aux classes et méthodes requises pour travailler avec Aspose.Page. Ajoutez les espaces de noms suivants au début de votre code :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Maintenant, décomposons l'exemple en plusieurs étapes.

## Étape 1 : Définir le répertoire des documents

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```

Assurez-vous de remplacer « Votre répertoire de documents » par le chemin réel où vous souhaitez enregistrer votre document XPS.

## Étape 2 : Créer un nouveau document XPS

```csharp
// Créer un nouveau document XPS
XpsDocument doc = new XpsDocument();
```

 Instancier un nouveau document XPS à l'aide de l'outil`XpsDocument` classe.

## Étape 3 : ajouter une image en mosaïque

```csharp
// Image de tuile
// Rectangle rempli d'ImageBrush en haut à droite ci-dessous
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Cette étape ajoute une image en mosaïque au document XPS. Ajustez les coordonnées et le chemin du fichier image selon vos besoins.

## Étape 4 : Enregistrez le document XPS résultant

```csharp
// Enregistrer le document XPS résultant
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Enregistrez le document XPS modifié dans le répertoire spécifié.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment ajouter une image en mosaïque à un document XPS à l'aide d'Aspose.Page pour .NET. Cette fonctionnalité simple mais puissante vous permet d'améliorer l'attrait visuel de vos documents sans effort.

## FAQ

### Q1 : Aspose.Page est-il compatible avec tous les environnements de développement .NET ?

A1 : Oui, Aspose.Page est conçu pour fonctionner de manière transparente avec divers environnements de développement .NET, y compris Visual Studio.

### Q2 : Puis-je ajuster l'opacité de l'image en mosaïque ?

A2 : Certes, comme démontré dans l'exemple, vous pouvez définir l'opacité du rectangle rempli à l'aide du`Opacity` propriété.

### Q3 : Existe-t-il d'autres modes de vignettes disponibles dans Aspose.Page pour .NET ?

 A3 : Oui, Aspose.Page propose différents modes de mosaïque. Dans ce tutoriel, nous avons utilisé`XpsTileMode.Tile`, mais vous pouvez explorer d'autres options dans la documentation.

### Q4 : Comment gérer les licences temporaires pour Aspose.Page ?

 A4 : Reportez-vous au[permis temporaire](https://purchase.aspose.com/temporary-license/) sur le site Web d'Aspose pour obtenir des conseils sur l'obtention et la mise en œuvre de licences temporaires.

### Q5 : Où puis-je demander de l'aide ou me connecter à la communauté Aspose.Page ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour interagir avec la communauté, poser des questions et trouver des solutions.