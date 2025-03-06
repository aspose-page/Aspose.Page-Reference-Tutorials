---
title: Ajoutez un rectangle à PostScript (PS) avec Aspose.Page pour .NET
linktitle: Ajouter un rectangle à PostScript (PS)
second_title: API Aspose.Page .NET
description: Améliorez la création de documents dans .NET avec Aspose.Page. Apprenez à ajouter des rectangles aux fichiers PostScript (PS), étape par étape.
weight: 12
url: /fr/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajoutez un rectangle à PostScript (PS) avec Aspose.Page pour .NET

## Introduction

Si vous souhaitez améliorer vos capacités de création de documents dans .NET, Aspose.Page fournit une solution puissante pour gérer les documents PostScript. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout de rectangles à un document PostScript à l'aide d'Aspose.Page pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Bibliothèque Aspose.Page pour .NET : téléchargez et installez la bibliothèque Aspose.Page pour .NET à partir de[ici](https://releases.aspose.com/page/net/).

- Environnement de développement : assurez-vous d'avoir un environnement de développement .NET configuré sur votre ordinateur.

## Importer des espaces de noms

Avant de commencer à coder, assurez-vous d'importer les espaces de noms nécessaires pour accéder aux classes et méthodes requises :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Maintenant, décomposons l'exemple en plusieurs étapes :

## Étape 1 : Configurez votre répertoire de documents

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```

Dans cette étape, remplacez « Votre répertoire de documents » par le chemin où vous souhaitez enregistrer votre document PostScript.

## Étape 2 : Créer un flux de sortie pour un document PostScript

```csharp
//Créer un flux de sortie pour un document PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ici, nous créons un flux de sortie pour le document PostScript et spécifions le nom du fichier ("AddRectangle_outPS.ps"). Ajustez le nom et l'emplacement du fichier selon vos préférences.

## Étape 3 : Définir les options d'enregistrement et créer un document PS

```csharp
//Créez des options de sauvegarde au format A4
PsSaveOptions options = new PsSaveOptions();

// Créer un nouveau document PS d'une page
PsDocument document = new PsDocument(outPsStream, options, false);
```

Définissez les options d'enregistrement en spécifiant le format de page souhaité (A4 dans ce cas). Ensuite, créez un nouveau document PostScript d'une seule page.

## Étape 4 : ajouter un rectangle et remplir

```csharp
//Créer un chemin graphique à partir du premier rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Définir la peinture
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Remplissez le rectangle
document.Fill(path);
```

Ici, nous créons un chemin graphique représentant le premier rectangle, définissons la couleur de la peinture (dans ce cas, orange) et remplissons le rectangle.

## Étape 5 : ajouter un autre rectangle et un autre contour

```csharp
//Créer un chemin graphique à partir du deuxième rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Définir la course
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Tracer (décrire) le rectangle
document.Draw(path);
```

Semblable à l'étape précédente, nous créons un chemin graphique pour le deuxième rectangle, définissons la couleur du trait (rouge avec une épaisseur de 3) et décrivons le rectangle.

## Étape 6 : fermez la page et enregistrez le document

```csharp
//Fermer la page actuelle
document.ClosePage();

//Enregistrez le document
document.Save();
```

Enfin, fermez la page actuelle et enregistrez l'intégralité du document.

## Conclusion

Toutes nos félicitations! Vous avez ajouté avec succès des rectangles à un document PostScript à l'aide d'Aspose.Page pour .NET. Ce tutoriel a couvert les étapes essentielles, de la configuration de votre environnement de développement à l'enregistrement du document final.

## FAQ

### Q1 : Puis-je personnaliser les couleurs des rectangles ?

A1 : Oui, vous pouvez personnaliser les couleurs en ajustant les paramètres dans le`SolidBrush` et`Pen` Des classes.

### Q2 : Aspose.Page est-il compatible avec d’autres formats de documents ?

A2 : Oui, Aspose.Page prend en charge divers formats de documents, notamment XPS et PostScript.

### Q3 : Comment puis-je ajouter du texte au document ?

 A3 : Vous pouvez utiliser le`TextFragment` classe dans Aspose.Page pour ajouter du texte à votre document.

### Q4 : Où puis-je trouver des exemples et de la documentation supplémentaires ?

 A4 : Explorer la documentation[ici](https://reference.aspose.com/page/net/) et visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien de la communauté.

### Q5 : Puis-je essayer Aspose.Page avant d’acheter ?

 A5 : Oui, vous pouvez obtenir une version d'essai gratuite[ici](https://releases.aspose.com/) , et pour une utilisation prolongée, envisagez un[permis temporaire](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
