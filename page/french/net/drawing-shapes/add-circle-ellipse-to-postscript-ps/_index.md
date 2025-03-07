---
title: Ajoutez Circle Ellipse à PostScript (PS) avec Aspose.Page
linktitle: Ajouter Circle Ellipse à PostScript (PS)
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter sans effort des ellipses circulaires aux documents PostScript (PS) à l'aide d'Aspose.Page pour .NET. Suivez notre guide étape par étape pour une intégration transparente.
weight: 10
url: /fr/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajoutez Circle Ellipse à PostScript (PS) avec Aspose.Page

## Introduction

Bienvenue dans ce didacticiel complet sur l'ajout d'ellipses circulaires aux documents PostScript (PS) à l'aide d'Aspose.Page pour .NET. Aspose.Page est une bibliothèque puissante qui permet aux développeurs de travailler de manière transparente avec PostScript et d'autres formats de documents. Dans ce guide, nous vous guiderons tout au long du processus d'incorporation facile d'ellipses circulaires dans vos documents PS.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Page pour .NET : téléchargez et installez la bibliothèque Aspose.Page pour .NET à partir de[ici](https://releases.aspose.com/page/net/).

2. Environnement de développement : assurez-vous de disposer d'un environnement de développement .NET fonctionnel configuré sur votre ordinateur.

Commençons maintenant par le guide étape par étape.

## Importer des espaces de noms

Dans la première étape, vous devez importer les espaces de noms nécessaires pour rendre la fonctionnalité Aspose.Page disponible dans votre code.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes pour vous guider tout au long du processus d'ajout d'ellipses circulaires à un document PostScript.

## Étape 1 : Définir le répertoire des documents

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```

Assurez-vous de remplacer « Votre répertoire de documents » par le chemin réel d'accès à votre répertoire de documents.

## Étape 2 : Créer un flux de sortie pour un document PostScript

```csharp
//Créer un flux de sortie pour un document PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Ici, un FileStream est créé pour écrire le document PostScript et le mode fichier est défini pour créer un nouveau fichier.

## Étape 3 : Créer des options de sauvegarde et un document PS

```csharp
//Créez des options de sauvegarde au format A4
PsSaveOptions options = new PsSaveOptions();

// Créer un nouveau document PS d'une page
PsDocument document = new PsDocument(outPsStream, options, false);
```

Cette étape consiste à créer des options de sauvegarde au format A4 et à initialiser un nouveau document PS d'une page.

## Étape 4 : Créer un chemin graphique pour la première ellipse

```csharp
//Créer un chemin graphique à partir de la première ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Un chemin graphique est créé pour la première ellipse, spécifiant sa position et ses dimensions.

## Étape 5 : définir la peinture et remplir l'ellipse

```csharp
//Définir la peinture
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Remplir l'ellipse
document.Fill(path);
```

Ici, la peinture est définie et la première ellipse est remplie de la couleur spécifiée.

## Étape 6 : Créer un chemin graphique pour la deuxième ellipse

```csharp
//Créer un chemin graphique à partir de la deuxième ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

De même, un chemin graphique est créé pour la deuxième ellipse, définissant sa position et ses dimensions.

## Étape 7 : définir le trait et dessiner l'ellipse

```csharp
//Définir la course
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Tracer (décrire) l'ellipse
document.Draw(path);
```

Dans cette étape, le trait est défini et la deuxième ellipse est délimitée avec la couleur et l'épaisseur de trait spécifiées.

## Étape 8 : fermez la page actuelle et enregistrez le document

```csharp
//Fermer la page actuelle
document.ClosePage();

//Enregistrez le document
document.Save();
```

Enfin, la page actuelle est fermée et l'intégralité du document est enregistrée, complétant ainsi le processus.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment ajouter des ellipses circulaires aux documents PostScript à l'aide d'Aspose.Page pour .NET. Ce didacticiel fournit un guide détaillé, étape par étape, pour vous aider à intégrer cette fonctionnalité dans vos projets de manière transparente.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET avec d’autres formats de document ?

 A1 : Aspose.Page se concentre principalement sur PostScript, mais Aspose fournit d'autres bibliothèques pour différents formats de documents. Vérifier la[Asposer la documentation](https://reference.aspose.com/page/net/) pour plus de détails.

### Q2 : Où puis-je trouver une assistance supplémentaire et des discussions communautaires ?

 A2 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour les discussions et le soutien de la communauté.

### Q3 : Existe-t-il un essai gratuit disponible pour Aspose.Page pour .NET ?

 A3 : Oui, vous pouvez accéder au[essai gratuit](https://releases.aspose.com/)pour explorer les fonctionnalités d'Aspose.Page pour .NET.

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page ?

 A4 : Obtenir un permis temporaire[ici](https://purchase.aspose.com/temporary-license/) à des fins de tests et d’évaluation.

### Q5 : Où puis-je acheter Aspose.Page pour .NET ?

 A5 : Achetez Aspose.Page pour .NET à partir du[page d'achat](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
