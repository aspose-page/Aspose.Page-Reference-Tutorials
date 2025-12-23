---
date: 2025-12-23
description: Convertissez XPS en TIFF sans effort avec Aspose.Page Java. Suivez notre
  guide étape par étape pour une intégration transparente avec Aspose.Page Java. Téléchargez
  maintenant !
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Convertir XSP en TIFF en Java avec Aspose.Page Java
url: /fr/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir XSP en TIFF en Java avec Aspose.Page Java

Dans le paysage logiciel actuel en évolution rapide, **aspose page java** rend la conversion de documents Java simple et fiable. Que vous ayez besoin de **convertir XPS en TIFF** pour l'archivage, l'impression ou le traitement par lots, ce tutoriel vous guide à travers les étapes précises, explique le « pourquoi » de chaque action et fournit des conseils pratiques que vous pouvez appliquer immédiatement.

## Réponses rapides
- **Quelle bibliothèque gère la conversion XPS‑to‑TIFF ?** Aspose.Page Java.  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence valide Aspose.Page Java est requise.  
- **Quelle version de Java est prise en charge ?** JDK 8 ou supérieur.  
- **Puis‑je convertir plusieurs fichiers XPS en même temps ?** Oui – vous pouvez créer une boucle de conversion XPS par lots autour du même code.  
- **Quelle résolution est la meilleure pour les TIFF prêts à l’impression ?** 300 DPI est un choix courant, mais vous pouvez l’ajuster via TiffSaveOptions.

## Qu’est‑ce que Aspose.Page Java ?
Aspose.Page Java est une API puissante qui permet la **conversion de documents java** de XPS (XML Paper Specification) vers une large gamme de formats raster et vectoriels, y compris TIFF. Elle gère les mises en page complexes, les polices et les graphiques sans nécessiter Microsoft XPS Document Writer.

## Pourquoi utiliser Aspose.Page Java pour la conversion XPS en TIFF ?
- **Haute fidélité :** préserve les données vectorielles et le rendu du texte.  
- **Performance :** optimisé pour les gros fichiers et les scénarios de conversion XPS par lots.  
- **Flexibilité :** affinez la sortie avec `tiff save options` telles que la résolution, la compression et la sélection des pages.  
- **Cross‑platform :** fonctionne sur tout OS supportant Java, ce qui le rend idéal pour le traitement côté serveur.

## Prérequis
Avant de vous plonger dans le processus de conversion, assurez‑vous d'avoir :

- Java Development Kit (JDK) installé sur votre machine.  
- La bibliothèque Aspose.Page for Java. Vous pouvez la télécharger [ici](https://releases.aspose.com/page/java/).  
- Une licence valide pour Aspose.Page for Java. Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/), ou acheter une licence complète [ici](https://purchase.aspose.com/buy).

## Importer les packages
Commencez par importer les packages nécessaires dans votre projet Java. Assurez‑vous que le JAR Aspose.Page for Java est ajouté à votre chemin de construction.

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Étape 1 : Configurer le répertoire du document
Définissez le chemin vers le dossier contenant votre fichier XPS source.

```java
String dataDir = "Your Document Directory";
```

## Étape 2 : Charger le document XPS
Créez une instance `XpsDocument` qui pointe vers le fichier d’entrée.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## Étape 3 : Initialiser TiffSaveOptions
Configurez les **tiff save options** qui contrôlent la qualité de l’image, la résolution et les pages à exporter.

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## Étape 4 : Créer le dispositif de rendu
Instanciez un `ImageDevice` qui rendra les pages en images TIFF.

```java
ImageDevice device = new ImageDevice();
```

## Étape 5 : Enregistrer le document en TIFF
Rendez le document XPS en utilisant le dispositif et les options définies précédemment.

```java
document.save(device, options);
```

## Étape 6 : Itérer et enregistrer les images TIFF
Parcourez les tampons d’images rendues et écrivez chaque page dans un fichier TIFF distinct.

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Félicitations ! Vous avez réussi à **convertir XPS en TIFF** en Java avec **aspose page java**. N’hésitez pas à explorer davantage les fonctionnalités de la bibliothèque dans la [documentation](https://reference.aspose.com/page/java/).

## Conclusion
Dans ce tutoriel, nous avons couvert tout ce que vous devez savoir pour effectuer la **conversion de documents java** de XPS en TIFF, depuis la configuration de l’environnement jusqu’à l’ajustement fin des `tiff save options`. Avec Aspose.Page Java, vous pouvez également créer des pipelines de **conversion XPS par lots** qui traitent automatiquement des dizaines ou des centaines de fichiers.

## Questions fréquentes
### Puis‑je utiliser Aspose.Page pour Java sans licence ?
Bien que vous puissiez obtenir une licence temporaire pour l’évaluation, une licence valide est requise pour une utilisation en production. Obtenez votre licence [ici](https://purchase.aspose.com/buy).

### Existe‑t‑il des limitations concernant la taille des fichiers XPS pour la conversion ?
Aspose.Page for Java gère des documents de différentes tailles, mais il est conseillé de tester avec des fichiers plus volumineux dans votre environnement spécifique.

### Comment puis‑je obtenir du support ou poser des questions sur Aspose.Page pour Java ?
Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire et les discussions.

### Existe‑t‑il un essai gratuit disponible pour Aspose.Page pour Java ?
Oui, vous pouvez explorer la bibliothèque avec un essai gratuit. Téléchargez‑la [ici](https://releases.aspose.com/).

### Quelle est la résolution recommandée pour les images TIFF dans cette conversion ?
L’exemple utilise une résolution de 300 DPI, mais vous pouvez l’ajuster en fonction de vos besoins spécifiques.

---

**Dernière mise à jour :** 2025-12-23  
**Testé avec :** Aspose.Page Java 24.11 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}