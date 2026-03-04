---
date: 2025-12-21
description: Apprenez à lire les métadonnées XMP avec Java et Aspose.Page. Ce guide
  étape par étape vous montre comment lire le XMP du format de document et extraire
  les propriétés clés.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Comment lire les métadonnées XMP avec Java – Guide Aspose.Page
url: /fr/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir les métadonnées XMP avec Java

## Comment lire les métadonnées XMP avec Java

Bienvenue dans notre tutoriel étape par étape qui montre **comment lire les métadonnées XMP** avec Java et la bibliothèque Aspose.Page. XMP (Extensible Metadata Platform) est une norme largement adoptée pour intégrer des métadonnées riches à l'intérieur des documents. À la fin de ce guide, vous serez capable de lire le XMP du format de document, d'extraire les informations sur le créateur, les horodatages, les miniatures, et plus encore—vous permettant de créer des solutions d'analyse de documents plus intelligentes.

## Réponses rapides
- **Que signifie « comment lire xmp » ?** Il s'agit d'extraire les métadonnées XMP des fichiers de façon programmatique.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (disponible depuis la page de téléchargement Aspose).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète est requise pour une utilisation en production ; un essai gratuit est disponible.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur.  
- **Puis‑je lire le XMP d’autres formats ?** Oui, Aspose.Page peut gérer EPS, PDF et plusieurs types d'images qui intègrent du XMP.

## Prérequis
Avant de plonger dans le code, assurez‑vous d'avoir :

- **Java Development Kit (JDK)** – Java 8+ installé et configuré sur votre machine.  
- **Aspose.Page for Java** – Téléchargez la bibliothèque depuis le site officiel [ici](https://releases.aspose.com/page/java/).  
- Un fichier EPS contenant des métadonnées XMP (par ex., `xmp1.eps`).  

## Importer les packages
Dans votre projet Java, importez les packages nécessaires :
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Étape 1 : Initialiser le flux du fichier EPS d’entrée
Commencez par définir le chemin vers votre répertoire de documents et initialiser le flux du fichier EPS d’entrée.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Étape 2 : Obtenir les métadonnées XMP
Récupérez les métadonnées XMP du fichier EPS. Si le fichier ne possède pas de métadonnées XMP, une nouvelle sera générée à partir des commentaires de métadonnées PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Étape 3 : Extraire l’information « CreatorTool »
Vérifiez et affichez la valeur « CreatorTool » des métadonnées XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Étape 4 : Extraire l’information « CreateDate »
Vérifiez et affichez la valeur « CreateDate » des métadonnées XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Étape 5 : Récupérer la largeur de la miniature
Si des miniatures existent, extrayez et affichez la largeur de la première miniature.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Étape 6 : Extraire l’information de format
Vérifiez et affichez la valeur « format » des métadonnées XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Étape 7 : Obtenir le DocumentID
Vérifiez et affichez la valeur « DocumentID » des métadonnées XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Pourquoi c’est important
Lire les métadonnées XMP vous permet de découvrir programmatique­ment l’origine, la date de création et d’autres attributs essentiels d’un document sans l’ouvrir dans un visualiseur. Cela est particulièrement utile pour le traitement par lots, les systèmes de gestion de contenu et les pipelines d’actifs numériques où les métadonnées pilotent l’indexation et la recherche.

## Pièges courants et conseils
- **XMP manquant :** Certains fichiers EPS peuvent ne pas contenir de XMP. L’appel `getXmpMetadata()` synthétisera un jeu minimal basé sur les commentaires PS existants, mais vous n’obtiendrez pas de métadonnées complètes tant qu’elles ne sont pas intégrées.  
- **Tableaux de miniatures :** La clé `xmp:Thumbnails` peut contenir plusieurs entrées. L’exemple n’extrait que la première ; parcourez le tableau si vous avez besoin de toutes les miniatures.  
- **Sensibilité aux espaces de noms :** Les clés XMP utilisent des espaces de noms (par ex., `xmp:`, `dc:`). Assurez‑vous de référencer le nom exact de la clé ; sinon `containsKey` renverra false.

## Questions fréquemment posées
### Puis‑je utiliser Aspose.Page for Java avec d’autres langages de programmation ?
Oui, Aspose.Page prend en charge plusieurs langages, dont Java, .NET et d’autres. Consultez la [documentation](https://reference.aspose.com/page/java/) pour plus de détails.

### Une version d’essai gratuite est‑elle disponible pour Aspose.Page for Java ?
Oui, vous pouvez accéder à l’essai gratuit [ici](https://releases.aspose.com/).

### Où puis‑je trouver du support pour Aspose.Page for Java ?
Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support communautaire.

### Comment obtenir une licence temporaire pour Aspose.Page for Java ?
Vous pouvez obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Existe‑t‑il des ressources supplémentaires pour Aspose.Page for Java ?
Explorez la documentation complète [ici](https://reference.aspose.com/page/java/) et téléchargez la bibliothèque [ici](https://releases.aspose.com/page/java/).

## FAQ supplémentaire
**Q : Cette approche fonctionne‑t‑elle avec des fichiers PDF contenant du XMP ?**  
R : Oui, Aspose.Page peut lire le XMP depuis PDF, EPS et plusieurs formats d’image.

**Q : Puis‑je modifier les métadonnées XMP après les avoir lues ?**  
R : Absolument. L’objet `XmpMetadata` est mutable ; vous pouvez ajouter, mettre à jour ou supprimer des clés puis enregistrer le document.

**Q : Existe‑t‑il un moyen d’extraire toutes les images miniatures, pas seulement leurs dimensions ?**  
R : Vous pouvez récupérer les données binaires de la propriété `xmpGImg:data` de chaque entrée de miniature et les écrire dans un fichier.

## Conclusion
Vous avez maintenant maîtrisé **comment lire les métadonnées XMP** avec Java et Aspose.Page. En suivant ces étapes, vous pouvez extraire les outils du créateur, les horodatages, les miniatures, les informations de format et les IDs de document—vous offrant une visibilité complète sur les métadonnées intégrées de vos fichiers EPS. N’hésitez pas à expérimenter avec d’autres espaces de noms XMP pour extraire des données encore plus riches pour vos applications.

---

**Dernière mise à jour :** 2025-12-21  
**Testé avec :** Aspose.Page for Java 24.12 (latest)  
**Auteur :** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
