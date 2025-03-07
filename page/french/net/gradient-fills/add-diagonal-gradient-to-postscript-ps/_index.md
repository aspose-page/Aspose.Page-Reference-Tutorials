---
title: Ajouter un dégradé diagonal à PostScript (PS) avec Aspose.Page .NET
linktitle: Ajouter un dégradé diagonal à PostScript (PS)
second_title: API Aspose.Page .NET
description: Découvrez la simplicité de l'ajout de dégradés diagonaux aux documents PostScript dans .NET avec Aspose.Page. Élevez vos projets avec des éléments visuels dynamiques.
weight: 10
url: /fr/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé diagonal à PostScript (PS) avec Aspose.Page .NET

## Introduction

L'ajout d'un dégradé diagonal à un document PostScript (PS) peut apporter un attrait visuel et de la créativité à vos projets. Aspose.Page pour .NET fournit une solution transparente pour intégrer cette fonctionnalité dans vos applications. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'un dégradé diagonal à un document PS à l'aide d'Aspose.Page, étape par étape.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).

- Répertoire de documents : configurez un répertoire pour vos documents dans lequel le fichier PS de sortie sera enregistré.

Passons maintenant au guide étape par étape.

## Importer des espaces de noms

Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms sont cruciaux pour travailler avec les fonctionnalités Aspose.Page.

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Étape 2 : Créer des options d'enregistrement au format A4

```csharp
	//Créez des options de sauvegarde au format A4
	PsSaveOptions options = new PsSaveOptions();
```

## Étape 3 : Créer un nouveau document PS d'une page

```csharp
	// Créer un nouveau document PS d'une page
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 4 : Définir les paramètres du rectangle

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Étape 5 : Créer un chemin graphique

```csharp
	//Créer un chemin graphique à partir du premier rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Étape 6 : Créer un pinceau dégradé linéaire

```csharp
	//Créez un pinceau dégradé linéaire avec un rectangle comme limites, des couleurs de début et de fin
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Étape 7 : Créer une transformation pour le pinceau

```csharp
	//Créez une transformation pour le pinceau. Les composants des échelles X et Y doivent être égaux à la largeur et à la hauteur du rectangle en conséquence.
	// Les composants de translation sont des décalages du rectangle
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Étape 8 : Appliquer des transformations au pinceau

```csharp
	//Faites pivoter le dégradé, puis redimensionnez et traduisez pour obtenir une transition de couleur visible dans le rectangle requis.
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Étape 9 : Définir la transformation sur le pinceau

```csharp
	//Définir la transformation
	brush.Transform = brushTransform;
```

## Étape 10 : Définir la peinture et remplir le rectangle

```csharp
	//Définir la peinture
	document.SetPaint(brush);

	//Remplissez le rectangle
	document.Fill(path);
```

## Étape 11 : Fermez la page actuelle

```csharp
	//Fermer la page actuelle
	document.ClosePage();
```

## Étape 12 : Enregistrez le document

```csharp
	//Enregistrez le document
	document.Save();
}
// ExFin : 1
```

En suivant ces étapes, vous réussirez à ajouter un dégradé diagonal à un document PostScript à l'aide d'Aspose.Page pour .NET.

## Conclusion

Améliorer vos documents PS avec des dégradés diagonaux peut rendre vos projets visuellement attrayants et dynamiques. Aspose.Page for .NET simplifie ce processus, permettant aux développeurs d'intégrer sans effort cette fonctionnalité dans leurs applications.

## FAQ

### Q1 : Aspose.Page est-il compatible avec tous les frameworks .NET ?

A1 : Aspose.Page prend en charge divers frameworks .NET, garantissant la compatibilité avec un large éventail d'environnements de développement.

### Q2 : Puis-je personnaliser les couleurs du dégradé dans Aspose.Page ?

A2 : Oui, Aspose.Page offre une flexibilité dans le choix et la personnalisation des couleurs dégradées en fonction des exigences de votre projet.

### Q3 : Existe-t-il une version d’essai disponible pour Aspose.Page ?

 A3 : Oui, vous pouvez explorer les fonctionnalités d'Aspose.Page en téléchargeant la version d'essai[ici](https://releases.aspose.com/).

### Q4 : Comment puis-je obtenir une licence temporaire pour Aspose.Page ?

 A4 : Obtenez une licence temporaire pour Aspose.Page[ici](https://purchase.aspose.com/temporary-license/) pour débloquer des fonctionnalités supplémentaires.

### Q5 : Où puis-je trouver le support communautaire pour Aspose.Page ?

 A5 : Engagez-vous avec la communauté Aspose.Page sur le[forum](https://forum.aspose.com/c/page/39) pour de l'aide et des discussions.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
