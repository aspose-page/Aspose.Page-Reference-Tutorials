---
date: 2026-05-20
description: Apprenez comment ajouter du texte Unicode dans Java PostScript en utilisant
  Aspose.Page – un guide étape par étape pour ajouter des chaînes Unicode sans effort.
keywords:
- how to add unicode
- java add arabic text
- java add chinese text
linktitle: Ajouter du texte avec une chaîne Unicode dans Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  headline: How to Add Unicode Text in Java PostScript with Aspose.Page
  type: TechArticle
- description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  name: How to Add Unicode Text in Java PostScript with Aspose.Page
  steps:
  - name: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
    text: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
  - name: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
    text: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
  - name: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
    text: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
  type: HowTo
- questions:
  - answer: Aspose.Page is built specifically for Java, but Aspose offers equivalent
      libraries for .NET, C++, and Python if you need cross‑language support.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      help, samples, and troubleshooting tips.
    question: Where can I find support and community discussions?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The API supports Regular, Bold, Italic, and BoldItalic styles for any
      TrueType or OpenType font you load.
    question: What font styles does Aspose.Page support?
  type: FAQPage
second_title: Aspose.Page Java API
title: Comment ajouter du texte Unicode dans Java PostScript avec Aspose.Page
url: /fr/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter du texte Unicode dans Java PostScript avec Aspose.Page

## Introduction
Si vous vous demandez **how to add Unicode** des caractères dans un flux de travail PostScript (ou XPS) basé sur Java, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons les étapes exactes nécessaires pour intégrer des chaînes Unicode à l'aide de la bibliothèque Aspose.Page pour Java. À la fin du guide, vous pourrez insérer tout texte spécifique à une langue — arabe, chinois, emojis, ce que vous voulez — directement dans votre sortie PostScript.

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.Page for Java  
- **Puis-je ajouter des scripts de droite à gauche ?** Oui, définissez le niveau Bidi comme indiqué dans le code  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit fonctionne pour les tests ; une licence commerciale est requise pour la production  
- **Quel IDE fonctionne le mieux ?** Tout IDE Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **Le code est-il multiplateforme ?** Absolument — exécutez-le sur Windows, macOS ou Linux  

## Qu'est-ce que “how to add Unicode” dans le contexte du PostScript ?
L'ajout de texte Unicode signifie intégrer des caractères dont les points de code se situent en dehors de la plage ASCII de base — comme l'arabe, le chinois ou les emojis — dans un document PostScript (ou XPS) à l'aide d'Aspose.Page. La bibliothèque mappe automatiquement ces points de code aux glyphes appropriés dans la police sélectionnée, gérant le façonnage complexe, les ligatures et l'ordre de droite à gauche sans aucun travail d'encodage manuel.

## Pourquoi utiliser Aspose.Page pour le texte Unicode ?
Aspose.Page vous offre une solution fiable, 100 % pure‑Java qui prend en charge **plus de 50 formats d'entrée et de sortie** et peut rendre du texte multilingue dans des documents allant jusqu'à 1 000 pages sans charger le fichier complet en mémoire. Elle élimine le besoin d'utilitaires externes de gestion des polices, réduit le temps de développement de 70 % et garantit une sortie visuelle cohérente sur les environnements Windows, macOS et Linux.

## Prérequis
Avant de plonger, assurez‑vous d'avoir les éléments suivants prêts :

