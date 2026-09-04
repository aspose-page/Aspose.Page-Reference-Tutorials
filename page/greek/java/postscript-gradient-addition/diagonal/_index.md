---
date: 2026-09-04
description: Μάθετε πώς να προσθέσετε διαβάθμιση σε Java PostScript με το Aspose.Page
  Java, δημιουργώντας διαγώνιες μεταβάσεις χρώματος χρησιμοποιώντας το LinearGradientPaint
  για ζωντανά έγγραφα.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Πώς να προσθέσετε διαβάθμιση: διαγώνια διαβάθμιση σε Java PostScript χρησιμοποιώντας
  το Aspose.Page Java'
og_description: Μάθετε πώς να προσθέσετε διαβάθμιση σε Java PostScript χρησιμοποιώντας
  το Aspose.Page Java. Αυτός ο οδηγός σας δείχνει πώς να δημιουργήσετε μια διαγώνια
  διαβάθμιση με το LinearGradientPaint σε λίγα μόνο βήματα.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Πώς να προσθέσετε διαβάθμιση σε Java PostScript με το Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Πώς να προσθέσετε διαβάθμιση: διαγώνια διαβάθμιση σε Java PostScript χρησιμοποιώντας
  το Aspose.Page Java'
url: /el/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη διαγώνιας διαβάθμισης σε Java PostScript χρησιμοποιώντας το Aspose.Page Java

## Εισαγωγή
Αν θέλετε να εμπλουτίσετε ένα αρχείο PostScript με μια ομαλή διαγώνια μετάβαση χρώματος, το **Aspose.Page Java** το καθιστά απίστευτα εύκολο. Σε αυτό το tutorial θα μάθετε **πώς να προσθέτετε διαβάθμιση** βήμα‑βήμα, χρησιμοποιώντας την κλάση `LinearGradientPaint` από το Java 2D. Στο τέλος θα έχετε ένα έτοιμο κομμάτι κώδικα που δημιουργεί ένα έγγραφο PostScript με μια ζωντανή διαγώνια διαβάθμιση, και θα καταλάβετε γιατί αυτή η προσέγγιση είναι πιο συντηρήσιμη από το χειροκίνητο κωδικοποίηση ακατέργαστων εντολών PostScript.

## Πώς να προσθέσετε διαβάθμιση σε Java PostScript
Η προσθήκη μιας διαβάθμισης μπορεί να ακούγεται σαν εργασία μόνο γραφικών, αλλά με το Aspose.Page έχετε πλήρη έλεγχο πάνω στις υποκείμενες εντολές PostScript ενώ παραμένετε σε καθαρή Java. Αυτή η ενότητα εξηγεί γιατί η προσέγγιση λειτουργεί και τι κερδίζετε σε σύγκριση με το χειροκίνητο κωδικοποίηση ακατέργαστου PostScript.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java.  
- **Ποια κλάση δημιουργεί τη διαβάθμιση;** `LinearGradientPaint`.  
- **Μπορώ να αλλάξω τα χρώματα;** Ναι – τροποποιήστε τον πίνακα `Color[]`.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια· είναι διαθέσιμη δωρεάν δοκιμή.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10 λεπτά για μια βασική διαβάθμιση.

## Τι είναι το Aspose.Page Java;
Το Aspose.Page Java είναι ένα πλήρες API που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να μετατρέπουν αρχεία PostScript και PDF χωρίς εξωτερικό λογισμικό. Η βιβλιοθήκη υποστηρίζει **50+ μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί έγγραφα με **500+ σελίδες** διατηρώντας τη χρήση μνήμης κάτω από 100 MB.

## Γιατί να χρησιμοποιήσετε διαγώνια διαβάθμιση;
Μια διαγώνια διαβάθμιση προσθέτει βάθος και οπτικό ενδιαφέρον σε διαγράμματα, λογότυπα ή οποιοδήποτε γραφικό στοιχείο που χρειάζεται μοντέρνα εμφάνιση. Επειδή η διαβάθμιση τρέχει από τη μία γωνία στην αντίθετη, λειτουργεί καλά για φόντα, επιφάνειες κουμπιών και διακοσμητικά σχήματα, παρέχοντας επαγγελματικό αποτέλεσμα χωρίς επιπλέον εικόνες.

