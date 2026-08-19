---
date: 2026-02-25
description: Apprenez à utiliser un pinceau de dégradé linéaire C# pour ajouter un
  dégradé aux fichiers PS et remplir un rectangle avec un dégradé en utilisant Aspose.Page
  pour .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Pinceau à dégradé linéaire – Ajouter un dégradé vertical au PostScript (PS)
  avec Aspose.Page
url: /fr/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# Linear Gradient Brush – Ajouter un dégradé vertical au PostScript (PS) avec Aspose.Page

## Introduction

Dans le domaine de la manipulation et de la création de documents, **Aspose.Page for .NET** se démarque comme un outil puissant pour les développeurs. Dans ce guide, vous découvrirez comment **ajouter un dégradé aux fichiers PS** en utilisant une **brosse de dégradé linéaire C#** pour **remplir un rectangle avec un dégradé**. À la fin de ce tutoriel, vous aurez une compréhension claire, étape par étape, du code requis et de la raison pour laquelle cette technique produit un dégradé vertical fluide dans votre sortie PostScript.

## Réponses rapides
- **Que fait une brosse de dégradé linéaire C# ?** Elle crée une transition douce entre plusieurs couleurs sur une forme.
- **Puis‑je l’utiliser avec n’importe quelle version .NET ?** Oui, Aspose.Page prend en charge .NET Framework 4.5+ et .NET Core/5+.
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour les builds non‑évaluatifs.
- **Le dégradé est‑il vraiment vertical ?** La brosse est tournée de 90°, assurant un flux vertical.
- **Où le fichier de sortie est‑il enregistré ?** Dans le chemin que vous spécifiez dans `dataDir` (par ex., `VerticalGradient_outPS.ps`).

## Qu’est‑ce qu’une brosse de dégradé linéaire C# ?
Une **brosse de dégradé linéaire C#** est un objet GDI+ (`LinearGradientBrush`) qui peint une transition de couleur linéaire entre des points définis. Lorsqu’elle est combinée avec l’API de dessin d’Aspose.Page, elle vous permet de rendre des dégradés sophistiqués directement dans un document PostScript (PS).

## Pourquoi utiliser une brosse de dégradé linéaire pour le PostScript ?
- **Sortie de haute qualité :** Les dégradés sont rendus au niveau de l’imprimante, préservant la fidélité.
- **Contrôle total :** Vous pouvez définir des arrêts de couleur personnalisés, la rotation et le redimensionnement.
- **Code réutilisable :** La même logique de brosse fonctionne pour PDF, SVG et d’autres formats pris en charge par Aspose.Page.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d’avoir les éléments suivants :

- Aspose.Page for .NET : Assurez‑vous d’avoir la bibliothèque Aspose.Page installée. Vous pouvez trouver les ressources nécessaires et la documentation [ici](https://reference.aspose.com/page/net/).
- Environnement de développement : Configurez un environnement de développement adapté, incluant un IDE pour le développement .NET.
- Connaissances de base : Familiarisez‑vous avec les bases du développement .NET, y compris la manipulation de flux, de chemins graphiques et de couleurs.

## Importer les espaces de noms

Dans votre projet C#, incluez les espaces de noms requis au début de votre fichier de code :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Configurer le répertoire du document

Commencez par spécifier le chemin vers votre répertoire de documents. C’est l’emplacement où votre document PS sera enregistré.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer le flux de sortie pour le document PostScript

Générez un flux de sortie pour le document PostScript en utilisant la classe `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Étape 3 : Créer les options d’enregistrement et le document PS

Créez des options d’enregistrement avec le format A4 et initialisez un nouveau document PS de 1 page.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 4 : Définir les dimensions du rectangle

Spécifiez les dimensions et la position du rectangle où le dégradé vertical sera appliqué.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Étape 5 : Créer le chemin graphique

Construisez un chemin graphique à partir du rectangle défini.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Étape 6 : Définir les couleurs d’interpolation

Établissez un tableau de couleurs d’interpolation et leurs positions pour le dégradé.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Étape 7 : Créer la brosse de dégradé linéaire

Formez une brosse de dégradé linéaire avec le rectangle comme limites, les couleurs de départ et d’arrivée.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Étape 8 : Définir la transformation de la brosse

Établissez une transformation pour la brosse, en veillant à ce que les composantes d’échelle X et Y correspondent à la largeur et à la hauteur du rectangle.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Étape 9 : Définir la peinture et remplir le rectangle

Définissez la peinture pour le document, et **remplissez le rectangle avec le dégradé** en utilisant le chemin précédemment défini.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Étape 10 : Fermer la page actuelle et enregistrer le document

Fermez la page actuelle et enregistrez le document PostScript.

```csharp
document.ClosePage();
document.Save();
```

Félicitations ! Vous avez réussi à **ajouter un dégradé vertical à un document PostScript** en utilisant une **brosse de dégradé linéaire C#** avec Aspose.Page for .NET. Expérimentez avec différents paramètres et couleurs pour obtenir divers effets visuels dans vos documents.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Comment corriger |
|----------|--------------------------|------------------|
| Le dégradé apparaît horizontal | Rotation de la brosse non appliquée | Assurez‑vous que `brushTransform.Rotate(90);` est appelé avant d’assigner à `brush.Transform`. |
| Les couleurs semblent délavées | Flux de sortie à basse résolution | Utilisez un `PsSaveOptions` à plus haute résolution ou augmentez la taille du document. |
| Le fichier de sortie est vide | Flux non vidé | Vérifiez que `document.Save();` est appelé en dehors du bloc `using`. |

## Foire aux questions

**Q1 : Puis‑je appliquer plusieurs dégradés à différentes régions du même document ?**  
R : Oui, vous pouvez. Répétez simplement les étapes pour chaque région avec ses dimensions et son jeu de couleurs spécifiques.

**Q2 : Comment intégrer ce code dans mon projet .NET existant ?**  
R : Copiez‑collez le code dans votre fichier de projet et assurez‑vous que la bibliothèque Aspose.Page est référencée.

**Q3 : Existe‑t‑il d’autres types de dégradés disponibles dans Aspose.Page pour .NET ?**  
R : Aspose.Page prend en charge divers types de dégradés, y compris les dégradés radiaux et de chemin. Consultez la documentation pour plus de détails.

**Q4 : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Oui, vous le pouvez. Visitez [ici](https://purchase.aspose.com/buy) pour explorer les options de licence.

**Q5 : Existe‑t‑il un forum communautaire pour Aspose.Page où je peux demander de l’aide ?**  
R : Bien sûr ! Rendez‑vous sur le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour échanger avec d’autres développeurs et obtenir de l’assistance.

**Dernière mise à jour :** 2026-02-25  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}