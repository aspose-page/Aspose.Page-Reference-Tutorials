---
date: 2026-02-25
description: Apprenez à créer un document XPS et à appliquer un dégradé linéaire avec
  Aspose.Page pour .NET. Suivez notre guide étape par étape pour enregistrer le fichier
  XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Créer un document XPS avec un dégradé vertical en utilisant Aspose.Page
url: /fr/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un dégradé vertical à XPS avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel, vous allez **créer un document XPS** comportant un dégradé vertical fluide. Ajouter des dégradés est une façon courante de rendre les fichiers XPS plus professionnels — parfait pour les rapports, les brochures ou tout graphique imprimable. Nous parcourrons chaque étape, de la configuration du projet à l’enregistrement du fichier XPS final, afin que vous puissiez appliquer rapidement un dégradé linéaire à n’importe quel tracé.

## Quick Answers
- **Quel est le sujet de ce tutoriel ?** Ajouter un dégradé linéaire vertical à un tracé dans un document XPS.  
- **Quelle bibliothèque est requise ?** Aspose.Page pour .NET.  
- **Ai-je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un exemple de base.  
- **Puis-je enregistrer le résultat en tant que fichier XPS ?** Oui, la méthode `Save` écrit le fichier sur le disque.

## What is a vertical gradient in XPS?

Un dégradé vertical est une transition de couleur qui s’étend du haut d’une forme jusqu’en bas. Dans XPS, cela est réalisé avec un **pinceau de dégradé linéaire** qui définit les points de départ et d’arrivée, ainsi qu’une collection de points d’arrêt du dégradé qui contrôlent la couleur à des positions spécifiques.

## Why use Aspose.Page to create XPS document with gradients?

- **Intégration .NET complète** – fonctionne avec .NET Framework, .NET Core et .NET 5/6+.  
- **Aucune dépendance externe** – tout le rendu est géré par la bibliothèque.  
- **Haute fidélité** – les dégradés sont rendus exactement comme définis, conformément à la spécification XPS.  
- **Facile à maintenir** – modèle d’objet clair pour les tracés, les pinceaux et les couleurs.

## Prerequisites

- Bibliothèque Aspose.Page pour .NET : assurez‑vous que la bibliothèque Aspose.Page pour .NET est installée dans votre environnement de développement. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).
- Environnement de développement : configurez un environnement de développement .NET avec votre IDE préféré, tel que Visual Studio.

Maintenant que tout est prêt, plongeons dans le code.

## Import Namespaces

Dans votre application .NET, incluez les espaces de noms nécessaires pour accéder aux classes et méthodes d’Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set Up Your Document Directory

Définissez le dossier où le fichier XPS généré sera enregistré.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

Instanciez un nouveau document XPS que nous remplirons ensuite avec un tracé rempli d’un dégradé.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Define Gradient Stops

Les points d’arrêt du dégradé déterminent les couleurs et leurs positions le long de la ligne du dégradé. Ici, nous créons cinq points d’arrêt pour produire une transition verticale fluide.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Step 4: Create a Path with Gradient

Nous dessinons un tracé de forme rectangulaire et appliquons un **pinceau de dégradé linéaire** qui s’étend verticalement du point (10, 110) au point (10, 200). Le pinceau reçoit les points d’arrêt du dégradé définis précédemment.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

Enfin, écrivez le document XPS sur le disque. Cette étape de **sauvegarde du fichier XPS** crée `AddVerticalGradient_outXPS.xps` dans le dossier que vous avez spécifié.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Astuce :** Vérifiez le résultat en ouvrant le fichier XPS dans le Visionneur XPS de Windows ou tout autre visualiseur tiers afin de vous assurer que le dégradé apparaît comme prévu.

## Common Issues & Troubleshooting

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le dégradé apparaît comme une couleur unie | Points d’arrêt du dégradé non ajoutés au pinceau | Assurez‑vous que `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` est exécuté. |
| Fichier introuvable lors de l’enregistrement | `dataDir` pointe vers un dossier inexistant | Créez d’abord le répertoire ou utilisez un chemin absolu. |
| Les couleurs diffèrent | Les valeurs de couleur utilisent l’ordre ARGB ; vérifiez l’ordre des canaux | Utilisez correctement `CreateColor(alpha, red, green, blue)`. |

## Frequently Asked Questions

**Q : Aspose.Page est‑il compatible avec Visual Studio 2019 ?**  
R : Oui, Aspose.Page est compatible avec Visual Studio 2019. Assurez‑vous d’avoir la bonne version de la bibliothèque installée.

**Q : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Oui, Aspose.Page peut être utilisé pour des projets commerciaux. Visitez [ici](https://purchase.aspose.com/buy) pour explorer les options de licence.

**Q : Un essai gratuit est‑il disponible ?**  
R : Oui, vous pouvez obtenir un essai gratuit d’Aspose.Page [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation d’Aspose.Page ?**  
R : La documentation est disponible [ici](https://reference.aspose.com/page/net/).

**Q : Comment obtenir du support ou poser des questions ?**  
R : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

## Conclusion

Vous savez maintenant comment **créer un document XPS**, **appliquer un dégradé linéaire** et **enregistrer un fichier XPS** en utilisant Aspose.Page pour .NET. Cette approche vous donne un contrôle total sur le style visuel des sorties XPS, faisant ressortir vos documents imprimables.

---  

**Dernière mise à jour :** 2026-02-25  
**Testé avec :** Aspose.Page for .NET 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}