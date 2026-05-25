---
date: 2026-05-25
description: Apprenez comment lire le XMP avec Aspose.Page en Java. Ce guide étape
  par étape montre comment extraire les XMP metadata, creator info, timestamps, thumbnails,
  et plus encore.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Comment lire les XMP metadata avec Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Lire le XMP avec Aspose.Page – Guide Java
url: /fr/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir les métadonnées XMP avec Java

## Comment lire le XMP avec Aspose.Page (Java) ?

Chargez le fichier EPS avec `new Document("file.eps")` — la classe `Document` représente un fichier chargé. Appelez `getXmpMetadata()`, qui extrait le paquet XMP, puis interrogez l'objet `XmpMetadata` retourné — une interface de type carte pour les propriétés XMP — afin de récupérer les clés dont vous avez besoin. C’est tout ce qui est nécessaire pour lire le XMP avec Aspose.Page. L’API abstrait l’analyse de bas niveau, vous obtenez ainsi une carte prête à l’emploi des propriétés en seulement deux lignes de code.

Bienvenue dans notre tutoriel étape par étape qui montre **comment lire les métadonnées XMP** avec Java et la bibliothèque Aspose.Page. XMP (Extensible Metadata Platform) est une norme largement adoptée pour intégrer des métadonnées riches à l’intérieur des documents. À la fin de ce guide, vous serez capable de lire le XMP du format de document, d’extraire les informations du créateur, les horodatages, les miniatures, et plus encore — vous permettant de créer des solutions d’analyse de documents plus intelligentes.

