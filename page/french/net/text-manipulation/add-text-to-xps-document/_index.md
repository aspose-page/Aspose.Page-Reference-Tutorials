---
date: 2026-03-21
description: Apprenez à créer un document XPS avec .NET et à ajouter du texte à l’aide
  d’Aspose.Page pour .NET. Guide étape par étape pour les développeurs .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Créer un document XPS .NET et ajouter du texte avec Aspose.Page
url: /fr/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS .NET et ajouter du texte avec Aspose.Page

Dans le développement .NET moderne, la capacité de **create XPS document .NET** fichiers de manière programmatique est une compétence précieuse, surtout lorsque vous devez générer des rapports imprimables, des factures ou des graphiques personnalisés. Ce tutoriel vous guide à travers l'utilisation d'Aspose.Page pour **aspose.page add text** à un document XPS, vous offrant un contrôle complet sur la mise en page et le style — le tout depuis votre application .NET.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Adding text to a newly created XPS document using Aspose.Page for .NET.  
- **Combien de temps cela prend‑il ?** About 5‑10 minutes for a basic implementation.  
- **Quelles sont les conditions préalables ?** .NET development environment and Aspose.Page library.  
- **Une licence est‑elle requise ?** Yes, a valid Aspose.Page license is needed for production use.  
- **Peut‑il fonctionner sur .NET Core / .NET 6+ ?** Absolutely – Aspose.Page supports all recent .NET versions.

## Qu'est‑ce que create xps document .net ?

Créer un document XPS dans .NET signifie générer un fichier à mise en page fixe qui préserve l'apparence exacte de votre contenu sur tous les appareils et imprimantes. XPS (XML Paper Specification) est la norme ouverte de Microsoft pour la description de pages, similaire au PDF mais entièrement basé sur XML.

## Pourquoi utiliser Aspose.Page pour ajouter du texte ?

Aspose.Page propose une API orientée objet de haut niveau qui abstrait le balisage XPS de bas niveau. Vous pouvez ajouter du texte, des graphiques et des formes sans manipuler du XML brut, rendant le processus de développement plus rapide et moins sujet aux erreurs.

## Prérequis

- Aspose.Page for .NET : Assurez‑vous que la bibliothèque Aspose.Page est installée. Vous pouvez la télécharger depuis la [documentation Aspose.Page for .NET](https://reference.aspose.com/page/net/).
- Environnement de développement : Configurez votre environnement de développement .NET. Si vous ne l’avez pas encore fait, suivez les instructions d’installation fournies dans la [documentation](https://reference.aspose.com/page/net/).
- Répertoire de documents : Créez un répertoire où vous stockerez vos documents. Remplacez "Your Document Directory" dans l’extrait de code fourni par le chemin réel.

Maintenant que nous avons couvert les bases, plongeons dans le code.

## Importer les espaces de noms

Tout d'abord, importez les espaces de noms nécessaires pour démarrer le projet :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Créer un document XPS .NET

Créez un nouveau document XPS qui servira de toile pour notre texte.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Étape 2 : Créer un pinceau pour le texte

Définissez un pinceau à couleur unie qui détermine la couleur du texte. Ici nous utilisons le noir.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Étape 3 : Ajouter des glyphes (aspose.page add text)

Les glyphes sont la représentation de bas niveau des caractères dans un document XPS. Cet appel ajoute le texte « Hello World! » aux coordonnées spécifiées.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Étape 4 : Enregistrer le document XPS résultant

Enregistrez le document sur le disque afin de pouvoir le visualiser ou l'imprimer plus tard.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

En suivant ces étapes, vous avez réussi à **create XPS document .NET** et ajouté du texte personnalisé en utilisant Aspose.Page.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| **Fichier non trouvé** lors de l'enregistrement | `dataDir` pointe vers un dossier inexistant | Assurez‑vous que le répertoire existe ou utilisez `Directory.CreateDirectory(dataDir)` avant d'enregistrer. |
| **Texte non visible** | La couleur du pinceau correspond à l'arrière‑plan | Changez `Color.Black` en une autre couleur contrastante. |
| **Police non prise en charge** | Police non installée sur la machine | Utilisez une police qui est garantie d'être présente, ou intégrez la police en utilisant les fonctionnalités d'intégration de police d'Aspose.Page. |

## Questions fréquemment posées

### Q1 : Puis‑je personnaliser la police et la taille du texte ajouté ?

A1 : Oui, vous avez un contrôle complet sur la police et la taille. Ajustez les paramètres de la méthode `AddGlyphs` en conséquence.

### Q2 : Aspose.Page est‑il compatible avec .NET Core ?

A2 : Absolument ! Aspose.Page prend en charge .NET Core, garantissant la compatibilité avec les dernières technologies .NET.

### Q3 : Existe‑t‑il des exigences de licence pour utiliser Aspose.Page ?

A3 : Oui, vous avez besoin d'une licence valide. Explorez les options de licence [ici](https://purchase.aspose.com/buy).

### Q4 : Comment obtenir du support ou de l'aide ?

A4 : Consultez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour rejoindre la communauté et obtenir de l'aide.

### Q5 : Une version d'essai gratuite est‑elle disponible ?

A5 : Bien sûr ! Vous pouvez obtenir une version d'essai gratuite [ici](https://releases.aspose.com/).

**Questions supplémentaires**

**Q : Puis‑je ajouter plusieurs blocs de texte sur la même page ?**  
A : Oui, il suffit d’appeler `doc.AddGlyphs` plusieurs fois avec des coordonnées différentes.

**Q : Aspose.Page permet‑il la rotation du texte ?**  
A : Vous pouvez appliquer une matrice de transformation à l’objet `XpsGlyphs` pour faire pivoter ou incliner le texte.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Dernière mise à jour :** 2026-03-21  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose  

---