## Προαπαιτούμενα
- Java Development Kit (JDK) 8 ή νεότερο.  
- Ένα IDE όπως το Eclipse, IntelliJ IDEA ή VS Code.  
- **Aspose.Page for Java** library – download the latest version from the [official download page](https://releases.aspose.com/page/java/).

## Εισαγωγή πακέτων
Το πακέτο `java.awt` παρέχει τις βασικές κλάσεις γραφικών, ενώ το πακέτο `com.aspose.page` σας δίνει πρόσβαση σε API ειδικά για PostScript.  

Η κλάση `LinearGradientPaint` είναι η γέφυρα του Aspose.Page προς τη λειτουργικότητα διαβάθμισης του Java 2D.  
`AffineTransform` επιτρέπει την περιστροφή και κλιμάκωση της διαβάθμισης ώστε να ευθυγραμμίζεται διαγώνια.

```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Βήμα 1: δημιουργία ροής εξόδου για έγγραφο PostScript
Πρώτα, ορίστε το φάκελο όπου θα αποθηκευτεί το αρχείο και ανοίξτε ένα `FileOutputStream`. Αυτή η ροή λαμβάνει τα παραγόμενα δεδομένα PostScript.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Βήμα 2: δημιουργία επιλογών αποθήκευσης με μέγεθος A4
`PsSaveOptions` σας επιτρέπει να καθορίσετε το μέγεθος σελίδας, την ανάλυση και άλλες ρυθμίσεις εξόδου. Εδώ χρησιμοποιούμε το προεπιλεγμένο μέγεθος A4, που είναι 595 × 842 points στα 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Βήμα 3: δημιουργία νέου εγγράφου PS
Η κλάση `PsDocument` αντιπροσωπεύει ένα έγγραφο PostScript και παρέχει μεθόδους για δημιουργία σελίδων και σχεδίαση γραφικών.  
Δημιουργήστε ένα `PsDocument` χρησιμοποιώντας τη ροή εξόδου και τις επιλογές αποθήκευσης. Η σημαία `false` λέει στον κατασκευαστή να μην ανοίξει αυτόματα μια νέα σελίδα – θα το κάνουμε αργότερα.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Βήμα 4: δημιουργία ορθογωνίου
Ορίστε το ορθογώνιο που θα λάβει τη γεμιστική διαβάθμιση. Η θέση του ορθογωνίου (200, 100) και το μέγεθός του (200 × 100) επιλέγονται ώστε η διαβάθμιση να είναι σαφώς ορατή.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Βήμα 5: δημιουργία μετασχηματισμού διαβάθμισης
Ένα `AffineTransform` μας επιτρέπει να περιστρέψουμε, κλιμακώσουμε και μετατοπίσουμε τη διαβάθμιση ώστε να τρέχει διαγώνια μέσα από το ορθογώνιο. Τα μαθηματικά παρακάτω υπολογίζουν την υποτείνουσα και προσαρμόζουν το λόγο κλίμας αναλόγως.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Βήμα 6: δημιουργία διαγώνιας γραμμικής διαβάθμισης
`LinearGradientPaint` είναι η βασική κλάση που δημιουργεί τη μετάβαση χρώματος. Εκτείνεται από το πάνω‑αριστερό του ορθογωνίου μέχρι το κάτω‑δεξιό, χρησιμοποιώντας τον προηγουμένως ορισμένο μετασχηματισμό. Το `MultipleGradientPaint.CycleMethod.NO_CYCLE` εξασφαλίζει ότι η διαβάθμιση δεν επαναλαμβάνεται.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Βήμα 7: ορισμός χρώματος και γεμίσματος του ορθογωνίου
Εφαρμόστε τη διαβάθμιση στο έγγραφο και γεμίστε το σχήμα του ορθογωνίου. Αυτό το βήμα αποδίδει τη διαγώνια μετάβαση χρώματος στη σελίδα PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Βήμα 8: κλείσιμο τρέχουσας σελίδας και αποθήκευση του εγγράφου
Τέλος, κλείστε τη σελίδα, αδειάστε τη ροή και αποθηκεύστε το αρχείο. Το προκύπτον αρχείο `DiagonalGradient_outPS.ps` μπορεί να ανοιχτεί με οποιονδήποτε προβολέα PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Συχνά προβλήματα & συμβουλές
- **Η διαβάθμιση εμφανίζεται επίπεδη** – ελέγξτε ξανά τη γωνία περιστροφής· μια περιστροφή 45° δημιουργεί πραγματική διαγώνιο.  
- **Τα χρώματα φαίνονται ξεθωριασμένα** – βεβαιωθείτε ότι χρησιμοποιείτε το `MultipleGradientPaint.ColorSpaceType.SRGB` για ακριβή απόδοση χρώματος.  
- **Σφάλμα αρχείου δεν βρέθηκε** – επαληθεύστε ότι το `dataDir` δείχνει σε υπάρχον φάκελο και ότι η εφαρμογή έχει δικαιώματα εγγραφής.  
- **Μεγάλα έγγραφα προκαλούν αυξήσεις μνήμης** – χρησιμοποιήστε το `PsSaveOptions.setCompress(true)` για μείωση του αποτυπώματος μνήμης.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτή τη βιβλιοθήκη για άλλες γραφικές λειτουργίες σε Java;**  
A: Ναι, το Aspose.Page for Java παρέχει ένα πλήρες σύνολο primitives σχεδίασης, απόδοσης κειμένου και δυνατότητες διαχείρισης εικόνων.

**Q: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Page Java;**  
A: Απολύτως. Μπορείτε να κατεβάσετε μια πλήρως λειτουργική δοκιμή από τη [Aspose free trial page](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω τεκμηρίωση για το Aspose.Page Java;**  
A: Η επίσημη αναφορά API είναι διαθέσιμη [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Πώς μπορώ να αγοράσω άδεια για το Aspose.Page Java;**  
A: Οι άδειες μπορούν να αγοραστούν απευθείας από το [Aspose purchase portal](https://purchase.aspose.com/buy).

**Q: Χρειάζεστε βοήθεια ή έχετε ερωτήσεις;**  
A: Επισκεφθείτε το κοινότητα‑διαχειριζόμενο [Aspose.Page forum](https://forum.aspose.com/c/page/39) για βοήθεια από μηχανικούς της Aspose και συναδέλφους προγραμματιστές.

---

**Τελευταία ενημέρωση:** 2026-09-04  
**Δοκιμάστηκε με:** Aspose.Page for Java 24.12 (latest)  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Δημιουργία ακτινικής διαβάθμισης σε PostScript με Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Πώς να προσθέσετε διαβάθμιση σε Java PostScript με Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Δημιουργία διαβάθμισης PostScript σε Java – Προσθήκη κάθετης διαβάθμισης](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}