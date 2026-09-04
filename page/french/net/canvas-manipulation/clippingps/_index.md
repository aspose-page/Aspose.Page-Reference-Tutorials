---
date: 2026-06-25
description: Apprenez comment ajouter un chemin de découpe dans PostScript en utilisant
  Aspose.Page pour .NET – guide étape par étape avec les techniques du pinceau et
  du rectangle en pointillés.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: Découpage PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Comment ajouter un chemin de découpe à PostScript avec Aspose.Page pour .NET
url: /fr/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un chemin de découpe à PostScript avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel complet, vous apprendrez **comment ajouter un chemin de découpe** à un document PostScript (PS) en utilisant Aspose.Page pour .NET. Nous parcourrons chaque étape, vous montrerons comment **définir un pinceau**, et démontrerons comment **dessiner un rectangle en pointillés** autour du contenu découpé. À la fin, vous disposerez d’un fichier PS entièrement fonctionnel illustrant la découpe par forme, donnant à vos graphiques un aspect plus dynamique et professionnel.

## Réponses rapides
- **Que fait « add clipping path » ?** Il restreint les opérations de dessin à une forme définie, masquant tout ce qui se trouve en dehors de cette forme.  
- **Quelle bibliothèque gère la découpe dans .NET ?** Aspose.Page pour .NET fournit une API riche pour la manipulation de PS/EPS.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je changer la couleur du pinceau ?** Oui, utilisez `SetPaint` avec n’importe quel `SolidBrush` ou dégradé de votre choix.  
- **Est‑il possible de dessiner un rectangle en pointillés ?** Absolument – créez un `Pen` avec `DashStyle.Dash` et utilisez `Draw`.  

## Qu’est‑ce qu’un chemin de découpe dans PostScript ?

Un chemin de découpe définit la région visible des commandes de dessin suivantes, en éliminant tout ce qui est rendu en dehors de ses limites. En pratique, il vous permet de masquer des graphiques de sorte que seule la partie à l’intérieur du chemin soit affichée, ce qui est essentiel pour créer des compositions complexes sans modifier définitivement les objets d’origine.

## Comment ajouter un chemin de découpe à un document PostScript avec Aspose.Page ?

Chargez un `PsDocument`, définissez un chemin graphique (par exemple, un cercle), appliquez `Clip()` pour restreindre la zone de dessin, puis utilisez `SetPaint` et `Fill` pour rendre le contenu à l’intérieur de la région découpée. Après avoir restauré l’état graphique, vous pouvez dessiner des formes supplémentaires—comme un rectangle en pointillés—sans affecter la zone découpée. Cette séquence réalise la découpe en quelques appels d’API concis.

`PsDocument` représente un objet document PostScript.  
`GraphicsPath` est un conteneur vectoriel pour les formes géométriques.  
`Clip()` définit la région de découpe pour les dessins suivants.  
`SetPaint` assigne un pinceau utilisé pour remplir les formes.  
`Fill` rend le chemin actuel en utilisant la peinture actuelle.

## Pourquoi utiliser Aspose.Page pour la découpe ?

Aspose.Page prend en charge **plus de 50 formats d’entrée et de sortie**, y compris PS, EPS, PDF, SVG et les types d’image, et peut traiter des documents de plusieurs centaines de pages sans charger le fichier complet en mémoire. La bibliothèque n’a **aucune dépendance externe**, fonctionne sur **.NET Framework 4.5+**, **.NET Core 3.1+** et **.NET 6+**, et offre un contrôle complet sur l’état graphique (enregistrement/restauration, translation, rotation). Ces avantages quantifiés en font un choix fiable pour la génération de graphiques côté serveur.

## Prérequis

- Connaissances de base en programmation C#.  
- Bibliothèque Aspose.Page pour .NET installée – vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).  
- Visual Studio ou tout IDE .NET de votre choix.  

## Importer les espaces de noms

Les espaces de noms suivants vous donnent accès aux objets graphiques de base et aux options d’enregistrement spécifiques à PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Décomposons maintenant l’exemple en étapes claires et numérotées.

