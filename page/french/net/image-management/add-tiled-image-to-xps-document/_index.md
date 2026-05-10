---
date: 2026-03-03
description: Apprenez à utiliser Aspose.Page pour .NET afin de disposer les images
  en mosaïque dans les documents XPS. Ce guide étape par étape montre comment disposer
  les images efficacement et améliorer l'attrait visuel.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Comment utiliser Aspose.Page pour ajouter une image en mosaïque à un document
  XPS
url: /fr/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser Aspose.Page pour ajouter une image en mosaïque à un document XPS

## Introduction

Si vous vous demandez **comment utiliser Aspose** pour donner à vos fichiers XPS un style visuel plus riche, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes nécessaires pour **mosaïquer une image** à l’intérieur d’un document XPS en utilisant Aspose.Page pour .NET. À la fin, vous disposerez d’un extrait réutilisable que vous pourrez intégrer à n’importe quel projet .NET afin de créer des graphiques d’images en mosaïque à la volée.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page pour .NET  
- **Quelle méthode crée le pinceau en mosaïque ?** `CreateImageBrush` avec `TileMode = XpsTileMode.Tile`  
- **Puis‑je contrôler l’opacité ?** Oui – définissez `path.Fill.Opacity` (par ex., 0.5f)  
- **Ai‑je besoin d’une licence pour les tests ?** Une licence temporaire fonctionne pour l’évaluation ; une licence complète est requise en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Qu’est‑ce qu’Aspose.Page et pourquoi mosaïquer des images ?

Aspose.Page est une API puissante qui permet aux développeurs de générer, modifier et rendre des fichiers XPS, PDF et autres formats basés sur des pages sans dépendre de Microsoft Office. Mosaïquer une image — répéter un bitmap sur une forme — vous aide à remplir de grandes zones avec des motifs, filigranes ou textures d’arrière‑plan tout en maintenant la taille du fichier faible.

## Comment utiliser Aspose.Page pour mosaïquer des images dans des documents XPS

Vous trouverez ci‑dessous un exemple complet, prêt à être exécuté. Chaque étape est expliquée en langage clair avant le bloc de code correspondant, afin que vous puissiez comprendre **pourquoi** chaque ligne est importante.

### Prérequis

- **Aspose.Page pour .NET** – téléchargez et référencez la bibliothèque depuis le site officiel [ici](https://reference.aspose.com/page/net/).  
- **Environnement de développement** – Visual Studio (toute édition) ou tout autre IDE .NET de votre choix.

### Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin que le compilateur sache où trouver les classes XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Étape 1 : Définir le répertoire du document

Spécifiez où le fichier XPS généré et l’image source seront stockés. Remplacez le texte de substitution par un dossier réel sur votre machine.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer un nouveau document XPS

Instanciez un document XPS vide qui contiendra le graphique en mosaïque.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Étape 3 : Ajouter une image en mosaïque

Ici, nous créons un chemin rectangulaire, le remplissons avec un `ImageBrush`, et définissons le pinceau en mode mosaïque. La propriété `TileMode` indique au moteur de répéter l’image à la fois horizontalement et verticalement. Ajustez les coordonnées du rectangle ou l’image source selon votre scénario.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Étape 4 : Enregistrer le document XPS résultant

Enfin, écrivez le document sur le disque. Le fichier de sortie peut être ouvert avec n’importe quel visualiseur XPS ou traité davantage avec Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Problèmes courants & astuces

- **Erreurs de chemin** – Assurez‑vous que `dataDir` se termine par un slash ou utilisez `Path.Combine` pour éviter les problèmes de séparateur manquant.  
- **Incohérences de taille d’image** – L’image source doit être suffisamment grande pour la zone de mosaïque ; sinon le motif peut sembler étiré.  
- **Opacité non visible** – Certains visualiseurs ignorent l’opacité sur XPS ; testez avec un visualiseur qui prend pleinement en charge le rendu XPS (par ex., XPS Viewer sous Windows).

## Foire aux questions

### Q1 : Aspose.Page est‑il compatible avec tous les environnements de développement .NET ?
R : Oui, Aspose.Page fonctionne avec Visual Studio, Rider, VS Code et tout IDE supportant .NET.

### Q2 : Puis‑je ajuster l’opacité de l’image en mosaïque ?
R : Absolument. L’exemple définit `path.Fill.Opacity = 0.5f;`—vous pouvez modifier la valeur flottante entre 0 (transparent) et 1 (opaque).

### Q3 : Existe‑t‑il d’autres modes de mosaïque disponibles dans Aspose.Page pour .NET ?
R : Oui. En plus de `XpsTileMode.Tile`, vous pouvez utiliser `FlipX`, `FlipY` et `FlipXY` pour créer des motifs miroir.

### Q4 : Comment gérer les licences temporaires pour Aspose.Page ?
R : Consultez la page de [licence temporaire](https://purchase.aspose.com/temporary-license/) sur le site Aspose pour obtenir des détails sur l’obtention et l’application d’une licence d’évaluation.

### Q5 : Où puis‑je obtenir de l’aide ou rejoindre la communauté Aspose.Page ?
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour poser des questions, partager des extraits et apprendre des autres développeurs.

### Q6 : Puis‑je utiliser cette approche pour créer un effet de filigrane ?
R : Oui. En réduisant l’opacité et en choisissant une image semi‑transparente, le pinceau en mosaïque fonctionne parfaitement comme filigrane répété.

## Conclusion

Vous savez maintenant **comment utiliser Aspose** pour ajouter une image en mosaïque à un document XPS, contrôler son opacité et enregistrer le résultat pour une utilisation ultérieure. Cette technique est idéale pour les motifs d’arrière‑plan, les filigranes ou toute situation où un graphique répété ajoute de l’intérêt visuel sans gonfler la taille du fichier. N’hésitez pas à expérimenter avec différentes formes, images et modes de mosaïque pour répondre aux besoins de votre projet.

---

**Dernière mise à jour :** 2026-03-03  
**Testé avec :** Aspose.Page pour .NET (dernière version)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}