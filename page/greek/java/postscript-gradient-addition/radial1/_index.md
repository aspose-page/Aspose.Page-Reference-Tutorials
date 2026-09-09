---
date: 2026-09-09
description: Μάθετε πώς να δημιουργήσετε radial gradient σε Java PostScript χρησιμοποιώντας
  Aspose.Page. Αυτός ο οδηγός βήμα‑βήμα σας δείχνει πώς να προσθέσετε ένα color stops
  gradient, να ορίσετε radii και να δημιουργήσετε ένα PS file γρήγορα.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Κατακτώντας radial gradients σε Java
og_description: Μάθετε πώς να δημιουργήσετε radial gradient σε Java PostScript χρησιμοποιώντας
  Aspose.Page. Αυτός ο οδηγός εξηγεί πώς να προσθέσετε color stops gradient, να ορίσετε
  radii και να δημιουργήσετε ένα PS file σε λίγα λεπτά.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Πώς να δημιουργήσετε radial gradient σε Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Πώς να δημιουργήσετε radial gradient σε Java PostScript
url: /el/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε κυκλική διαβάθμιση σε Java PostScript με Aspose.Page

## Εισαγωγή
Αν χρειάζεστε **να δημιουργήσετε μια κυκλική διαβάθμιση** μέσα σε ένα αρχείο PostScript, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε βήμα-βήμα όλες τις απαιτούμενες ενέργειες για να δημιουργήσετε ένα έγγραφο PostScript που περιέχει μια ομαλή κυκλική διαβάθμιση, χρησιμοποιώντας **Aspose.Page for Java**. Στο τέλος θα κατανοήσετε το API, θα δείτε ένα πλήρες εκτελέσιμο παράδειγμα και θα γνωρίζετε πώς να ρυθμίσετε τα χρώματα, τις θέσεις και τις ακτίνες για οποιοδήποτε σενάριο σχεδίασης.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί κυκλικές διαβαθμίσεις σε PostScript;** Aspose.Page for Java.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για ένα βασικό παράδειγμα.  
- **Χρειάζομαι άδεια για να εκτελέσω τον κώδικα;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια έκδοση της Java υποστηρίζεται;** Java 8 ή νεότερη.  
- **Μπορώ να αλλάξω το σχήμα της διαβάθμισης;** Ναι – προσαρμόστε την ακτίνα και το κεντρικό σημείο στον κατασκευαστή `RadialGradientPaint`.

## Πώς να δημιουργήσετε κυκλική διαβάθμιση σε Java
Φορτώστε το έργο Java, εισάγετε τις απαιτούμενες κλάσεις και ακολουθήστε τον οδηγό βήμα-βήμα παρακάτω. Η κύρια λύση είναι ότι δημιουργείτε ένα αντικείμενο `RadialGradientPaint` με τα χρώματα-σταθμούς σας και στη συνέχεια το εφαρμόζετε σε ένα ορθογώνιο που σχεδιάζεται σε ένα `PsDocument`. Αυτή η προσέγγιση δύο αντικειμένων διαχειρίζεται όλες τις χαμηλού επιπέδου εντολές PostScript για εσάς.

## Τι είναι μια κυκλική διαβάθμιση;
`RadialGradientPaint` είναι μια κλάση Java AWT που ορίζει μια κυκλική μετάβαση χρώματος από ένα κεντρικό σημείο προς τα έξω. Δημιουργεί ένα ομαλό μίγμα πολλαπλών χρωματικών σταθμών, καθιστώντας το ιδανικό για φώτα spot, ήπιες παρασκήνιες ή οποιοδήποτε εφέ όπου τα χρώματα ακτινοβολούν από ένα σημείο εστίασης.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για κυκλικές διαβαθμίσεις;
Το Aspose.Page σας παρέχει πλήρη προγραμματιστικό έλεγχο της εξόδου PostScript ενώ διαχειρίζεται τις πολύπλοκες λεπτομέρειες της χαμηλού επιπέδου σύνταξης PS. Υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου**, μπορεί να αποδώσει έγγραφα με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, και λειτουργεί σε οποιοδήποτε λειτουργικό σύστημα που υποστηρίζει Java 8+. Αυτή η μετρήσιμη δυνατότητα το καθιστά αξιόπιστη επιλογή για δημιουργία γραφικών επιχειρησιακού επιπέδου.

