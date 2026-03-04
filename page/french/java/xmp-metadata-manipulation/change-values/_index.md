---
date: 2025-12-21
description: Apprenez à modifier le XMP des documents EPS avec Java. Améliorez rapidement
  les métadonnées grâce à Aspose.Page pour Java.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page modifier xmp – Modifier les valeurs du XMP avec Java
url: /fr/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modifier les valeurs XMP avec Java

## Introduction
Si vous devez **aspose.page modify xmp** des données à l'intérieur d'un fichier EPS, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons les étapes exactes nécessaires pour lire, mettre à jour et enregistrer les valeurs XMP (Extensible Metadata Platform) à l'aide de la bibliothèque Aspose.Page pour Java. À la fin, vous pourrez personnaliser les métadonnées du document — telles que le créateur, le titre et la date de modification — pour répondre aux exigences de votre projet.

## Quick Answers
- **Que fait « aspose.page modify xmp » ?** Il vous permet de lire et d'écrire les métadonnées XMP dans les fichiers EPS via l'API Java d'Aspose.Page.  
- **Quelle version de la bibliothèque est requise ?** Toute version récente d'Aspose.Page pour Java (l'API est stable d'une version à l'autre).  
- **Ai‑je besoin d'une licence pour exécuter l'exemple ?** Un essai gratuit suffit pour l'évaluation ; une licence commerciale est requise pour la production.  
- **Puis‑je modifier plusieurs champs XMP en même temps ?** Oui — appelez `put` pour chaque champ avant d'enregistrer le document.  
- **La gestion du fuseau horaire est‑elle nécessaire ?** Définir le fuseau horaire par défaut (par ex. UTC) garantit des valeurs de date cohérentes.

## Qu’est‑ce que XMP et pourquoi le modifier ?
XMP (Extensible Metadata Platform) est une méthode normalisée pour intégrer des métadonnées riches directement à l'intérieur de fichiers tels que EPS, PDF et images. Mettre à jour le XMP vous permet de contrôler la façon dont les documents sont indexés, affichés et recherchés — essentiel pour le branding, la conformité et l'automatisation des flux de travail.

## Pourquoi utiliser Aspose.Page pour Java ?
- **API complète** – Aucun besoin d'outils externes ; tout est géré en‑processus.  
- **Multiplateforme** – Fonctionne sur tout système d'exploitation supportant Java.  
- **Aucune dépendance native** – Implémentation pure Java qui simplifie le déploiement.  
- **Support robuste** – Gère les blocs XMP existants et crée de nouveaux blocs à partir des commentaires PS lorsqu'ils sont absents.

## Prérequis
Avant de commencer ce tutoriel, assurez‑vous d'avoir les prérequis suivants :
1. **Environnement de développement Java** – Un JDK (8 ou supérieur) et un IDE ou un outil de construction de votre choix.  
2. **Bibliothèque Aspose.Page pour Java** – Téléchargez et installez la bibliothèque Aspose.Page pour Java. Vous pouvez trouver le package nécessaire [ici](https://releases.aspose.com/page/java/).

## Import Packages
Commencez par importer les packages requis dans votre projet Java. Ces packages sont indispensables pour interagir avec les documents EPS et les manipuler.

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

## Étape 1 : Obtenir les métadonnées XMP
Récupérez les métadonnées XMP du document EPS. Si le fichier EPS ne contient pas de métadonnées XMP, un nouveau bloc sera créé à partir des commentaires de métadonnées PS tels que %%Creator, %%CreateDate et %%Title.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 2 : Modifier la valeur « ModifyDate »
Modifiez la valeur « ModifyDate » dans les métadonnées XMP pour refléter la date souhaitée.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Étape 3 : Modifier la valeur « Creator »
Mettez à jour la valeur « Creator » dans les métadonnées XMP afin de spécifier le créateur du document.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Étape 4 : Modifier la valeur « Title »
Modifiez la valeur « Title » dans les métadonnées XMP pour définir un titre approprié au document.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Étape 5 : Enregistrer le document avec les métadonnées XMP modifiées
Enregistrez le document avec les métadonnées XMP mises à jour dans un nouveau fichier EPS.

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
- **Erreurs d'accès aux fichiers** – Vérifiez que les chemins d'entrée et de sortie sont corrects et que votre application dispose des permissions de lecture/écriture.

## FAQ

**Q : Comment gérer les considérations de fuseau horaire lors de la modification des valeurs XMP ?**  
R : Utilisez `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` pour garantir la cohérence des paramètres de fuseau horaire.

**Q : Puis‑je changer plusieurs valeurs XMP en une seule opération?**  
R : Oui, en utilisant la méthode `put` pour chaque valeur souhaitée, vous pouvez modifier plusieurs valeurs XMP simultanément.

**Q : Où trouver une documentation supplémentaire pour Aspose.Page pour Java ?**  
R : Consultez la documentation complète [ici](https://reference.aspose.com/page/java/).

**Q : Existe‑t‑il un essai gratuit pour Aspose.Page pour Java ?**  
R : Oui, vous pouvez accéder à l'essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page pour Java ?**  
R : Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : La modification du XMP affecte‑t‑elle le contenu visuel du EPS ?**  
R : Non. Les changements XMP concernent uniquement les métadonnées et n'altèrent pas les éléments graphiques du fichier EPS.

**Q : Puis‑je lire programmatique les valeurs mises à jour pour vérifier la modification ?**  
R : Absolument — appelez simplement `xmp.get("dc:creator")` (ou la clé correspondante) après l'enregistrement et avant la fermeture du document.

## Conclusion
Félicitations ! Vous avez réussi à modifier les valeurs **aspose.page modify xmp** dans des documents EPS à l'aide d'Aspose.Page pour Java. Ce tutoriel vous a fourni les connaissances nécessaires pour ajuster les métadonnées, assurant que vos documents répondent parfaitement à vos exigences spécifiques.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
