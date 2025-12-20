---
date: 2025-12-20
description: Apprenez à ajouter l'espace de noms XMP dans les fichiers EPS avec Aspose.Page
  pour Java dans ce tutoriel complet sur aspose.page xmp.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: Tutoriel Aspose.Page XMP – Ajouter un espace de noms dans XMP avec Java
url: /fr/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp tutorial – Ajouter un espace de noms XMP avec Java

## Introduction

Si vous devez modifier ou enrichir les métadonnées des fichiers EPS, **aspose.page xmp tutorial** vous montre exactement **comment ajouter un espace de noms XMP** en Java. Dans ce guide, nous parcourrons chaque étape — du chargement d’un document EPS, à l’enregistrement d’un espace de noms personnalisé, en passant par l’insertion d’une nouvelle propriété, jusqu’à l’enregistrement du fichier mis à jour. À la fin, vous disposerez d’un modèle clair et réutilisable pour travailler avec les métadonnées XMP dans tout projet Java utilisant Aspose.Page.

## Quick Answers
- **Quel est l’objectif principal ?** Ajouter un espace de noms XMP personnalisé et une propriété à un fichier EPS.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java.  
- **Ai‑je besoin d’une licence pour les tests ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Combien de modifications de code sont nécessaires ?** Seulement cinq courts extraits de code — un pour chaque étape.  
- **Puis‑je réutiliser ce modèle pour d’autres espaces de noms ?** Oui, il suffit de changer le préfixe et l’URI dans l’appel `registerNamespaceURI`.

## What is an XMP Namespace?

Un espace de noms XMP (Extensible Metadata Platform) est un identifiant unique qui regroupe des propriétés de métadonnées liées sous une même URI. Enregistrer un espace de noms vous permet de stocker des données personnalisées—comme des balises propriétaires—sans entrer en conflit avec les standards existants.

## Why Use Aspose.Page for XMP Manipulation?

- **Contrôle total** sur les métadonnées EPS et PDF sans avoir besoin des outils Adobe.  
- **Création automatique** de blocs XMP lorsqu’ils n’existent pas, à partir des commentaires PS.  
- **Support Java multiplateforme**, facilitant l’intégration dans les pipelines existants.

## Prerequisites

- Aspose.Page for Java : assurez‑vous que la bibliothèque est installée. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).  
- Environnement de développement Java : configurez un environnement Java sur votre système.  
- Fichier de document : disposez d’un fichier EPS contenant des métadonnées XMP. S’il ne contient pas de métadonnées XMP, la bibliothèque en créera un à partir des commentaires PS.

## Import Packages

Pour commencer, importez les packages nécessaires dans votre projet Java :

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Step 1: Get XMP Metadata

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### Why this matters
Récupérer l’objet `XmpMetadata` vous donne un accès direct aux métadonnées du document, vous permettant de les lire, les modifier ou les étendre avant l’enregistrement.

## Step 2: Register New Namespace *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### Explanation
La méthode `registerNamespaceURI` associe un préfixe court (`tmp`) à une URI complète. Cette étape est indispensable pour l’opération suivante, car les propriétés XMP doivent être qualifiées avec un espace de noms enregistré.

## Step 3: Add New Property

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### What’s happening?
Ici nous créons une propriété personnalisée nommée `tmp:newKey` et lui attribuons la valeur `"NewValue"`. Vous pouvez remplacer la clé et la valeur par tout ce qui correspond à votre logique métier.

## Step 4: Save Document

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Tip
Enveloppez toujours l’appel `save` dans un bloc `try/finally` (ou utilisez try‑with‑resources) afin de garantir que le flux de sortie soit fermé, même en cas d’exception.

## Step 5: Close Streams

```java
// Close input EPS stream
psStream.close();
```

### Best practice
Fermer le flux d’entrée libère rapidement le handle du fichier, évitant ainsi les problèmes de verrouillage de fichier sous Windows.

## Common Issues and Solutions

| Issue | Likely Cause | Fix |
|-------|--------------|-----|
| No XMP block appears after saving | Original EPS lacked XMP and comments were insufficient | Ensure the EPS contains standard PS comments (`%%Creator`, `%%Title`, etc.) or manually create an empty `XmpMetadata` object before registering a namespace. |
| `registerNamespaceURI` throws an exception | Prefix already used | Choose a unique prefix or check existing namespaces via `xmp.getRegisteredNamespaces()`. |
| Saved file is corrupted | Output stream not flushed | Use `try‑with‑resources` or explicitly call `outPsStream.flush()` before closing. |

## Conclusion

En suivant ce **aspose.page xmp tutorial**, vous disposez désormais d’une méthode réutilisable pour ajouter des espaces de noms et des propriétés personnalisées aux fichiers EPS avec Aspose.Page for Java. Cette capacité ouvre la porte à des stratégies de métadonnées plus riches—que vous intégriez des identifiants de workflow, des balises propriétaires ou des données d’intégration pour les systèmes en aval.

## FAQs

### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page primarily supports Java, but there are versions available for other languages such as .NET.

### Is there a free trial available?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Where can I find comprehensive documentation?
Refer to the documentation [here](https://reference.aspose.com/page/java/).

### How can I obtain a temporary license?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Are there community forums for Aspose.Page?
Yes, you can engage with the community on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}