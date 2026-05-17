---
date: 2026-02-25
description: Améliorez les documents PostScript avec un rectangle à dégradé linéaire
  en utilisant Aspose.Page pour .NET. Suivez notre guide étape par étape pour apprendre
  le remplissage de texte en dégradé et le contour de texte en dégradé.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Ajouter un rectangle à dégradé linéaire à PostScript (PS) avec Aspose.Page
url: /fr/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

Congratulations! ..." -> "Félicitations ! Vous avez ajouté avec succès un **rectangle à dégradé linéaire** à un document PostScript et utilisé le même pinceau pour le **remplissage de texte avec dégradé** et le **contour de texte avec dégradé**."

Translate "Common Use Cases & Tips" -> "Cas d'utilisation courants et conseils". Translate bullet points.

Translate "Frequently Asked Questions" -> "FAQ". Keep subheadings.

Translate Q1 etc.

Make sure to keep markdown formatting.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un rectangle à dégradé linéaire à PostScript (PS) avec Aspose.Page

## Introduction

Bienvenue dans ce tutoriel complet sur l'ajout d'un **rectangle à dégradé linéaire** aux documents PostScript (PS) à l'aide d'Aspose.Page pour .NET. Aspose.Page est une bibliothèque puissante qui vous permet de créer, modifier et rendre des documents dans divers formats, et aujourd'hui nous nous concentrerons sur la façon d'introduire des dégradés attrayants dans vos fichiers PS.

### Réponses rapides
- **Que fait le rectangle à dégradé linéaire ?** Il remplit une zone rectangulaire avec une transition de couleur fluide d'un côté à l'autre.  
- **Quelle API gère le texte avec remplissage dégradé ?** `LinearGradientBrush` combiné avec `SetPaint` et `FillAndStrokeText`.  
- **Puis-je tracer le texte avec un dégradé ?** Oui — utilisez `SetStroke` avec un pinceau dégradé et appelez `OutlineText`.  
- **Ai‑je besoin d'une licence pour la production ?** Une licence commerciale Aspose.Page est requise pour une utilisation non‑évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Pré‑requis

Avant de commencer, assurez‑vous d'avoir :

- Bibliothèque Aspose.Page pour .NET : assurez‑vous que la bibliothèque est référencée dans votre projet. Vous pouvez la télécharger depuis la [documentation Aspose.Page pour .NET](https://reference.aspose.com/page/net/).
- Répertoire de documents : créez un dossier sur le disque où le fichier PS généré sera enregistré et remplacez **« Your Document Directory »** dans le code par ce chemin.

## Importer les espaces de noms

Pour commencer, importez les espaces de noms qui vous donnent accès aux classes de dessin et spécifiques à PS :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Qu'est‑ce qu'un rectangle à dégradé linéaire ?

Un **rectangle à dégradé linéaire** est simplement une forme rectangulaire dont l'intérieur est peint avec un dégradé linéaire — les couleurs passent en douceur le long d'une ligne droite, généralement de gauche à droite (horizontal) ou de haut en bas (vertical). Dans Aspose.Page, vous obtenez cela en combinant un `GraphicsPath` qui définit le rectangle avec un `LinearGradientBrush` qui décrit la transition de couleur.

## Pourquoi utiliser le remplissage de texte avec dégradé et le contour de texte avec dégradé ?

- **Attrait visuel** : le texte rempli de dégradé ajoute de la profondeur et un style moderne aux rapports, factures ou supports promotionnels.  
- **Cohérence de marque** : associez les couleurs d'entreprise avec des valeurs ARGB précises.  
- **Polyvalence** : le même pinceau peut être réutilisé pour les remplissages de formes, les remplissages de texte et les dégradés de contour, réduisant ainsi la duplication de code.

## Étape 1 : Configurer le document

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 2 : Définir le rectangle dégradé et les couleurs

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Étape 3 : Définir la transformation pour le pinceau

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Étape 4 : Définir la peinture et remplir le rectangle

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Comment appliquer le remplissage de texte avec dégradé

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Utilisation du contour de texte avec dégradé

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Étape 7 : Fermer la page actuelle et enregistrer le document

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Félicitations ! Vous avez ajouté avec succès un **rectangle à dégradé linéaire** à un document PostScript et utilisé le même pinceau pour le **remplissage de texte avec dégradé** et le **contour de texte avec dégradé**.

## Cas d'utilisation courants et conseils

- **En‑têtes de rapports** : remplissez de grands blocs de texte avec des dégradés pour mettre en valeur les titres de sections.  
- **Logos de marque** : recréez les formes de logo avec des formes à remplissage dégradé pour une identité visuelle cohérente.  
- **Astuce pro** : réutilisez la même instance de `LinearGradientBrush` pour plusieurs appels de dessin afin de garder les couleurs parfaitement alignées entre les formes et le texte.

## FAQ

### Q1 : Puis‑je appliquer des dégradés à d'autres formes que les rectangles ?
**R :** Oui, vous pouvez appliquer des dégradés à toute forme définie par un `GraphicsPath`. Ajoutez simplement des cercles, des polygones ou des chemins personnalisés avant d'appeler `document.Fill(path)`.

### Q2 : Comment changer les couleurs du dégradé ?
**R :** Modifiez les valeurs `Color.FromArgb` lors de la construction du `LinearGradientBrush`. La première couleur est le départ, la seconde est la fin du dégradé.

### Q3 : Aspose.Page est‑il compatible avec différents formats de documents ?
**R :** Absolument. Aspose.Page prend en charge XPS, PS, PDF et plusieurs autres formats vectoriels. Consultez la documentation officielle pour la liste complète.

### Q4 : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?
**R :** Oui, une licence commerciale est disponible. Voir la page d'achat pour plus de détails : [here](https://purchase.aspose.com/buy).

### Q5 : Où puis‑je trouver du support communautaire ?
**R :** Rejoignez le forum communautaire Aspose.Page : [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Dernière mise à jour :** 2026-02-25  
**Testé avec :** Aspose.Page 24.10 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}