## Réponses rapides
- **Que signifie « read XMP » ?** Cela signifie extraire programmétiquement le paquet XMP qui stocke les métadonnées à l’intérieur d’un fichier.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (téléchargez depuis la page officielle [here](https://releases.aspose.com/page/java/)).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour la production ; un essai gratuit fonctionne pour l’évaluation.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur.  
- **Puis‑je lire le XMP à partir d’autres formats ?** Oui – Aspose.Page extrait le XMP des fichiers EPS, PDF, JPEG, PNG et plus de 20 autres formats.

## Prérequis
- **Java Development Kit (JDK)** – Java 8+ installé et configuré sur votre machine.  
- **Aspose.Page for Java** – Téléchargez la bibliothèque depuis le site officiel [here](https://releases.aspose.com/page/java/).  
- Un fichier EPS contenant des métadonnées XMP (par ex., `xmp1.eps`).  

## Importer les packages
La classe `XmpMetadata` se trouve dans l’espace de noms `com.aspose.page.xmp`, tandis que la classe `Document` se trouve dans `com.aspose.page`. Importez les deux afin de pouvoir travailler avec le fichier EPS et ses métadonnées.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Étape 1 : Initialiser le flux du fichier EPS d’entrée
Commencez par définir le chemin vers votre répertoire de documents et initialisez le flux du fichier EPS d’entrée.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Étape 2 : Obtenir les métadonnées XMP
`XmpMetadata` est l’objet d’Aspose.Page qui contient le paquet XMP extrait d’un document. Récupérez‑le avec `document.getXmpMetadata()`. Si le fichier ne possède pas de XMP, l’API synthétise un paquet minimal à partir des commentaires PostScript existants.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 3 : Extraire l’information CreatorTool
La clé `CreatorTool` se trouve dans l’espace de noms `xmp` et enregistre l’application qui a généré le fichier. Vérifiez sa présence et affichez la valeur.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Étape 4 : Extraire l’information CreateDate
`CreateDate` stocke l’horodatage du moment où le document a été créé à l’origine. Utilisez le même modèle `containsKey`/`get` pour le lire.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Étape 5 : Récupérer la largeur de la miniature
Si des miniatures existent, le tableau `xmp:Thumbnails` contient une ou plusieurs entrées. Chaque entrée possède `width`, `height` et des données binaires. L’exemple extrait la largeur de la première miniature.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Étape 6 : Extraire l’information de format
La clé `format` indique le format de fichier original (par ex., “application/postscript”). Ceci est utile lorsque vous devez enregistrer ou valider les types de source.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Étape 7 : Obtenir le DocumentID
`DocumentID` est un identifiant unique attribué par l’application créatrice. Il peut être utilisé pour la déduplication dans de grandes bibliothèques d’actifs.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Pourquoi c’est important
Aspose.Page peut lire le XMP à partir de **plus de 20** formats de fichiers et traite des documents jusqu’à **500 Mo** sans charger le fichier complet en mémoire, vous offrant un accès rapide et à faible surcharge aux métadonnées essentielles. Cette capacité est cruciale pour les pipelines de traitement par lots, les systèmes de gestion d’actifs numériques et toute solution qui repose sur des attributs de documents recherchables et lisibles par machine.

## Pièges courants et conseils
- **XMP manquant :** Certains fichiers EPS peuvent ne pas contenir de XMP. L’appel `getXmpMetadata()` synthétisera un jeu minimal basé sur les commentaires PS existants, mais vous n’obtiendrez pas les métadonnées complètes à moins qu’elles ne soient intégrées.  
- **Tableaux de miniatures :** La clé `xmp:Thumbnails` peut contenir plusieurs entrées. L’exemple n’extrait que la première ; parcourez le tableau si vous avez besoin de toutes les miniatures.  
- **Conscience des espaces de noms :** Les clés XMP utilisent des espaces de noms (par ex., `xmp:`, `dc:`). Assurez‑vous de référencer le nom de clé exact ; sinon `containsKey` renverra false.  

## Questions fréquemment posées
### Puis‑je utiliser Aspose.Page pour Java avec d’autres langages de programmation ?
Oui, Aspose.Page prend en charge Java, .NET et plusieurs autres langages. Voir la liste complète dans la [documentation](https://reference.aspose.com/page/java/).

### Une version d’essai gratuite est‑elle disponible pour Aspose.Page pour Java ?
Oui, vous pouvez accéder à l’essai gratuit [here](https://releases.aspose.com/).

### Où puis‑je trouver du support pour Aspose.Page pour Java ?
Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l’aide communautaire et le support officiel.

### Comment obtenir une licence temporaire pour Aspose.Page pour Java ?
Vous pouvez obtenir une licence temporaire [here](https://purchase.aspose.com/temporary-license/).

### Existe‑t‑il des ressources supplémentaires pour Aspose.Page pour Java ?
Explorez la [documentation complète](https://reference.aspose.com/page/java/) et téléchargez la bibliothèque [here](https://releases.aspose.com/page/java/).

## FAQ supplémentaires
**Q : Cette approche fonctionne‑t‑elle avec les fichiers PDF contenant du XMP ?**  
R : Oui, Aspose.Page peut lire le XMP à partir de PDF, EPS et de plusieurs formats d’image.

**Q : Puis‑je modifier les métadonnées XMP après les avoir lues ?**  
R : Absolument. L’objet `XmpMetadata` est mutable ; vous pouvez ajouter, mettre à jour ou supprimer des clés, puis enregistrer le document.

**Q : Existe‑t‑il un moyen d’extraire toutes les images miniatures, pas seulement les dimensions ?**  
R : Vous pouvez récupérer les données binaires de la propriété `xmpGImg:data` de chaque entrée de miniature et les écrire dans un fichier.

## Conclusion
Vous avez maintenant maîtrisé **comment lire les métadonnées XMP** avec Java et Aspose.Page. En suivant ces étapes, vous pouvez extraire les outils du créateur, les horodatages, les miniatures, les informations de format et les IDs de document — vous offrant une vision complète des métadonnées intégrées de vos fichiers EPS. N’hésitez pas à expérimenter avec des espaces de noms XMP supplémentaires pour extraire des données encore plus riches pour vos applications.

---

**Dernière mise à jour :** 2026-05-25  
**Testé avec :** Aspose.Page for Java 24.12 (latest)  
**Auteur :** Aspose

## Tutoriels associés

- [Tutoriel Aspose Page Java – Ajouter des métadonnées XMP aux fichiers EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Tutoriel aspose.page xmp – Ajouter un espace de noms dans le XMP avec Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Tutoriel aspose page xmp – Modifier une valeur nommée dans le XMP avec Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}