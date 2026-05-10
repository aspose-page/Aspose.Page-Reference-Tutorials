---
date: 2026-02-23
description: Apprenez à ajouter un dégradé aux fichiers PostScript, à enregistrer
  le fichier PostScript au format A4 et à remplir un rectangle avec un dégradé à l’aide
  d’Aspose.Page pour .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Comment ajouter un dégradé – dégradé diagonal dans PostScript (PS) avec Aspose.Page
  .NET
url: /fr/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé : dégradé diagonal à PostScript (PS) avec Aspose.Page .NET

## Introduction

Ajouter un dégradé diagonal à un document PostScript (PS) peut améliorer considérablement l'attrait visuel, surtout lorsque vous devez **comment ajouter un dégradé** dans des rapports techniques, des brochures ou des applications très graphiques. Dans ce tutoriel, vous verrez exactement comment ajouter un dégradé à un fichier PostScript, définir une taille de page A4 et remplir un rectangle avec une transition de couleur fluide en utilisant Aspose.Page pour .NET.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Puis‑je changer la direction du dégradé ?** Oui – faites pivoter la transformation du pinceau comme indiqué dans le code  
- **Comment enregistrer le résultat ?** Utilisez `PsDocument.Save()` qui écrit un fichier PostScript sur le disque  
- **Une licence est‑elle nécessaire pour la production ?** Oui, une licence commerciale débloque toutes les fonctionnalités  

## Qu’est‑ce qu’un dégradé diagonal en PostScript ?

Un dégradé diagonal est une transition de couleur linéaire qui s’exécute sous un angle (généralement 45°) à travers une forme. En PostScript, cela se réalise en appliquant un `LinearGradientBrush` avec une matrice de transformation personnalisée qui fait pivoter, mettre à l’échelle et translater le dégradé pour correspondre au rectangle souhaité.

## Pourquoi utiliser Aspose.Page pour les remplissages en dégradé ?

Aspose.Page abstrait les commandes PostScript de bas niveau, vous permettant de travailler avec des objets graphiques .NET familiers. Vous pouvez créer des remplissages complexes, définir les dimensions de la page et exporter directement vers un **save PostScript file** sans manipuler la syntaxe PS brute.

## Prérequis

- **Aspose.Page pour .NET Library** – téléchargez‑la [ici](https://releases.aspose.com/page/net/).  
- **Répertoire du document** – un dossier où le fichier `*.ps` généré sera écrit.

Maintenant que les bases sont couvertes, parcourons l’implémentation étape par étape.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms qui vous donnent accès au dispositif EPS, aux utilitaires de dessin et aux classes d’E/S.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Créer le flux de sortie pour le document PostScript (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Étape 2 : Définir la taille de page A4 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Étape 3 : Créer un nouveau document PS d’une page

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 4 : Définir les paramètres du rectangle

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Étape 5 : Créer le chemin graphique

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Étape 6 : Créer un pinceau à dégradé linéaire (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Étape 7 : Créer la transformation pour le pinceau

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Étape 8 : Appliquer les transformations au pinceau (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Étape 9 : Définir la transformation au pinceau

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Étape 10 : Définir la peinture et remplir le rectangle

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Étape 11 : Fermer la page actuelle

```csharp
	//Close current page
	document.ClosePage();
```

## Étape 12 : Enregistrer le document (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Comment enregistrer le fichier PostScript

L’appel `PsDocument.Save()` écrit le contenu PostScript complet dans le flux que vous avez ouvert à l’**Étape 1**. Après la fin du bloc `using`, le fichier `DiagonaGradient_outPS.ps` sera disponible dans le répertoire que vous avez spécifié.

## Cas d’utilisation courants

- **Documentation technique** nécessitant une ombre de fond subtile.  
- **Brochures marketing** où un dégradé diagonal apporte un aspect moderne.  
- **Générateurs de rapports automatisés** qui produisent des fichiers PS imprimables à la volée.

## Dépannage et conseils

- **Couleurs incorrectes** – vérifiez les valeurs ARGB passées à `LinearGradientBrush`.  
- **Dégradé invisible** – assurez‑vous que la matrice de transformation fait correctement pivoter et mettre à l’échelle ; l’appel `Rotate(-45)` définit l’angle diagonal.  
- **Fichier non créé** – vérifiez que `dataDir` pointe vers un dossier existant et que l’application possède les droits d’écriture.

## Questions fréquentes

**Q : Aspose.Page est‑il compatible avec toutes les versions de .NET ?**  
R : Aspose.Page prend en charge un large éventail de versions .NET, de .NET Framework 4.5+ à .NET 6+, assurant une compatibilité étendue.

**Q : Puis‑je personnaliser les couleurs du dégradé dans Aspose.Page ?**  
R : Oui, vous pouvez spécifier n’importe quelles couleurs ARGB lors de la création de `LinearGradientBrush`, vous donnant un contrôle total sur les teintes de départ et d’arrivée.

**Q : Existe‑t‑il une version d’essai d’Aspose.Page ?**  
R : Oui, vous pouvez explorer les fonctionnalités d’Aspose.Page en téléchargeant la version d’essai [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page ?**  
R : Obtenez une licence temporaire pour Aspose.Page [ici](https://purchase.aspose.com/temporary-license/) afin de débloquer des capacités supplémentaires pendant l’évaluation.

**Q : Où puis‑je trouver le support communautaire pour Aspose.Page ?**  
R : Rejoignez la communauté Aspose.Page sur le [forum](https://forum.aspose.com/c/page/39) pour obtenir de l’aide et participer aux discussions.

---

**Dernière mise à jour :** 2026-02-23  
**Testé avec :** Aspose.Page pour .NET (dernière version stable)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}