---
title: Appliquer un motif de mosaïque de texture à PostScript (PS) avec Aspose.Page
linktitle: Appliquer un motif de mosaïque de texture à PostScript (PS)
second_title: API Aspose.Page .NET
description: Améliorez vos documents PostScript (PS) avec des modèles de mosaïque de texture à l'aide d'Aspose.Page pour .NET. Suivez notre guide étape par étape pour une touche créative.
weight: 10
url: /fr/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Appliquer un motif de mosaïque de texture à PostScript (PS) avec Aspose.Page

## Introduction

Bienvenue dans ce didacticiel étape par étape expliquant comment appliquer un motif de mosaïque de texture à un document PostScript (PS) à l'aide d'Aspose.Page pour .NET. Aspose.Page est une bibliothèque puissante qui vous permet de travailler avec différents formats de documents. Dans ce didacticiel, nous explorerons comment améliorer vos documents PS en ajoutant des motifs de mosaïque de texture.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :

- [Visual Studio](https://visualstudio.microsoft.com/) installé sur votre machine.
- Connaissance de base de la programmation C#.
-  Téléchargez et installez le[Aspose.Page pour la bibliothèque .NET](https://releases.aspose.com/page/net/).
- Un fichier image pour le motif de texture (par exemple, "TestTexture.bmp").

## Importer des espaces de noms

Dans votre code C#, assurez-vous d'importer les espaces de noms nécessaires :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Décomposons l'exemple fourni en plusieurs étapes pour vous guider tout au long du processus.

## Étape 1 : configurer le répertoire de documents

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```

Assurez-vous de remplacer « Votre répertoire de documents » par le chemin où vous souhaitez enregistrer votre document PS.

## Étape 2 : Créer un flux de sortie pour le document PS

```csharp
// Créer un flux de sortie pour un document PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Créez des options de sauvegarde au format A4
    PsSaveOptions options = new PsSaveOptions();

    // Créer un nouveau document PS d'une page
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Cette étape configure le flux de sortie du document PS, notamment en définissant la taille du document.

## Étape 3 : Appliquer un motif de carrelage texturé

```csharp
// Créer un objet Bitmap à partir du fichier image
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Créer un pinceau de texture à partir de l'image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //Ajouter une mise à l'échelle dans la direction X au motif
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Définir ce pinceau de texture comme peinture actuelle
    document.SetPaint(brush);
}
```

Cette étape consiste à créer un pinceau de texture à partir d'une image et à le définir comme peinture actuelle du document.

## Étape 4 : Créer un chemin rectangulaire et remplir

```csharp
// Créer un chemin rectangulaire
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Remplir le rectangle
document.Fill(path);
```

Ici, nous définissons un chemin rectangulaire et le remplissons avec le pinceau de texture précédemment défini.

## Étape 5 : Définir le trait et dessiner

```csharp
// Obtenir la peinture actuelle
Brush paint = document.GetPaint();

// Définir un trait rouge
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Tracez le rectangle
document.Draw(path);
```

Cette étape consiste à définir les propriétés du trait et à dessiner le rectangle délimité.

## Étape 6 : Remplir et décrire le texte avec un motif de texture

```csharp
// Remplir le texte avec un motif de texture
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Décrire le texte avec un motif de texture
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Enfin, nous remplissons et décrivons le texte avec le motif de texture, améliorant ainsi l'attrait visuel de votre document.

## Étape 7 : Enregistrer et fermer le document

```csharp
// Fermer la page actuelle
document.ClosePage();

// Enregistrez le document
document.Save();
```

Assurez-vous de fermer la page actuelle et d'enregistrer le document pour appliquer les modifications.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment appliquer un motif de mosaïque de texture à un document PostScript à l'aide d'Aspose.Page pour .NET. Expérimentez avec différentes images et modèles pour personnaliser davantage vos documents PS.

## FAQ

### Q1 : Puis-je utiliser d’autres formats d’image pour le motif de texture ?

A1 : Oui, Aspose.Page prend en charge différents formats d'image. Assurer la compatibilité avec la documentation de la bibliothèque.

### Q2 : Aspose.Page est-il compatible avec .NET Core ?

A2 : Oui, Aspose.Page est compatible avec .NET Framework et .NET Core.

### Q3 : Comment puis-je ajuster la taille du rectangle texturé ?

 A3 : Modifier les dimensions dans le`RectangleF` paramètres lors de la création du chemin.

### Q4 : Puis-je ajouter plusieurs motifs de texture à un seul document ?

A4 : Oui, vous pouvez répéter le processus avec des images et des chemins différents.

### Q5 : Où puis-je trouver des ressources et une assistance supplémentaires ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir le soutien de la communauté et explorer les[Documentation](https://reference.aspose.com/page/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
