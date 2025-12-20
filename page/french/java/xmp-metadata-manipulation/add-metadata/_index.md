---
date: 2025-12-20
description: Apprenez à ajouter des métadonnées XMP aux fichiers EPS avec le tutoriel
  Aspose Page Java. Suivez ce guide étape par étape pour améliorer votre gestion de
  documents.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Tutoriel Aspose Page Java – Ajouter des métadonnées XMP aux fichiers EPS
url: /fr/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des métadonnées XMP avec Java

## Introduction
Dans ce **aspose page java tutorial**, vous apprendrez comment améliorer les métadonnées de votre document en ajoutant des informations XMP à l'aide de Java. Ce guide étape par étape vous guide à travers la lecture d'un fichier EPS existant, l'extraction de ses métadonnées XMP, et l'enregistrement des modifications sur le disque avec la bibliothèque Aspose.Page for Java. À la fin du tutoriel, vous disposerez d'un modèle solide et réutilisable pour travailler avec XMP dans n'importe quel flux de travail EPS.

## Quick Answers
- **Quelle bibliothèque est requise ?** Aspose.Page for Java  
- **Puis-je ajouter du XMP à n'importe quel fichier EPS ?** Yes – the API creates a new XMP block if one does not already exist.  
- **Ai-je besoin d'une licence pour le développement ?** A free trial works for evaluation; a commercial license is required for production.  
- **Quelle version de Java est prise en charge ?** Java 8 and later.  
- **Combien de temps prend l'implémentation ?** Typically under 10 minutes for a basic metadata update.

## Aspose Page Java Tutorial Overview
Ce tutoriel démontre les étapes essentielles nécessaires pour manipuler les métadonnées XMP dans les fichiers EPS. Comprendre ces étapes vous aidera à intégrer la gestion des métadonnées dans des pipelines de traitement de documents plus larges, à améliorer la recherchabilité et à respecter les normes industrielles de gestion des actifs numériques.

## Prérequis
Avant de commencer le tutoriel, assurez-vous de disposer des prérequis suivants :
- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page for Java installée. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).  
- Un fichier EPS que vous souhaitez modifier.

## Import Packages
Tout d'abord, importez les packages nécessaires dans votre programme Java :

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Étape 1 : Obtenir les métadonnées XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Remplacez `"Your Document Directory"` par le chemin réel où vos documents sont stockés.

## Étape 2 : Récupérer la valeur CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Étape 3 : Récupérer la valeur CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Étape 4 : Récupérer la valeur Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Étape 5 : Récupérer la valeur Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Étape 6 : Récupérer la valeur Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Étape 7 : Récupérer la valeur MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Étape 8 : Enregistrer le document avec les nouvelles métadonnées XMP
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Enfin, n'oubliez pas de fermer le flux EPS d'entrée :

```java
// Close input EPS stream
psStream.close();
```

Vous avez maintenant ajouté avec succès des métadonnées à votre fichier EPS en utilisant Aspose.Page for Java !

## Conclusion
Dans ce **aspose page java tutorial**, nous avons exploré comment ajouter des métadonnées XMP à un fichier EPS à l'aide de la bibliothèque Aspose.Page for Java. Cette API puissante vous permet de manipuler les métadonnées des documents de manière programmatique, vous aidant à garder vos actifs organisés et recherchables.

## Frequently Asked Questions

**Q : Aspose.Page for Java est-il gratuit ?**  
A : Aspose.Page for Java is a commercial product. You can explore its features through a free trial [here](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation pour Aspose.Page for Java ?**  
A : The documentation is available [here](https://reference.aspose.com/page/java/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
A : You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q : Quels formats de fichiers Aspose.Page for Java prend‑il en charge ?**  
A : Aspose.Page for Java supports various formats, including EPS, PDF, and XPS.

**Q : Puis‑je acheter Aspose.Page for Java ?**  
A : Yes, you can purchase Aspose.Page for Java [here](https://purchase.aspose.com/buy).

**Q : Comment gérer les gros fichiers EPS lors de l’ajout de métadonnées ?**  
A : Process the file in a streaming fashion (as shown) to keep memory usage low, and close streams promptly.

**Q : Puis‑je modifier les champs XMP existants au lieu de simplement les lire ?**  
A : Absolutely – you can use `xmp.put(key, value)` to update or add new entries before saving.

---

**Dernière mise à jour :** 2025-12-20  
**Testé avec :** Aspose.Page for Java 24.12 (latest)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}