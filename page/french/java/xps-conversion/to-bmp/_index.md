---
date: 2025-12-21
description: Apprenez comment définir la résolution lors de la conversion de XPS en
  BMP en Java avec Aspose.Page. Ce guide de conversion d’images Java garantit des
  résultats de haute qualité.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Comment définir la résolution lors de la conversion de XPS en BMP en Java
url: /fr/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS en BMP en Java

## Introduction
Bienvenue dans ce guide étape par étape sur **comment définir la résolution** lors de la conversion de fichiers XPS (XML Paper Specification) en format BMP (Bitmap) en Java à l'aide d'Aspose.Page. Aspose.Page pour Java est une bibliothèque puissante qui offre des fonctionnalités complètes pour travailler avec les documents XPS. Dans ce tutoriel, nous vous guiderons à travers le processus de conversion des fichiers XPS en images BMP sans effort.

## Réponses rapides
- **Quelle bibliothèque dois-je utiliser ?** Aspose.Page pour Java fournit les fonctionnalités de conversion XPS → BMP les plus complètes.  
- **Puis-je contrôler la qualité de l'image ?** Oui – utilisez `BmpSaveOptions` pour définir la résolution et le mode d'anticrénelage.  
- **Dois-je convertir uniquement des pages spécifiques ?** Absolument, `options.setPageNumbers()` vous permet de choisir les pages exactes.  
- **S'agit-il d'une véritable conversion d'image Java ?** L'API rend les pages XPS directement en données bitmap, aucune format intermédiaire n'est requis.  
- **Quelle version de Java est prise en charge ?** Toutes les versions modernes de Java (8 et supérieures) sont compatibles.

## Quel est le but de définir la résolution ?
La résolution détermine le nombre de points par pouce (DPI) dans l'image BMP générée. Un DPI plus élevé produit des images plus nettes, ce qui est essentiel pour l'impression ou le travail graphique détaillé. Ajuster la résolution vous donne un contrôle total sur la qualité de sortie de votre **java convert xps** workflow.

## Pourquoi utiliser Aspose.Page pour la conversion XPS → BMP ?
- **Haute fidélité** – conserve la qualité vectorielle de l'XPS original.  
- **Contrôle fin** – vous pouvez définir le DPI, l'anticrénelage, et même sélectionner des pages spécifiques à convertir.  
- **Aucune dépendance externe** – pur Java, aucune bibliothèque native requise.  
- **Scalable** – fonctionne pour les documents d'une seule page ainsi que pour les gros fichiers XPS multi‑pages.

## Prérequis
Avant de plonger dans le processus de conversion, assurez-vous de disposer des prérequis suivants :
- **Environnement de développement Java** – Java 8 ou version plus récente installé sur votre machine.  
- **Bibliothèque Aspose.Page pour Java** – Téléchargez et incluez la bibliothèque Aspose.Page pour Java dans votre projet. Vous pouvez trouver la bibliothèque [ici](https://releases.aspose.com/page/java/).  
- **Fichier XPS d'exemple** – Préparez un document XPS d'exemple que vous souhaitez convertir en BMP.

## Importer les packages
Incluez les packages Aspose.Page nécessaires dans votre code Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Comment définir la résolution pour la conversion XPS en BMP
Voici un guide concis, numéroté, qui montre exactement où et comment définir la résolution, ainsi que comment **convertir des pages spécifiques**.

### Étape 1 : Charger le document XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Étape 2 : Initialiser les options (résolution et sélection de pages)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Étape 3 : Créer le dispositif de rendu
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Étape 4 : Enregistrer le document en utilisant les options
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Étape 5 : Parcourir les images rendues et écrire les fichiers
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Répétez ces étapes pour toute personnalisation ou modification supplémentaire dont vous pourriez avoir besoin dans le processus de conversion.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Sortie BMP de mauvaise qualité** | Vérifiez que `options.setResolution()` est réglé à une valeur ≥ 300 DPI. |
| **Seule une partie du document est convertie** | Assurez‑vous que `options.setPageNumbers()` inclut tous les indices de pages souhaités. |
| **OutOfMemoryError sur de gros fichiers XPS** | Traitez le document en partitions plus petites ou augmentez la taille du tas JVM (`-Xmx`). |
| **Fichier introuvable** | Revérifiez le chemin `dataDir` et que le fichier XPS d'entrée existe. |

## Questions fréquemment posées
### Q : Puis‑je personnaliser la résolution des images BMP ?
R : Oui, vous pouvez ajuster la résolution en modifiant le paramètre `options.setResolution()` dans le code.

### Q : Aspose.Page est‑il compatible avec différentes versions de Java ?
R : Oui, Aspose.Page prend en charge un large éventail de versions de Java. Assurez‑vous d'avoir une version compatible installée.

### Q : Comment convertir des fichiers XPS à partir d'une plage de pages spécifique ?
R : Utilisez la méthode `options.setPageNumbers()` pour spécifier les numéros de pages que vous souhaitez convertir.

### Q : Existe‑t‑il d'autres formats de sortie pris en charge par Aspose.Page ?
R : Oui, Aspose.Page prend en charge divers formats de sortie. Consultez la documentation pour une liste complète.

### Q : Où puis‑je trouver de l'aide ou du support supplémentaire ?
R : Consultez le [Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.Page pour Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}