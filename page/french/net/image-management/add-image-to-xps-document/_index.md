---
title: Ajouter une image au document XPS avec Aspose.Page pour .NET
linktitle: Ajouter une image au document XPS
second_title: API Aspose.Page .NET
description: Découvrez l'intégration transparente des images dans les documents XPS avec Aspose.Page pour .NET. Suivez notre guide étape par étape pour une expérience de développement fluide.
weight: 11
url: /fr/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une image au document XPS avec Aspose.Page pour .NET

## Introduction

Dans le monde du développement .NET, l'incorporation d'images dans des documents XPS est une exigence courante. Aspose.Page for .NET simplifie ce processus en offrant une boîte à outils puissante pour manipuler et améliorer les documents XPS sans effort. Ce didacticiel vous guidera à travers les étapes d'ajout d'une image à un document XPS à l'aide d'Aspose.Page pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Aspose.Page pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir de[Documentation Aspose.Page .NET](https://reference.aspose.com/page/net/).

2. Environnement de développement : configurez un environnement de développement .NET, tel que Visual Studio.

3. Exemple d'image : disposez d'un exemple de fichier image (par exemple, "QL_logo_color.tif") que vous souhaitez ajouter au document XPS.

## Importer des espaces de noms

Commencez par importer les espaces de noms nécessaires dans votre projet .NET. Ces espaces de noms sont essentiels pour utiliser les fonctionnalités fournies par Aspose.Page pour .NET.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Étape 1 : Définir le répertoire des documents

Commencez par spécifier le chemin d'accès à votre répertoire de documents. Cette étape garantit que votre projet sait où localiser et enregistrer les fichiers.

```csharp
// ExDébut : 1
string dataDir = "Your Document Directory";
// ExFin : 1
```

## Étape 2 : Créer un document XPS

Créez un nouveau document XPS à l'aide d'Aspose.Page pour .NET.

```csharp
// ExDébut : 1
XpsDocument doc = new XpsDocument();
// ExFin : 1
```

## Étape 3 : Ajouter une image au document XPS

Maintenant, ajoutons l'image au document XPS. Dans cet exemple, nous utiliserons un exemple d'image nommé "QL_logo_color.tif".

```csharp
// ExDébut : 1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// ExFin : 1
```

## Étape 4 : Enregistrer le document XPS résultant

Enregistrez le document XPS avec l'image ajoutée.

```csharp
// ExDébut : 1
doc.Save(dataDir + "AddImage_outXPS.xps");
// ExFin : 1
```

Vous avez maintenant ajouté avec succès une image à un document XPS à l'aide d'Aspose.Page pour .NET !

## Conclusion

Dans ce didacticiel, nous avons exploré comment exploiter Aspose.Page pour .NET pour incorporer de manière transparente des images dans des documents XPS. Ce guide étape par étape garantit un processus d'intégration fluide, améliorant ainsi vos capacités de développement .NET.

## FAQ

### Q1 : Aspose.Page pour .NET est-il compatible avec les dernières versions du framework .NET ?

 A1 : Aspose.Page pour .NET est conçu pour être compatible avec un large éventail de versions du framework .NET, y compris les dernières versions. Se référer au[Documentation](https://reference.aspose.com/page/net/) pour des détails spécifiques.

### Q2 : Puis-je utiliser Aspose.Page pour .NET dans les environnements Windows et Linux ?

A2 : Oui, Aspose.Page pour .NET est indépendant de la plate-forme, ce qui le rend adapté à une utilisation dans les environnements Windows et Linux.

### Q3 : Existe-t-il des options de licence pour Aspose.Page pour .NET ?

 A3 : Oui, vous pouvez explorer les options de licence et effectuer un achat[ici](https://purchase.aspose.com/buy).

### Q4 : Existe-t-il un essai gratuit disponible pour Aspose.Page pour .NET ?

 A4 : Oui, vous pouvez essayer Aspose.Page pour .NET gratuitement en accédant au[essai gratuit](https://releases.aspose.com/).

### Q5 : Où puis-je demander de l'aide ou dialoguer avec la communauté pour Aspose.Page pour .NET ?

 A5 : Visitez le[Aspose.Page pour le forum .NET](https://forum.aspose.com/c/page/39) pour se connecter avec la communauté et obtenir du soutien.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
