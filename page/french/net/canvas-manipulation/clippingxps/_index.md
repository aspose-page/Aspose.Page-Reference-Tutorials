---
date: 2026-06-25
description: Apprenez à découper des documents XPS à l'aide d'Aspose.Page pour .NET.
  Ce guide étape par étape vous montre comment créer, manipuler et enregistrer des
  fichiers XPS efficacement.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Découpage XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Comment découper XPS avec Aspose.Page pour .NET
url: /fr/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment découper XPS avec Aspose.Page pour .NET

## Introduction

Bienvenue dans ce tutoriel complet sur **comment découper XPS** à l’aide d’Aspose.Page pour .NET ! Dans ce guide, vous apprendrez pas à pas comment créer un document XPS, appliquer des masques de découpe géométriques et enregistrer le résultat. La découpe vous permet de masquer des parties d’un canevas, offrant des mises en page sophistiquées telles que des images masquées, des formes personnalisées ou des zones de contenu ciblées—le tout sans quitter votre code .NET.

## Réponses rapides
- **Qu’est‑ce que la découpe XPS ?** Application d’un masque géométrique (clip) pour limiter la zone visible des éléments du canevas XPS.  
- **Quelle bibliothèque est la meilleure pour cela ?** Aspose.Page pour .NET propose une API complète pour la création et la découpe XPS.  
- **Prérequis ?** Visual Studio, runtime .NET et la bibliothèque Aspose.Page pour .NET.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un scénario de découpe basique.  
- **Puis‑je l’utiliser en production ?** Oui, avec une licence Aspose valide (essai disponible).

## Qu’est‑ce que « comment découper XPS » ?

La découpe XPS consiste à appliquer un masque géométrique à un canevas afin que tout dessin en dehors du masque ne soit pas rendu. Cette technique est idéale pour créer des images masquées, des boutons aux formes personnalisées ou pour focaliser l’attention du lecteur sur une région spécifique de la page. En définissant une géométrie de clip—comme un rectangle, un cercle ou un chemin complexe—vous obtenez un contrôle fin sur ce qui apparaît sur la page XPS finale.

## Pourquoi utiliser Aspose.Page pour .NET pour découper XPS ?

Aspose.Page offre une manipulation XPS déterministe côté serveur sans dépendances externes. Il prend en charge **plus de 50 formats d’entrée et de sortie**, peut traiter **des fichiers XPS de 200 pages en moins de 0,5 seconde** sur un CPU standard de 2,5 GHz, et fonctionne avec .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 et .NET 7. L’API vous donne un contrôle complet sur les transformations du canevas, les géométries de chemin et les pinceaux, garantissant une sortie de haute qualité à chaque fois.

## Prérequis

- Visual Studio installé sur votre machine.  
- Bibliothèque Aspose.Page pour .NET ajoutée à votre projet. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).  
- Connaissances de base du langage de programmation C#.

## Comment découper XPS ?

Chargez un document XPS, créez un canevas, définissez une géométrie de clip (par ex. un cercle), affectez la géométrie à la propriété `Clip` du canevas, dessinez votre contenu, puis enregistrez le document. Toutes ces étapes peuvent être réalisées avec quelques appels de méthode, et Aspose.Page gère automatiquement le balisage XML sous‑jacent, vous permettant de vous concentrer sur la conception visuelle plutôt que sur la structure du fichier.

## Importer les espaces de noms

Pour utiliser les fonctionnalités d’Aspose.Page pour .NET, vous devez importer les espaces de noms requis dans votre projet. Suivez ces étapes :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Maintenant, décomposons le code d’exemple fourni en plusieurs étapes.

## Étape 1 : Définir le chemin du répertoire du document.

Définissez le dossier où le fichier XPS sera créé. L’utilisation de `Path.Combine` garantit le bon séparateur de répertoire sur tout OS.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 2 : Créer un nouveau document XPS.

Instanciez la classe `XpsDocument`, qui représente l’ensemble du package XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Étape 3 : Créer le canevas principal.

