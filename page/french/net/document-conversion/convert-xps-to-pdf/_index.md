---
date: 2026-01-10
description: Convertissez facilement XPS en PDF avec .NET grâce à Aspose.Page. Téléchargez
  la bibliothèque, explorez la documentation et obtenez un essai gratuit.
linktitle: Convert XPS to PDF
second_title: Aspose.Page .NET API
title: Convertir XPS en PDF avec Aspose.Page pour .NET
url: /fr/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS en PDF avec Aspose.Page pour .NET

## Introduction

Dans ce tutoriel, vous apprendrez **comment convertir XPS en PDF** en utilisant la bibliothèque Aspose.Page pour .NET. La conversion de XPS en PDF est une exigence courante lorsque vous devez partager des documents XPS avec des utilisateurs qui ne disposent que de lecteurs PDF, ou lorsque vous souhaitez intégrer du contenu XPS dans des flux de travail PDF plus importants. Nous parcourrons chaque étape, expliquerons pourquoi chaque paramètre est important et vous montrerons comment affiner la sortie — par exemple en définissant la qualité JPEG et en appliquant la compression d'images PDF.

## Réponses rapides
- **Quelle bibliothèque est la meilleure pour la conversion XPS en PDF ?** Aspose.Page for .NET
- **Ai-je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise ; un essai gratuit est disponible.
- **Puis-je contrôler la qualité de l’image ?** Absolument—utilisez `JpegQualityLevel` et `PdfImageCompression`.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Est‑il possible de convertir plusieurs fichiers XPS en un seul PDF ?** Oui, en parcourant les fichiers et en fusionnant les résultats.

## Prérequis

Avant de nous lancer dans cette conversion, assurez‑vous d’avoir les prérequis suivants :

