---
date: 2026-01-05
description: Apprenez à transformer les documents XPS sans effort avec Aspose.Page
  pour .NET. Suivez notre guide étape par étape pour des transformations fluides.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Comment transformer XPS avec Aspose.Page pour .NET
url: /fr/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment transformer XPS avec Aspose.Page pour .NET

## Introduction

Welcome to the world of Aspose.Page for .NET, a powerful library that enables you to perform various transformations on XPS documents effortlessly. **In this tutorial, you’ll discover how to transform XPS documents using Aspose.Page for .NET**, whether you’re a seasoned developer or just getting started. We’ll walk through each step, explain the reasoning behind every transformation, and give you practical tips you can apply in real projects.

## Réponses rapides
- **Que pouvez‑vous réaliser ?** Créer, translater, mettre à l’échelle et faire pivoter des éléments de canevas XPS par programme.  
- **Quelle bibliothèque est requise ?** Aspose.Page for .NET (dernière version).  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Plateformes prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour les transformations de base présentées ici.

## Qu’est‑ce que « how to transform xps » ?
The phrase *how to transform xps* refers to programmatically modifying the layout, size, and orientation of elements inside an XPS (XML Paper Specification) document. Using Aspose.Page, you can apply matrix‑based transformations to canvases, giving you fine‑grained control over positioning, scaling, and rotation without manually editing the XPS XML.

## Pourquoi utiliser Aspose.Page pour les transformations XPS ?
- **Full .NET integration** – works seamlessly with Visual Studio, Rider, and other IDEs.  
- **No external dependencies** – the API handles all low‑level XPS details for you.  
- **Rich transformation support** – translate, scale, rotate, and combine multiple transforms in a single call.  
- **Performance‑optimized** – suitable for generating reports, invoices, or any printable graphics on the fly.

## Prérequis

Before we begin, make sure you have:

- **Aspose.Page for .NET Library** – download and install it from the official documentation: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, Visual Studio Code, or any other .NET‑compatible IDE.  
- **Document Directory** – a folder on your machine where you’ll read/write XPS files. Replace the placeholder in the code with the actual path.

Now that we have everything set up, let’s dive into the code.

## Importer les espaces de noms

First, import the namespaces that expose the Aspose.Page classes you’ll need:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Comment transformer XPS – Guide étape par étape

### Étape 1 : créer un nouveau document XPS

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explanation*: We start by defining the folder that holds our source and output files, then instantiate an empty `XpsDocument`. This object will be the canvas for all subsequent transformations.

### Étape 2 : créer un canevas principal

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Why this matters*: The main canvas acts as a container for all other canvases. By applying a small offset we ensure the content isn’t clipped at the page edge.

### Étape 3 : créer une géométrie de chemin rectangulaire

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: The path string follows the standard XPS path syntax (`M` for move, `L` for line, `Z` to close). Adjust the coordinates to change rectangle size.

### Étape 4 : ajouter un remplissage pour les rectangles

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Use `CreateColor` with RGB values to match your brand palette.

### Étape 5 : ajouter un nouveau canevas sans transformations

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Here we simply place a rectangle on the page with no extra transformation—useful as a baseline element.

### Étape 6 : ajouter un nouveau canevas avec transformation de translation

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*What’s happening?* The first matrix moves the rectangle down by 200 units. The subsequent `Translate` call shifts it 500 units to the right, demonstrating how multiple translations can be chained.

### Étape 7 : ajouter un nouveau canevas avec double transformation d’échelle

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Why scale?* Scaling by 2 doubles the rectangle’s width and height, letting you create larger graphics without redefining the geometry.

### Étape 8 : ajouter un nouveau canevas avec rotation autour d’un point

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Key insight*: `RotateAround` pivots the canvas around a custom point (here (100, 50)), giving you fine control over rotation anchors.

### Étape 9 : enregistrer le document XPS résultant

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

After all transformations are applied, the document is persisted to `output1.xps`. Open the file in any XPS viewer to see the stacked rectangles with their respective translations, scaling, and rotation.

## Problèmes courants & dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Fichier de sortie vide | `dataDir` pointe vers un dossier inexistant | Assurez‑vous que le répertoire existe ou utilisez un chemin absolu |
| Les rectangles ne sont pas positionnés comme prévu | Valeurs de matrice incorrectes | Vérifiez l’ordre des appels `Translate`, `Scale` et `RotateAround` |
| Les couleurs sont incorrectes | Valeurs RGB hors de la plage 0‑255 | Utilisez des valeurs d’octet valides pour chaque canal |

## Questions fréquentes

**Q : Aspose.Page for .NET est‑il compatible avec tous les environnements de développement .NET ?**  
A : Oui, il fonctionne parfaitement avec Visual Studio, Visual Studio Code, Rider et tout IDE supportant .NET.

**Q : Où puis‑je trouver des exemples supplémentaires et la documentation détaillée de l’API ?**  
A : Consultez la documentation officielle à [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q : Puis‑je essayer Aspose.Page avant d’acheter une licence ?**  
A : Absolument. Un essai gratuit est disponible ici : [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour les tests ?**  
A : Vous pouvez en demander une via la page de licence temporaire : [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q : Où acheter une licence complète ?**  
A : Achetez‑la directement dans la boutique Aspose : [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-01-05  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}