---
date: 2026-01-23
description: Apprenez à modifier les fichiers EPS en ajoutant des valeurs nommées
  à l’aide d’Aspose.Page pour .NET. Ce guide étape par étape aide les développeurs
  à manipuler les métadonnées EPS.
linktitle: Add Named Value
second_title: Aspose.Page .NET API
title: Comment modifier les fichiers EPS – Ajouter une valeur nommée avec Aspose.Page
url: /fr/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment modifier les fichiers EPS – Ajouter une valeur nommée avec Aspose.Page

## Comment modifier les fichiers EPS – Introduction

Dans ce tutoriel sur **comment modifier les fichiers EPS**, nous vous guidons pas à pas pour ajouter une valeur nommée à un document EPS en utilisant la bibliothèque Aspose.Page pour .NET. Que vous construisiez un outil de traitement par lots ou que vous deviez enrichir les métadonnées EPS à la volée, les étapes ci‑dessous vous offrent un guide clair et pratique.

## Réponses rapides
- **Que peut faire Aspose.Page ?** Elle ?** Un essai gratuit’implémentation  minutes pour le scénario de valeur nommée de base.  
- **Est‑ce sûr pour les gros fichiers EPS ?** Oui – Aspose.Page diffuse les données, maintenant une faible consommation de mémoire.

## Prérequis

Avant de commencer le tutoriel, assurez‑vous que les prérequis suivants sont en place :

- Connaissances de base du langage de programmation C#.  
- Un environnement de développement intégré (IDE) tel que Visual Studio installé.  
- La bibliothèque Aspose.Page pour .NET. Si elle n’est pas installée, vous pouvez la télécharger [ici](https://releases.aspose.com/page/net/).

## Importer les espaces de noms

Tout d’abord, importons les espaces de noms nécessaires dans votre code C#. Ces espaces de noms sont essentiels pour accéder aux fonctionnalités fournies par Aspose.Page :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Étape 1 : Initialiser le flux d’entrée du fichier EPS

L’étape initiale consiste à initialiser le flux d’entrée pour le fichier EPS. Remplacez `"Your Document Directory"` par le chemin de votre répertoire de documents :

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Étape 2 : Obtenir les métadonnées XMP

Récupérez les métadonnées XMP du fichier EPS. Si le fichier EPS ne possède pas de métadonnées XMP, une nouvelle sera créée, remplie avec les valeurs provenant des commentaires de métadonnées PS :

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

##onnées XMP. Dans cetmée à la structure `"xmpTPg:MaxPageSize"` :

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Étape 4 : Enregistrer le fichier EPS avec les métadonnées XMP modifiées

Enregistrez le fichier EPS avec les métadonnées XMP mises à jour. Créez un flux de sortie et sauvegardez le fichier EPS modifié :

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

##

###‑il compatible avec différentes versions de fichiers EPS ?

R1 : Aspose2 : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?

R2 : Oui, Aspose.Page est fourni avec une licence commerciale, que vous pouvez acheter [ici](https://purchase.aspose.com/buy).

### Q3 : Existe‑t‑il un essai gratuit pour Aspose.Page ?

R3 : Oui, vous pouvez explorer Aspose.Page grâce à un essai gratuit disponible [ici](https://releases.aspose.com/).

### Q4 : Comment obtenir du support ou rejoindre la communauté Aspose ?

R4 : Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide et échanger avec la communauté.

### Q5 : Qu’est‑ce qu’une licence temporaire et comment en obtenir une ?

R5 : Si vous avez besoin d’une licence temporaire pour des tests ou une évaluation, vous pouvez en acquérir une [ici](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-23  
**Testé avec :** Aspose.Page 24.11 pour .NET  
**Auteur :** Aspose  

---