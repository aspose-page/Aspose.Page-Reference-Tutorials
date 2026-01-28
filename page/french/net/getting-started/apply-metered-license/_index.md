---
date: 2026-01-28
description: Apprenez à convertir EPS en PNG en utilisant Aspose.Page pour .NET et
  à appliquer une licence à compteurs pour un traitement fluide des documents.
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: Convertir EPS en PNG et appliquer une licence à compteurs avec Aspose.Page
  pour .NET
url: /fr/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir EPS en PNG et appliquer une licence à usage mesuré avec Aspose.Page pour .NET

## Introduction

Débloquez tout le potentiel d'Aspose.Page pour .NET en **convertissant EPS en PNG** et en appliquant une licence à usage mesuré. Ce tutoriel vous guide à travers chaque étape — du chargement d'un fichier EPS à son enregistrement en tant qu'image PNG — afin que vous puissiez traiter les documents efficacement et sans filigranes d'évaluation.

## Réponses rapides
- **Quel est le sujet de ce tutoriel ?** Conversion de fichiers EPS en images PNG et application d'une licence à usage mesuré avec Aspose.Page pour .NET.  
- **Ai-je besoin d'une licence ?** Oui, une licence à usage mesuré est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de temps prend l'implémentation ?** Environ 10 à 15 minutes pour une conversion de base.  
- **Puis-je exécuter cela sur Linux/macOS ?** Absolument — Aspose.Page est multiplateforme.

## Qu'est-ce que « convertir EPS en PNG » ?

Convertir EPS en PNG signifie rasteriser un fichier Encapsulated PostScript (EPS) basé sur des vecteurs en une image bitmap PNG. Cela est utile lorsque vous devez afficher ou intégrer des graphiques dans des pages web, des rapports ou des composants d'interface utilisateur qui ne prennent pas en charge le format EPS.

## Pourquoi utiliser une licence à usage mesuré pour la conversion d'EPS en image ?

Une licence à usage mesuré vous permet de ne payer que pour les pages que vous traitez, ce qui est idéal pour des charges de travail à volume variable. Elle supprime également la bannière d'évaluation rouge qui apparaît lors de l'utilisation de la version d'essai gratuite, garantissant une sortie propre pour vos utilisateurs finaux.

## Prérequis

Avant de plonger dans les étapes, assurez-vous d'avoir les prérequis suivants en place :

- Une licence valide d'Aspose.Page pour .NET : vous pouvez l'obtenir sur [purchase.aspose.com](https://purchase.aspose.com/buy).
- Bibliothèque Aspose.Page installée : consultez la [documentation](https://reference.aspose.com/page/net/) pour les instructions d'installation.
- Environnement de développement .NET : assurez‑vous d'avoir un environnement .NET fonctionnel installé sur votre machine.

## Importer les espaces de noms

Dans votre projet .NET, importez les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Page :

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Comment convertir EPS en PNG avec une licence à usage mesuré ?

Voici un guide étape par étape qui couvre tout ce que vous devez savoir.

### Étape 1 : Définir les clés publiques et privées de la licence à usage mesuré

Initialisez la classe `Aspose.Page.Metered` et définissez les clés publiques et privées de la licence à usage mesuré. Remplacez `<type public key here>` et `<type private key here>` par vos clés réelles.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### Étape 2 : Charger le fichier EPS et créer le document

Spécifiez le chemin de votre fichier EPS et créez un flux pour lire son contenu. Ensuite, créez une instance de la classe `PsDocument` à partir du flux.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Étape 3 : Convertir le fichier EPS en image PNG

Créez un `ImageDevice` pour convertir le fichier EPS en image PNG. Enregistrez le fichier EPS en tant qu'image à l'aide de `ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### Étape 4 : Récupérer les octets de l'image

Obtenez les octets de l'image, chaque tableau d'octets représentant une page. Dans ce cas, nous avons une page.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### Étape 5 : Enregistrer les octets de l'image dans un fichier

Enregistrez les octets de l'image dans un fichier, garantissant une conversion réussie d'EPS en PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### Étape 6 : Vérifier la licence à usage mesuré

Vérifiez visuellement si la licence à usage mesuré a été appliquée avec succès. Si l'image résultante ne contient pas le message d'évaluation rouge, cela indique que la licence à usage mesuré a été appliquée sans problème.

Vous êtes maintenant prêt à exploiter toutes les capacités d'Aspose.Page pour .NET avec une licence à usage mesuré !

## Problèmes courants et solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| La bannière d'évaluation rouge apparaît toujours | Licence non définie ou clés incorrectes | Vérifiez à nouveau les clés publiques/privées et assurez‑vous que `SetMeteredKey` est appelé avant tout traitement de document |
| Aucun fichier de sortie créé | Chemin `dataDir` incorrect ou permissions de fichier | Vérifiez que le répertoire existe et que l'application possède les permissions d'écriture |
| Plusieurs pages non enregistrées | Seule la première page est écrite | Bouclez sur `imagesBytes` et écrivez chaque tableau dans un fichier PNG séparé |

## Questions fréquemment posées

**Q : Puis‑je utiliser la licence à usage mesuré dans un pipeline CI/CD ?**  
**R :** Oui, vous pouvez stocker les clés en toute sécurité (par ex., dans des variables d'environnement) et appeler `SetMeteredKey` pendant le processus de construction.

**Q : Aspose.Page prend‑il en charge la préservation du profil couleur lors de la conversion en PNG ?**  
**R :** La sortie PNG conserve les informations de couleur d'origine, mais vous pouvez la personnaliser davantage via `ImageSaveOptions`.

**Q : Est‑il possible de convertir EPS en d'autres formats raster (JPEG, BMP) ?**  
**R :** Absolument — il suffit de changer `ImageSaveOptions` vers le format souhaité.

**Q : Quelle est la taille maximale de fichier EPS prise en charge ?**  
**R :** Aspose.Page gère les gros fichiers, mais la consommation de mémoire augmente avec la résolution de l'image. Envisagez de traiter les pages individuellement pour les documents très volumineux.

**Q : Comment puis‑je récupérer programmétiquement le nombre de pages du fichier EPS ?**  
**R :** Utilisez `document.PagesCount` après avoir chargé le `PsDocument`.

## FAQ

### Q1 : Comment obtenir une licence à usage mesuré pour Aspose.Page pour .NET ?

R1 : Visitez [purchase.aspose.com](https://purchase.aspose.com/buy) pour acquérir une licence valide.

### Q2 : Où puis‑je trouver la documentation d'Aspose.Page pour .NET ?

R2 : Consultez [Aspose.Page .NET](https://reference.aspose.com/page/net/) pour une documentation complète.

### Q3 : Existe‑t‑il un forum pour les discussions et le support d'Aspose.Page ?

R3 : Oui, visitez le [forum](https://forum.aspose.com/c/page/39) pour interagir avec la communauté et demander de l'aide.

### Q4 : Puis‑je essayer Aspose.Page pour .NET avant d'acheter ?

R4 : Absolument ! Accédez à l'essai gratuit [ici](https://releases.aspose.com/).

### Q5 : Comment obtenir une licence temporaire pour Aspose.Page pour .NET ?

R5 : Visitez [temporary license/](https://purchase.aspose.com/temporary-license/) pour obtenir une licence temporaire.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**Dernière mise à jour :** 2026-01-28  
**Testé avec :** Aspose.Page 24.12 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}