## Προαπαιτούμενα
- **Java Development Kit (JDK) 8+** – επαληθεύστε με `java -version`.  
- **Aspose.Page for Java** – κατεβάστε το τελευταίο JAR από την επίσημη [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE της επιλογής σας** – Eclipse, IntelliJ IDEA ή VS Code με επεκτάσεις Java.  
- **Φάκελος με δικαιώματα εγγραφής** – όπου θα αποθηκευτεί το παραγόμενο αρχείο `.ps`.

## Εισαγωγή πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Το πακέτο `java.awt` παρέχει τα αντικείμενα χρωματικής διαβάθμισης, ενώ το `com.aspose.eps` περιέχει τις κλάσεις διαχείρισης εγγράφων PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Οδηγός βήμα-βήμα

### Βήμα 1: δημιουργήστε ένα ορθογώνιο και ανοίξτε ένα έγγραφο PS
`PsDocument` είναι η κλάση του Aspose.Page που αντιπροσωπεύει ένα έγγραφο PostScript και παρέχει μεθόδους για σχεδίαση σχημάτων, κειμένου και εικόνων. Ξεκινάμε δημιουργώντας ένα ρεύμα εξόδου, ρυθμίζοντας το μέγεθος σελίδας (A4 εξ ορισμού) και ορίζοντας ένα ορθογώνιο που θα φιλοξενήσει τη διαβάθμιση.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Συμβουλή:** Προσαρμόστε τις συντεταγμένες του ορθογωνίου (`200, 100, 200, 200`) για να τοποθετήσετε τη διαβάθμιση οπουδήποτε στη σελίδα.

### Βήμα 2: ορίστε χρώματα και κλάσματα
Μια κυκλική διαβάθμιση δημιουργείται από *χρωματικούς σταθμούς* (τα χρώματα) και *κλάσματα* (τις σχετικές θέσεις αυτών των σταθμών). Εδώ δημιουργούμε έναν πίνακα με έξι χρώματα και τα αντίστοιχα κλάσματά τους.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Γιατί είναι σημαντικό:** Με την τροποποίηση των `fractions` ελέγχετε πόσο γρήγορα μεταβαίνουν τα χρώματα, επιτρέποντας ήπια ή δραματικά εφέ.

### Βήμα 3: δημιουργήστε χρώμα κυκλικής διαβάθμισης
`RadialGradientPaint` είναι η βασική κλάση που περιγράφει μια κυκλική χρωματική διαβάθμιση, συμπεριλαμβανομένου του κεντρικού σημείου, της ακτίνας, του σημείου εστίασης, των κλασμάτων, των χρωμάτων, της μεθόδου κύκλου και του χρωματικού χώρου. Τώρα δημιουργούμε το αντικείμενο `RadialGradientPaint` χρησιμοποιώντας τους πίνακες που ορίστηκαν παραπάνω.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Σημείωση:** Το `transform` μπορεί να είναι `null` αν δεν χρειάζεστε πρόσθετη κλιμάκωση ή περιστροφή. Μη διστάσετε να πειραματιστείτε με το `AffineTransform` για λοξές διαβαθμίσεις.

### Βήμα 4: ορίστε το χρώμα και γεμίστε το ορθογώνιο
Με το χρώμα έτοιμο, ενημερώνουμε το `PsDocument` να το χρησιμοποιήσει και στη συνέχεια γεμίζουμε το ορθογώνιο που ορίσαμε νωρίτερα.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Σε αυτό το σημείο η σελίδα PostScript περιέχει ένα ορθογώνιο γεμάτο ομαλά με την κυκλική διαβάθμιση που διαμορφώσαμε.

### Βήμα 5: κλείστε και αποθηκεύστε το έγγραφο
Τέλος, κλείστε την τρέχουσα σελίδα και γράψτε το αρχείο στο δίσκο.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ανοίξτε το `RadialGradient1_outPS.ps` σε οποιονδήποτε προβολέα PostScript (π.χ., Ghostscript) και θα δείτε τη διαβάθμιση να αποδίδεται ακριβώς όπως ορίστηκε.

## Συχνά προβλήματα & λύσεις
| Σύμπτωμα | Πιθανή αιτία | Διόρθωση |
|---------|--------------|----------|
| Η διαβάθμιση εμφανίζεται ως στερεό χρώμα | `fractions` array δεν ξεκινά στο `0.0f` ή δεν τελειώνει στο `1.0f` | Βεβαιωθείτε ότι το πρώτο κλάσμα είναι `0.0f` και το τελευταίο είναι `1.0f`. |
| Τα χρώματα φαίνονται ξεθωριασμένα | Χρήση του λανθασμένου `ColorSpaceType` | Αλλάξτε σε `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` για πιο ζωντανή έξοδο. |
| Δεν δημιουργείται αρχείο εξόδου | Η διαδρομή του `FileOutputStream` είναι άκυρη ή δεν είναι εγγράψιμη | Επαληθεύστε ότι το `dataDir` υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής. |

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java σε εμπορικά έργα;**  
A: Ναι. Απαιτείται εμπορική άδεια για χρήση σε παραγωγή. Μπορείτε να αγοράσετε μία από τη [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Πού μπορώ να βρω την επίσημη τεκμηρίωση API;**  
A: Η πλήρης τεκμηρίωση είναι διαθέσιμη στο [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Διατίθεται δωρεάν δοκιμή για δοκιμές;**  
A: Απόλυτα. Κατεβάστε μια δοκιμαστική έκδοση από τη [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για αξιολόγηση;**  
A: Μπορείτε να ζητήσετε προσωρινή άδεια από τη [temporary license request page](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να βρω υποστήριξη από την κοινότητα;**  
A: Εγγραφείτε στο φόρουμ της κοινότητας Aspose.Page στο [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να δημιουργήσετε κυκλική διαβάθμιση** σε ένα έγγραφο Java PostScript χρησιμοποιώντας το Aspose.Page. Με την προσαρμογή του μεγέθους του ορθογωνίου, των χρωματικών σταθμών και της ακτίνας της διαβάθμισης, μπορείτε να δημιουργήσετε αμέτρητα οπτικά εφέ—από ήπιες γεμίσεις φόντου μέχρι έντονα γραφικά φωτισμού. Μη διστάσετε να πειραματιστείτε με διαφορετικές τιμές `AffineTransform` για περιστροφή ή κλίση της διαβάθμισης, και να συνδυάσετε αυτήν την τεχνική με κείμενο και εικόνες για πιο πλούσιες εξόδους PDF ή EPS.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Γέμισμα Σχήματος με Διαβάθμιση: Παράδειγμα Κυκλικής Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Δημιουργία Διαβάθμισης PostScript σε Java – Προσθήκη Κατακόρυφης Διαβάθμισης](/page/java/postscript-gradient-addition/vertical/)
- [Μάθημα Διαφάνειας Aspose.Page – Προσθήκη Διαφάνειας σε Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}