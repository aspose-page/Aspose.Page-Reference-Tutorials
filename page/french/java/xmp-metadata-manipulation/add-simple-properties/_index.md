---
date: 2025-12-20
description: Apprenez à créer des métadonnées XMP EPS dans les fichiers EPS à l’aide
  d’Aspose.Page pour Java. Guide étape par étape pour ajouter des propriétés XMP simples
  de manière programmatique.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Comment créer des métadonnées XMP EPS avec Java
url: /fr/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des propriétés simples dans XMP avec Java

## Introduction
Dans les flux de travail modernes de documents, pouvoir **create XMP metadata EPS** des fichiers de manière programmatique vous donne un contrôle total sur la façon dont vos graphiques sont décrits, recherchés et archivés. Avec Aspose.Page for Java, vous pouvez lire, modifier et écrire des paquets XMP à l'intérieur des documents EPS sans quitter l'écosystème Java. Dans ce tutoriel, nous vous guiderons à travers les étapes exactes pour ajouter des propriétés XMP simples à un fichier EPS, afin que vous puissiez enrichir vos graphiques avec des métadonnées personnalisées rapidement et de manière fiable.

## Réponses rapides
- **What does “create xmp metadata eps” mean?** Ajouter un paquet XMP (métadonnées basées sur XML) à un fichier EPS.  
- **Which library is required?** Aspose.Page for Java (téléchargeable depuis le site Aspose).  
- **Do I need a license for testing?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **How many lines of code?** Moins de 30 lignes de Java plus quelques instructions d'importation.  
- **Can I add other data types?** Oui – les dates, entiers, doubles, chaînes et même les tableaux sont pris en charge.

## Qu'est-ce que create xmp metadata eps ?
XMP (Extensible Metadata Platform) est une norme permettant d'intégrer des métadonnées riches à l'intérieur des fichiers. Lorsque vous **create XMP metadata EPS**, vous intégrez un paquet XML dans un document EPS (Encapsulated PostScript), permettant aux applications en aval de lire l'auteur, la date de création, des balises personnalisées, etc.

## Pourquoi ajouter des métadonnées XMP aux fichiers EPS ?
- **Searchability :** Permet l'indexation automatique par les systèmes DAM.  
- **Compliance :** Stocke les informations légales ou de licence directement dans le fichier.  
- **Automation :** Permet aux pipelines en aval de prendre des décisions basées sur les données intégrées.  
- **Portability :** Les métadonnées voyagent avec l'EPS, assurant la cohérence entre les plateformes.

## Prérequis
Avant de commencer, assurez‑vous d'avoir :

- Connaissances de base en programmation Java.  
- Bibliothèque Aspose.Page for Java installée. Vous pouvez la télécharger **[ici](https://releases.aspose.com/page/java/)**.  
- Un fichier EPS d'exemple contenant des métadonnées. Si vous n'en avez pas, utilisez le fichier **`xmp3.eps`** fourni.

## Importer les packages
Tout d'abord, importez les classes dont vous aurez besoin. Les importations restent exactement les mêmes que dans l'exemple original :

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

## Étape 1 : Charger le document EPS et obtenir les métadonnées XMP
Nous ouvrons le fichier EPS, créons une instance `PsDocument` et récupérons (ou créons) le paquet XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 2 : Ajouter une propriété Date
Ajouter une date est aussi simple que de créer un objet `Date` et de le placer dans la carte XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Étape 3 : Ajouter une propriété Entier
Vous pouvez stocker des identifiants numériques ou des numéros de version à l'aide d'une valeur entière.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Étape 4 : Ajouter une propriété Double
Les nombres à virgule flottante sont utiles pour des mesures ou des évaluations.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Étape 5 : Ajouter une propriété Chaîne
Les balises textuelles personnalisées (par ex., des codes projet) sont stockées sous forme de chaînes.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Étape 6 : Enregistrer le fichier EPS mis à jour
Après avoir ajouté toutes les propriétés, écrivez le document sur le disque.

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

## Étape 7 : Nettoyer les ressources
Fermez toujours le flux d'entrée pour éviter les fuites de descripteurs de fichier.

```java
// Close input EPS stream
psStream.close();
```

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| **Null XMP metadata** | Le fichier EPS ne contenait aucun paquet XMP et la bibliothèque n'a pas pu déduire les commentaires PS. | Assurez‑vous que le fichier EPS source contient au moins un commentaire PS (par ex., `%%Creator`). La bibliothèque générera automatiquement un paquet XMP minimal. |
| **Time zone mismatch** | Les dates apparaissent décalées lorsqu'elles sont ouvertes dans une autre application. | Définissez `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` avant de créer l'objet `Date`, comme indiqué à l'étape 2. |
| **License exception** | Le runtime lance `LicenseException`. | Appliquez une licence valide d'Aspose.Page avant d'utiliser l'API, ou exécutez en mode essai pour l'évaluation. |

## Conclusion
En suivant ces étapes, vous savez maintenant comment **create XMP metadata EPS** à l'aide d'Aspose.Page for Java. Ajouter des propriétés simples telles que des dates, des entiers, des doubles et des chaînes est simple, et les fichiers EPS résultants contiennent des métadonnées riches et recherchables qui profitent à tout flux de travail en aval.

## Questions fréquentes
### Puis-je utiliser Aspose.Page for Java avec d'autres langages de programmation ?
Aspose.Page prend principalement en charge Java, mais des versions sont disponibles pour d'autres langages comme .NET.

### Une version d'essai gratuite est‑elle disponible pour Aspose.Page for Java ?
Oui, vous pouvez explorer les fonctionnalités d'Aspose.Page en obtenant un essai gratuit [ici](https://releases.aspose.com/).

### Où puis‑je trouver la documentation détaillée d'Aspose.Page for Java ?
La documentation est disponible [ici](https://reference.aspose.com/page/java/).

### Comment obtenir une licence temporaire pour Aspose.Page for Java ?
Une licence temporaire peut être obtenue [ici](https://purchase.aspose.com/temporary-license/).

### Où acheter Aspose.Page for Java ?
Vous pouvez acheter le produit [ici](https://purchase.aspose.com/buy).

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}