---
title: Afficher la pseudo-transparence dans PostScript (PS) avec Aspose.Page
linktitle: Afficher la pseudo-transparence dans PostScript (PS)
second_title: API Aspose.Page .NET
description: Explorez la puissance de la pseudo-transparence dans PostScript avec Aspose.Page pour .NET. Suivez notre guide étape par étape pour des documents visuellement époustouflants.
weight: 13
url: /fr/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Afficher la pseudo-transparence dans PostScript (PS) avec Aspose.Page

## Introduction

Cherchez-vous à améliorer l'attrait visuel de vos documents PostScript (PS) en incorporant une pseudo-transparence ? Aspose.Page pour .NET fournit une solution puissante pour obtenir cet effet sans effort. Dans ce didacticiel étape par étape, nous vous guiderons tout au long du processus d'affichage de la pseudo-transparence dans PostScript à l'aide d'Aspose.Page.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée. Vous pouvez le télécharger depuis le[Documentation Aspose.Page](https://reference.aspose.com/page/net/).

- Répertoire de documents : configurez un répertoire pour stocker vos documents PostScript.

Maintenant que vous disposez des outils nécessaires dans votre arsenal, explorons comment mettre en valeur la pseudo-transparence dans PostScript à l'aide d'Aspose.Page.

## Importer des espaces de noms

Avant de vous plonger dans l'exemple, assurez-vous d'importer les espaces de noms requis :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Créer un flux de sortie pour un document PostScript

```csharp
// ExDébut : 1
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
//Créer un flux de sortie pour un document PostScript
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Créez des options de sauvegarde au format A4
	PsSaveOptions options = new PsSaveOptions();

	// Créer un nouveau document PS d'une page
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 2 : Créer un rectangle avec un remplissage dégradé opaque

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Étape 3 : Créer un rectangle avec un remplissage dégradé translucide

```csharp
	offsetX = 350;

	//Créer un chemin graphique à partir du premier rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Créez des couleurs de pinceau à dégradé linéaire dont la transparence n'est pas de 255, mais de 150 et 50. Il est donc translucide.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Étape 4 : Fermez la page actuelle et enregistrez le document

```csharp
	document.ClosePage();
	document.Save();
}
// ExFin : 1
```

En suivant ces étapes, vous pouvez intégrer de manière transparente la pseudo-transparence dans vos documents PostScript à l'aide d'Aspose.Page pour .NET.

## Conclusion

En conclusion, Aspose.Page pour .NET offre un moyen simple et efficace d'améliorer les éléments visuels de vos documents PostScript. Les étapes décrites ci-dessus fournissent un chemin clair pour incorporer la pseudo-transparence, vous permettant de créer des sorties visuellement époustouflantes.

## FAQ

### Q1 : Aspose.Page est-il compatible avec toutes les versions de .NET ?

A1 : Aspose.Page pour .NET est compatible avec différentes versions du framework .NET, garantissant flexibilité et facilité d'intégration.

### Q2 : Puis-je appliquer une pseudo-transparence à d'autres formes que les rectangles ?

A2 : Oui, les mêmes principes peuvent être appliqués à d’autres formes en ajustant GraphicsPath en conséquence.

### Q3 : Où puis-je trouver des exemples et de la documentation supplémentaires ?

 A3 : Explorez le[Documentation Aspose.Page](https://reference.aspose.com/page/net/) pour des exemples complets et une documentation détaillée.

### Q4 : Existe-t-il un essai gratuit disponible pour Aspose.Page ?

 A4 : Oui, vous pouvez accéder à un essai gratuit d'Aspose.Page à partir de[ce lien](https://releases.aspose.com/).

### Q5 : Comment puis-je obtenir une licence temporaire pour Aspose.Page ?

 A5 : Visite[ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire pour Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
