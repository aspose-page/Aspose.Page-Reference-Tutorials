---
date: 2026-09-09
description: Μάθετε πώς να δημιουργήσετε gradient σε Java PostScript και να προσθέσετε
  gradient σε σχήμα χρησιμοποιώντας Aspose.Page. Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα
  με κώδικα και συμβουλές.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient με Aspose.Page
og_description: Μάθετε πώς να δημιουργήσετε gradient σε Java PostScript και να προσθέσετε
  gradient σε σχήμα χρησιμοποιώντας Aspose.Page. Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα
  με κώδικα και συμβουλές.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Πώς να δημιουργήσετε gradient σε Java PostScript με radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Πώς να δημιουργήσετε gradient σε Java PostScript με radial fill
url: /el/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε διαβάθμιση σε Java PostScript με ακτινική γέμιση

## Εισαγωγή
Σε αυτό το σεμινάριο θα μάθετε **πώς να δημιουργήσετε διαβάθμιση** γραφικών σε ένα έγγραφο PostScript χρησιμοποιώντας Java και Aspose.Page. Θα περάσουμε από κάθε βήμα—από τη ρύθμιση του έργου μέχρι την απόδοση ενός κύκλου γεμάτου με ομαλή ακτινική διαβάθμιση—ώστε να μπορείτε **να προσθέσετε διαβάθμιση σε αντικείμενα σχήματος** αμέσως και να βελτιώσετε την οπτική ποιότητα των εφαρμογών Java.

## Γρήγορες απαντήσεις
- **Τι δημιουργεί αυτό το σεμινάριο;** Ένα αρχείο PostScript (`.ps`) που περιέχει έναν κύκλο γεμάτο με ακτινική διαβάθμιση.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java (τελευταία έκδοση).  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για ένα λειτουργικό παράδειγμα.  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια για παραγωγική χρήση· μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη.  
- **Μπορώ να επαναχρησιμοποιήσω τον κώδικα για PDF ή SVG;** Ναι—το Aspose.Page υποστηρίζει πολλαπλές μορφές εξόδου με ελάχιστες αλλαγές.

## Πώς να γεμίσετε σχήμα με διαβάθμιση σε PostScript
Μπορείτε να γεμίσετε ένα σχήμα με ακτινική διαβάθμιση σε PostScript δημιουργώντας ένα `PsDocument`, ορίζοντας ένα `RadialGradientPaint`, εφαρμόζοντάς το στο στόχο σχήμα και, τέλος, αποθηκεύοντας το έγγραφο. Αυτή η σύντομη ροή εργασίας σας επιτρέπει να παράγετε επαγγελματικής εμφάνισης διανυσματικά γραφικά χωρίς ραστερ εικόνες, και ο ίδιος κώδικας μπορεί να επαναχρησιμοποιηθεί για έξοδο PDF ή SVG. Η διαδικασία είναι απλή και λειτουργεί σταθερά σε όλες τις υποστηριζόμενες μορφές.

## Τι είναι η ακτινική διαβάθμιση;
Μια ακτινική διαβάθμιση μεταβάλλει τα χρώματα από το κεντρικό σημείο προς τα έξω, δημιουργώντας μια ομαλή, κυκλική ανάμειξη. Είναι ιδανική για επισημάνσεις, φόντο κουμπιών ή οποιοδήποτε οπτικό στοιχείο που χρειάζεται ένα φυσικό εφέ «λαμπρότητας». Με την αλλαγή των σημείων χρώματος και της ακτίνας, μπορείτε να προσομοιώσετε φωτισμό, βάθος και ιδιότητες υλικού σε καθαρή διανυσματική μορφή.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για ακτινικές διαβάθμιση;
Το Aspose.Page σας επιτρέπει να δημιουργείτε διανυσματικά γραφικά ανεξάρτητα από τη συσκευή με ένα μόνο Java API. Υποστηρίζει πάνω από 50 μορφές εισόδου και εξόδου—συμπεριλαμβανομένων των PostScript, PDF και SVG—διατηρώντας την ακρίβεια των χρωμάτων και το anti‑aliasing για εξαγωγή υψηλής ανάλυσης. Η βιβλιοθήκη παρέχει επίσης εύχρηστες κλάσεις διαβάθμισης, καθιστώντας τα σύνθετα οπτικά εφέ απλά στην υλοποίηση.

