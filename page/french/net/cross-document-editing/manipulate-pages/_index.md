---
date: 2026-01-10
description: Apprenez à fusionner des documents XPS avec Aspose.Page pour .NET. Ce
  guide étape par étape montre les techniques de manipulation de pages pour des résultats
  efficaces.
linktitle: Manipulate Pages
second_title: Aspose.Page .NET API
title: Fusionner des documents XPS avec Aspose.Page pour .NET
url: /fr/net/cross-document-editing/manipulate-pages/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fusionner des documents XPS avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel, vous découvrirez comment **fusionner des documents XPS** et manipuler leurs pages à l'aide de la bibliothèque Aspose.Page dans un environnement .NET. Que vous ayez besoin de combiner plusieurs rapports en un seul fichier XPS ou de réorganiser les pages pour un rendu soigné, ce guide vous accompagne pas à pas, avec des explications claires et du code prêt à l'emploi.

## Quick Answers
- **Que puis‑je faire avec Aspose.Page ?** Fusionner des documents XPS, insérer, ajouter ou supprimer des pages, et enregistrer le résultat.  
- **Ai‑je besoin d'une licence pour les tests ?** Une licence temporaire est disponible pour l'évaluation.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Visual Studio est‑il requis ?** Non, tout IDE supportant C# fonctionne, mais Visual Studio est recommandé.  
- **Combien de temps prend la fusion ?** Typiquement quelques secondes pour des fichiers XPS de taille standard.

## What is merging XPS documents?
Fusionner des documents XPS consiste à prendre des pages de deux fichiers XPS existants ou plus et à les combiner en un seul document XPS. Cela est utile pour créer des rapports consolidés, compiler des manuels multipages ou préparer des paquets prêts à l'impression sans conversion vers un autre format.

## Why use Aspose.Page for .NET?
Aspose.Page propose une **API pure .NET** qui travaille directement avec les fichiers XPS — aucune nécessité d'outils externes ou de composants tiers. Elle vous offre un contrôle fin de l'ordre des pages, des points d'insertion et de la préservation du contenu, rendant le processus de fusion fiable et rapide.

## Prerequisites

- **Aspose.Page for .NET** – téléchargez depuis la [documentation Aspose.Page for .NET](https://reference.aspose.com/page/net/).  
- **Environnement de développement** – Visual Studio, Rider ou tout IDE supportant C#.  
- **Fichiers XPS d'entrée** – trois fichiers d'exemple (`input1.xps`, `input2.xps`, `input3.xps`) placés dans un dossier connu.

## Import Namespaces

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Ces espaces de noms vous donnent accès aux classes principales de documents XPS, aux modèles de pages et aux utilitaires de dessin de base.

## Step 1: Set the Document Directory

```csharp
string dataDir = "Your Document Directory";
```

Remplacez **Your Document Directory** par le chemin complet où vos fichiers XPS sont stockés, par ex., `C:\\Docs\\XpsFiles\\`.

## Step 2: Create XPS Document Instances

```csharp
XpsDocument doc1 = new XpsDocument(dataDir + "input1.xps");
XpsDocument doc2 = new XpsDocument(dataDir + "input2.xps");
XpsDocument doc3 = new XpsDocument(dataDir + "input3.xps");
XpsDocument doc4 = new XpsDocument();
```

- `doc1`, `doc2` et `doc3` représentent les documents source que vous souhaitez fusionner.  
- `doc4` est un document XPS vide qui contiendra le résultat fusionné.

## Step 3: Insert, Add, and Remove Pages

```csharp
doc4.InsertPage(1, doc2.Page, false);
doc4.AddPage(doc3.Page, false);
doc4.RemovePageAt(2);
doc4.InsertPage(2, doc1.SelectActivePage(3), false);
```

Voici ce que chaque ligne fait :

1. **InsertPage(1, doc2.Page, false)** – place la première page de `doc2` à la position 1 dans `doc4`.  
2. **AddPage(doc3.Page, false)** – ajoute la première page de `doc3` à la fin de `doc4`.  
3. **RemovePageAt(2)** – supprime la page actuellement à l'index 2 (utile pour éliminer les pages indésirables).  
4. **InsertPage(2, doc1.SelectActivePage(3), false)** – insère la troisième page de `doc1` à la position 2, complétant la fusion.

Ces opérations illustrent comment vous pouvez **fusionner des documents XPS** tout en réordonnant ou en supprimant des pages selon les besoins.

## Step 4: Save the Merged Document

```csharp
doc4.Save(dataDir + "out.xps");
```

Le fichier XPS fusionné final (`out.xps`) est écrit dans le même répertoire. Vous pouvez maintenant l'ouvrir avec n'importe quel visualiseur XPS ou le traiter davantage avec Aspose.Page.

## Common Issues and Solutions
- **Fichier non trouvé** – vérifiez le chemin `dataDir` et assurez‑vous que les fichiers d'entrée existent.  
- **Index de page invalide** – les index de pages commencent à 1 ; tenter d'insérer une page inexistante déclenche une exception.  
- **Erreurs de licence** – utilisez une licence temporaire ou complète avant de déployer en production.

## FAQ's

### Q1 : Puis‑je manipuler des pages provenant de différents documents XPS ?
R1 : Oui, comme démontré dans le tutoriel, vous pouvez insérer des pages de plusieurs documents XPS dans un nouveau document.

### Q2 : Comment puis‑je supprimer une page spécifique d'un document ?
R2 : Utilisez la méthode `RemovePageAt`, en spécifiant l'index de la page à supprimer.

### Q3 : Aspose.Page est‑il compatible avec Visual Studio ?
R3 : Oui, Aspose.Page est entièrement compatible avec Visual Studio, ce qui facilite son intégration dans vos projets .NET.

### Q4 : Existe‑t‑il des options de licence ?
R4 : Oui, vous pouvez explorer les options de licence et obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Q5 : Où puis‑je obtenir du support ou poser des questions ?
R5 : Consultez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir du support et échanger avec la communauté.

## Frequently Asked Questions

**Q : Puis‑je fusionner plus de trois fichiers XPS ?**  
R : Absolument. Créez des instances supplémentaires de `XpsDocument` et utilisez `InsertPage` ou `AddPage` de façon répétée pour construire un document fusionné plus grand.

**Q : La fusion préserve‑t‑elle le formatage et les graphiques d'origine ?**  
R : Oui. Aspose.Page copie le contenu de la page octet par octet, ainsi le texte, les images et les graphiques vectoriels restent inchangés.

**Q : Comment insérer une page à la fin sans spécifier d'index ?**  
R : Utilisez `AddPage(sourcePage, false)` qui ajoute la page à la fin du document.

**Q : Est‑il possible de fusionner des documents XPS sur un serveur sans interface utilisateur ?**  
R : L'API est entièrement sans tête ; vous pouvez exécuter le même code dans ASP.NET, Azure Functions ou tout environnement .NET côté serveur.

**Q : Et si mes fichiers XPS sont protégés par mot de passe ?**  
R : Aspose.Page ne prend actuellement pas en charge les fichiers XPS chiffrés ; vous devez les déchiffrer avant de les fusionner.

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.Page for .NET 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}