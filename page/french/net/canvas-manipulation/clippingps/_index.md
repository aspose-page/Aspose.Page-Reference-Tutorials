---
date: 2026-01-05
description: Apprenez à ajouter un chemin de découpe dans PostScript en utilisant
  Aspose.Page pour .NET – guide étape par étape avec les techniques de définition
  du pinceau et de dessin d’un rectangle en pointillés.
linktitle: Clipping PS
second_title: Aspose.Page .NET API
title: Ajouter un chemin de détourage à PS avec Aspose.Page pour .NET
url: /fr/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un chemin de découpe à PS avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel complet, vous découvrirez comment **ajouter un chemin de découpe** à un document PostScript (PS) en utilisant Aspose.Page pour .NET. Nous parcourrons chaque étape, vous montrerons comment **définir le pinceau**, et démontrerons comment **dessiner un rectangle en pointillé** autour du contenu découpé. À la fin, vous disposerez d’un fichier PS entièrement fonctionnel illustrant la découpe par forme, rendant vos graphiques plus dynamiques et professionnels.

## Réponses rapides
- **Que fait « ajouter un chemin de découpe » ?** Il limite les opérations de dessin à une forme définie, masquant tout ce qui se trouve en dehors de cette forme.  
- **Quelle bibliothèque gère la découpe sous .NET ?** Aspose.Page pour .NET offre une API riche pour la manipulation de PS/EPS.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je changer la couleur du pinceau ?** Oui, utilisez `SetPaint` avec n’importe quel `SolidBrush` ou dégradé de votre choix.  
- **Est‑il possible de dessiner un rectangle en pointillé ?** Absolument – créez un `Pen` avec `DashStyle.Dash` et utilisez `Draw`.  

## Qu’est‑ce qu’un chemin de découpe dans PostScript ?
Un chemin de découpe définit la région visible des commandes de dessin suivantes. Tout ce qui est dessiné en dehors du chemin est ignoré, vous permettant de créer des graphiques masqués complexes sans modifier le contenu original.

## Pourquoi utiliser Aspose.Page pour la découpe ?
- **Aucune dépendance externe** – bibliothèque pure .NET.  
- **Contrôle total** sur l’état graphique (save/restore, translate, rotate).  
- **Primitives de dessin riches** telles que `SetPaint`, `Clip` et `Draw` avec des stylos et pinceaux personnalisables.  

## Prérequis

- Connaissances de base en programmation C#.  
- Bibliothèque Aspose.Page pour .NET installée – vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).  
- Visual Studio ou tout IDE .NET de votre choix.  

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms nécessaires à la manipulation graphique :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Passons maintenant à la décomposition de l’exemple en étapes numérotées claires.

### Étape 1 : Définir le répertoire du document

Définissez le dossier où vos fichiers source et de sortie seront stockés.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Étape 2 : Créer le flux de sortie pour le document PostScript

Créez un flux inscriptible qui contiendra le fichier PS généré.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Étape 3 : Créer les options d’enregistrement

Instanciez `PsSaveOptions` avec les paramètres par défaut. Vous pourrez les personnaliser plus tard si nécessaire.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Étape 4 : Créer un nouveau document PS d’une page

Initialisez l’objet `PsDocument` qui représente votre fichier PS.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Étape 5 : Créer un chemin graphique à partir du rectangle

Nous utiliserons un rectangle comme forme de base qui sera ensuite découpée.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Étape 6 : Découper par forme

Ici nous **ajoutons un chemin de découpe** en utilisant un cercle, **définissons le pinceau** en bleu, et remplissons le rectangle à l’intérieur de la région découpée.

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

### Étape 7 : Déplacer l’état graphique de niveau supérieur et dessiner un rectangle en pointillé

Après avoir restauré l’état précédent, nous déplaçons à nouveau le curseur graphique, **dessinons un rectangle en pointillé**, et appliquons un trait bleu.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Étape 8 : Fermer et enregistrer le document

Terminez la page et écrivez le fichier PS sur le disque.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Vous avez maintenant ajouté avec succès un **chemin de découpe**, défini un pinceau personnalisé et dessiné un rectangle en pointillé autour de vos graphiques en utilisant Aspose.Page pour .NET.

## Problèmes courants et solutions

- **Découpe non visible :** Assurez‑vous d’appeler `WriteGraphicsSave()` avant la translation et `WriteGraphicsRestore()` après le remplissage.  
- **Couleurs incorrectes :** Vérifiez que `SetPaint` est appelé après `Clip` et avant `Fill`.  
- **Les lignes pointillées apparaissent solides :** Assurez‑vous que la propriété `DashStyle` du `Pen` est réglée sur `DashStyle.Dash` avant `SetStroke`.  

## Questions fréquemment posées

### Q1 : Puis‑je utiliser Aspose.Page pour .NET avec d’autres langages de programmation ?
R : Aspose.Page est principalement conçu pour les applications .NET. Cependant, Aspose propose des bibliothèques similaires pour d’autres langages de programmation.

### Q2 : Où puis‑je trouver des exemples supplémentaires et la documentation d’Aspose.Page pour .NET ?
R : Vous pouvez explorer davantage d’exemples et la documentation détaillée sur la [documentation Aspose.Page](https://reference.aspose.com/page/net/).

### Q3 : Existe‑t‑il un essai gratuit d’Aspose.Page pour .NET ?
R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.Page pour .NET [ici](https://releases.aspose.com/).

### Q4 : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?
R : Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis‑je obtenir du support ou discuter des questions liées à Aspose.Page ?
R : Visitez les [forums Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

---

**Dernière mise à jour :** 2026-01-05  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}