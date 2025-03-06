---
title: Transformations PS avec Aspose.Page pour .NET
linktitle: Transformations PS
second_title: API Aspose.Page .NET
description: Libérez le potentiel d'Aspose.Page pour .NET avec ce guide complet sur les transformations PostScript. Créez des graphiques dynamiques sans effort.
weight: 12
url: /fr/net/canvas-manipulation/transformationsps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Transformations PS avec Aspose.Page pour .NET

## Introduction

Bienvenue dans le monde d'Aspose.Page pour .NET, où vous pouvez libérer la puissance des transformations dans les documents PostScript. Ce didacticiel vous guidera à travers diverses transformations telles que la translation, la mise à l'échelle, la rotation, le cisaillement et les transformations complexes, vous permettant de créer des graphiques visuellement époustouflants et dynamiques.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

-  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est intégrée à votre projet. Vous pouvez le télécharger depuis le[lien de téléchargement](https://releases.aspose.com/page/net/).

- Répertoire de documents : créez un répertoire pour vos documents et remplacez l'espace réservé dans le code par le chemin réel.

## Importer des espaces de noms

Dans votre projet .NET, importez les espaces de noms nécessaires pour travailler avec Aspose.Page :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Maintenant, décomposons chaque exemple en plusieurs étapes dans un format de guide étape par étape.


## Aucune transformation

### Étape 1 : Créer un flux de sortie

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";

// Créer un flux de sortie pour un document PostScript
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Créer des options de sauvegarde avec des valeurs par défaut
    PsSaveOptions options = new PsSaveOptions();

    // Créer un nouveau document PS d'une page
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Créer un chemin graphique à partir du rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Définir la peinture dans l'état graphique au niveau supérieur
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Remplissez le premier rectangle qui se trouve dans l'état graphique de niveau supérieur et sans aucune transformation
    document.Fill(path);

    // Fermer la page actuelle
    document.ClosePage();

    // Enregistrez le document
    document.Save();
}
```

Ce code crée un document PostScript sans transformation, remplissant un rectangle de couleur orange.

## Traduction

### Étape 1 : Enregistrer l'état des graphiques

```csharp
// Enregistrez l'état graphique pour revenir à cet état après la transformation
document.WriteGraphicsSave();
```

Cette étape enregistre l'état graphique actuel, nous permettant d'y revenir après la transformation.

### Étape 2 : Traduire l’état des graphiques

```csharp
// Déplacer l'état graphique actuel de 250 vers la droite
document.Translate(250, 0);
```

Traduisez l’état graphique actuel en ajoutant un composant de traduction, puis définissez la peinture dans l’état graphique actuel sur une couleur bleue.

### Étape 3 : remplir le rectangle avec la transformation de traduction

```csharp
// Définir la peinture dans l'état graphique actuel
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Remplissez le deuxième rectangle dans l'état graphique actuel (a une transformation de traduction)
document.Fill(path);
```

Cette étape remplit le deuxième rectangle dans l'état graphique actuel, qui inclut désormais la transformation de traduction.

### Étape 4 : restaurer l'état des graphiques

```csharp
// Restaurer l'état graphique au niveau précédent (supérieur)
document.WriteGraphicsRestore();
```

Après avoir rempli le rectangle, restaurez l'état graphique au niveau précédent.

Continuez ce guide étape par étape pour chaque type de transformation, y compris la mise à l'échelle, la rotation, le cisaillement et les transformations complexes.

## Conclusion

Toutes nos félicitations! Vous avez parcouru avec succès les capacités de transformation d’Aspose.Page pour .NET. Maintenant, expérimentez différentes combinaisons et libérez votre créativité dans les transformations de documents PostScript.

## FAQ

### Q1 : Comment puis-je appliquer plusieurs transformations à un seul objet ?

A1 : Pour appliquer plusieurs transformations, utilisez le`Transform` méthode avec une matrice de transformation personnalisée.

### Q2 : Puis-je prévisualiser les transformations avant d'enregistrer le document ?

A2 : Oui, vous pouvez visualiser les transformations en rendant le document et en le prévisualisant dans une visionneuse appropriée.

### Q3 : Est-il possible d'appliquer des transformations à des éléments spécifiques d'un document ?

A3 : Oui, vous pouvez isoler les transformations d'éléments graphiques spécifiques dans un document.

### Q4 : Y a-t-il des considérations en matière de performances lors de transformations complexes ?

A4 : Les transformations complexes peuvent avoir un impact sur les performances, alors optimisez votre code pour plus d'efficacité.

### Q5 : Comment puis-je obtenir de l'aide ou demander de l'aide pour les requêtes liées à Aspose.Page ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le soutien et les discussions de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
