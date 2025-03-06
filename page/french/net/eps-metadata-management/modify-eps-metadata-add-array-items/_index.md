---
title: Ajouter des éléments de tableau avec Aspose.Page
linktitle: Ajouter des éléments de tableau
second_title: API Aspose.Page .NET
description: Découvrez comment ajouter des éléments de tableau dans des fichiers EPS à l'aide d'Aspose.Page pour .NET. Suivez notre guide étape par étape pour une manipulation fluide des documents.
weight: 11
url: /fr/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des éléments de tableau avec Aspose.Page

## Introduction

Dans le domaine de la manipulation et du traitement de documents dans .NET, Aspose.Page se distingue comme un outil puissant. Parmi ses nombreuses fonctionnalités, la gestion des éléments du tableau dans un fichier EPS est une exigence courante. Dans ce didacticiel, nous explorerons le processus étape par étape d'ajout d'éléments de tableau à l'aide d'Aspose.Page dans un environnement .NET. Que vous soyez un développeur chevronné ou un nouveau venu, ce guide vous guidera tout au long du processus avec clarté et précision.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

- Une compréhension de base de la programmation .NET.
-  Aspose.Page pour .NET installé. Sinon, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/page/net/).
- Un éditeur de code, tel que Visual Studio, à suivre avec les exemples.

## Importer des espaces de noms

Dans votre projet .NET, assurez-vous d'importer les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Page. Ajoutez les lignes suivantes au début de votre code :

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ces espaces de noms donnent accès aux classes et méthodes essentielles requises pour la manipulation des fichiers EPS.

## Étape 1 : Initialiser le flux d'entrée du fichier EPS

```csharp
// ExDébut : 3
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Initialiser le flux d'entrée du fichier EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Créer une instance PsDocument à partir du flux
PsDocument document = new PsDocument(psStream);            
// ExFin : 3
```

 Ici, nous configurons le flux d'entrée initial pour le fichier EPS et créons un`PsDocument` exemple.

## Étape 2 : Obtenez les métadonnées XMP

```csharp
// ExDébut : 4
// Obtenez les métadonnées XMP. Si le fichier EPS ne contient pas de métadonnées XMP, nous en obtenons une nouvelle remplie de valeurs provenant des commentaires de métadonnées PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
// ExFin : 4
```

Récupérez les métadonnées XMP du fichier EPS. Si le fichier EPS ne contient pas de métadonnées XMP, un nouveau fichier est créé avec les valeurs des commentaires de métadonnées PS.

## Étape 3 : Modifier les valeurs des métadonnées XMP

```csharp
// ExDébut : 5
// Modifier les valeurs des métadonnées XMP

// Ajoutez un titre supplémentaire. Il sera ajouté par défaut à la fin du tableau.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Ajoutez un créateur supplémentaire. Il sera ajouté dans le tableau par un index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExFin : 5
```

Modifiez les métadonnées XMP en ajoutant de nouveaux titres et créateurs au tableau.

## Étape 4 : Enregistrez le fichier EPS avec les métadonnées XMP modifiées

```csharp
// ExDébut : 6
// Enregistrer le fichier EPS avec les métadonnées XMP modifiées

// Créer un flux de sortie
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Enregistrer le fichier EPS
    document.Save(outPsStream);
}
// ExFin : 6
```

Enfin, enregistrez le fichier EPS avec les métadonnées XMP mises à jour. Les modifications apportées aux éléments du tableau seront reflétées dans le fichier de sortie.

## Conclusion

L'ajout d'éléments de tableau avec Aspose.Page dans .NET est un processus simple, comme le démontre ce didacticiel. Avec les bonnes conditions préalables et un guide étape par étape, les développeurs peuvent manipuler de manière transparente les fichiers EPS, garantissant que leurs documents répondent à des exigences spécifiques en matière de métadonnées.

## FAQ

### Q1 : Aspose.Page est-il compatible avec tous les environnements .NET ?

A1 : Oui, Aspose.Page est conçu pour fonctionner de manière transparente avec tous les environnements .NET, offrant des fonctionnalités cohérentes sur toutes les plateformes.

### Q2 : Puis-je utiliser Aspose.Page gratuitement ?

 A2 : Aspose.Page propose une version d'essai gratuite, permettant aux utilisateurs d'explorer ses fonctionnalités. Pour une utilisation continue, une licence doit être achetée auprès de[ici](https://purchase.aspose.com/buy).

### Q3 : Des licences temporaires sont-elles disponibles pour Aspose.Page ?

 A3 : Oui, des licences temporaires peuvent être obtenues auprès de[ici](https://purchase.aspose.com/temporary-license/) pour les besoins du projet à court terme.

### Q4 : Où puis-je trouver le support communautaire pour Aspose.Page ?

A4 : Pour les discussions et le soutien de la communauté, visitez le[Forum Aspose.Page](https://forum.aspose.com/c/page/39).

### Q5 : Quelle est la dernière version d’Aspose.Page pour .NET ?

 A5 : Pour accéder à la dernière version d'Aspose.Page pour .NET, reportez-vous au[Documentation](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
