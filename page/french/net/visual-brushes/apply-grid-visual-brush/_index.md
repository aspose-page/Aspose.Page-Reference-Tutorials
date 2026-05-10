---
date: 2026-04-03
description: Apprenez à ajouter un rectangle transparent et à appliquer un pinceau
  visuel Grid en .NET avec Aspose.Page pour créer des documents XPS époustouflants.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Appliquer le pinceau visuel de grille
second_title: Aspose.Page .NET API
title: Ajouter un rectangle transparent à l'aide du pinceau visuel de grille (.NET)
url: /fr/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un rectangle transparent avec Grid Visual Brush (.NET)

## Introduction

Si vous cherchez à **ajouter un rectangle transparent** à un document XPS tout en appliquant un élégant Grid Visual Brush, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons les étapes exactes avec Aspose.Page for .NET, afin que vous puissiez créer des documents visuellement riches qui se démarquent. À la fin, vous disposerez d’un exemple complet et exécutable démontrant les deux techniques dans un flux de travail simple à suivre.

## Réponses rapides
- **Que fait un rectangle transparent ?** Il ajoute une superposition semi‑opaque qui laisse le contenu d'arrière‑plan visible.  
- **Quelle API crée le pinceau ?** `XpsDocument.CreateVisualBrush` crée le Grid Visual Brush.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un exemple de base.

## Qu'est-ce qu'un rectangle transparent dans XPS ?
Un rectangle transparent est simplement une forme dont la couleur de remplissage comprend un composant alpha inférieur à 1,0, permettant aux graphiques sous‑jacent d’être partiellement visibles. C’est parfait pour mettre en évidence des sections sans masquer complètement l’arrière‑plan.

## Pourquoi utiliser un Grid Visual Brush ?
Un Grid Visual Brush vous permet de répéter un petit graphique vectoriel sur une zone plus grande, créant des motifs tels que des grilles, des hachures ou des textures personnalisées. Le combiner avec un rectangle transparent vous offre des effets visuels superposés, à la fois légers et indépendants de la résolution.

## Prérequis

Avant de plonger dans le code, assurez‑vous d’avoir :

- **Aspose.Page for .NET** – vous pouvez le télécharger [ici](https://releases.aspose.com/page/net/).
- Un environnement de développement .NET (Visual Studio, VS Code, ou tout IDE de votre choix).
- Un dossier où les fichiers XPS générés seront enregistrés.

## Importer les espaces de noms

Dans votre fichier C#, importez les espaces de noms requis :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Passons maintenant à la décomposition de la solution en étapes numérotées claires.

## Étape 1 : Initialiser XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Nous commençons par créer une instance `XpsDocument`, qui contiendra toutes les opérations de dessin suivantes.

## Étape 2 : Créer la géométrie de la grille magenta

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Cette géométrie définit le contour de la grille que le visual brush remplira.

## Étape 3 : Concevoir le VisualBrush de la grille magenta

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Ici, nous dessinons une petite tuile magenta qui sera répétée sur toute la grille.

## Étape 4 : Appliquer le VisualBrush à la grille

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

L'appel `CreateVisualBrush` lie la tuile magenta à la géométrie de la grille et active le carrelage.

## Étape 5 : Ajouter la grille au canevas

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Nous plaçons la grille carrelée sur un canevas et appliquons une transformation de translation afin qu'elle apparaisse à l'emplacement souhaité.

## Étape 6 : Ajouter un rectangle transparent

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Dans cette étape, nous **ajoutons un rectangle transparent** (la forme rouge avec `Opacity = 0.7f`). Ajustez la valeur d'opacité pour contrôler le degré de transparence du rectangle.

## Étape 7 : Enregistrer le document

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Le fichier XPS est écrit dans le dossier que vous avez spécifié précédemment.

## Cas d'utilisation courants

- **Mise en évidence de rapports :** Superposez un rectangle semi‑transparent pour mettre en avant un graphique ou un tableau.  
- **Effets de filigrane :** Combinez une grille carrelée avec une superposition transparente pour un branding discret.  
- **PDF/XPS interactifs :** Utilisez le motif comme arrière‑plan pour les champs de formulaire tout en conservant une interface lisible.

## Conseils de dépannage

- **Opacité non visible ?** Assurez‑vous que votre visualiseur prend en charge la transparence XPS ; certains visualiseurs plus anciens peuvent ignorer la propriété `Opacity`.  
- **Taille de tuile incorrecte ?** Vérifiez que le rectangle source (`new RectangleF(0f, 0f, 10f, 10f)`) correspond aux dimensions de la tuile vectorielle.  
- **Fichier non enregistré ?** Vérifiez que `dataDir` pointe vers un répertoire existant et accessible en écriture.

## Questions fréquemment posées

**Q : Puis‑je utiliser Aspose.Page for .NET à la fois dans des applications web et desktop ?**  
R : Oui, la bibliothèque fonctionne avec tous les types d’applications .NET.

**Q : Existe‑t‑il une version d’essai disponible avant l’achat ?**  
R : Absolument, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver un support supplémentaire ou des discussions communautaires ?**  
R : Consultez le [Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide de la communauté et des ingénieurs Aspose.

**Q : Comment obtenir une licence temporaire pour l’évaluation ?**  
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Quelle autre documentation est disponible pour Aspose.Page for .NET ?**  
R : Explorez la documentation complète [ici](https://reference.aspose.com/page/net/).

---

**Dernière mise à jour** : 2026-04-03  
**Testé avec** : Aspose.Page 24.12 for .NET  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}