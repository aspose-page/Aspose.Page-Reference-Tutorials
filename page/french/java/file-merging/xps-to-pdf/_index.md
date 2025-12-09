---
date: 2025-11-29
description: Apprenez comment enregistrer XPS en PDF en Java avec Aspose.Page Java.
  Suivez notre guide étape par étape pour une conversion efficace de XPS en PDF et
  les paramètres de compression PDF.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Convertir XPS en PDF en Java avec Aspose.Page Java
url: /fr/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS en PDF en Java avec Aspose.Page Java

## Introduction
Dans ce tutoriel, vous apprendrez **comment convertir XPS en PDF en Java en utilisant Aspose.Page Java**, une bibliothèque robuste conçue pour la conversion de documents Java. Que vous ayez besoin de traiter en lot des factures, de générer des rapports imprimables, ou simplement de migrer des fichiers XPS hérités, Aspose.Page Java rend la tâche rapide, fiable et entièrement configurable.

## Quick Answers
- **Quelle bibliothèque gère la conversion XPS vers PDF ?** Aspose.Page Java  
- **Combien de temps prend une conversion de base ?** Généralement moins d’une seconde pour un fichier XPS d’une seule page.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour l’évaluation ; une licence est requise pour la production.  
- **Puis‑je contrôler la compression du PDF ?** Oui – utilisez `PdfSaveOptions` pour définir la compression des images et du texte.  
- **Quelle version de Java est requise ?** Java 8 ou supérieure (JDK 11+ recommandé).

## What is Aspose.Page Java?
Aspose.Page Java est une **API haute performance** qui permet aux développeurs de créer, modifier et convertir des documents XPS de manière programmatique. Elle prend en charge le rendu XPS vers PDF, PNG, JPEG et d’autres formats tout en offrant un contrôle granulaire sur les paramètres de sortie tels que **set PDF compression**.

## Why use Aspose.Page Java for XPS‑to‑PDF conversion?
- **Rendu sans dépendance** – aucune bibliothèque native ni outil externe.  
- **Préservation précise de la mise en page** – la sortie PDF reflète l’apparence originale du XPS.  
- **Contrôle complet de la sortie PDF** – vous pouvez ajuster la qualité des images, choisir les algorithmes de compression et sélectionner des pages spécifiques à rendre.  
- **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS avec n’importe quel JDK standard.

## Prerequisites
Avant de commencer, assurez‑vous d’avoir :

1. **Java Development Kit (JDK) 8+** – le dernier JDK est recommandé pour les performances et la sécurité.  
2. **Bibliothèque Aspose.Page pour Java** – téléchargez le JAR depuis la documentation officielle [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
3. Un **IDE** (IntelliJ IDEA, Eclipse, VS Code) ou un simple éditeur de texte avec des outils de construction en ligne de commande (Maven/Gradle).  

## Import Packages
Ajoutez les imports requis à votre classe Java afin de pouvoir travailler avec les documents XPS et la sortie PDF.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Step‑by‑Step Guide

### Step 1: Set Document Directory Path
Définissez le dossier qui contient votre fichier XPS source et où le PDF sera enregistré.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Step 2: Initialize PDF Output Stream
Créez un `FileOutputStream` qui pointe vers le fichier PDF de destination.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Astuce :** Utilisez `try‑with‑resources` pour fermer automatiquement le flux et éviter les fuites de ressources.

### Step 3: Load XPS Document
Instanciez un objet `XpsDocument` en chargeant le fichier XPS source.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Step 4: Initialize PDF Save Options (Set PDF Compression)
Configurez la façon dont le PDF doit être compressé. Cette étape vous permet de **set PDF compression** pour les images et le texte, ce qui réduit la taille du fichier sans sacrifier la qualité.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Pourquoi c’est important :** Ajuster la qualité JPEG et les types de compression peut réduire un PDF de 10 Mo à moins de 2 Mo tout en conservant la fidélité visuelle requise.

### Step 5: Create Rendering Device for PDF Format
Le `PdfDevice` transmet les pages rendues dans le flux de sortie PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Step 6: Save the Document
Enfin, rendez le contenu XPS en PDF en utilisant les options configurées.

```java
document.save(device, options);
```

> **Résultat :** Après exécution, `XPStoPDF.pdf` apparaîtra dans le dossier `dataDir`, contenant les pages converties avec les paramètres de compression que vous avez spécifiés.

## Common Issues & Solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **`FileNotFoundException`** | Chemin `dataDir` incorrect | Vérifiez que le répertoire existe et que l’application dispose des permissions de lecture/écriture. |
| **Pages PDF vides** | Initialisation manquante de `PdfDevice` | Assurez‑vous que `PdfDevice` est créé avec le même `FileOutputStream` utilisé pour la sortie. |
| **Taille PDF importante** | La compression par défaut est faible | Augmentez `setJpegQualityLevel` ou passez à `PdfImageCompression.Jpeg` avec un niveau de qualité inférieur. |
| **Seules certaines pages apparaissent** | Le filtre `setPageNumbers` exclut des pages | Ajustez le tableau pour inclure tous les numéros de pages nécessaires ou supprimez l’appel pour exporter toutes les pages. |

## Frequently Asked Questions

**Q : Aspose.Page Java est‑il compatible avec différentes versions de Java ?**  
R : Oui, Aspose.Page Java prend en charge Java 8 à Java 21, y compris les distributions Oracle et OpenJDK.

**Q : Puis‑je personnaliser les paramètres de compression du PDF converti ?**  
R : Absolument. Utilisez `PdfSaveOptions` pour définir la qualité JPEG, le type de compression d’image et la compression du texte comme indiqué à l’étape 4.

**Q : Où puis‑je trouver un support supplémentaire ou des discussions communautaires ?**  
R : Consultez le [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pour obtenir de l’aide de la communauté, des exemples de code et des conseils de dépannage.

**Q : Une version d’essai gratuite d’Aspose.Page est‑elle disponible ?**  
R : Oui, vous pouvez télécharger une version d’essai pleinement fonctionnelle depuis la [page de téléchargement Aspose](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page ?**  
R : Une licence temporaire peut être demandée [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
En exploitant **Aspose.Page Java**, vous pouvez facilement **enregistrer XPS en PDF** et contrôler chaque aspect de la sortie, de la sélection des pages à la compression. Ce tutoriel a couvert tout ce dont vous avez besoin pour intégrer la conversion XPS‑vers‑PDF dans vos applications Java, que vous construisiez un utilitaire ponctuel ou une chaîne de traitement de documents à grande échelle.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}