- **Aspose.Page for .NET Library** – Assurez‑vous d’avoir la bibliothèque Aspose.Page pour .NET installée dans votre environnement de développement. Vous pouvez la télécharger depuis la [documentation Aspose.Page](https://reference.aspose.com/page/net/).
- **Development Environment** – Configurez un environnement de développement .NET avec Visual Studio ou tout autre IDE compatible.
- **XPS Document** – Préparez le document XPS que vous souhaitez convertir en PDF. Il peut s’agir de votre fichier XPS d’exemple stocké dans un répertoire désigné.

## Importer les espaces de noms

Avant de plonger dans le code, importons l’espace de noms nécessaire pour rendre les fonctionnalités d’Aspose.Page pour .NET accessibles dans notre projet :

```csharp
using Aspose.Page.XPS;
```

## Guide étape par étape

### Étape 1 : Initialiser le répertoire du document

Définissez le dossier qui contient votre fichier XPS source et où le PDF résultant sera enregistré.

```csharp
string dataDir = "Your Document Directory";
```

Remplacez `"Your Document Directory"` par le chemin absolu ou relatif vers le dossier contenant votre document XPS.

### Étape 2 : Ouvrir les flux pour la sortie PDF et l’entrée XPS

Nous utilisons deux flux de fichiers — un pour lire le fichier XPS et un autre pour écrire le PDF généré.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Astuce :** Assurez‑vous que les chemins sont corrects et que l’application dispose des permissions de lecture/écriture sur le dossier cible.

### Étape 3 : Charger le document XPS

Créez une instance `XpsDocument` à partir du flux XPS. L’objet `XpsLoadOptions` vous permet de spécifier les préférences de chargement, mais les paramètres par défaut fonctionnent dans la plupart des scénarios.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

### Étape 4 : Configurer les options d’enregistrement PDF

Ici nous définissons les préférences de sortie PDF. Notez l’utilisation de **compression d’image PDF** (`PdfImageCompression.Jpeg`) et de **qualité JPEG** (`JpegQualityLevel = 100`). Ces paramètres influencent directement la taille du fichier et la fidélité visuelle.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Contrôle la qualité des images JPEG intégrées dans le PDF (plus élevé = meilleure qualité, fichier plus volumineux).
- **`ImageCompression`** – Choisit l’algorithme de compression ; JPEG est idéal pour les images photographiques.
- **`TextCompression`** – La compression Flate réduit la taille du PDF sans perdre la qualité du texte.
- **`PageNumbers`** – Vous permet de **enregistrer XPS en PDF** pour les pages sélectionnées uniquement.

### Étape 5 : Créer un dispositif de rendu PDF

Le `PdfDevice` agit comme la cible de rendu qui écrit les données PDF dans le flux que nous avons ouvert précédemment.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Étape 6 : Enregistrer le document en PDF

Enfin, invoquez la méthode `Save`, en passant le dispositif de rendu et les options configurées.

```csharp
document.Save(device, options);
```

Lorsque le code aura terminé son exécution, `XPStoPDF_out.pdf` apparaîtra dans le répertoire spécifié, contenant les pages converties avec les réglages de compression et de qualité que vous avez définis.

## Pourquoi convertir XPS en PDF ?

- **Accessibilité universelle** – Les visionneuses PDF sont installées sur pratiquement tous les appareils, tandis que les lecteurs XPS sont rares.
- **Préserver la mise en page** – Le PDF conserve la mise en page visuelle exacte, les polices et les graphiques du XPS original.
- **Traitement ultérieur** – Une fois en PDF, vous pouvez fusionner, annoter ou signer numériquement le document à l’aide d’autres bibliothèques Aspose.

## Cas d’utilisation courants

- **Reporting d’entreprise** – Générer des rapports XPS à partir de systèmes hérités et les convertir en PDF pour la distribution.
- **Archivage** – Stocker les documents au format PDF pour une conservation à long terme tout en pouvant les créer à partir de sources XPS.
- **Services web** – Proposer un point de terminaison API qui accepte les téléchargements XPS et renvoie des fichiers PDF à la volée.

## Dépannage et astuces

- **Fichier introuvable** – Vérifiez à nouveau le chemin `dataDir` et assurez‑vous que le nom du fichier XPS correspond exactement.
- **Erreurs de permission** – Exécutez Visual Studio en tant qu’administrateur ou accordez des permissions d’écriture au dossier de sortie.
- **PDF volumineux** – Si le PDF résultant est trop gros, réduisez `JpegQualityLevel` ou changez `ImageCompression` en `PdfImageCompression.Zip`.

## FAQ

### Q1 : Puis‑je convertir plusieurs fichiers XPS en un seul PDF en utilisant Aspose.Page pour .NET ?

A1 : Oui, vous pouvez parcourir plusieurs fichiers XPS et suivre les mêmes étapes pour les fusionner en un seul PDF.

### Q2 : Existe‑t‑il d’autres formats de sortie pris en charge par Aspose.Page pour .NET ?

A2 : Oui, Aspose.Page pour .NET prend en charge divers formats de sortie, notamment TIFF, JPEG, PNG, et plus encore.

### Q3 : Comment puis‑je personnaliser l’apparence du document PDF converti ?

A3 : Vous pouvez ajuster les paramètres de l’objet options, tels que la compression d’image et la compression du texte, pour obtenir l’apparence souhaitée.

### Q4 : Une version d’essai est‑elle disponible pour Aspose.Page pour .NET ?

A4 : Oui, vous pouvez explorer les capacités d’Aspose.Page pour .NET en obtenant un essai gratuit depuis [ici](https://releases.aspose.com/).

### Q5 : Où puis‑je obtenir du support communautaire pour Aspose.Page pour .NET ?

A5 : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour les discussions communautaires et le support.

## Questions fréquemment posées (compatible IA)

**Q : Comment définir la qualité JPEG lors de la conversion de XPS en PDF ?**  
A : Utilisez la propriété `JpegQualityLevel` dans `PdfSaveOptions`. La régler à 100 donne la qualité maximale.

**Q : Que signifie « compression d’image PDF » dans ce contexte ?**  
A : Cela fait référence à l’option `ImageCompression`, qui détermine comment les images sont compressées à l’intérieur du PDF (par ex., JPEG, Zip).

**Q : Puis‑je générer programmétiquement un PDF sans source XPS ?**  
A : Oui, Aspose.Page prend également en charge **c# generate pdf** directement à partir de commandes de dessin, mais cela dépasse le cadre de ce tutoriel.

**Q : Existe‑t‑il un moyen de convertir XPS en PDF sans perdre les graphiques vectoriels ?**  
A : La conversion conserve les données vectorielles ; évitez simplement de rasteriser les images en maintenant `ImageCompression` réglé sur JPEG ou Zip selon les besoins.

**Q : La bibliothèque prend‑elle en charge .NET Core ?**  
A : Absolument – Aspose.Page pour .NET fonctionne avec .NET Core, .NET 5, .NET 6, et les versions ultérieures.

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** Aspose.Page 24.11 for .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}