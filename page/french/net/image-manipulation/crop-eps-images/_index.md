---
date: 2026-03-16
description: Apprenez à recadrer des images EPS et à redimensionner des fichiers d'images
  EPS dans .NET à l'aide d'Aspose.Page. Suivez ce guide pas à pas pour recadrer les
  EPS et redimensionner les images EPS sans effort.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Comment recadrer des images EPS avec Aspose.Page pour .NET
url: /fr/net/image-manipulation/crop-eps-images/
weight: 10
---

**Author:** Aspose => "**Auteur :** Aspose"

Then closing shortcodes.

Make sure to keep all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment recadrer des images EPS avec Aspose.Page pour .NET

## Introduction

Si vous devez savoir **comment recadrer des EPS** dans une application .NET, vous êtes au bon endroit. Dans ce tutoriel, nous vous guiderons à travers le recadrage et le redimensionnement des fichiers EPS en utilisant la puissante bibliothèque Aspose.Page pour .NET. Que vous peaufiniez un outil de reporting ou prépariez des graphiques pour un service web, maîtriser cette technique vous fera gagner du temps et vous donnera des résultats pixel‑parfait.

## Réponses rapides
- **Quelle bibliothèque gère le recadrage EPS ?** Aspose.Page for .NET  
- **Méthode principale ?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Puis-je également redimensionner le EPS ?** Oui – utilisez `ResizeEps` avec des pouces, millimètres ou pourcentages.  
- **Prérequis ?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page installé, un fichier EPS.  
- **Temps d'implémentation typique ?** Environ 10 minutes pour un flux de travail basique de recadrage et redimensionnement.

## Prérequis

- Une connaissance pratique du développement .NET.  
- Bibliothèque Aspose.Page pour .NET installée. Sinon, vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).  
- Une image EPS d'exemple (remplacez `"input.eps"` dans le code par votre fichier réel).

## Importer les espaces de noms

Commençons par importer les espaces de noms qui nous donnent accès aux classes de gestion EPS.

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

## Comment recadrer des images EPS – Guide étape par étape

### Étape 1 : Initialiser `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Nous créons une instance de `PsDocument` à partir du flux EPS d'entrée. Cet objet représente le fichier EPS en mémoire et nous donne accès aux méthodes de recadrage et de redimensionnement.

### Étape 2 : Extraire la boîte englobante d'origine

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

La boîte englobante indique les dimensions actuelles du canevas EPS. Connaître ces valeurs vous aide à définir un rectangle de recadrage sûr.

### Étape 3 : Créer un flux de sortie

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Nous ouvrons un flux en écriture où l'EPS recadré sera enregistré. L'utilisation d'un bloc `using` garantit que le flux est correctement fermé.

### Étape 4 : Définir une nouvelle boîte englobante

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Remplacez les nombres par les coordonnées que vous souhaitez conserver. Assurez‑vous que les nouvelles valeurs restent à l'intérieur de la boîte englobante d'origine ; sinon l'opération échouera.

### Étape 5 : Recadrer et enregistrer l'EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Cette ligne unique effectue le recadrage et écrit le résultat dans `output_crop.eps`. La méthode modifie le document en mémoire, vous pouvez donc chaîner d'autres opérations si nécessaire.

## Redimensionner l'image EPS

Après le recadrage, vous souhaitez souvent changer la taille de l'EPS pour l'affichage ou l'impression. Aspose.Page prend en charge trois unités de mesure.

### Redimensionner en pouces

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Redimensionner en millimètres

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Redimensionner en pourcentages

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Chaque appel écrase la sortie précédente, assurez‑vous donc de créer un nouveau flux si vous avez besoin de fichiers séparés pour chaque taille.

## Problèmes courants et dépannage

| Symptom | Cause probable | Solution |
|---------|----------------|----------|
| **Valeurs de la boîte englobante hors limites** | La nouvelle boîte dépasse les dimensions originales | Vérifiez les valeurs de `initialBoundingBox` et choisissez des coordonnées à l'intérieur de cette plage. |
| **Le fichier de sortie est vide** | Le flux de sortie n'est pas vidé ou fermé | Assurez‑vous que le bloc `using` se termine avant d'accéder au fichier, ou appelez `outputEpsStream.Flush()`. |
| **Mise à l'échelle inattendue** | Mélange d'unités (p. ex. pouces vs. millimètres) | Spécifiez toujours le bon enum `Units` qui correspond à vos valeurs de taille. |

## FAQ

### Q1 : Puis‑je utiliser Aspose.Page pour .NET avec d'autres formats d'image ?

R1 : Aspose.Page se concentre principalement sur les images EPS, mais Aspose propose diverses bibliothèques pour différents formats. Consultez leur documentation pour les formats spécifiques.

### Q2 : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?

R2 : Visitez [ce lien](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire pour les tests.

### Q3 : Existe‑t‑il des limitations concernant la taille d'image que je peux traiter avec Aspose.Page pour .NET ?

R3 : Aspose.Page est conçu pour gérer des images de différentes tailles. Cependant, les performances peuvent varier en fonction de la complexité de l'image.

### Q4 : Existe‑t‑il un forum communautaire pour les discussions sur Aspose.Page ?

R4 : Oui, vous pouvez rejoindre la communauté Aspose.Page [ici](https://forum.aspose.com/c/page/39).

### Q5 : Où puis‑je trouver la documentation détaillée pour Aspose.Page pour .NET ?

R5 : Consultez la documentation [ici](https://reference.aspose.com/page/net/).

---

**Dernière mise à jour :** 2026-03-16  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}