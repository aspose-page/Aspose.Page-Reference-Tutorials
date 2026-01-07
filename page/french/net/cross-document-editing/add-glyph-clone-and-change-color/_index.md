---
date: 2026-01-07
description: Apprenez à créer un document XPS, ajouter des clones de glyphes, utiliser
  un pinceau à couleur unie et enregistrer le fichier XPS avec Aspose.Page pour .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Créer un document XPS – Ajouter un clone de glyphe et changer la couleur avec
  Aspose.Page pour .NET
url: /fr/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un document XPS – Ajouter un clone de glyphe et changer la couleur avec Aspose.Page pour .NET

## Introduction

Bienvenue dans ce guide étape par étape qui montre **comment créer des fichiers de document XPS**, cloner des glyphes et changer leurs couleurs en utilisant Aspose.Page pour .NET. Que vous construisiez des rapports dynamiques, des factures ou des graphiques personnalisés, maîtriser ces techniques vous permet de produire une sortie XPS visuellement riche sans quitter l'écosystème .NET.

## Quick Answers
- **Quel est l'objectif principal ?** Créer un document XPS, ajouter des clones de glyphes et changer leurs couleurs.  
- **Quelle bibliothèque est utilisée ?** Aspose.Page pour .NET.  
- **Ai-je besoin d'une licence ?** Une licence temporaire est disponible pour l'évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Comment enregistrer le résultat ?** Utilisez la méthode `Save` pour écrire le fichier XPS sur le disque.

## Prerequisites

- Une compréhension de base du langage de programmation C#.  
- Visual Studio ou tout autre environnement de développement C# préféré installé.  
- Bibliothèque Aspose.Page pour .NET. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).  
- Familiarité avec le format de document XPS.

## Import Namespaces

Pour commencer, incluez les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## How to Create XPS Document and Add Glyph Clones

### Step 1: Set up Your Document Directory

Commencez par configurer le répertoire où vos documents seront stockés :

```csharp
string dataDir = "Your Document Directory";
```

### Step 2: Create the First XPS Document

Créons maintenant le premier document XPS :

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Step 3: Add Glyphs to the First Document

Ajoutez des glyphes au premier document en utilisant les paramètres spécifiés :

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 4: Fill Glyphs with a Solid Color Brush

Remplissez les glyphes du premier document avec un **pinceau de couleur unie**, par exemple, vert :

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Step 5: Create the Second XPS Document

Créons maintenant le deuxième document XPS :

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Step 6: How to Add Glyph Clone to Another Document

Clonez les glyphes du premier document et ajoutez-les au deuxième document :

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Step 7: How to Change Color of the Cloned Glyph

Changez la couleur des glyphes clonés dans le deuxième document, par exemple, en rouge. Cela montre **comment changer la couleur** d'un glyphe après le clonage :

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Step 8: Save XPS File – First Document

Enregistrez le premier document XPS dans le dossier que vous avez défini précédemment :

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Step 9: Save XPS File – Second Document

Enregistrez le deuxième document XPS :

```csharp
doc2.Save(dataDir + "out2.xps");
```

Félicitations ! Vous avez créé avec succès des fichiers de **document XPS**, ajouté des clones de glyphes et changé leurs couleurs en utilisant Aspose.Page pour .NET.

## Why Use Glyph Cloning and Color Changes?

- **Réutilisabilité :** Clonez des glyphes existants pour réutiliser des formes vectorielles complexes sans les redéfinir.  
- **Performance :** Réduit le temps de traitement comparé à la recréation de glyphes à partir de zéro.  
- **Flexibilité de conception :** Appliquez différentes instances de `SolidColorBrush` au même glyphe pour obtenir des thèmes visuels variés.  
- **Édition inter‑documents :** Clonez des glyphes entre plusieurs fichiers XPS, permettant une identité visuelle cohérente dans les rapports.

## Common Issues & Troubleshooting

| Issue | Solution |
|-------|----------|
| **Le clone renvoie null** | Assurez‑vous que le glyphe source (`glyphs`) est ajouté au premier document avant le clonage. |
| **La couleur ne change pas** | Convertissez (`cast`) `glyphs.Fill` en `XpsSolidColorBrush` avant de définir la propriété `Color` (comme montré à l'étape 7). |
| **Le fichier n'est pas enregistré** | Vérifiez que `dataDir` pointe vers un dossier valide et accessible en écriture et que vous disposez des autorisations nécessaires. |
| **Taille du glyphe inattendue** | Ajustez le paramètre de taille de police (deuxième argument de `AddGlyphs`) pour mettre à l'échelle le glyphe correctement. |

## Frequently Asked Questions

**Q1 : Puis‑je utiliser Aspose.Page pour .NET avec d'autres formats de documents ?**  
R1 : Aspose.Page pour .NET est spécifiquement conçu pour travailler avec les documents XPS. Si vous devez manipuler d'autres formats, vous pouvez explorer d'autres bibliothèques Aspose adaptées à ces formats.

**Q2 : Une licence temporaire est‑elle disponible pour Aspose.Page pour .NET ?**  
R2 : Oui, vous pouvez obtenir une licence temporaire à des fins de test. Consultez [ici](https://purchase.aspose.com/temporary-license/) pour plus d'informations.

**Q3 : Comment obtenir du support ou de l'aide pour d'éventuels problèmes ?**  
R3 : N'hésitez pas à visiter le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour entrer en contact avec la communauté et demander de l'aide.

**Q4 : Y a‑t‑il des limitations à la version d'essai gratuite ?**  
R4 : La version d'essai gratuite comporte certaines limitations ; il est recommandé de consulter la documentation pour les détails avant utilisation.

**Q5 : Où puis‑je trouver la documentation complète d'Aspose.Page pour .NET ?**  
R5 : Vous pouvez consulter la documentation [ici](https://reference.aspose.com/page/net/) pour des informations détaillées et des exemples.

**Q6 : Comment changer la couleur du contour d'un glyphe au lieu du remplissage ?**  
R6 : Utilisez `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` pour définir un pinceau de contour.

**Q7 : Puis‑je ajouter plusieurs clones de glyphes au même document ?**  
R7 : Oui, appelez `doc2.Add(glyphs.Clone());` de façon répétée, en ajustant les positions selon les besoins.

---

**Dernière mise à jour :** 2026-01-07  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}