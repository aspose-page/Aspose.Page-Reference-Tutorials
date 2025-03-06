---
title: Ajouter une valeur nommée avec Aspose.Page
linktitle: Ajouter une valeur nommée
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter des valeurs nommées aux fichiers EPS dans .NET à l'aide d'Aspose.Page. Ce didacticiel complet vous guide pas à pas tout au long du processus.
weight: 12
url: /fr/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une valeur nommée avec Aspose.Page

## Introduction

Dans le domaine du traitement de documents avec .NET, Aspose.Page s'impose comme un outil puissant de gestion des fichiers EPS. Aspose.Page permet aux développeurs de manipuler les métadonnées XMP, facilitant ainsi les tâches telles que l'ajout de valeurs nommées. Ce didacticiel vous guidera étape par étape tout au long du processus d'ajout de valeurs nommées à un fichier EPS à l'aide d'Aspose.Page.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Connaissance de base du langage de programmation C#.
- Un environnement de développement intégré (IDE) tel que Visual Studio installé.
-  Aspose.Page pour la bibliothèque .NET. S'il n'est pas installé, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires dans votre code C#. Ces espaces de noms sont essentiels pour accéder aux fonctionnalités fournies par Aspose.Page :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Étape 1 : initialiser le flux d'entrée du fichier EPS

 La première étape consiste à initialiser le flux d’entrée du fichier EPS. Remplacer`"Your Document Directory"` avec le chemin d'accès à votre répertoire de documents :

```csharp
// ExDébut : 1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Étape 2 : Obtenez les métadonnées XMP

Récupérez les métadonnées XMP du fichier EPS. Si le fichier EPS ne contient pas de métadonnées XMP, un nouveau fichier sera créé, rempli des valeurs des commentaires de métadonnées PS :

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Étape 3 : modifier les valeurs des métadonnées XMP

Maintenant, apportons des modifications aux métadonnées XMP. Dans cet exemple, nous ajouterons une valeur nommée à la structure « xmpTPg:MaxPageSize » :

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Étape 4 : Enregistrez le fichier EPS avec les métadonnées XMP modifiées

Enregistrez le fichier EPS avec les métadonnées XMP mises à jour. Créez un flux de sortie et enregistrez le fichier EPS modifié :

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Conclusion

Toutes nos félicitations! Vous avez ajouté avec succès une valeur nommée à un fichier EPS à l'aide d'Aspose.Page dans .NET. Ce didacticiel vous a guidé à travers les étapes essentielles, mettant en valeur la simplicité et l'efficacité d'Aspose.Page dans la manipulation de documents.

## FAQ

### Q1 : Aspose.Page est-il compatible avec différentes versions de fichiers EPS ?

A1 : Aspose.Page prend en charge différentes versions de fichiers EPS, garantissant la compatibilité avec un large éventail de documents.

### Q2 : Puis-je utiliser Aspose.Page pour des projets commerciaux ?

 A2 : Oui, Aspose.Page est livré avec une licence commerciale et vous pouvez l'acheter[ici](https://purchase.aspose.com/buy).

### Q3 : Existe-t-il un essai gratuit disponible pour Aspose.Page ?

 A3 : Oui, vous pouvez explorer Aspose.Page avec un essai gratuit disponible[ici](https://releases.aspose.com/).

### Q4 : Comment puis-je obtenir de l'aide ou me connecter à la communauté Aspose ?

 A4 : Visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir du soutien et se connecter avec la communauté.

### Q5 : Qu'est-ce qu'une licence temporaire et comment puis-je en obtenir une ?

 A5 : Si vous avez besoin d'une licence temporaire à des fins de test ou d'évaluation, vous pouvez en acquérir une[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
