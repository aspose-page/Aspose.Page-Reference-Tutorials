---
date: 2026-03-26
description: Apprenez à créer des documents PostScript .NET avec des motifs de tuiles
  de texture en utilisant Aspose.Page. Suivez notre guide étape par étape pour ajouter
  des textures riches à vos fichiers PS.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Créer un document PostScript .NET avec du carrelage de texture
url: /fr/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document PostScript .NET avec un motif de texture en mosaïque

## Comment créer un document PostScript .NET avec un motif de texture en mosaïque

Dans ce tutoriel, vous apprendrez à **créer un document PostScript .NET** et à l’enrichir d’un motif de texture en mosaïque à l’aide de la bibliothèque Aspose.Page. Nous parcourrons chaque étape, de la configuration de votre projet au remplissage et au contour du texte avec le pinceau de texture, afin que vous puissiez produire des fichiers PS visuellement attrayants en quelques minutes.

## Réponses rapides
- **Quelle bibliothèque est utilisée ?** Aspose.Page pour .NET  
- **Puis‑je utiliser .NET Core ?** Oui, la bibliothèque prend en charge .NET Core et .NET 5/6  
- **Quels formats d’image fonctionnent pour la texture ?** Tout format pris en charge par System.Drawing (BMP, PNG, JPEG, etc.)  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un exemple de base  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour les tests ; une licence est requise pour la production  

## Prérequis

- [Visual Studio](https://visualstudio.microsoft.com/) installé sur votre machine.  
- Connaissances de base en programmation C#.  
- Téléchargez et installez la [bibliothèque Aspose.Page pour .NET](https://releases.aspose.com/page/net/).  
- Un fichier image pour le motif de texture (par ex., **TestTexture.bmp**).

## Importer les espaces de noms

Dans votre fichier C#, importez les espaces de noms requis afin que le compilateur sache où trouver les types que nous allons utiliser :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Configurer le répertoire du document

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Remplacez **Your Document Directory** par le dossier où vous souhaitez enregistrer le fichier PS généré.

## Étape 2 : Créer le flux de sortie pour le document PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Ce bloc ouvre un flux de fichier, configure la taille de page (A4 par défaut) et crée une nouvelle instance **PsDocument** sur laquelle nous allons dessiner.

## Étape 3 : Appliquer le motif de texture en mosaïque

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Ici nous chargeons le bitmap, l’enveloppons dans un **TextureBrush**, l’étirons éventuellement horizontalement, puis indiquons au **PsDocument** d’utiliser ce pinceau pour les opérations de dessin suivantes.

## Étape 4 : Créer le chemin du rectangle et le remplir

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Un rectangle simple est défini et rempli avec le pinceau de texture que nous avons configuré précédemment.

## Étape 5 : Définir le trait et dessiner

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Nous récupérons le pinceau actuel (le TextureBrush), créons un crayon rouge pour le contour et dessinons la bordure du rectangle.

## Étape 6 : Remplir et tracer le texte avec le motif de texture

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Cette étape montre la capacité **fill and stroke text** : les caractères « ABC » sont remplis avec le pinceau de texture puis contournés, produisant un effet visuel saisissant.

## Étape 7 : Enregistrer et fermer le document

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

La fermeture de la page finalise les commandes de dessin, et `Save()` écrit le fichier PostScript sur le disque.

## Problèmes courants et solutions

- **La texture apparaît étirée de façon incorrecte** – Ajustez les valeurs de `Matrix` pour contrôler l’échelle en X/Y.  
- **Image introuvable** – Vérifiez que `dataDir` pointe vers le bon dossier et que le nom du fichier correspond exactement, y compris la casse.  
- **Les couleurs semblent fausses** – Rappelez‑vous que PostScript utilise un espace couleur indépendant du dispositif ; assurez‑vous d’utiliser des objets `Color` correctement mappés.

## Questions fréquemment posées

**Q :** Puis‑je utiliser d’autres formats d’image pour le motif de texture ?  
**R :** Oui, tout format pris en charge par `System.Drawing.Bitmap` (BMP, PNG, JPEG, GIF, etc.) fonctionne.

**Q :** Aspose.Page est‑il compatible avec .NET Core ?  
**R :** Absolument. La bibliothèque fonctionne sur .NET Framework, .NET Core et .NET 5/6.

**Q :** Comment modifier la taille du rectangle texturé ?  
**R :** Modifiez les valeurs de `RectangleF` dans l’étape de création du rectangle (par ex., `new RectangleF(0, 0, 300, 150)`).

**Q :** Puis‑je appliquer plusieurs motifs de texture dans un même document ?  
**R :** Oui. Créez simplement un nouveau `TextureBrush` avec une image différente et appelez à nouveau `SetPaint` avant de dessiner la forme ou le texte suivant.

**Q :** Où trouver plus d’exemples et la référence API ?  
**R :** Consultez le [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pour l’aide de la communauté et la [documentation officielle](https://reference.aspose.com/page/net/) pour une utilisation détaillée de l’API.

## Conclusion

Vous savez maintenant comment **créer un document PostScript .NET** et appliquer un motif de texture en mosaïque, y compris comment **remplir et tracer du texte** avec cette texture. Expérimentez avec différentes images, matrices d’échelle et primitives de dessin pour produire des fichiers PS personnalisés pour des rapports, flyers ou toute sortie graphique lourde.

---

**Dernière mise à jour :** 2026-03-26  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}