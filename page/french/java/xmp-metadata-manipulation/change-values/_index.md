---
date: 2026-05-25
description: Apprenez à modifier le XMP dans les documents EPS à l'aide de Java avec
  Aspose.Page. Mettez à jour les métadonnées rapidement et de manière fiable.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Modifier les valeurs du XMP avec Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Comment modifier le XMP avec Aspose.Page – Modifier les valeurs du XMP avec
  Java
url: /fr/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifier les valeurs XMP avec Java

## Introduction
Si vous cherchez **comment modifier xmp** à l'intérieur d'un fichier EPS avec Java, vous êtes au bon endroit. Ce tutoriel vous guide à travers chaque étape — lecture du bloc XMP existant, mise à jour des champs tels que le créateur, le titre et la date de modification, puis persistance des modifications dans le document EPS. À la fin, vous disposerez d'un extrait réutilisable qui s'intègre à n'importe quel flux de travail automatisé, garantissant que vos fichiers contiennent les métadonnées correctes pour le branding, la conformité ou l'indexation par les moteurs de recherche.

## Réponses rapides
- **Que fait “aspose.page modify xmp” ?** Cela vous permet de lire et d'écrire des métadonnées XMP dans les fichiers EPS via l'API Aspose.Page Java.  
- **Quelle version de la bibliothèque est requise ?** Toute version récente d'Aspose.Page pour Java (l'API est stable entre les versions).  
- **Ai‑je besoin d'une licence pour exécuter l'exemple ?** Un essai gratuit suffit pour l'évaluation ; une licence commerciale est requise pour la production.  
- **Puis‑je modifier plusieurs champs XMP en même temps ?** Oui — appelez `put` pour chaque champ avant d'enregistrer le document.  
- **Une gestion du fuseau horaire est‑elle nécessaire ?** Définir le fuseau horaire par défaut (par ex., UTC) garantit des valeurs de date cohérentes.

## Qu'est‑ce que le XMP et pourquoi le modifier ?
XMP (Extensible Metadata Platform) est un format standardisé, basé sur XML, permettant d'intégrer des métadonnées riches directement dans des fichiers tels que EPS, PDF et images. Mettre à jour le XMP vous permet de contrôler la façon dont les documents sont indexés, affichés et recherchés — essentiel pour la cohérence de la marque, la conformité réglementaire et les pipelines de contenu automatisés.

## Pourquoi utiliser Aspose.Page pour Java ?
Aspose.Page fournit une **API complète, pure Java** qui élimine le besoin d'outils externes ou de bibliothèques natives. Elle prend en charge **plus de 50 formats d'entrée et de sortie** et peut traiter des fichiers EPS jusqu'à **500 Mo** sans charger le document complet en mémoire, offrant une manipulation rapide et à faible consommation de mémoire des métadonnées sur tout système d'exploitation exécutant Java.

