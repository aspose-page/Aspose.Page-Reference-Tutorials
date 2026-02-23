---
date: 2026-02-23
description: Apprenez à créer des documents XPS à dégradé diagonal en utilisant Aspose.Page
  pour .NET et améliorez vos présentations visuelles sans effort.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Créer un XPS à dégradé diagonal avec Aspose.Page pour .NET
url: /fr/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un XPS à gradient diagonal avec Aspose.Page pour .NET

## Introduction

Si vous devez **créer des fichiers XPS à gradient diagonal** qui attirent l'attention, Aspose.Page pour .NET rend cela simple. Dans ce tutoriel, vous apprendrez comment ajouter un gradient diagonal à un document XPS, étape par étape, en utilisant l’API Aspose.Page. À la fin, vous disposerez d’un modèle réutilisable que vous pourrez adapter à n’importe quelle forme ou palette de couleurs.

## Réponses rapides
- **Que fait la méthode API ?** Elle crée un pinceau de gradient linéaire qui s’étend diagonalement le long d’un chemin.  
- **Quelle classe représente le document XPS ?** `XpsDocument`.  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Une version d’essai gratuite suffit pour le développement ; une licence est requise en production.  
- **Puis‑je changer la direction du gradient ?** Oui — ajustez les valeurs `PointF` de début et de fin.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Qu’est‑ce que **create diagonal gradient xps** ?
Un gradient diagonal est une transition de couleur fluide qui s’étend d’un coin d’une forme au coin opposé. Dans XPS, cet effet est obtenu en appliquant un `LinearGradientBrush` à la propriété de remplissage d’un chemin. La bibliothèque Aspose.Page abstrait le balisage XPS de bas niveau, vous permettant de vous concentrer sur les couleurs et la géométrie.

## Pourquoi utiliser Aspose.Page pour les gradients diagonaux ?
- **Rendu haute fidélité** – la sortie correspond exactement à la spécification XPS.  
- **Intégration complète à .NET** – fonctionne avec C#, VB.NET et tout langage .NET.  
- **Aucune dépendance externe** – tout est géré en‑processus, sans COM ni Office requis.  
- **Scalable pour des documents complexes** – vous pouvez combiner plusieurs gradients, images et textes sur la même page.

## Prérequis

1. **Bibliothèque Aspose.Page pour .NET** – téléchargez‑la [ici](https://releases.aspose.com/page/net/).  
2. **Environnement de développement** – Visual Studio, Rider ou tout éditeur supportant les projets .NET.  

Passons maintenant au code.

## Importer les espaces de noms

Dans votre projet .NET, incluez les espaces de noms nécessaires de la bibliothèque Aspose.Page pour accéder aux classes et méthodes requises. Ajoutez les espaces de noms suivants au début de votre code :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Étape 1 : Définir le répertoire du document

Commencez par spécifier le chemin vers votre répertoire de documents. C’est ici que le document XPS résultant avec le gradient diagonal sera enregistré.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Étape 2 : Créer un nouveau document XPS

Initialisez un nouveau `XpsDocument` en utilisant la bibliothèque Aspose.Page.

```csharp
XpsDocument doc = new XpsDocument();
```

## Étape 3 : Définir les couleurs du gradient

Créez une liste d’objets `XpsGradientStop`, chacun représentant une couleur dans le gradient diagonal.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Étape 4 : Ajouter un gradient diagonal à un chemin

Créez un nouveau chemin avec une géométrie définie, et appliquez‑lui le gradient diagonal. Ajustez la transformation de rendu et les propriétés de remplissage selon vos besoins.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Étape 5 : Enregistrer le document XPS résultant

Enfin, enregistrez le document XPS modifié dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

Vous avez maintenant **créé un fichier XPS à gradient diagonal** avec succès. N’hésitez pas à expérimenter avec différents arrêts de couleur, chaînes de géométrie ou matrices de transformation pour produire une variété d’effets visuels.

## Problèmes courants et solutions
- **Gradient invisible** – Vérifiez que la géométrie du chemin est fermée et que les points de début/fin du pinceau se trouvent à l’intérieur des limites du chemin.  
- **Couleurs incorrectes** – Assurez‑vous d’utiliser `CreateColor` avec les bonnes valeurs ARGB ; la méthode attend des valeurs entre 0 et 255.  
- **Fichier non enregistré** – Vérifiez que `dataDir` pointe vers un dossier existant et que l’application possède les droits d’écriture.

## Foire aux questions

**Q : Puis‑je appliquer plusieurs gradients à différentes parties du document ?**  
R : Oui, vous pouvez créer plusieurs chemins et appliquer des gradients distincts à chacun.

**Q : Existe‑t‑il des styles de gradient prédéfinis ?**  
R : Aspose.Page permet des gradients personnalisés, vous offrant un contrôle total sur les transitions de couleur.

**Q : Puis‑je utiliser Aspose.Page pour .NET avec d’autres formats de documents ?**  
R : Aspose.Page se concentre principalement sur la manipulation de documents XPS.

**Q : Comment gérer les erreurs liées au traitement du document ?**  
R : Consultez la [documentation](https://reference.aspose.com/page/net/) pour les meilleures pratiques de gestion des erreurs.

**Q : Une version d’essai est‑elle disponible avant l’achat ?**  
R : Oui, vous pouvez explorer l’[essai gratuit](https://releases.aspose.com/) pour découvrir Aspose.Page pour .NET.

**Q : Comment changer la direction du gradient en vertical ou horizontal ?**  
R : Modifiez les arguments `PointF` dans `CreateLinearGradientBrush` pour définir de nouveaux points de début et de fin.

**Q : La bibliothèque prend‑elle en charge la transparence dans les gradients ?**  
R : Oui—incluez une valeur alpha lors de la création des couleurs avec `CreateColor`.

## Conclusion

Aspose.Page pour .NET simplifie le processus d’enrichissement des documents XPS avec des gradients diagonaux. Ce guide vous a accompagné depuis la configuration des prérequis jusqu’à l’enregistrement du fichier final. Continuez à expérimenter avec différentes formes et palettes de couleurs pour que vos rapports, brochures ou factures XPS se démarquent réellement.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-02-23  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

---