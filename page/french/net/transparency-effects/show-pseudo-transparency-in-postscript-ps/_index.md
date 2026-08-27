---
date: 2026-03-29
description: Apprenez à utiliser un pinceau à dégradé linéaire C# pour créer une pseudo‑transparence
  dans PostScript avec Aspose.Page pour .NET.
linktitle: Show Pseudo-Transparency in PostScript (PS)
second_title: Aspose.Page .NET API
title: Pinceau à dégradé linéaire C# pour la pseudo-transparence dans PS
url: /fr/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pinceau à dégradé linéaire C# pour la pseudo-transparence en PostScript (PS)

## Introduction

Si vous devez ajouter un effet de transparence subtil à vos fichiers PostScript (PS), le **linear gradient brush C#** est l'outil idéal. Aspose.Page for .NET facilite la peinture de rectangles avec des remplissages en dégradé opaques et translucides, donnant à vos documents un aspect moderne et superposé. Dans ce tutoriel, nous parcourrons les étapes exactes nécessaires pour créer une pseudo-transparence à l'aide d'un pinceau à dégradé linéaire en C#.

## Réponses rapides
- **Quelle bibliothèque fournit le linear gradient brush ?** Aspose.Page for .NET
- **Quelle classe graphique crée le dégradé ?** `LinearGradientBrush`
- **Puis-je contrôler l'opacité par couleur ?** Oui, en utilisant `Color.FromArgb(alpha, …)`
- **Ai‑je besoin d'une licence pour la production ?** Une licence Aspose.Page valide est requise
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Qu'est‑ce qu'un linear gradient brush C# ?

Un `LinearGradientBrush` est un objet GDI+ qui peint une transition douce entre deux couleurs le long d'une ligne droite. Lorsque vous spécifiez le canal alpha (0‑255) pour chaque couleur, vous pouvez créer des dégradés translucides — exactement ce dont nous avons besoin pour la pseudo‑transparence en PostScript.

## Pourquoi utiliser un linear gradient brush C# pour la pseudo‑transparence ?

- **Contrôle d'opacité granulaire :** Ajustez l'alpha de chaque couleur pour obtenir le niveau de transparence souhaité.  
- **Rendu indépendant du dispositif :** Le pinceau fonctionne de la même façon sur l'écran, PDF, EPS et PS.  
- **API simple :** Quelques lignes de code C# produisent des effets visuels de qualité professionnelle.

## Prérequis

Avant de plonger dans le code, assurez‑vous d'avoir :

- Aspose.Page for .NET installé. Vous pouvez le télécharger depuis la [documentation Aspose.Page](https://reference.aspose.com/page/net/).
- Un dossier accessible en écriture où le document PostScript généré sera enregistré.

Maintenant que vous disposez des outils nécessaires, commençons à créer les rectangles pseudo‑transparents.

## Importer les espaces de noms

Before we begin, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Étape 1 : Créer le flux de sortie pour le document PostScript

Nous commençons par créer un flux de fichier qui contiendra le fichier PS résultant, puis nous initialisons le `PsDocument`.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();

	// Create new 1‑paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Étape 2 : Créer un rectangle avec un remplissage en dégradé **opaque**

Ici nous construisons un `LinearGradientBrush` dont les couleurs sont entièrement opaques (alpha = 255). Ce rectangle servira de couche d'arrière‑plan.

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

## Étape 3 : Créer un rectangle avec un remplissage en dégradé **translucide**

Nous utilisons maintenant un **linear gradient brush C#** où les valeurs alpha sont inférieures à 255 (par exemple 150 et 50). Cela rend le rectangle partiellement transparent, réalisant l'effet de pseudo‑transparence.

```csharp
	offsetX = 350;

	//Create graphics path from the first rectangle
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//Create linear gradient brush colors which transparency are not 255, but 150 and 50. So it are translucent.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## Étape 4 : Fermer la page et enregistrer le document

Enfin, nous terminons la page et écrivons le fichier PS sur le disque.

```csharp
	document.ClosePage();
	document.Save();
}
// ExEnd:1
```

En suivant ces quatre étapes, vous pouvez fusionner de manière fluide les rectangles opaques et translucides, créant ainsi un effet de pseudo‑transparence convaincant dans n'importe quelle sortie PostScript.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| Les couleurs apparaissent complètement opaques | Valeur alpha définie à 255 par erreur | Utilisez `Color.FromArgb(alpha, …)` avec `alpha` < 255 |
| Le dégradé est étiré de manière incorrecte | Matrice de transformation incorrecte | Vérifiez que les paramètres de la matrice correspondent aux dimensions du rectangle |
| Le fichier de sortie est vide | Flux non fermé ou `Save()` non appelé | Assurez‑vous que `document.ClosePage()` et `document.Save()` sont exécutés dans le bloc `using` |

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec toutes les versions de .NET ?**  
R : Aspose.Page for .NET est compatible avec diverses versions du framework .NET, garantissant flexibilité et facilité d'intégration.

**Q : Puis‑je appliquer la pseudo‑transparence à d'autres formes que les rectangles ?**  
R : Oui, les mêmes principes peuvent être appliqués à toute forme en ajustant le `GraphicsPath` en conséquence.

**Q : Où puis‑je trouver des exemples supplémentaires et de la documentation ?**  
R : Explorez la [documentation Aspose.Page](https://reference.aspose.com/page/net/) pour des exemples complets et des références API détaillées.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page ?**  
R : Oui, vous pouvez accéder à un essai gratuit d'Aspose.Page depuis [ce lien](https://releases.aspose.com/).

**Q : Comment puis‑je obtenir une licence temporaire pour Aspose.Page ?**  
R : Visitez [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire pour Aspose.Page.

---

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}