1. **Java Development Kit (JDK)** – Toute version récente (8 ou supérieure).  
2. **Aspose.Page for Java** – Téléchargez et installez la bibliothèque depuis le [lien de téléchargement](https://releases.aspose.com/page/java/). Vous pouvez également parcourir toutes les versions [ici](https://releases.aspose.com/).  
3. **IDE de votre choix** – IntelliJ IDEA, Eclipse, ou tout autre IDE Java que vous préférez.

## Importer les packages
Ajoutez les classes Aspose.Page requises à votre fichier source Java :

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Étape 1 : Configurer votre projet
Créez un nouveau projet Java, ajoutez le JAR Aspose.Page au chemin de construction du projet, et créez un dossier où le fichier XPS généré sera enregistré. Ce dossier est référencé plus tard sous le nom `dataDir`.

## Étape 2 : Initialiser le document XPS
La classe `XpsDocument` représente un fichier XPS en mémoire et fournit le canevas pour toutes les opérations de dessin.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Étape 3 : Ajouter du texte Unicode
Nous allons maintenant réellement ajouter la chaîne Unicode. L'exemple ci‑dessous écrit la phrase inversée « AVAJ rof SPX.esopsA », qui ne contient que des caractères ASCII, mais vous pouvez la remplacer par n'importe quel texte Unicode (par ex., l'arabe « مرحبا » ou le chinois « 你好 »). C’est ainsi que vous **java add arabic text** ou **java add chinese text** ajoutez du texte à votre document.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Astuce :** Pour rendre correctement les langues de droite à gauche, définissez `glyphs.setBidiLevel(1);`. Pour les scripts de gauche à droite, vous pouvez omettre cette ligne.

## Étape 4 : Enregistrer le document
Enregistrez le fichier XPS sur le disque :

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Après avoir exécuté le programme, ouvrez le fichier généré `AddEncodingText_out.xps` avec n'importe quel visualiseur XPS pour voir le texte Unicode rendu aux coordonnées spécifiées.

## Problèmes courants et solutions
| Problème | Raison | Solution |
|----------|--------|----------|
| Le texte apparaît sous forme de carrés | Police non trouvée ou ne supporte pas les caractères | Utilisez une police qui inclut les glyphes requis (par ex., « Arial Unicode MS ») |
| Le texte de droite à gauche s'affiche de gauche à droite | Niveau Bidi non défini | Appelez `glyphs.setBidiLevel(1);` |
| Fichier non enregistré | Chemin `dataDir` invalide ou permissions d'écriture manquantes | Assurez‑vous que le répertoire existe et que l'application a les droits d'écriture |

## Questions fréquemment posées
**Q : Puis‑je utiliser Aspose.Page pour Java avec d'autres langages de programmation ?**  
R : Aspose.Page est conçu spécifiquement pour Java, mais Aspose propose des bibliothèques équivalentes pour .NET, C++ et Python si vous avez besoin d'un support multi‑langage.

**Q : Une version d'essai gratuite est‑elle disponible ?**  
R : Oui, vous pouvez accéder à une version d'essai gratuite d'Aspose.Page [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver du support et des discussions communautaires ?**  
R : Consultez le [forum Aspose.Page](https://forum.aspose.com/c/page/39) pour obtenir de l'aide, des exemples et des astuces de dépannage.

**Q : Comment obtenir une licence temporaire pour les tests ?**  
R : Vous pouvez acquérir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Quels styles de police Aspose.Page prend‑il en charge ?**  
R : L'API prend en charge les styles Regular, Bold, Italic et BoldItalic pour toute police TrueType ou OpenType que vous chargez.

## Conclusion
Vous avez maintenant maîtrisé **how to add Unicode** du texte dans un document Java PostScript (XPS) en utilisant Aspose.Page. Cette capacité ouvre la voie à des rapports multilingues, des factures internationalisées, et tout scénario nécessitant des caractères non‑ASCII. N'hésitez pas à explorer des fonctionnalités supplémentaires comme la rotation du texte, les chemins de découpe, ou l'intégration de polices personnalisées — les détails sont disponibles dans la [documentation](https://reference.aspose.com/page/java/) officielle.

---

**Dernière mise à jour :** 2026-05-20  
**Testé avec :** Aspose.Page for Java 23.12 (latest at time of writing)  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment ajouter du texte dans PostScript avec Aspose.Page pour Java](/page/java/postscript-text-manipulation/)
- [Définir la couleur du texte Java avec Aspose.Page – Guide de manipulation de texte](/page/java/postscript-text-manipulation/add-text/)
- [Ajouter des pages PostScript Java – Un guide fluide avec Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}