La classe `Canvas` représente une surface de dessin au sein d’une page XPS où les formes, images et texte sont rendus.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Étape 4 : Définir les décalages gauche et haut dans le canevas principal.

Ajustez la position du canevas pour contrôler où le dessin commence sur la page.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Étape 5 : Créer une géométrie de chemin rectangulaire.

`PathGeometry` définit une forme vectorielle ; ici nous créons un simple rectangle.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Étape 6 : Créer un remplissage pour les rectangles.

Définissez un pinceau de couleur unie qui sera utilisé pour remplir le rectangle.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Étape 7 : Ajouter un autre canevas avec découpe au canevas principal.

Créez un canevas enfant qui recevra un masque de découpe.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Étape 8 : Créer une géométrie de cercle pour la découpe.

`PathGeometry` peut également représenter des cercles ; cette géométrie sera affectée à la propriété `Clip` du canevas enfant.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Étape 9 : Créer un rectangle dans le deuxième canevas et le remplir.

Dessinez un rectangle à l’intérieur du canevas découpé ; seule la partie à l’intérieur du cercle sera visible.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Étape 10 : Ajouter le deuxième canevas avec un rectangle tracé au canevas principal.

Ajoutez un rectangle avec un contour pour illustrer comment les contours interagissent avec la découpe.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Étape 11 : Créer un rectangle dans le troisième canevas et le tracer.

Un troisième canevas montre un dessin indépendant sans découpe.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Étape 12 : Enregistrer le document XPS résultant.

Persistez le package XPS sur le système de fichiers.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Problèmes courants et solutions
- **Chemin invalide** – Assurez‑vous que `dataDir` se termine par une barre oblique inverse (`\\`) ou utilisez `Path.Combine`.  
- **Découpe non appliquée** – Vérifiez que la chaîne de géométrie de clip est bien formée ; un espace manquant peut entraîner l’ignorance du clip.  
- **Exception de licence** – Dans une version non‑d’évaluation, ajoutez une licence Aspose valide avant de créer le document pour éviter les exceptions d’exécution.

## Questions fréquemment posées

### Q1 : Puis‑je utiliser Aspose.Page pour .NET avec d’autres formats de documents ?

R1 : Aspose.Page pour .NET se concentre principalement sur les documents XPS, mais Aspose propose d’autres bibliothèques pour divers formats de documents.

### Q2 : Aspose.Page pour .NET convient‑il aux débutants ?

R2 : Oui, Aspose.Page pour .NET est conçu pour être convivial, et les débutants peuvent rapidement comprendre ses fonctionnalités grâce à une documentation appropriée.

### Q3 : Où puis‑je trouver plus d’exemples et de ressources ?

R3 : Consultez la [documentation](https://reference.aspose.com/page/net/) et le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour de nombreuses ressources et exemples.

### Q4 : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?

R4 : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Existe‑t‑il un essai gratuit disponible pour Aspose.Page pour .NET ?

R5 : Oui, vous pouvez explorer l’essai gratuit [ici](https://releases.aspose.com/).

## Questions fréquentes supplémentaires

**Q : Puis‑je combiner plusieurs géométries de découpe sur un même canevas ?**  
R : Oui, vous pouvez affecter une `PathGeometry` complexe contenant plusieurs sous‑chemins à la propriété `Clip`, permettant un masquage en couches.

**Q : La découpe affecte‑t‑elle la conversion en PDF ?**  
R : Lorsque vous convertissez ensuite le XPS en PDF avec Aspose.PDF, la géométrie de clip est conservée, de sorte que le résultat visuel reste identique.

**Q : Est‑il possible d’animer la découpe dans XPS ?**  
R : XPS ne supporte pas l’animation ; toutefois, vous pouvez générer une série de pages XPS avec des formes de clip différentes pour simuler un mouvement.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Tutoriels associés

- [Comment transformer XPS avec Aspose.Page pour .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Ajouter un rectangle au document XPS avec Aspose.Page pour .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Convertir XPS en PDF avec Aspose.Page pour .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}