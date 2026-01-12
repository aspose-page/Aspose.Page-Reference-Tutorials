---
date: 2026-01-12
description: Apprenez à enregistrer un fichier PostScript et à créer un document PostScript
  à l'aide d'Aspose.Page pour .NET, et à appliquer plusieurs transformations pour
  des graphiques dynamiques.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Enregistrer le fichier PostScript avec les transformations Aspose.Page (.NET)
url: /fr/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer un fichier PostScript avec les transformations Aspose.Page (.NET)

## Introduction

Dans ce tutoriel, vous découvrirez comment **enregistrer un fichier PostScript** tout en travaillant avec Aspose.Page pour .NET. Nous parcourrons la création d’un document PostScript, l’application de multiples transformations telles que la translation, le redimensionnement, la rotation et le cisaillement, puis l’enregistrement du résultat. À la fin, vous serez à l’aise pour créer des graphiques dynamiques par programme et saurez exactement où placer chaque transformation dans l’état graphique.

## Réponses rapides
- **Que puis‑je créer ?** Un document PostScript complet avec des graphiques transformés.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET (téléchargeable depuis le site officiel).  
- **Comment enregistrer le fichier ?** Utilisez `PsDocument.Save()` après avoir configuré les états graphiques.  
- **Puis‑je appliquer plusieurs transformations ?** Oui – combinez‑les avec `Transform` ou des appels séquentiels.  
- **Une licence est‑elle nécessaire ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.

## Qu’est‑ce qu’une opération « save postscript file » ?

Enregistrer un fichier PostScript signifie persister les commandes de dessin que vous avez construites en mémoire dans un fichier `.ps` sur le disque. Le fichier peut alors être rendu par n’importe quel interpréteur PostScript, imprimante ou visualiseur.

## Pourquoi utiliser Aspose.Page pour .NET afin de créer un document PostScript ?

Aspose.Page fournit une API de haut niveau, indépendante du dispositif, qui abstrait la syntaxe PostScript de bas niveau. Vous obtenez :

- Des objets C# fortement typés pour les chemins, les pinceaux et les transformations.  
- La gestion automatique de la pile d’état graphique (save/restore).  
- Un support complet des matrices de transformation complexes sans calculs manuels.  

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- La bibliothèque **Aspose.Page pour .NET** intégrée à votre projet. Téléchargez‑la depuis le [lien de téléchargement](https://releases.aspose.com/page/net/).  
- Un dossier accessible en écriture où le fichier `.ps` généré sera stocké. Remplacez le chemin factice dans le code par votre répertoire réel.

## Importer les espaces de noms

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Passons maintenant en revue chaque étape de transformation, une par une.

## Aucune transformation

### Étape 1 : Créer le flux de sortie

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Cet extrait crée un **document PostScript** contenant un seul rectangle orange et **enregistre le fichier PostScript** sans appliquer de transformation.

## Translation

### Étape 1 : Enregistrer l’état graphique

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

Enregistrer l’état graphique vous permet de revenir en arrière après avoir déplacé des objets.

### Étape 2 : Translater l’état graphique

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

La translation déplace tout ce qui est dessiné après cet appel de 250 unités vers la droite.

### Étape 3 : Remplir le rectangle avec la transformation de translation

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

Maintenant, un rectangle bleu apparaît 250 points à droite de l’orange.

### Étape 4 : Restaurer l’état graphique

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

La restauration ramène le système de coordonnées à sa position d’origine, de sorte que les dessins ultérieurs ne soient pas affectés par la translation.

## Redimensionnement

> *Vous pouvez suivre le même schéma — enregistrer l’état, appliquer `Scale`, dessiner, puis restaurer.*  
> **Astuce :** Utilisez le redimensionnement non uniforme (`Scale(sx, sy)`) pour étirer les objets uniquement dans une direction.

## Rotation

> *Tournez autour de l’origine ou d’un point pivot personnalisé avec `Rotate(angle)`.*
> **Astuce :** Combinez `Translate` avant la rotation pour pivoter autour d’un point spécifique.

## Cisaillement

> *Les transformations de cisaillement (`Shear(shx, shy)`) inclinent les formes, utiles pour des effets italiques.*  

## Transformations complexes

> *Pour des scénarios avancés, créez une `Matrix` personnalisée et transmettez‑la à `Transform(matrix)`.*
> C’est ici que vous **appliquez plusieurs transformations** en une seule étape.

## Conclusion

Vous avez appris comment **enregistrer un fichier PostScript**, **créer un document PostScript** et **appliquer plusieurs transformations** à l’aide d’Aspose.Page pour .NET. Expérimentez avec différents ordres de transformation, combinez‑les, et observez l’évolution des graphiques.

## Foire aux questions

**Q : Comment appliquer plusieurs transformations à un même objet ?**  
R : Utilisez la méthode `Transform` avec une `Matrix` personnalisée qui combine translation, redimensionnement, rotation ou cisaillement dans l’ordre souhaité.

**Q : Puis‑je prévisualiser les transformations avant d’enregistrer le document ?**  
R : Oui—rendez le `PsDocument` en image ou utilisez un visualiseur PostScript pour inspecter le résultat avant d’appeler `Save()`.

**Q : Est‑il possible d’appliquer des transformations à des éléments spécifiques d’un document ?**  
R : Absolument. Enregistrez l’état graphique avant de dessiner l’élément, appliquez la transformation désirée, dessinez, puis restaurez l’état.

**Q : Y a‑t‑il des considérations de performance lorsqu’on manipule des transformations complexes ?**  
R : Les matrices complexes augmentent le travail du CPU. Gardez les transformations aussi simples que possible et réutilisez les états enregistrés lorsque vous dessinez de nombreux objets similaires.

**Q : Comment obtenir de l’aide ou du support pour les questions relatives à Aspose.Page ?**  
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour l’aide de la communauté, ou contactez directement le support Aspose.

---

**Dernière mise à jour :** 2026-01-12  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}