## Prérequis
Avant de commencer ce tutoriel, assurez‑vous que les prérequis suivants sont en place :
1. **Environnement de développement Java** – Un JDK (8 ou supérieur) et un IDE ou un outil de construction de votre choix.  
2. **Bibliothèque Aspose.Page pour Java** – Téléchargez et installez la bibliothèque Aspose.Page pour Java. Vous pouvez trouver le package nécessaire [ici](https://releases.aspose.com/page/java/).

## Importer les packages
Commencez par importer les packages requis dans votre projet Java. Ces packages sont essentiels pour interagir avec et manipuler les documents EPS.

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

## Comment modifier le XMP dans un EPS avec Java ?
`Document` est la classe Aspose.Page qui représente un fichier EPS et fournit l'accès à son contenu et à ses métadonnées. `XmpMetadata` représente le bloc XMP attaché au document et permet la lecture et l'écriture des champs de métadonnées. `put` ajoute ou met à jour une entrée de métadonnées dans l'objet XmpMetadata. `save` écrit le document modifié, y compris les métadonnées XMP mises à jour, dans un fichier.

Chargez le fichier EPS avec `new Document("input.eps")`, récupérez son objet `XmpMetadata`, mettez à jour les clés souhaitées à l'aide de `put`, puis appelez `save` pour écrire les modifications dans un nouveau fichier. Ce flux concis gère automatiquement les blocs XMP manquants, en crée un à partir des commentaires PostScript si nécessaire, et assure des dates cohérentes au niveau du fuseau horaire.

## Étape 1 : Obtenir les métadonnées XMP
La classe `XmpMetadata` représente le bloc XMP attaché à un document EPS. Lorsque vous appelez `document.getXmpMetadata()`, l'API renvoie soit le bloc existant, soit en crée un nouveau à partir des commentaires PS tels que `%%Creator`, `%%CreateDate` et `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 2 : Modifier la valeur "ModifyDate"
Mettez à jour l'entrée `"ModifyDate"` pour refléter le nouveau horodatage de modification. Utilisez `java.util.Date` combiné avec `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` pour garantir que la valeur stockée soit indépendante du fuseau horaire.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Étape 3 : Modifier la valeur "Creator"
La clé `"Creator"` stocke le nom de l'application ou de la personne qui a généré le fichier EPS. Appelez `xmp.put("dc:creator", "Your Company Name")` pour remplacer la valeur existante par un identifiant personnalisé.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Étape 4 : Modifier la valeur "Title"
Le champ `"Title"` est affiché par de nombreux systèmes de gestion d'actifs. Le définir via `xmp.put("dc:title", "New Document Title")` garantit que le document apparaît correctement dans les catalogues et les résultats de recherche.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Étape 5 : Enregistrer le document avec les métadonnées XMP modifiées
Après toutes les modifications, invoquez `document.save("output.eps")`. La bibliothèque écrit le bloc XMP mis à jour dans le flux EPS tout en préservant le contenu graphique original inchangé.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Problèmes courants et solutions
- **Bloc XMP manquant** – L'API crée automatiquement un bloc à partir des commentaires PS, mais vous pouvez également instancier manuellement `XmpMetadata` si nécessaire.  
- **Incohérences de fuseau horaire** – Définissez toujours `TimeZone.setDefault` avant de créer l'objet `Date` afin d'éviter des décalages inattendus.  
- **Erreurs d'accès aux fichiers** – Assurez‑vous que les chemins d'entrée et de sortie sont corrects et que votre application dispose des permissions de lecture/écriture.

## Questions fréquemment posées

**Q : Comment gérer les considérations de fuseau horaire lors de la modification des valeurs XMP ?**  
R : Utilisez `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` pour garantir la cohérence des paramètres de fuseau horaire.

**Q : Puis‑je modifier plusieurs valeurs XMP en une seule opération ?**  
R : Oui, en utilisant la méthode `put` pour chaque valeur souhaitée, vous pouvez modifier plusieurs valeurs XMP simultanément.

**Q : Où puis‑je trouver une documentation supplémentaire pour Aspose.Page pour Java ?**  
R : Explorez la documentation complète [ici](https://reference.aspose.com/page/java/).

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page pour Java ?**  
R : Oui, vous pouvez accéder à l'essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page pour Java ?**  
R : Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : La modification du XMP affecte‑t‑elle le contenu visuel du EPS ?**  
R : Non. Les changements XMP concernent uniquement les métadonnées et n'altèrent pas les éléments graphiques du fichier EPS.

**Q : Puis‑je lire programmétiquement les valeurs mises à jour pour vérifier le changement ?**  
R : Absolument — appelez simplement `xmp.get("dc:creator")` (ou la clé correspondante) après l'enregistrement et avant de fermer le document.

## Conclusion
Félicitations ! Vous avez maîtrisé **comment modifier xmp** dans les documents EPS en utilisant Aspose.Page pour Java. En intégrant des métadonnées précises de créateur, de titre et de date de modification, vous assurez que vos actifs sont recherchables, conformes et alignés avec vos standards de branding. N'hésitez pas à intégrer ce modèle dans des pipelines de traitement par lots, des étapes CI/CD ou tout flux de travail automatisé de génération de documents.

---

**Dernière mise à jour :** 2026-05-25  
**Testé avec :** Aspose.Page for Java (latest release)  
**Auteur :** Aspose

## Tutoriels associés

- [Tutoriel Aspose Page Java – Ajouter des métadonnées XMP aux fichiers EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Comment lire les métadonnées XMP avec Java – Guide Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Modifier les éléments de tableau dans XMP avec Java](/page/java/xmp-metadata-manipulation/change-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}