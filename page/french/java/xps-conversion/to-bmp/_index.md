---
date: 2026-03-08
description: Apprenez à convertir XPS en BMP en Java et à définir la résolution BMP
  à l'aide de la bibliothèque de conversion d'images Aspose.Page pour Java. Ce guide
  couvre la sortie haute qualité et des astuces économes en mémoire.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Convertir XPS en BMP en Java – Définir la résolution pour une sortie de haute
  qualité
url: /fr/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XPS en BMP en Java

## Introduction
Bienvenue dans ce guide étape par étape sur la façon de **convertir XPS en BMP** en Java et de définir la résolution pour une qualité d'image optimale à l'aide d'Aspose.Page. Que vous construisiez une chaîne d'impression, génériez des vignettes ou ayez besoin de graphiques haute résolution, le contrôle du DPI vous offre la flexibilité nécessaire pour répondre à toute exigence.

## Réponses rapides
- **Quelle bibliothèque devrais-je utiliser ?** Aspose.Page for Java est la bibliothèque **java image conversion library** la plus complète pour XPS → BMP.  
- **Puis-je contrôler la qualité de l'image ?** Oui – utilisez `BmpSaveOptions` pour **set BMP resolution** et le mode de lissage.  
- **Comment éviter OutOfMemoryError Java lors du traitement de gros fichiers XPS ?** Rendre les pages par partitions ou augmenter le tas JVM (`-Xmx`).  
- **Dois-je convertir uniquement des pages spécifiques ?** Absolument, `options.setPageNumbers()` vous permet de choisir les pages exactes.  
- **Quelles versions de Java sont prises en charge ?** Toutes les versions modernes de Java (8 et supérieures) fonctionnent parfaitement.

## Quel est le but de définir la résolution ?
La résolution détermine le nombre de points par pouce (DPI) dans l'image BMP générée. Un DPI plus élevé produit des images plus nettes, ce qui est essentiel pour l'impression ou le travail graphique détaillé. Ajuster la résolution vous donne un contrôle total sur la qualité de sortie de votre flux de travail **convert xps to bmp**.

## Pourquoi utiliser Aspose.Page pour la conversion XPS → BMP ?
- **High fidelity** – conserve la qualité vectorielle de l'XPS original.  
- **Fine‑grained control** – vous pouvez définir le DPI, le lissage, et même sélectionner des pages spécifiques à convertir.  
- **No external dependencies** – pur Java, aucune bibliothèque native requise.  
- **Scalable** – fonctionne pour les documents d'une seule page ainsi que pour les gros fichiers XPS multi‑pages.  

## Prérequis
Avant de plonger dans le processus de conversion, assurez-vous de disposer des prérequis suivants :
- **Java Development Environment** – Java 8 ou version plus récente installé sur votre machine.  
- **Aspose.Page for Java Library** – Téléchargez et incluez la bibliothèque Aspose.Page for Java dans votre projet. Vous pouvez trouver la bibliothèque [here](https://releases.aspose.com/page/java/).  
- **Sample XPS File** – Préparez un document XPS d'exemple que vous souhaitez convertir en BMP.

## Importer les packages
Incluez les packages Aspose.Page nécessaires dans votre code Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Comment définir la résolution pour la conversion XPS en BMP
Voici un guide concis, numéroté, qui montre exactement où et comment définir la résolution, ainsi que comment **convertir des pages spécifiques**.

### Étape 1 : Charger le document XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Étape 2 : Initialiser les options (résolution et sélection de pages)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Étape 3 : Créer le dispositif de rendu
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Étape 4 : Enregistrer le document en utilisant les options
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Étape 5 : Parcourir les images rendues et écrire les fichiers
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

## Comment éviter OutOfMemoryError Java lors de la conversion de gros fichiers XPS
- **Process in partitions** – L'exemple rend déjà le document par partitions (`device.getResult()`), ce qui réduit la pression mémoire.  
- **Increase JVM heap** – Utilisez le drapeau `-Xmx` (par ex., `-Xmx2g`) pour allouer plus de mémoire aux gros documents.  
- **Dispose of resources** – Appelez `document.close()` lorsque vous avez terminé pour libérer les ressources natives.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Sortie BMP de basse qualité** | Vérifiez que `options.setResolution()` est réglé sur une valeur ≥ 300 DPI. |
| **Seule une partie du document est convertie** | Assurez-vous que `options.setPageNumbers()` inclut tous les indices de pages souhaités. |
| **OutOfMemoryError sur de gros fichiers XPS** | Traitez le document par partitions plus petites ou augmentez la taille du tas JVM (`-Xmx`). |
| **Fichier non trouvé** | Vérifiez à nouveau le chemin `dataDir` et que le fichier XPS d'entrée existe. |

## Questions fréquemment posées
### Q : Puis-je personnaliser la résolution des images BMP ?
R : Oui, vous pouvez ajuster la résolution en modifiant le paramètre `options.setResolution()` dans le code.

### Q : Aspose.Page est‑il compatible avec différentes versions de Java ?
R : Oui, Aspose.Page prend en charge un large éventail de versions de Java. Assurez‑vous d'avoir une version compatible installée.

### Q : Comment puis‑je convertir des fichiers XPS d'une plage de pages spécifique ?
R : Utilisez la méthode `options.setPageNumbers()` pour spécifier les numéros de pages que vous souhaitez convertir.

### Q : Existe‑t‑il d'autres formats de sortie pris en charge par Aspose.Page ?
R : Oui, Aspose.Page prend en charge divers formats de sortie. Consultez la documentation pour une liste complète.

### Q : Où puis‑je trouver de l'aide ou du support supplémentaire ?
R : Visitez le [Aspose.Page Forum](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

---

**Dernière mise à jour :** 2026-03-08  
**Testé avec :** Aspose.Page for Java 24.12  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}