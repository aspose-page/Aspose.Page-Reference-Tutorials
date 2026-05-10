---
date: 2026-03-26
description: Apprenez comment définir un masque d'opacité et appliquer plusieurs masques
  d'opacité dans les documents XPS à l'aide d'Aspose.Page pour .NET.
linktitle: Set Opacity Mask in XPS Document
second_title: Aspose.Page .NET API
title: Définir plusieurs masques d'opacité dans un document XPS avec Aspose.Page pour
  .NET
url: /fr/net/transparency-effects/set-opacity-mask-in-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Définir plusieurs masques d'opacité dans un document XPS avec Aspose.Page pour .NET

## Introduction

Les masques d'opacité vous permettent de contrôler la transparence de tout élément visuel, et en utilisant **plusieurs masques d'opacité** vous pouvez obtenir des effets de calque sophistiqués qui font ressortir vos documents XPS. Dans ce tutoriel, nous vous guiderons à travers **la façon de définir un masque d'opacité** sur des formes et nous démontrerons comment combiner plusieurs masques pour des résultats visuels plus riches. À la fin, vous pourrez ajouter un ou plusieurs masques d'opacité à n'importe quel élément XPS avec seulement quelques lignes de code C#.

## Réponses rapides
- **Qu'est‑ce qu'un masque d'opacité ?** Un bitmap, un dégradé ou un pinceau de couleur unie qui définit la transparence pixel par pixel pour une forme.  
- **Pourquoi utiliser plusieurs masques d'opacité ?** Empiler les masques crée des motifs de transparence complexes qu'un seul masque ne peut pas réaliser.  
- **Quelle bibliothèque prend en charge cela ?** Aspose.Page for .NET fournit une prise en charge complète des masques d'opacité sur les graphiques XPS.  
- **Ai‑je besoin d'une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu'est‑ce que les « masques d'opacité multiples » ?
Les masques d'opacité multiples désignent la technique consistant à appliquer plus d'un masque—soit séquentiellement, soit en couches—de sorte que chaque masque contribue à la carte de transparence finale. Cette approche est utile pour créer des dégradés, des textures ou des transparences à motifs sans recourir à une édition d'image complexe.

## Pourquoi utiliser Aspose.Page pour .NET afin de définir des masques d'opacité ?
- **Ensemble complet de fonctionnalités XPS** – Toutes les capacités graphiques XPS sont exposées via une API .NET claire.  
- **Aucune dépendance externe** – Travaillez directement avec les objets XPS ; aucune bibliothèque d'imagerie supplémentaire n'est nécessaire.  
- **Optimisé pour les performances** – Gère efficacement les documents volumineux et les masques haute résolution.  

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous de disposer des prérequis suivants :

- Aspose.Page for .NET : Assurez‑vous d'avoir la bibliothèque installée. Sinon, vous pouvez la télécharger depuis le [site web](https://releases.aspose.com/page/net/).

- Répertoire de documents : Créez un répertoire pour stocker vos documents XPS.

## Importer les espaces de noms

Dans votre projet .NET, commencez par importer les espaces de noms nécessaires :

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## Étape 1 : Créer un nouveau document XPS

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Commencez par créer un nouveau document XPS en utilisant Aspose.Page for .NET.

## Étape 2 : Ajouter un canvas à l'instance XpsDocument

```csharp
// Add Canvas to XpsDocument instance
XpsCanvas canvas = doc.AddCanvas();
```

Ajoutez maintenant un canvas au document XPS. Le canvas servira de conteneur pour divers éléments graphiques.

## Étape 3 : Ajouter un rectangle avec un masque d'opacité

```csharp
// Rectangle with opacity masked by ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

Ajoutez un rectangle au canvas et définissez son opacité à l'aide de la propriété `OpacityMask`. Dans cet exemple, nous utilisons une image comme masque d'opacité. Vous pouvez répéter cette étape avec un pinceau différent pour appliquer **plusieurs masques d'opacité** à la même forme, obtenant ainsi des effets de transparence superposés.

## Étape 4 : Enregistrer le document XPS résultant

```csharp
// Save resultant XPS document
doc.Save(dataDir + "OpacityMask_out.xps");
```

Enfin, enregistrez le document XPS modifié avec le masque d'opacité appliqué.

## Cas d'utilisation courants pour les masques d'opacité multiples
- **Filigrane** – Combinez un masque de texte avec un masque de motif pour créer des filigranes semi‑transparents.  
- **Cartes thématiques** – Superposez un masque de dégradé sur une image raster pour mettre en évidence des régions spécifiques.  
- **Branding** – Utilisez un masque d'image de logo conjointement avec un masque de dégradé de couleur pour des éléments de marque sophistiqués.

## Dépannage & Conseils
- **Alignement du masque** – Assurez‑vous que les dimensions du rectangle source correspondent à la forme cible afin d'éviter les étirements.  
- **TileMode** – Expérimentez avec `XpsTileMode.Tile` ou `XpsTileMode.None` pour contrôler la façon dont le masque se répète.  
- **Performance** – Réutilisez les instances de `XpsImageBrush` lors de l'application du même masque à plusieurs éléments.

## FAQ

### Q1 : Puis‑je appliquer des masques d'opacité à d'autres formes que les rectangles ?

**R1** : Oui, Aspose.Page for .NET vous permet d'appliquer des masques d'opacité à diverses formes, y compris des cercles, des polygones et des chemins personnalisés.

### Q2 : Le masque d'opacité est‑il limité aux images ?

**R2** : Non, bien que ce tutoriel utilise une image comme masque d'opacité, vous pouvez également exploiter des couleurs unies, des dégradés ou même des motifs.

### Q3 : Existe‑t‑il des options avancées pour affiner les niveaux d'opacité ?

**R3** : Absolument, Aspose.Page for .NET offre un contrôle détaillé des paramètres d'opacité, vous permettant d'obtenir des effets de transparence précis.

### Q4 : Puis‑je appliquer plusieurs masques d'opacité à un même élément ?

**R4** : Oui, vous pouvez superposer plusieurs masques d'opacité pour créer des effets de transparence complexes.

### Q5 : Aspose.Page est‑il compatible avec d'autres formats de documents ?

**R5** : Aspose.Page se concentre principalement sur les documents XPS, mais Aspose propose une gamme de produits pour la gestion de différents formats.

**Questions supplémentaires**

**Q : Comment combiner deux masques différents sur la même forme ?**  
**R :** Créez deux objets `XpsImageBrush` (ou pinceau de dégradé), assignez‑en un à `OpacityMask`, puis encapsulez la forme dans un `XpsCanvas` et appliquez le second masque au canvas lui‑même.

**Q : L'API prend‑elle en charge les changements d'opacité animés ?**  
**R :** Bien que XPS ne supporte pas l'animation, vous pouvez générer une série de pages XPS avec des opacités de masque variables pour simuler une animation.

---

**Dernière mise à jour :** 2026-03-26  
**Testé avec :** Aspose.Page for .NET 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}