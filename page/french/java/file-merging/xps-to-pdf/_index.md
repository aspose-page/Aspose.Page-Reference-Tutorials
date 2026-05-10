---
date: 2026-02-02
description: Apprenez à compresser les PDF tout en convertissant des XPS en PDF avec
  Aspose.Page. Ce guide couvre la conversion XPS vers PDF, les paramètres de compression
  PDF et les astuces de conversion par lots.
linktitle: How to Compress PDF when Converting XPS to PDF in Java
second_title: Aspose.Page Java API
title: Comment compresser le PDF lors de la conversion de XPS en PDF en Java
url: /fr/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment compresser un PDF lors de la conversion de XPS en PDF en Java

## Introduction
Dans ce tutoriel, vous découvrirez **comment compresser un PDF** lors de la conversion de fichiers XPS en PDF en utilisant **Aspose.Page Java**. Que vous manipuliez une facture unique ou que vous deviez **convertir en lot des documents XPS PDF** pour l'archivage, ce guide vous accompagne à chaque étape qui maintiennent les tailles de fichier petites- **Quelle bibliothèque gère la conversion XPS vers PDF ?** Aspose.Page Java  
- **Combien de temps prend une conversion de base ?** Typiquement moins d'une seconde pour un fichier XPS d'une seule page.  
- **Ai‑je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour l'évaluation ;Puis‑je contrôler la compression du PDF ?** Oui – utilisez `PdfSaveOptions` pour définir la compression des images et du texte.  
 Java est requise ?## Howose.Page fournit un contrôle granulaire sur **la compression PDF** via la classe `PdfSaveOptions`. En ajustant la qualité JPEG, en sélectionnant les algorithmes de compression d'image, et en activant la compression du flux de texte, vous pouvez réduire considérablement la taille du résultat. Les sections suivantes démontrent le code exact nécessaire pour **enregistrer XPS en PDF** tout en appliquant ces paramètres.

## What is Aspose.Page Java?
Aspose.Page Java est une **API haute performance** qui permet programmatique. XPS vers PDF, PNG sur les paramètres de sortie tels que **set PDF compression**.

## Why use Aspose.Page Java for XPS‑to‑PDF conversion?
- **Rendu sans dépendance** – aucune bibliothèque native ni outil externe.  
- **Préservation précise de la mise en page** – le PDF généré reflète l'apparence originale du XPS.  
- **Contrôle complet sur la sortie PDF** – vous pouvez ajuster la qualité des images, choisir les algorithmes de compression et sélectionner des pages spécifiques à rendre.  
- **Multi‑plateforme** – fonctionne sous Windows, Linux et macOS avec n'importe quel JDK standard.

## Prerequisites
Avant de commencer, :

1. **Java Development Kit (JDK la sécurité.  
2. **Aspose.Page for Java library** – téléchargez le JAR depuis la [documentation officielle Aspose.Page Java](https://reference.aspose.com/page/java/).  
3. Un **IDE** (IntelliJ IDEA, Eclipse, VS Code) ou un simple éditeur de texte plus des outils de construction en ligne de commande (Maven/Gradle).  

## Import Packages
Ajoutez les imports requis à votre classe Java afin de travailler avec les documents XPS et la sortie PDF.

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
Définissez le dossier contenant votre fichier XPS source et où le PDF sera enregistré.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Step 2: Initialize PDF Output Stream
Créez un `FileOutputStream` qui pointe vers le fichier PDF de destination.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Astuce pro :** Utilisez `try‑with‑resources` pour fermer automatiquement le flux et éviter les fuites de ressources.

### Step 3: Load XPS Document
Instanciez un objet `XpsDocument` en chargeant le fichier XPS source.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Step 4: Initialize PDF Save Options (Set PDF Compression)
Configurez la façon dont le PDF doit être compressé. Cette étape vous permet de **définir la compression PDF** pour les images et le texte, ce qui réduit la taille du fichier sans sacrifier la qualité.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Pourquoi c'est important :** Ajuster la qualité JPEG et les types de compression peut réduire un PDF de 10 Mo à moins de 2 Mo tout en conservant la fidélité visuelle requise.

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

## How to Batch Convert XPS to PDF (and compress PDFs)
Si vous devez **convertir en lot des fichiers XPS PDF**, placez simplement tous les fichiers XPS dans un dossier et parcourez‑les avec la même logique de code. Appliquez les mêmes `PdfSaveOptions` à chaque itération pour que chaque PDF soit compressé de manière cohérente. Cette approche s'adapte bien aux grands dépôts de documents.

## Common Issues & Solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **`FileNotFoundException`** | Chemin `dataDir` incorrect | Vérifiez que le répertoire existe et que l'application possède les permissions de lecture/écriture. |
| **Pages PDF vides** | Initialisation manquante de `PdfDevice` | Assurez‑vous que `PdfDevice` est créé avec le même `FileOutputStream` utilisé pour la sortie. |
| **Taille PDF importante** | La compression par défaut est faible | Diminuez `setJpegQualityLevel` ou passez à un autre paramètre `PdfImageCompression`. |
| **Seules certaines pages apparaissent** | Le filtre `setPageNumbers` exclut des pages | Ajustez le tableau pour inclure tous les numéros de pages nécessaires ou supprimez l'appel afin d'exporter toutes les pages. |

## Frequently Asked Questions

**Q : Aspose.Page Java est‑il compatible avec différentes versions de Java ?**  
R : Oui, Aspose.Page Java prend en charge Java 8 à Java 21, y compris les distributions Oracle et OpenJDK.

**Q : Puis‑je personnaliser les paramètres de compression du PDF converti ?**  
R : Absolument. Utilisez `PdfSaveOptions` pour définir la qualité JPEG, le type de compression d'image et la compression du texte comme illustré à l'étape 4.

**Q : Où puis‑je trouver un support supplémentaire ou des discussions communautaires ?**  
R : Consultez le [Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l'aide de la communauté, des exemples de code et des astuces de dépannage.

**Q : Existe‑t‑il un essai gratuit pour Aspose.Page ?**  
R : Oui, vous pouvez télécharger un essai complet depuis la [page de téléchargement Aspose](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page ?**  
R : Une licence temporaire peut être demandée [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
En exploitant **Aspose.Page Java**, vous pouvez facilement **enregistrer XPS en PDF**, appliquer des **paramètres précis de compression PDF**, et même **convertir en lot des fichiers XPS PDF** — tout en gardant un contrôle total sur la qualité des images et la taille du fichier. Ce tutoriel a couvert tout ce dont vous avez besoin pour intégrer la conversion XPS‑vers‑PDF dans vos applications Java, que vous construisiez un utilitaire ponctuel ou une chaîne de traitement de documents à grande échelle.

---

**Dernière mise à jour :** 2026-02-02  
**Testé avec :** Aspose.Page for Java 24.10  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}