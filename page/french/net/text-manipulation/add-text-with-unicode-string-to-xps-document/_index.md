---
date: 2026-03-21
description: Apprenez à ajouter du texte Unicode à un document XPS en utilisant Aspose.Page
  pour .NET. Ce guide vous montre comment créer un document XPS en C# et ajouter du
  texte avec des chaînes Unicode à l’aide d’Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Comment ajouter du texte Unicode à un document XPS avec Aspose.Page
url: /fr/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter du texte Unicode à un document XPS avec Aspose.Page

## Introduction

Si vous devez **ajouter du texte unicode** à un fichier XPS, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes nécessaires pour **créer un document XPS en C#** à l’aide d’Aspose.Page pour .NET et démontrer la capacité **aspose page add text** avec une chaîne Unicode. À la fin, vous disposerez d’un document XPS pleinement fonctionnel affichant correctement le texte Unicode de droite à gauche (RTL).

## Réponses rapides
- **Que couvre le tutoriel ?** Ajouter du texte Unicode à un document XPS avec Aspose.Page pour .NET.  
- **Quel langage est utilisé ?** C# (compatible avec .NET Framework et .NET Core).  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je changer la police ou la taille ?** Oui – l’exemple utilise Arial 20 pt, mais toute police installée fonctionne.  
- **Le support RTL est‑il inclus ?** Le paramètre `BidiLevel = 1` active le rendu de droite à gauche pour les chaînes Unicode.

## Qu’est‑ce que “how to add unicode” dans XPS ?

Ajouter du texte Unicode signifie insérer des caractères de n’importe quelle langue — arabe, hébreu, chinois, etc. — dans un document XPS. La classe `XpsGlyphs` d’Aspose.Page gère le placement bas‑niveau des glyphes, tandis que la propriété `BidiLevel` contrôle la direction du texte pour les scripts RTL.

## Pourquoi utiliser Aspose.Page pour ajouter du texte ?

- **Intégration .NET complète** – fonctionne avec .NET Framework, .NET Core, .NET 5/6+.  
- **Aucune dépendance externe** – code purement géré, pas d’interop COM.  
- **Support typographique riche** – polices, styles, couleurs et texte bidirectionnel.  
- **Haute performance** – crée et enregistre rapidement des fichiers XPS, idéal pour la génération côté serveur.

## Prérequis

- Connaissances de base en C# et développement .NET.  
- Visual Studio (toute version récente).  
- Bibliothèque Aspose.Page pour .NET – téléchargez‑la depuis [here](https://releases.aspose.com/page/net/).

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms qui vous donnent accès au modèle XPS et aux utilitaires de dessin.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Configurer le document – créer un document XPS C#

Créez un nouveau document XPS qui hébergera le texte Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Étape 2 : Ajouter du texte Unicode – aspose page add text

Nous ajoutons maintenant la chaîne Unicode réelle. Dans cet exemple, nous utilisons la police Arial, taille 20, et plaçons le texte à (400 f, 200 f). Le `BidiLevel` à 1 indique au rendu de traiter la chaîne comme de droite à gauche.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Étape 3 : Enregistrer le document

Enfin, persistez le fichier XPS sur le disque.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Félicitations ! Vous avez ajouté avec succès du **texte unicode** à un document XPS en utilisant Aspose.Page pour .NET.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Le texte apparaît illisible | La police ne prend pas en charge la plage Unicode | Utilisez une police contenant les glyphes requis (par ex., Arial Unicode MS). |
| Le texte RTL reste de gauche à droite | `BidiLevel` non défini ou à 0 | Assurez‑vous que `glyphs.BidiLevel = 1;` pour les scripts RTL. |
| Le fichier n’est pas enregistré | Chemin `dataDir` invalide | Vérifiez que le répertoire existe et que l’application possède les droits d’écriture. |

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec les dernières versions de .NET ?**  
R : Oui, Aspose.Page est régulièrement mis à jour pour prendre en charge .NET Framework, .NET Core et .NET 5/6+.

**Q : Puis‑je personnaliser le style et la taille de la police lors de l’ajout de texte ?**  
R : Absolument ! La méthode `AddGlyphs` vous permet de spécifier n’importe quelle famille de polices, taille et `FontStyle` dont vous avez besoin.

**Q : Où puis‑je trouver une documentation supplémentaire pour Aspose.Page ?**  
R : Vous pouvez consulter la documentation [here](https://reference.aspose.com/page/net/) pour des détails complets sur l’API.

**Q : Existe‑t‑il des ressources gratuites pour débuter avec Aspose.Page ?**  
R : Oui, explorez le forum communautaire à [Aspose.Page forum](https://forum.aspose.com/c/page/39) pour des astuces, exemples et soutien entre pairs.

**Q : Une version d’essai est‑elle disponible avant l’achat ?**  
R : Bien sûr ! Téléchargez l’essai gratuit depuis [here](https://releases.aspose.com/) pour évaluer la bibliothèque.

---

**Dernière mise à jour :** 2026-03-21  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}