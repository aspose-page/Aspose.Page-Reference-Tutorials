---
title: Ajouter un dégradé horizontal à PostScript (PS) avec Aspose.Page
linktitle: Ajouter un dégradé horizontal à PostScript (PS)
second_title: API Aspose.Page .NET
description: Améliorez les documents PostScript avec de superbes dégradés horizontaux à l'aide d'Aspose.Page pour .NET. Suivez notre didacticiel étape par étape pour une mise en œuvre transparente.
weight: 12
url: /fr/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé horizontal à PostScript (PS) avec Aspose.Page

## Introduction

Bienvenue dans ce didacticiel complet sur l'ajout de dégradés horizontaux aux documents PostScript (PS) à l'aide d'Aspose.Page pour .NET. Aspose.Page est une bibliothèque puissante qui facilite la manipulation de documents dans différents formats, fournissant aux développeurs les outils dont ils ont besoin pour créer, modifier et restituer des documents de manière transparente.

Dans ce didacticiel, nous nous concentrerons sur l'amélioration de vos documents PostScript en incorporant des dégradés horizontaux accrocheurs. Nous vous guiderons à travers chaque étape du processus, en veillant à ce que vous acquériez une solide compréhension de la mise en œuvre.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est intégrée à votre environnement de développement. Vous pouvez le télécharger depuis le[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/).

- Répertoire de documents : configurez un répertoire pour stocker vos documents et remplacez "Votre répertoire de documents" dans le code fourni par le chemin réel.

Voyons maintenant comment ajouter un dégradé horizontal à un document PostScript, étape par étape.

## Importer des espaces de noms

Avant de commencer, il est essentiel d'importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par Aspose.Page. Ajoutez les espaces de noms suivants au début de votre code :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : configurer le document

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";

// Créer un flux de sortie pour un document PostScript
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Créez des options de sauvegarde au format A4
    PsSaveOptions options = new PsSaveOptions();

    // Créer un nouveau document PS d'une page
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 2 : Définir le rectangle de dégradé et les couleurs

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Créer un chemin graphique à partir du premier rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //Créez un pinceau dégradé linéaire avec un rectangle comme limites, des couleurs de début et de fin
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Étape 3 : Définir la transformation pour le pinceau

```csharp
    // Créez une transformation pour le pinceau. Les composants des échelles X et Y doivent être égaux à la largeur et à la hauteur du rectangle en conséquence.
    // Les composants de translation sont des décalages du rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Définir la transformation
    brush.Transform = brushTransform;
```

## Étape 4 : définir la peinture et remplir le rectangle

```csharp
    // Définir la peinture
    document.SetPaint(brush);

    // Remplissez le rectangle
    document.Fill(path);
```

## Étape 5 : remplir le texte avec un dégradé

```csharp
    // Remplir le texte avec un dégradé
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Étape 6 : Définir le contour et le texte du contour

```csharp
    // Définir la course actuelle
    document.SetStroke(new Pen(brush, 5));
    // Décrire le texte avec un dégradé
    document.OutlineText("ABC", font, 200, 400);
```

## Étape 7 : fermez la page actuelle et enregistrez le document

```csharp
    // Fermer la page actuelle
    document.ClosePage();

    // Enregistrez le document
    document.Save();
}
```

Toutes nos félicitations! Vous avez ajouté avec succès un dégradé horizontal à un document PostScript à l'aide d'Aspose.Page pour .NET.

## Conclusion

Dans ce didacticiel, nous avons couvert le processus d'amélioration de vos documents PostScript avec des dégradés horizontaux à l'aide de la bibliothèque Aspose.Page pour .NET. En suivant le guide étape par étape, vous avez acquis des informations précieuses sur l'exploitation de ce puissant outil de manipulation de documents.

## FAQ

### Q1 : Puis-je appliquer des dégradés à d’autres formes que les rectangles ?

 A1 : Oui, vous pouvez appliquer des dégradés à diverses formes à l'aide d'Aspose.Page. Modifier le`GraphicsPath` création adaptée à votre forme spécifique.

### Q2 : Comment puis-je modifier les couleurs du dégradé ?

 A2 : Ajustez le`Color.FromArgb` valeurs dans le`LinearGradientBrush` instanciation pour obtenir les couleurs de dégradé souhaitées.

### Q3 : Aspose.Page est-il compatible avec différents formats de documents ?

A3 : Aspose.Page prend en charge divers formats de documents, notamment XPS, PS, PDF, etc. Reportez-vous à la documentation pour une liste complète.

### Q4 : Puis-je utiliser Aspose.Page pour des projets commerciaux ?

 A4 : Oui, Aspose.Page est livré avec des options de licence commerciale. Visite[ici](https://purchase.aspose.com/buy) pour plus de détails.

### Q5 : Existe-t-il un forum communautaire pour les utilisateurs d'Aspose.Page ?

 A5 : Oui, rejoignez la communauté Aspose.Page sur[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour se connecter avec d’autres utilisateurs et demander de l’aide.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