## Προαπαιτούμενα
- Βασική εξοικείωση με τον προγραμματισμό Java.  
- Εγκατεστημένο JDK 8 ή νεότερο στο σύστημα σας.  
- Βιβλιοθήκη Aspose.Page for Java (λήψη από την [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Εισαγωγή πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Αυτές περιλαμβάνουν τυπικούς τύπους γραφικών AWT και το API του Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Βήμα 1: ρύθμιση καταλόγου εγγράφου
Ορίστε το φάκελο όπου θα αποθηκευτεί το παραγόμενο αρχείο PostScript. Αντικαταστήστε το σύμβολο κράτησης θέσης με μια πραγματική διαδρομή στο σύστημά σας.

```java
String dataDir = "Your Document Directory";
```

## Βήμα 2: δημιουργία ροής εξόδου
Το FileOutputStream γράφει ακατέργαστα byte σε ένα αρχείο, επιτρέποντας την αποθήκευση δυαδικών δεδομένων. Το άνοιγμα ενός που στοχεύει σε αρχείο `.ps` επιτρέπει στο Aspose.Page να μεταφέρει τα παραγόμενα δεδομένα PostScript απευθείας στο δίσκο.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Βήμα 3: δημιουργία επιλογών αποθήκευσης
Το PsSaveOptions ρυθμίζει πώς αποθηκεύεται ένα αρχείο PostScript, συμπεριλαμβανομένου του μεγέθους σελίδας και της συμπίεσης. Μπορείτε να προσαρμόσετε αυτές τις ρυθμίσεις, αλλά οι προεπιλογές είναι κατάλληλες για αυτό το παράδειγμα.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Βήμα 4: δημιουργία εγγράφου ps
Το PsDocument αντιπροσωπεύει ένα έγγραφο PostScript στη μνήμη και παρέχει μεθόδους για προσθήκη σελίδων και γραφικών.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Βήμα 5: δημιουργία κύκλου
`Ellipse2D.Float` περιγράφει ένα σχήμα έλλειψης· όταν το πλάτος = ύψος γίνεται τέλειος κύκλος. Αυτό το αντικείμενο θα λειτουργήσει ως καμβάς για τη γέμιση με διαβάθμιση.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Πώς να σχεδιάσετε κύκλο με διαβάθμιση
Για να σχεδιάσετε έναν κύκλο με ακτινική διαβάθμιση, φορτώνετε ένα `RadialGradientPaint` στο γραφικό περιβάλλον και στη συνέχεια γεμίζετε την προηγουμένως ορισμένη έλλειψη. Αυτή η μοναδική λειτουργία βαφά το σχήμα με μια ομαλή μετάβαση χρώματος από το κέντρο προς τα έξω, δημιουργώντας ένα οπτικά ελκυστικό εφέ.

## Βήμα 6: ορισμός χρωμάτων διαβάθμισης
Προετοιμάστε δύο πίνακες: έναν για τα χρώματα που θα εμφανιστούν στη διαβάθμιση και έναν για τις αντίστοιχες κλασματικές θέσεις (0 = κέντρο, 1 = άκρη).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Βήμα 7: δημιουργία AffineTransform
Το AffineTransform είναι ένας πίνακας που μπορεί να μετατοπίζει, περιστρέφει, κλιμακώνει ή παραμορφώνει γραφικά αντικείμενα. Εδώ κλιμακώνει και μετατοπίζει τη διαβάθμιση ώστε να ταιριάζει ακριβώς μέσα στον κύκλο.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Βήμα 8: δημιουργία RadialGradientPaint
Το RadialGradientPaint δημιουργεί μια ακτινική χρωματική διαβάθμιση βασισμένη σε ένα κεντρικό σημείο, ακτίνα και σημεία χρώματος.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Βήμα 9: ορισμός χρώματος και γέμισμα κύκλου
Εφαρμόστε τη διαβάθμιση στο έγγραφο και γεμίστε τον προηγουμένως ορισμένο κύκλο. Αυτό αποτελεί τον πυρήνα του **παραδείγματος ακτινικής διαβάθμισης** και δείχνει πώς να **γεμίσετε σχήμα με διαβάθμιση**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Βήμα 10: κλείσιμο σελίδας και αποθήκευση εγγράφου
Ολοκληρώστε τη σελίδα, γράψτε το περιεχόμενο στο δίσκο και κλείστε τη ροή. Το αρχείο PostScript είναι τώρα έτοιμο για προβολή με οποιονδήποτε προβολέα PS.

```java
document.closePage();
document.save();
```

Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα παράδειγμα ακτινικής διαβάθμισης σε Java PostScript χρησιμοποιώντας το Aspose.Page. Διαθέτετε τώρα ένα επαναχρησιμοποιήσιμο πρότυπο για **γέμισμα σχήματος με διαβάθμιση** που μπορεί να προσαρμοστεί σε άλλα σχήματα και μορφές εξόδου.

## Συνηθισμένα προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **FileNotFoundException** κατά το άνοιγμα της ροής εξόδου | Επαληθεύστε ότι το `dataDir` δείχνει σε έναν υπάρχοντα φάκελο και ότι έχετε δικαιώματα εγγραφής. |
| Η διαβάθμιση φαίνεται επίπεδη ή λείπει | Βεβαιωθείτε ότι ο πίνακας `fractions` ταιριάζει με το μήκος του πίνακα `colors` και ότι το `AffineTransform` κλιμακώνεται σωστά. |
| Τα χρώματα εμφανίζονται αντιστροφικά | Αντιστρέψτε τη σειρά των χρωμάτων στον πίνακα `colors` ή προσαρμόστε τις συντεταγμένες του σημείου `focus`. |

## Συχνές ερωτήσεις

**Ε: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page for Java;**  
Α: Η πλήρης αναφορά API είναι διαθέσιμη στην [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).

**Ε: Πώς μπορώ να κατεβάσω το Aspose.Page for Java;**  
Α: Κατεβάστε το τελευταίο JAR από τη [σελίδα releases](https://releases.aspose.com/page/java/).

**Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
Α: Ναι—κατεβάστε μια δοκιμαστική έκδοση από τη [σελίδα δωρεάν δοκιμής Aspose](https://releases.aspose.com/).

**Ε: Μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
Α: Φυσικά, ζητήστε μία από τη [σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω υποστήριξη από την κοινότητα;**  
Α: Συμμετέχετε στη συζήτηση στο [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39).

## Συμπέρασμα
Σε αυτόν τον οδηγό δημιουργήσαμε ένα πλήρες **παράδειγμα ακτινικής διαβάθμισης** για ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page for Java. Ακολουθώντας τα βήματα, έχετε τώρα ένα επαναχρησιμοποιήσιμο πρότυπο για **γέμισμα σχήματος με διαβάθμιση**, το οποίο μπορείτε να προσαρμόσετε σε PDF, SVG ή οποιαδήποτε άλλη μορφή υποστηρίζεται από το Aspose.Page. Πειραματιστείτε με διαφορετικά χρώματα, ακτίνες και σχήματα για να εμπλουτίσετε τα Java γραφικά σας έργα.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Σχετικά Σεμινάρια

- [Δημιουργία διαβάθμισης PostScript σε Java – Προσθήκη κάθετης διαβάθμισης](/page/java/postscript-gradient-addition/vertical/)
- [Δημιουργία μοτίβου υφής σε PostScript με Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Aspose.Page Διαφάνεια Σεμινάριο – Προσθήκη διαφάνειας σε Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}