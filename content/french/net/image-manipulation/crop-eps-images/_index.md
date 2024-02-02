---
title: Recadrer des images EPS avec Aspose.Page pour .NET
linktitle: Recadrer Images EPS
second_title: API Aspose.Page .NET
description: Explorez le monde transparent de la manipulation d'images EPS dans .NET avec Aspose.Page. Recadrez et redimensionnez les images sans effort pour des résultats époustouflants.
type: docs
weight: 10
url: /fr/net/image-manipulation/crop-eps-images/
---
## Introduction

Avez-vous du mal à manipuler des images EPS dans vos applications .NET ? Cherchez pas plus loin! Dans ce didacticiel, nous vous guiderons tout au long du processus de recadrage d'images EPS à l'aide de la puissante bibliothèque Aspose.Page pour .NET. Que vous soyez un développeur chevronné ou tout juste débutant, ce guide étape par étape vous aidera à réaliser un recadrage d'image précis sans effort.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Une connaissance pratique du développement .NET.
-  Aspose.Page pour la bibliothèque .NET installée. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/page/net/).
- Un exemple d'image EPS (remplacez "input.eps" dans le code par votre fichier réel).

## Importer des espaces de noms

Commençons par importer les espaces de noms nécessaires au bon fonctionnement de notre code. 

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

Maintenant, décomposons le didacticiel en plusieurs étapes.

## Étape 1 : initialiser PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Initialiser un`PsDocument` objet avec le flux EPS d’entrée.

## Étape 2 : Extraire le cadre de délimitation

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Récupérez le cadre de délimitation initial de l’image EPS.

## Étape 3 : Créer un flux de sortie

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Créez un flux de sortie pour l'image EPS recadrée.

## Étape 4 : Définir un nouveau cadre de délimitation

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Définissez un nouveau cadre de délimitation pour le recadrage. Assurez-vous que les nouvelles valeurs se trouvent dans la zone de délimitation initiale.

## Étape 5 : Recadrer et enregistrer

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Recadrez l'image EPS à l'aide du nouveau cadre de délimitation et enregistrez-la dans le flux de sortie.

Répétez ces étapes pour différents scénarios de redimensionnement.

## Redimensionnement des images EPS

### Redimensionner en pouces

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Redimensionnez l'image EPS et enregistrez-la avec les dimensions spécifiées en pouces.

### Redimensionner en millimètres

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Redimensionnez l'image EPS et enregistrez-la avec les dimensions spécifiées en millimètres.

### Redimensionner en pourcentage

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Redimensionnez l'image EPS et enregistrez-la avec les dimensions spécifiées en pourcentages.

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment recadrer et redimensionner des images EPS à l'aide d'Aspose.Page pour .NET. Améliorez désormais vos capacités de manipulation d'images et faites passer vos applications .NET au niveau supérieur.

## FAQ

### Q1 : Puis-je utiliser Aspose.Page pour .NET avec d’autres formats d’image ?

A1 : Aspose.Page se concentre principalement sur les images EPS, mais Aspose propose diverses bibliothèques pour différents formats. Consultez leur documentation pour les formats spécifiques.

### Q2 : Comment puis-je obtenir une licence temporaire pour Aspose.Page pour .NET ?

 A2 : Visite[ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire pour les tests.

### Q3 : Existe-t-il des limites à la taille de l'image que je peux traiter avec Aspose.Page pour .NET ?

A3 : Aspose.Page est conçu pour gérer des images de différentes tailles. Cependant, les performances peuvent varier en fonction de la complexité de l'image.

### Q4 : Existe-t-il un forum communautaire pour les discussions sur Aspose.Page ?

 A4 : Oui, vous pouvez interagir avec la communauté Aspose.Page[ici](https://forum.aspose.com/c/page/39).

### Q5 : Où puis-je trouver une documentation détaillée pour Aspose.Page pour .NET ?

 A5 : Reportez-vous à la documentation[ici](https://reference.aspose.com/page/net/).