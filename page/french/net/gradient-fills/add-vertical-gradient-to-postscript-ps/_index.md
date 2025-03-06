---
title: Ajouter un dégradé vertical à PostScript (PS) avec Aspose.Page
linktitle: Ajouter un dégradé vertical à PostScript (PS)
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter des dégradés verticaux visuellement attrayants aux documents PostScript (PS) dans .NET à l'aide d'Aspose.Page. Améliorez la création de vos documents avec ce guide étape par étape.
weight: 14
url: /fr/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé vertical à PostScript (PS) avec Aspose.Page

## Introduction

Dans le domaine de la manipulation et de la création de documents, Aspose.Page for .NET s'impose comme un outil puissant pour les développeurs. Ce didacticiel vous guidera tout au long du processus d'ajout d'un dégradé vertical à un document PostScript (PS) à l'aide d'Aspose.Page pour .NET. À la fin de ce guide, vous aurez une compréhension claire des étapes nécessaires pour obtenir cet effet visuellement attrayant.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants en place :

-  Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page est installée. Vous pouvez trouver les ressources et la documentation nécessaires[ici](https://reference.aspose.com/page/net/).

- Environnement de développement : mettre en place un environnement de développement approprié, y compris un environnement de développement intégré (IDE) pour le développement .NET.

- Compréhension de base : Familiarisez-vous avec les bases du développement .NET, notamment l'utilisation des flux, des chemins graphiques et de la manipulation des couleurs.

## Importer des espaces de noms

Dans votre projet C#, incluez les espaces de noms requis au début de votre fichier de code :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : configurer le répertoire de documents

Commencez par spécifier le chemin d'accès à votre répertoire de documents. C'est l'emplacement où votre document PS sera enregistré.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer un flux de sortie pour un document PostScript

Générez un flux de sortie pour le document PostScript à l'aide de la classe FileStream.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Étape 3 : Créer des options de sauvegarde et un document PS

Créez des options de sauvegarde au format A4 et initialisez un nouveau document PS d'une page.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 4 : Définir les dimensions du rectangle

Spécifiez les dimensions et la position du rectangle où le dégradé vertical sera appliqué.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Étape 5 : Créer un chemin graphique

Construisez un chemin graphique à partir du rectangle défini.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Étape 6 : Définir les couleurs d'interpolation

Établissez un tableau de couleurs et de positions d'interpolation pour le dégradé.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Étape 7 : Créer un pinceau dégradé linéaire

Formez un pinceau dégradé linéaire avec le rectangle comme limites, les couleurs de début et de fin.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Étape 8 : Définir la transformation du pinceau

Établissez une transformation pour le pinceau, en vous assurant que les composants des échelles X et Y correspondent à la largeur et à la hauteur du rectangle.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Étape 9 : définir la peinture et remplir le rectangle

Définissez la peinture du document et remplissez le rectangle précédemment défini.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Étape 10 : fermez la page actuelle et enregistrez le document

Fermez la page actuelle et enregistrez le document PostScript.

```csharp
document.ClosePage();
document.Save();
```

Toutes nos félicitations! Vous avez ajouté avec succès un dégradé vertical à un document PostScript à l'aide d'Aspose.Page pour .NET. Expérimentez avec différents paramètres et couleurs pour obtenir divers effets visuels dans vos documents.

## Conclusion

Dans ce didacticiel, nous avons exploré le processus d'amélioration de vos documents PostScript en incorporant des dégradés verticaux. Aspose.Page pour .NET fournit un environnement transparent pour de telles manipulations, permettant aux développeurs de créer sans effort des documents visuellement époustouflants.

## FAQ

### Q1 : Puis-je appliquer plusieurs dégradés à différentes régions du même document ?

A1 : Oui, vous pouvez. Répétez simplement les étapes pour chaque région avec ses dimensions et sa palette de couleurs spécifiques.

### Q2 : Comment puis-je intégrer ce code dans mon projet .NET existant ?

A2 : copiez et collez le code dans votre fichier de projet et assurez-vous que la bibliothèque Aspose.Page est référencée.

### Q3 : Existe-t-il d'autres types de dégradés disponibles dans Aspose.Page pour .NET ?

A3 : Aspose.Page prend en charge différents types de dégradés, notamment les dégradés radiaux et de chemin. Reportez-vous à la documentation pour plus de détails.

### Q4 : Puis-je utiliser Aspose.Page pour des projets commerciaux ?

 A4 : Oui, vous pouvez. Visite[ici](https://purchase.aspose.com/buy) pour explorer les options de licence.

### Q5 : Existe-t-il un forum communautaire pour Aspose.Page où je peux demander de l'aide ?

 A5 : Certainement ! Dirigez-vous vers le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour vous connecter avec d'autres développeurs et obtenir de l'aide.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
