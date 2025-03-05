---
title: Redimensionner les images EPS avec Aspose.Page pour .NET
linktitle: Redimensionner les images EPS
second_title: API Aspose.Page .NET
description: Explorez le processus transparent de redimensionnement des images EPS dans .NET à l'aide d'Aspose.Page. Obtenez une précision en points, pouces, millimètres et pourcentages sans effort.
type: docs
weight: 11
url: /fr/net/image-manipulation/resize-eps-images/
---
## Introduction

Cherchez-vous à redimensionner des images EPS de manière transparente à l’aide d’Aspose.Page pour .NET ? Ce didacticiel est votre guide complet pour manipuler sans effort la taille des images EPS dans diverses unités telles que les points, les pouces, les millimètres et les pourcentages. Aspose.Page pour .NET fournit un ensemble d'outils puissants et, dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus.

## Conditions préalables

Avant de plonger dans la magie du redimensionnement, assurez-vous d'avoir les conditions préalables suivantes en place :

-  Bibliothèque Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page pour .NET est installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).

- Répertoire de documents : créez un répertoire dans lequel vous stockerez votre fichier EPS d'entrée et vos fichiers redimensionnés de sortie.

Maintenant que tout est configuré, passons à l'importation des espaces de noms nécessaires et examinons le guide étape par étape.

## Importer des espaces de noms

Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour travailler avec Aspose.Page. Ajoutez le code suivant au début de votre fichier :

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Étape 1 : Redimensionnement en points

Commençons par redimensionner une image EPS en points. Les points sont une unité de mesure standard dans l’industrie de l’imprimerie.

```csharp
public static void ResizeInPoints()
{
    // Votre répertoire de documents
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## Étape 2 : Redimensionnement en pouces

Maintenant, redimensionnons une image EPS en pouces, une unité couramment utilisée en conception graphique.

```csharp
public static void ResizeInInches()
{
    // Votre répertoire de documents
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## Étape 3 : Redimensionnement en millimètres

Maintenant, redimensionnons une image EPS en millimètres, une autre unité largement utilisée en conception et en impression.

```csharp
public static void ResizeInMillimeters()
{
    // Votre répertoire de documents
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## Étape 4 : Redimensionnement en pourcentages

Enfin, redimensionnons une image EPS à l'aide de pourcentages, offrant ainsi une approche flexible pour ajuster la taille de l'image.

```csharp
public static void ResizeInPercents()
{
    // Votre répertoire de documents
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

N'hésitez pas à intégrer ces méthodes dans votre projet et vous redimensionnerez les images EPS sans effort. Expérimentez avec différentes unités pour obtenir les dimensions souhaitées.

## Conclusion

Toutes nos félicitations! Vous maîtrisez l'art du redimensionnement des images EPS avec Aspose.Page pour .NET. Cette puissante bibliothèque ouvre un monde de possibilités pour manipuler des graphiques vectoriels. Que vous conceviez pour des supports imprimés ou numériques, Aspose.Page vous permet d'obtenir des résultats précis et personnalisés.

## FAQ

### Q1 : Puis-je redimensionner plusieurs images EPS simultanément ?

A1 : Oui, vous pouvez parcourir une collection de fichiers EPS, en appliquant les méthodes de redimensionnement en conséquence.

### Q2 : Aspose.Page est-il compatible avec d’autres formats d’image ?

A2 : Aspose.Page se concentre principalement sur les formats PostScript et EPS. Pour d'autres formats d'image, pensez à utiliser Aspose.Imaging.

### Q3 : Y a-t-il des considérations en matière de licence pour les projets commerciaux ?

 A3 : Oui, assurez-vous d'avoir une licence valide. Visite[ici](https://purchase.aspose.com/buy) pour les détails de la licence.

### Q4 : Puis-je essayer Aspose.Page avant d’acheter ?

 A4 : Absolument ! Vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).

### Q5 : Où puis-je demander de l'aide supplémentaire ou discuter de problèmes ?

 A5 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour entrer en contact avec la communauté et obtenir de l'aide.