---
date: 2026-03-13
description: Apprenez à convertir XPS en JPEG en Java avec Aspose.Page Java. Ce guide
  étape par étape vous montre comment convertir XPS en JPEG efficacement en utilisant
  la bibliothèque Aspose.Page Java.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Comment convertir XPS en JPEG en Java avec Aspose.Page Java
url: /fr/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment convertir XPS en JPEG en Java avec Aspose.Page Java

## Introduction à Aspose.Page Java
Dans ce tutoriel **vous apprendrez comment convertir XPS en JPEG** avec la bibliothèque **Aspose.Page Java**. Convertir des fichiers XPS en images JPEG est une exigence fréquente lorsque vous devez afficher les pages d’un document sous forme de graphiques raster dans des portails web, des visionneuses de bureau ou des pièces jointes d’e‑mail. Nous passerons en revue chaque ligne de code, expliquerons pourquoi chaque paramètre est important, et partagerons des astuces pratiques afin que vous puissiez intégrer ce pipeline de conversion dans vos propres applications Java en toute confiance.

## Réponses rapides
- **Quelle bibliothèque gère la conversion ?** Aspose.Page Java  
- **Puis‑je sélectionner des pages spécifiques ?** Oui – utilisez `setPageNumbers` dans `JpegSaveOptions`  
- **Quelle qualité d’image puis‑je contrôler ?** Mode de lissage, résolution et paramètres de qualité JPEG  
- **Ai‑je besoin d’une licence pour la production ?** Oui, une licence commerciale est requise (un essai gratuit est disponible)  
- **Le code est‑il compatible Java 8 ?** Absolument – l’API fonctionne avec Java 8 et versions ultérieures  

## Qu’est‑ce que le XPS et pourquoi le convertir en JPEG ?
XPS (XML Paper Specification) est un format de document à mise en page fixe similaire au PDF. Convertir du XPS en JPEG est utile lorsque vous avez besoin d’images raster pour des miniatures, des pièces jointes d’e‑mail, ou lors de l’intégration avec des systèmes qui n’acceptent que des fichiers image. JPEG offre un bon compromis entre qualité visuelle et taille de fichier, ce qui le rend idéal pour les aperçus web.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de :

- **Environnement de développement Java** – JDK 8 ou version ultérieure installé et configuré.  
- **Aspose.Page pour Java** – Téléchargez la dernière bibliothèque depuis le site officiel [ici](https://releases.aspose.com/page/java/).  
- **Document XPS d’exemple** – Un fichier XPS que vous souhaitez transformer en images JPEG.  

## Importer les packages
Commencez par importer les classes nécessaires dans votre fichier source Java :

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Étape 1 : Initialiser les chemins et charger le document XPS
Définissez le répertoire contenant votre fichier XPS source et créez une instance `XpsDocument` :

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Astuce :** Utilisez `Paths.get()` de `java.nio.file` pour une gestion des chemins indépendante de la plateforme.

## Étape 2 : Configurer les options d’enregistrement JPEG
Définissez comment les images JPEG doivent être rendues — résolution, lissage et quelles pages exporter :

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` produit une sortie haute résolution adaptée à l’impression.  
- `setPageNumbers` vous permet de choisir uniquement les pages dont vous avez besoin, économisant ainsi du temps et de la mémoire.

## Étape 3 : Créer le dispositif de rendu
Le `ImageDevice` capture les pages rendues sous forme de tableaux d’octets :

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Étape 4 : Rendre le document XPS en JPEG
Appelez la méthode `save`, en passant le dispositif et les options que vous avez configurées :

```java
document.save(device, options);
```

À ce stade, le `device` contient un tableau à deux dimensions où chaque élément représente une page encodée en JPEG.

## Étape 5 : Parcourir le résultat et écrire les fichiers
Parcourez les pages rendues et écrivez chaque tableau d’octets dans un fichier JPEG séparé :

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Chaque fichier sera nommé `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, ce qui facilite l’identification du document source et du numéro de page.

## Cas d’utilisation courants
- **Génération de miniatures** pour les systèmes de gestion de documents.  
- **Intégration d’aperçus de pages** dans les applications web où seuls les formats image sont pris en charge.  
- **Traitement par lots de grandes archives XPS** en JPEG pour l’archivage ou la génération de rapports.  

## Problèmes courants & Dépannage
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| **Fichiers JPEG vides** | Le flux de sortie n’est pas correctement vidé ou fermé | Assurez‑vous que `imageStream.close()` est appelé à l’intérieur de la boucle interne (comme indiqué). |
| **Erreurs de mémoire insuffisante** sur de gros fichiers XPS | Le rendu de toutes les pages en même temps consomme trop de RAM | Traitez les pages par lots plus petits ou augmentez le tas JVM (`-Xmx`). |
| **Pages manquantes** | `setPageNumbers` n’inclut pas la page souhaitée | Vérifiez que le tableau des numéros de page correspond aux indices réels du XPS (basés sur 1). |

## Questions fréquemment posées

### Q : Aspose.Page convient‑il aux projets commerciaux ?
R : Oui, Aspose.Page est un produit commercial avec des options de licence disponibles. Consultez les détails [ici](https://purchase.aspose.com/buy).

### Q : Puis‑je essayer Aspose.Page avant d’acheter ?
R : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

### Q : Où puis‑je trouver la documentation d’Aspose.Page ?
R : La documentation est disponible [ici](https://reference.aspose.com/page/java/).

### Q : Comment obtenir du support pour Aspose.Page ?
R : Visitez le [Forum Aspose.Page](https://forum.aspose.com/c/page/39) pour un support communautaire.

### Q : Ai‑je besoin d’une licence temporaire pour les tests ?
R : Oui, vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous avez maintenant maîtrisé **comment convertir XPS en JPEG** en utilisant **Aspose.Page Java**. En suivant ce guide pas à pas, vous pouvez intégrer ce pipeline de conversion dans n’importe quelle application Java — qu’il s’agisse d’un outil de bureau, d’un service web ou d’une utilité de traitement par lots. N’hésitez pas à expérimenter avec différentes résolutions, sélections de pages et formats d’image pour répondre aux besoins de votre projet.

---

**Dernière mise à jour** : 2026-03-13  
**Testé avec** : Aspose.Page 24.11 pour Java (dernière version au moment de la rédaction)  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}