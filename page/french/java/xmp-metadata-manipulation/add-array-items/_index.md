---
date: 2026-03-05
description: Apprenez comment ajouter des éléments du tableau dc:title aux métadonnées XMP
  des fichiers EPS à l’aide d’Aspose.Page pour Java. Suivez ce guide étape par étape
  pour obtenir des résultats rapides.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Comment ajouter des éléments de tableau dc:title dans les métadonnées XMP avec
  Java
url: /fr/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des éléments de tableau aux métadonnées XMP avec Java

## Introduction
Dans ce tutoriel, vous découvrirez **comment ajouter dc:title** (et d’autres éléments de tableau) aux métadonnées XMP d’un fichier EPS avec Aspose.Page for Java. Mettre à jour les métadonnées XMP est utile lorsque vous devez intégrer des informations recherchables — telles que des titres, des créateurs ou des mots‑clé — directement dans vos fichiers graphiques. Nous parcourrons chaque étape, expliquerons pourquoi chaque ligne est importante et vous montrerons comment vérifier les modifications.

## Quick Answers
- **Que représente “dc:title” ?** C’est la propriété titre du Dublin Core stockée sous forme de tableau XMP.  
- **Pourquoi modifier les métadonnées XMP ?** Cela permet une meilleure gestion des actifs, une recherche plus efficace et la conformité aux normes.  
- **Ai‑je besoin d’un bloc XMP existant ?** Non — Aspose.Page en générera un à partir des commentaires PS s’il est absent.  
- **Quelle version de la bibliothèque est requise ?** Toute version récente d’Aspose.Page for Java (testée avec la dernière build 2026).  
- **Puis‑je ajouter d’autres propriétés de tableau ?** Oui — utilisez la même méthode `addArrayItem` pour des propriétés comme `dc:creator`.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir :

- La bibliothèque Aspose.Page for Java installée (ajoutez le JAR à votre classpath).  
- Une expérience de base en développement Java (JDK 8+ recommandé).  
- Un fichier EPS contenant déjà des métadonnées XMP ou au moins des commentaires PS (par ex., `%%Title`, `%%Creator`).  

## Import Packages
Pour commencer, importez les classes nécessaires à la lecture, la manipulation et l’enregistrement des fichiers EPS :

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Step 1: Load the EPS Document and Retrieve XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Ici, nous ouvrons le fichier EPS et demandons à Aspose.Page son bloc XMP. Si le fichier ne possède pas de XMP, la bibliothèque crée automatiquement un bloc à partir des commentaires PS existants, garantissant ainsi la présence d’un conteneur de métadonnées avec lequel travailler.

## Step 2: Add a New **dc:title** Array Item  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Cette ligne montre **comment ajouter dc:title**. Remplacez `"NewTitle"` par le titre réel que vous souhaitez intégrer. La méthode ajoute la valeur au tableau de titres existant, en conservant les titres précédents.

## Step 3: Add a New **dc:creator** Array Item  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

De la même façon, vous pouvez enrichir la propriété `dc:creator`. Plusieurs créateurs peuvent être stockés ; chaque appel ajoute une nouvelle entrée.

## Step 4: Prepare the Output Stream  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Nous créons un flux pour le fichier EPS modifié. Utiliser un nom de fichier différent (`xmp3_changed.eps`) permet de laisser le fichier original intact.

## Step 5: Save the Document with Updated XMP Metadata  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

L’appel `save` écrit les données EPS ainsi que le bloc XMP mis à jour. Le bloc `finally` garantit que le handle du fichier est libéré même en cas d’exception.

## Why This Matters
Intégrer des valeurs précises de `dc:title` et `dc:creator` améliore :

- **La recherchabilité** dans les systèmes de gestion d’actifs numériques (DAM).  
- **La conformité** aux standards de publication qui exigent des métadonnées.  
- **La collaboration**, car les membres de l’équipe peuvent identifier rapidement le contenu du fichier sans l’ouvrir.

## Common Pitfalls & Tips
- **Pitfall :** Écraser accidentellement des éléments de tableau existants.  
  **Tip :** Utilisez `xmp.getArrayItems("dc:title")` pour inspecter les valeurs actuelles avant d’en ajouter de nouvelles.  
- **Pitfall :** Oublier de fermer les flux, ce qui entraîne des verrous de fichier.  
  **Tip :** Enveloppez toujours les I/O dans un try‑with‑resources ou un bloc `finally` comme illustré.  
- **Tip :** Vous pouvez chaîner plusieurs appels `addArrayItem` pour ajouter plusieurs titres ou créateurs en une seule passe.

## Frequently Asked Questions

### Puis‑je utiliser Aspose.Page for Java avec d’autres formats de documents ?
Oui, Aspose.Page prend en charge divers formats, notamment EPS, PDF et XPS.

### Existe‑t‑il un essai gratuit pour Aspose.Page for Java ?
Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

### Où puis‑je trouver la documentation d’Aspose.Page for Java ?
La documentation est disponible [ici](https://reference.aspose.com/page/java/).

### Comment puis‑je acheter Aspose.Page for Java ?
Vous pouvez acheter le produit [ici](https://purchase.aspose.com/buy).

### Des licences temporaires sont‑elles disponibles pour Aspose.Page for Java ?
Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest 2026 release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}