### Étape 1 : Définir le répertoire du document

Définissez le dossier où vos fichiers source et de sortie seront stockés. Cela facilite la localisation du fichier PS généré ultérieurement.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer le flux de sortie pour le document PostScript

Créez un flux d’écriture qui contiendra le fichier PS généré. L’utilisation d’un `FileStream` garantit que le fichier est écrit directement sur le disque.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Étape 3 : Créer les options d’enregistrement

`PsSaveOptions` est l’objet de configuration d’Aspose.Page pour la sortie PS. Il vous permet de contrôler la compression, la version et d’autres détails de rendu.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Étape 4 : Créer un nouveau document PS d’une page

`PsDocument` représente un objet document PostScript. Vous l’instanciez avec le flux de sortie et les options d’enregistrement que vous venez de configurer.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Étape 5 : Créer un chemin graphique à partir du rectangle

`GraphicsPath` est un conteneur vectoriel pour les formes géométriques. Ici, nous commençons avec un simple rectangle qui sera découpé plus tard.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Étape 6 : Découper par forme

Nous ajoutons un chemin de découpe à l’aide d’un cercle, définissons le pinceau de peinture en bleu, et remplissons le rectangle à l’intérieur de la région découpée. Cela montre comment la découpe limite le dessin à l’intérieur du cercle.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Étape 7 : Déplacer l’état graphique de niveau supérieur et dessiner un rectangle en pointillés

Après avoir restauré l’état graphique précédent, nous déplaçons le curseur, créons un `Pen` avec `DashStyle.Dash`, et dessinons un rectangle en pointillés autour du contenu découpé. Le trait bleu met en évidence la frontière de découpe.

`Pen` définit les attributs du trait tels que la couleur et le style de tiret.  
`DashStyle.Dash` spécifie un motif de ligne en pointillés.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Étape 8 : Fermer et enregistrer le document

Terminez la page, videz le flux et libérez les ressources. Le fichier PS est maintenant écrit sur le disque et prêt à être visualisé dans n’importe quel visualiseur PostScript.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Vous avez maintenant ajouté avec succès **un chemin de découpe**, défini un pinceau personnalisé, et dessiné un rectangle en pointillés autour de vos graphiques en utilisant Aspose.Page pour .NET.

## Problèmes courants et solutions

- **Découpage non visible :** Assurez‑vous d’appeler `WriteGraphicsSave()` avant la translation et `WriteGraphicsRestore()` après le remplissage.  
- **Couleurs incorrectes :** Vérifiez que `SetPaint` est appelé après `Clip` et avant `Fill`.  
- **Les lignes en pointillés apparaissent solides :** Assurez‑vous que le `DashStyle` du `Pen` est réglé sur `DashStyle.Dash` avant `SetStroke`.  

## Questions fréquentes

### Q1 : Puis‑je utiliser Aspose.Page pour .NET avec d’autres langages de programmation ?

R : Aspose.Page est principalement conçu pour les applications .NET, mais Aspose propose des bibliothèques équivalentes pour Java, C++ et d’autres plateformes.

### Q2 : Où puis‑je trouver des exemples supplémentaires et la documentation pour Aspose.Page pour .NET ?

R : Vous pouvez explorer davantage d’exemples et la documentation détaillée sur la [documentation Aspose.Page](https://reference.aspose.com/page/net/).

### Q3 : Existe‑t‑il un essai gratuit disponible pour Aspose.Page pour .NET ?

R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.Page pour .NET [ici](https://releases.aspose.com/).

### Q4 : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?

R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis‑je obtenir du support ou discuter des questions liées à Aspose.Page ?

R : Visitez les [forums Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

---

**Dernière mise à jour :** 2026-06-25  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment créer un document PostScript avec Aspose.Page pour .NET](/page/net/document-creation/create-postscript-document/)
- [Enregistrer un fichier PostScript avec les transformations Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [Créer un document postscript .net – Ajouter un rectangle avec Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}