---
title: Ajouter du texte au document XPS avec Aspose.Page pour .NET
linktitle: Ajouter du texte au document XPS
second_title: API Aspose.Page .NET
description: Découvrez un guide étape par étape sur l'ajout de texte aux documents XPS à l'aide d'Aspose.Page pour .NET. Améliorez vos projets .NET sans effort.
type: docs
weight: 13
url: /fr/net/text-manipulation/add-text-to-xps-document/
---
## Introduction

Dans le monde dynamique du développement .NET, Aspose.Page s'impose comme un outil puissant pour travailler avec des documents XPS. L'ajout de texte aux documents XPS est une exigence courante et Aspose.Page simplifie ce processus. Dans ce didacticiel, nous verrons comment utiliser Aspose.Page pour .NET pour ajouter de manière transparente du texte aux documents XPS.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Aspose.Page pour .NET : assurez-vous que la bibliothèque Aspose.Page est installée. Vous pouvez le télécharger depuis le[Aspose.Page pour la documentation .NET](https://reference.aspose.com/page/net/).

-  Environnement de développement : configurez votre environnement de développement .NET. Si vous ne l'avez pas encore fait, suivez les instructions d'installation fournies dans le[Documentation](https://reference.aspose.com/page/net/).

- Répertoire de documents : créez un répertoire dans lequel vous stockerez vos documents. Remplacez « Votre répertoire de documents » dans l'extrait de code fourni par le chemin réel.

Passons maintenant au guide étape par étape.

## Importer des espaces de noms

Tout d'abord, importons les espaces de noms nécessaires pour démarrer notre projet :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Créer un nouveau document XPS

Pour commencer à travailler avec Aspose.Page, créez un nouveau document XPS. Ce sera la toile sur laquelle nous ajouterons notre texte.

```csharp
// ExDébut : 3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExFin : 3
```

## Étape 2 : Créer un pinceau pour le texte

Créons maintenant un pinceau pour définir la couleur du texte. Dans cet exemple, nous utilisons un pinceau de couleur noire.

```csharp
// ExDébut : 4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExFin : 4
```

## Étape 3 : ajouter des glyphes au document

Les glyphes représentent le texte dans les documents XPS. Ajoutez des glyphes au document avec la police, la taille, le style et la position souhaités.

```csharp
// ExDébut : 5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExFin : 5
```

## Étape 4 : Enregistrez le document XPS résultant

Enfin, enregistrez le document XPS avec le texte ajouté dans votre répertoire spécifié.

```csharp
// ExDébut : 6
doc.Save(dataDir + "AddText_out.xps");
// ExFin : 6
```

En suivant ces étapes simples, vous avez réussi à ajouter du texte à un document XPS à l'aide d'Aspose.Page pour .NET.

## Conclusion

En conclusion, Aspose.Page pour .NET fournit une solution simple pour ajouter du texte aux documents XPS dans vos projets .NET. La simplicité de la bibliothèque, combinée à ses fonctionnalités robustes, en fait un outil précieux pour la manipulation de documents.

## Questions fréquemment posées

### Q1 : Puis-je personnaliser la police et la taille du texte ajouté ?

 A1 : Oui, vous avez un contrôle total sur la police et la taille. Ajustez les paramètres dans le`AddGlyphs` méthode en conséquence.

### Q2 : Aspose.Page est-il compatible avec .NET Core ?

A2 : Absolument ! Aspose.Page prend en charge .NET Core, garantissant la compatibilité avec les dernières technologies .NET.

### Q3 : Existe-t-il des exigences de licence pour utiliser Aspose.Page ?

 A3 : Oui, vous avez besoin d’une licence valide. Explorez les options de licence[ici](https://purchase.aspose.com/buy).

### Q4 : Comment puis-je obtenir de l'aide ou demander de l'aide ?

 A4 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour entrer en contact avec la communauté et obtenir de l'aide.

### Q5 : Existe-t-il un essai gratuit ?

 A5 : Certainement ! Vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).