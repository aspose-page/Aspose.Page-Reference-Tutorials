---
date: 2025-11-30
description: Apprenez à recadrer des fichiers EPS en Java avec Aspose.Page – un tutoriel
  clair, étape par étape, sur la façon de recadrer des EPS à l'aide de la bibliothèque
  Aspose.Page.
language: fr
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: Comment recadrer des fichiers EPS en Java – Guide Aspose.Page
url: /java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment recadrer des fichiers EPS en Java – Guide étape par étape avec Aspose.Page

## Introduction
Si vous devez **recadrer des fichiers eps** de manière programmatique dans une application Java, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons l’ensemble du processus de recadrage d’une image EPS à l’aide de la puissante bibliothèque Aspose.Page for Java. À la fin du guide, vous comprendrez pourquoi le recadrage d’EPS est important, verrez le code exact dont vous avez besoin et serez prêt à intégrer la solution dans vos propres projets.

## Réponses rapides
- **Quelle bibliothèque gère le recadrage EPS en Java ?** Aspose.Page for Java.  
- **Combien de temps faut‑il pour implémenter un recadrage de base ?** Environ 5‑10 minutes.  
- **Ai‑je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Quelles versions de Java sont prises en charge ?** Java 8 et versions ultérieures.  
- **Puis‑je définir une boîte englobante personnalisée ?** Oui – vous fournissez les coordonnées dont vous avez besoin.

## Qu’est‑ce que le recadrage EPS et pourquoi l’utiliser ?
Encapsulated PostScript (EPS) est un format graphique qui stocke des images vectorielles ainsi qu’une boîte englobante définissant la zone visible. Recadrer un fichier EPS consiste à créer une nouvelle boîte englobante afin que seule la région qui vous intéresse soit conservée. Cela est utile lorsque vous souhaitez supprimer les marges blanches, extraire un logo ou adapter le graphique à une mise en page plus serrée sans recréer le fichier source.

## Prérequis
Avant de plonger dans le code, assurez‑vous d’avoir :

- La bibliothèque **Aspose.Page for Java** installée – téléchargez‑la depuis la page officielle [ici](https://releases.aspose.com/page/java/).  
- Le **Java Development Kit (JDK)** 8 ou supérieur installé sur votre machine.  
- **Un dossier** pour stocker votre EPS d’entrée (`input.eps`) et le fichier recadré résultant (`output_crop.eps`).

## Importer les packages
Tout d’abord, importez les classes Java nécessaires. Cet extrait reste exactement tel qu’il apparaît dans le tutoriel original :

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### Étape 1 : Définir le répertoire du document et le flux d’entrée
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Ici nous indiquons le code vers le dossier contenant notre fichier EPS source et ouvrons un flux pour le lire.

### Étape 2 : Initialiser l’objet PsDocument
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
La classe `PsDocument` représente le document EPS en mémoire, nous permettant d’interroger et de manipuler ses propriétés.

### Étape 3 : Extraire la boîte englobante initiale
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Extraire la boîte englobante originale vous fournit les coordonnées de la zone visible actuelle – pratique pour décider de la quantité à découper.

### Étape 4 : Créer le flux de sortie
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Nous ouvrons un flux où l’EPS recadré sera écrit.

### Étape 5 : Définir la nouvelle boîte englobante et recadrer
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Fournissez les quatre coordonnées (x inférieur‑gauche, y inférieur‑gauche, x supérieur‑droit, y supérieur‑droit) qui définissent la zone à conserver. La méthode `cropEps` effectue le recadrage et écrit le résultat dans `output_crop.eps`.

## Problèmes courants et solutions
- **Coordonnées incorrectes :** EPS utilise des points (1/72 pouce). Si le recadrage semble décalé, revérifiez la conversion d’unité.  
- **Erreurs de fichier introuvable :** Assurez‑vous que `dataDir` se termine par le séparateur de chemin approprié (`/` ou `\`).  
- **Exceptions de licence :** Exécuter le code sans licence valide peut ajouter un filigrane à la sortie. Appliquez votre licence temporaire ou permanente avant l’utilisation en production.

## Questions fréquemment posées

**Q : Aspose.Page est‑il compatible avec Java 8 ?**  
R : Oui, Aspose.Page fonctionne avec Java 8 et toutes les versions ultérieures.

**Q : Puis‑je utiliser Aspose.Page pour des projets commerciaux ?**  
R : Absolument. Une licence commerciale est requise pour les déploiements en production. Vous pouvez en obtenir une [ici](https://purchase.aspose.com/buy).

**Q : Où puis‑je trouver des ressources supplémentaires et du support communautaire ?**  
R : Visitez le forum officiel [Aspose.Page](https://forum.aspose.com/c/page/39) pour des discussions, des exemples de code et des conseils de dépannage.

**Q : Existe‑t‑il un essai gratuit disponible pour les tests ?**  
R : Oui, vous pouvez télécharger un essai gratuit d’Aspose.Page depuis la page des releases [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour une évaluation à court terme ?**  
R : Une licence temporaire peut être demandée via le portail de licence [ici](https://purchase.aspose.com/temporary-license/).

## Conclusion
Vous savez maintenant **comment recadrer des eps** en Java en utilisant Aspose.Page. En définissant une boîte englobante personnalisée et en appelant `cropEps`, vous pouvez éliminer les marges indésirables ou isoler des parties spécifiques d’un graphique EPS avec seulement quelques lignes de code. Intégrez cet extrait dans vos pipelines de traitement de documents plus larges pour automatiser la manipulation d’EPS et garder vos actifs visuels bien organisés.

---

**Dernière mise à jour :** 2025-11-30  
**Testé avec :** Aspose.Page for Java 24.11  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}