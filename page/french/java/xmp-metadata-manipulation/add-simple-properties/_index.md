---
date: 2026-05-20
description: Apprenez à ajouter des métadonnées XMP aux fichiers EPS avec Aspose.Page
  for Java. Guide étape par étape pour intégrer des propriétés XMP simples par programme.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Ajouter des propriétés simples en XMP avec Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Ajouter des métadonnées XMP aux fichiers EPS avec Java
url: /fr/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des métadonnées XMP aux fichiers EPS à l'aide de Java

## Introduction
Dans les pipelines graphiques modernes, pouvoir **ajouter des métadonnées XMP** aux fichiers EPS de manière programmatique vous donne un contrôle total sur la façon dont vos illustrations sont décrites, recherchées et archivées. Avec Aspose.Page for Java, vous pouvez lire, modifier et écrire des paquets XMP à l'intérieur des documents EPS sans quitter l'écosystème Java. Dans ce tutoriel, nous vous guiderons à travers les étapes exactes pour ajouter des propriétés XMP simples à un fichier EPS, afin que vous puissiez enrichir vos graphiques avec des métadonnées personnalisées rapidement et de manière fiable.

## Réponses rapides
- **Que signifie « ajouter des métadonnées XMP aux EPS » ?** Intégrer un paquet XMP (métadonnées basées sur XML) à l'intérieur d'un fichier EPS.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (téléchargeable depuis le site Aspose).  
- **Ai‑je besoin d’une licence pour les tests ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Combien de lignes de code ?** Moins de 30 lignes de Java plus quelques instructions d’importation.  
- **Puis‑je ajouter d’autres types de données ?** Oui – les dates, entiers, doubles, chaînes et même les tableaux sont pris en charge.

## Comment ajouter des métadonnées XMP aux fichiers EPS avec Java ?
Chargez le fichier EPS avec `new PsDocument("input.eps")`, récupérez ou créez son paquet XMP, insérez les propriétés souhaitées, puis enregistrez le document sur le disque – le tout en moins de dix lignes de code Java. Cette approche vous permet d’intégrer des métadonnées recherchables et conformes aux normes sans modifier manuellement la source EPS.

## Qu'est‑ce que les métadonnées XMP dans les EPS ?
Les métadonnées XMP dans un EPS sont un paquet XML qui vit à l'intérieur du fichier EPS et stocke des informations telles que l'auteur, la date de création et des balises personnalisées. L’intégration de ce paquet permet aux outils en aval de lire et d’utiliser les données sans avoir besoin de fichiers annexes séparés.

## Pourquoi ajouter des métadonnées XMP aux fichiers EPS ?
Intégrer des métadonnées XMP rend les actifs EPS immédiatement recherchables, assure la conformité en stockant les informations de licence à l'intérieur du fichier, permet aux pipelines automatisés de prendre des décisions basées sur les balises intégrées, et garantit que les métadonnées voyagent avec le graphique sur toutes les plateformes. Aspose.Page peut traiter des fichiers jusqu’à 500 Mo sans charger le document complet en mémoire, offrant ainsi des performances rapides pour des charges de travail à grande échelle.

## Prérequis
- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page for Java installée. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  
- Un fichier EPS d'exemple contenant des métadonnées. Si vous n’en avez pas, utilisez le fichier **`xmp3.eps`** fourni.

## Importer les packages
Tout d'abord, importez les classes dont vous aurez besoin. Les importations restent exactement les mêmes que dans l'exemple original :

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Étape 1 : Charger le document EPS et obtenir les métadonnées XMP
La classe `PsDocument` représente un fichier EPS et fournit des méthodes pour accéder à son contenu et à ses métadonnées.  
L'objet `XmpMetadata` contient le paquet XMP associé au document.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 2 : Ajouter une propriété Date
La classe `Date` représente un instant précis dans le temps, avec une précision à la milliseconde.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Étape 3 : Ajouter une propriété Integer
La classe `Integer` encapsule une valeur primitive `int` sous forme d'objet.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Étape 4 : Ajouter une propriété Double
La classe `Double` encapsule une valeur primitive `double` sous forme d'objet.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Étape 5 : Ajouter une propriété String
La classe `String` représente une séquence de caractères.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Étape 6 : Enregistrer le fichier EPS mis à jour
La méthode `save` écrit le document modifié sur le disque, en préservant la structure EPS.

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

## Étape 7 : Nettoyer les ressources
Fermez toujours les flux pour éviter les fuites de descripteurs de fichiers et assurez‑vous que tous les tampons sont vidés.

```java
// Close input EPS stream
psStream.close();
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Métadonnées XMP nulles** | Le fichier EPS ne contenait aucun paquet XMP et la bibliothèque n’a pas pu déduire les commentaires PS. | Assurez‑vous que l’EPS source contient au moins un commentaire PS (par ex., `%%Creator`). La bibliothèque générera automatiquement un paquet XMP minimal. |
| **Décalage de fuseau horaire** | Les dates apparaissent décalées lorsqu’elles sont ouvertes dans une autre application. | Définissez `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` avant de créer l’objet `Date`, comme indiqué à l’Étape 2. |
| **Exception de licence** | Le runtime lève `LicenseException`. | Appliquez une licence valide d’Aspose.Page avant d’utiliser l’API, ou exécutez en mode essai pour l’évaluation. |

## Questions fréquentes
**Q : Puis‑je utiliser Aspose.Page for Java avec d’autres langages de programmation ?**  
R : Aspose.Page prend principalement en charge Java, mais des bibliothèques équivalentes sont disponibles pour .NET, C++ et Python.

**Q : Une version d’essai gratuite est‑elle disponible pour Aspose.Page for Java ?**  
R : Oui, vous pouvez explorer les fonctionnalités d’Aspose.Page en obtenant un essai gratuit **[ici](https://releases.aspose.com/)**.

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.Page for Java ?**  
R : La documentation est disponible **[ici](https://reference.aspose.com/page/java/)**.

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
R : Une licence temporaire peut être obtenue **[ici](https://purchase.aspose.com/temporary-license/)**.

**Q : Où puis‑je acheter Aspose.Page for Java ?**  
R : Vous pouvez acheter le produit **[ici](https://purchase.aspose.com/buy)**.

**Dernière mise à jour :** 2026-05-20  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment lire les métadonnées XMP avec Java – Guide Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Tutoriel xmp aspose.page – Ajouter un espace de noms dans XMP avec Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Ajouter des éléments de tableau dans les métadonnées XMP avec Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}