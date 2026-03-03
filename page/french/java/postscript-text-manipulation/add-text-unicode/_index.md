---
date: 2025-12-17
description: Apprenez à ajouter du texte Unicode en Java PostScript avec Aspose.Page
  – un guide étape par étape pour ajouter des chaînes Unicode sans effort.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Comment ajouter du texte Unicode en Java PostScript avec Aspose.Page
url: /fr/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter du texte Unicode dans Java PostScript avec Aspose.Page

## Introduction
Si vous demandez **comment ajouter des caractères Unicode** à un flux de travail PostScript (ou XPS) basé sur Java, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes nécessaires pour intégrer des chaînes Unicode à l'aide de la bibliothèque Aspose.Page pour Java. À la fin du guide, vous pourrez insérer n'importe quel texte spécifique à une langue — arabe, chinois, emojis, ce que vous voulez — directement dans votre sortie PostScript.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java
- **Puis-je ajouter des scripts de droite à gauche ?** Oui, définit le niveau Bidi comme indiqué dans le code
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests; une licence commerciale est requise pour la production
- **Quel IDE fonctionne le mieux ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans)
- **Le code est-il multiplateforme ?** Absolument—exécutez-le sous Windows, macOS ou Linux

## Qu'entend-on par « comment ajouter Unicode » dans le contexte du PostScript ?
Ajouter Unicode signifie insérer des caractères représentés par des points de code au-delà de la plage ASCII de base. Aspose.Page abstraite les détails d’encodage bas‑niveau, vous permettant de vous concentrer sur le contenu texte et son placement visuel.

## Pourquoi utiliser Aspose.Page pour du texte Unicode ?
- **Prise en charge complète d'Unicode** – Gère les scripts complexes, les ligatures et les langues de droite à gauche.
- **Aucune dépendance externe** – Pas besoin de gérer manuellement les fichiers de polices; l'API fonctionne avec les politiques du système.
- **API simple** – Quelques appels de méthode suffisent pour rendre le texte multilingue.

## Prérequis
Avant de plonger, assurez-vous d'avoir les éléments suivants prêts :

1. **Kit de développement Java (JDK)** – Toute version récente (8 ou supérieure).
2. **Aspose.Page pour Java** – Téléchargez et installez la bibliothèque depuis le [lien de téléchargement](https://releases.aspose.com/page/java/).
3. **IDE de votre choix** – IntelliJ IDEA, Eclipse ou tout autre IDE Java que vous préférez.

## Importer des packages
Ajoutez les classes Aspose.Page requises à votre fichier source Java :

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Étape 1 : Configurer votre projet
Créez un nouveau projet Java, ajoutez le JAR Aspose.Page au chemin de construction du projet, et créez un dossier où le fichier XPS généré sera enregistré. Ce dossier sera référencé plus tard sous le nom `dataDir`.

## Étape 2 : Initialiser le document XPS
Instanciez un document XPS vide qui contiendra le contenu :

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Étape 3 : Ajouter du texte Unicode
Nous allons maintenant ajouter réellement la chaîne Unicode. L'exemple ci‑dessous écrit la phrase inversée « AVAJ rof SPX.esopsA », qui ne contient que des caractères ASCII, mais vous pouvez la remplacer par n'importe quel texte Unicode (par ex. l'arabe « مرحبا » ou le chinois « 你好 »).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Astuce :** Pour rendre correctement les langues de droite à gauche, définissez `glyphs.setBidiLevel(1);`. Pour les scripts de gauche à droite, vous pouvez omettre cette ligne.

## Étape 4 : Enregistrer le document
Enregistrez le fichier XPS sur le disque :

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Après l'exécution du programme, ouvrez le `AddEncodingText_out.xps` généré avec n'importe quel visualiseur XPS pour voir le texte Unicode rendu aux coordonnées spécifiées.

## Problèmes courants et solutions
| Problème | Raison | Solutions |
|--------------|--------|--------------|
| Le texte apparaît sous forme de carrés | Police introuvable ou ne prend pas en charge les caractères | Utilisez une police incluant les glyphes requis (par ex. «Arial Unicode MS») |
| Le texte de droite à gauche s'affiche de gauche à droite | Niveau Bidi non défini | Appelez `glyphs.setBidiLevel(1);` |
| Le fichier n'est pas enregistré | Chemin `dataDir` invalide ou permissions d'écriture manquantes | Assurez-vous que le répertoire existe et que l'application dispose des droits d'écriture |

## Questions fréquemment posées
### Puis‑je utiliser Aspose.Page pour Java avec d'autres langages de programmation ?
Aspose.Page est principalement conçu pour Java, mais Aspose propose des bibliothèques pour divers langages de programmation.

### Un essai gratuit est-il disponible ?
Oui, vous pouvez à un essai gratuit d'Aspose.Page [ici](https://releases.aspose.com/).

### Où puis‑je trouver du support et des discussions sur Aspose.Page?
Visitez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour le support et les discussions.

### Comment obtenir une licence temporaire pour Aspose.Page?
Vous pouvez posséder une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### Quels sont les styles de police disponibles dans Aspose.Page?
Aspose.Page prend en charge les styles de police tels que Regular, Bold, Italic et BoldItalic.

## Conclusion
Vous avez maintenant maîtrisé **comment ajouter du texte Unicode** à un document Java PostScript (XPS) en utilisant Aspose.Page. Cette capacité ouvre la voie à des rapports multilingues, des factures internationalisées et tout scénario nécessitant des caractères non‑ASCII. N'hésitez pas à explorer des fonctionnalités supplémentaires comme la rotation du texte, les chemins de découpe ou l'intégration de polices personnalisées—les détails sont disponibles dans la [documentation officielle](https://reference.aspose.com/page/java/).

---

**Dernière mise à jour :** 2025-12-17  
**Testé avec :** Aspose.Page for Java 23.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
