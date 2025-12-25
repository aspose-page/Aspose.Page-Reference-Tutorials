---
date: 2025-12-25
description: Apprenez comment ajouter un dégradé vertical en Java XPS avec Aspose.Page.
  Suivez ce guide étape par étape pour améliorer l'attrait visuel de votre document.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Comment ajouter un dégradé vertical dans Java XPS
url: /fr/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment ajouter un dégradé vertical dans Java XPS

## Introduction
Dans ce tutoriel, vous découvrirez **comment ajouter un dégradé vertical** aux documents XPS lorsque vous travaillez avec Java. L'application d'un dégradé vertical peut améliorer considérablement l'impact visuel de vos rapports, factures ou tout contenu imprimable. Nous parcourrons chaque étape, de la configuration du projet à l'enregistrement du fichier XPS final, en utilisant la puissante bibliothèque Aspose.Page for Java.

## Réponses rapides
- **Que fait un dégradé vertical ?** Il crée une transition de couleur fluide du haut vers le bas d'une forme.  
- **Quelle bibliothèque est requise ?** Aspose.Page for Java (téléchargeable depuis le site officiel).  
- **Ai-je besoin d'une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour la production.  
- **Cette solution est‑elle compatible avec Java 8+ ?** Oui, l'API prend en charge Java 8 et les versions ultérieures.  
- **Combien de temps prend l'implémentation ?** Généralement moins de 10 minutes une fois l'environnement configuré.

## Prérequis
Avant de plonger dans le code, assurez‑vous de disposer de ce qui suit :

- Un environnement de développement Java fonctionnel (JDK 8 ou plus récent).  
- Bibliothèque Aspose.Page for Java. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/page/java/).  
- Une compréhension de base des concepts de programmation Java.  

## Importer les packages
Commencez par importer les packages nécessaires pour votre projet Java. Assurez‑vous que la bibliothèque Aspose.Page for Java est ajoutée au classpath de votre projet.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Étape 1 : Initialiser le document
Commencez par créer un nouveau document XPS. Cet objet contiendra tous les éléments de dessin que vous ajouterez ultérieurement.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Étape 2 : Créer un chemin avec un dégradé vertical
Ensuite, définissez un chemin rectangulaire et appliquez un dégradé linéaire vertical. Les arrêts du dégradé déterminent les couleurs et leurs positions le long de l'axe vertical.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Étape 3 : Enregistrer le document
Enfin, écrivez le fichier XPS sur le disque. Le fichier résultant contiendra le rectangle rempli du dégradé vertical que vous avez défini.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Félicitations ! Vous avez appris avec succès **comment ajouter un dégradé vertical** à un document Java XPS en utilisant Aspose.Page.

## Pourquoi utiliser un dégradé vertical ?
- **Esthétique améliorée :** Les dégradés ajoutent de la profondeur et un aspect moderne aux formes statiques.  
- **Cohérence de la marque :** Harmonisez les couleurs d'entreprise de manière fluide sur les pages.  
- **Personnalisation facile :** Modifiez les couleurs ou les positions des arrêts sans redessiner les graphiques.

## Problèmes courants et dépannage
- **Dégradé non visible :** Vérifiez que les points de départ et d'arrivée du `LinearGradientBrush` sont correctement définis pour une orientation verticale.  
- **Fichier non enregistré :** Assurez‑vous que `dataDir` pointe vers un dossier accessible en écriture et que vous avez les permissions nécessaires.  
- **Bibliothèque introuvable :** Revérifiez que le JAR Aspose.Page est inclus dans le chemin de construction de votre projet.

## Questions fréquemment posées

**Q : Puis-je utiliser Aspose.Page for Java dans des projets commerciaux ?**  
A : Oui, Aspose.Page for Java est disponible pour une utilisation commerciale. Vous pouvez l'acheter [ici](https://purchase.aspose.com/buy).

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.Page for Java ?**  
A : Oui, vous pouvez accéder à un essai gratuit [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation d'Aspose.Page for Java ?**  
A : La documentation est disponible [ici](https://reference.aspose.com/page/java/).

**Q : Comment obtenir une licence temporaire pour Aspose.Page for Java ?**  
A : Obtenez une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

**Q : Besoin d'aide ou avez‑vous des questions ?**  
A : Visitez le Aspose.Page community [forum](https://forum.aspose.com/c/page/39).

---

**Dernière mise à jour :** 2025-12-25  
**Testé avec :** Aspose.Page for Java 24.12 (dernière version au moment de la rédaction)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}