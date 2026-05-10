---
date: 2026-03-03
description: Apprenez à redimensionner les images EPS dans .NET avec Aspose.Page –
  un guide étape par étape sur la façon de redimensionner les EPS en utilisant des
  points, des pouces, des millimètres ou des pourcentages.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: Comment redimensionner les images EPS avec Aspose.Page pour .NET
url: /fr/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment redimensionner les images EPS avec Aspose.Page pour .NET

## Introduction

Vous cherchez **comment redimensionner des images EPS** de manière fluide en utilisant Aspose.Page pour .NET ? Ce tutoriel est votre guide complet pour manipuler facilement la taille des images EPS dans différentes unités telles que les points, les pouces, les millimètres et les pourcentages. Aspose.Page pour .NET offre un ensemble d'outils puissant, et dans ce tutoriel, nous vous accompagnerons pas à pas.

## Quick Answers
- **Quelle bibliothèque gère le redimensionnement EPS ?** Aspose.Page pour .NET  
- **Quelles unités sont prises en charge ?** Points, Pouces, Millimètres et Pourcentages  
- **Ai-je besoin d'une licence pour la production ?** Oui – une licence commerciale est requise  
- **Puis-je redimensionner plusieurs fichiers à la fois ?** Absolument – il suffit de parcourir les fichiers en boucle  
- **.NET Core est‑il supporté ?** Oui, l'API fonctionne avec .NET Framework et .NET Core  

## What is EPS Resizing?
Encapsulated PostScript (EPS) est un format graphique vectoriel couramment utilisé dans les flux de travail d'impression et de conception. Redimensionner un fichier EPS modifie sa boîte englobante sans rasteriser le dessin, préservant ainsi la netteté à n'importe quelle échelle.

## Why Resize EPS Images?
- **Conserver la qualité d'impression :** Le redimensionnement vectoriel maintient les bords nets.  
- **Répondre aux exigences de mise en page :** Ajuster les dimensions pour correspondre aux tailles de page ou de canevas.  
- **Automatiser les traitements par lots :** Redimensionner programmatique des dizaines de fichiers en quelques secondes.  

## Prerequisites

Avant de plonger dans la magie du redimensionnement, assurez-vous que les prérequis suivants sont en place :

- Bibliothèque Aspose.Page pour .NET : Assurez‑vous d'avoir installé la bibliothèque Aspose.Page pour .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).

- Répertoire de documents : Créez un répertoire où vous stockerez votre fichier EPS d'entrée et les fichiers redimensionnés en sortie.

Maintenant que tout est configuré, passons à l'importation des espaces de noms nécessaires et plongeons dans le guide étape par étape.

## Import Namespaces

Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour travailler avec Aspose.Page. Ajoutez le code suivant au début de votre fichier :

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

## How to Resize EPS in Points

Les points sont une unité de mesure standard dans l'industrie de l'impression. L'exemple ci‑dessous double la largeur et la hauteur d'origine.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
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

## How to Resize EPS in Inches

Les pouces sont fréquemment utilisés par les graphistes lors de la préparation d'actifs pour l'impression.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
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

## How to Resize EPS in Millimeters

Les millimètres sont courants dans les régions qui utilisent le système métrique.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
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

## How to Resize EPS Using Percentages

Le redimensionnement basé sur les pourcentages vous permet d'échelonner l'image par rapport à sa taille originale.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
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

N'hésitez pas à intégrer ces méthodes dans votre projet, et vous redimensionnerez les images EPS sans effort. Expérimentez avec différentes unités pour obtenir les dimensions souhaitées.

## Common Issues and Solutions
- **Fichier introuvable :** Vérifiez que `dataDir` pointe vers le bon dossier et que `input.eps` existe.  
- **Taille inattendue :** Rappelez‑vous que `Units.Percents` attend des valeurs comme 150 pour 150 % de la taille originale.  
- **Exception de licence :** Si vous voyez une erreur de licence, assurez‑vous qu'un fichier de licence Aspose.Page valide est chargé avant de créer `PsDocument`.

## Conclusion

Félicitations ! Vous avez maîtrisé **comment redimensionner des images EPS** avec Aspose.Page pour .NET. Cette bibliothèque puissante ouvre un monde de possibilités pour manipuler les graphiques vectoriels. Que vous conceviez pour l'impression ou les médias numériques, Aspose.Page vous permet d'obtenir des résultats précis et personnalisés.

## FAQ's

### Q1 : Puis‑je redimensionner plusieurs images EPS simultanément ?

A1 : Oui, vous pouvez parcourir une collection de fichiers EPS, en appliquant les méthodes de redimensionnement en conséquence.

### Q2 : Aspose.Page est‑il compatible avec d'autres formats d'image ?

A2 : Aspose.Page se concentre principalement sur les formats PostScript et EPS. Pour d'autres formats d'image, envisagez d'utiliser Aspose.Imaging.

### Q3 : Existe‑t‑il des considérations de licence pour les projets commerciaux ?

A3 : Oui, assurez‑vous de disposer d'une licence valide. Visitez [ici](https://purchase.aspose.com/buy) pour les détails de licence.

### Q4 : Puis‑je essayer Aspose.Page avant d'acheter ?

A4 : Absolument ! Vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

### Q5 : Où puis‑je obtenir une aide supplémentaire ou discuter de problèmes ?

A5 : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour rejoindre la communauté et obtenir de l'assistance.

## Frequently Asked Questions

**Q : Ce code fonctionne‑t‑il avec .NET Core 6 ?**  
A : Oui. L'API est compatible avec .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ et .NET 6+.

**Q : Comment puis‑je préserver le profil couleur original ?**  
A : La méthode `ResizeEps` ne modifie pas les données couleur ; elle ne change que la boîte englobante.

**Q : Est‑il possible de redimensionner un EPS sans charger le fichier complet en mémoire ?**  
A : Utiliser un flux comme indiqué maintient une faible consommation de mémoire ; le document est traité à la volée.

**Q : Puis‑je chaîner plusieurs opérations de redimensionnement ?**  
A : Absolument. Appelez `ResizeEps` séquentiellement sur la même instance de `PsDocument`.

**Q : Que se passe‑t‑il avec les images intégrées à l'intérieur de l'EPS ?**  
A : Elles sont redimensionnées proportionnellement au contenu vectoriel, préservant la qualité.

---

**Dernière mise à jour :** 2026-03-03  
**Testé avec :** Aspose.Page 24.12 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}