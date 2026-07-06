---
date: 2026-02-13
description: Μάθετε πώς να γεμίζετε σχήμα με διαβάθμιση και να σχεδιάζετε κύκλο με
  διαβάθμιση σε Java PostScript χρησιμοποιώντας το Aspose.Page. Οδηγός βήμα‑προς‑βήμα
  με κώδικα και συμβουλές.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Γέμισμα σχήματος με διαβάθμιση: Παράδειγμα ακτινικού Java PostScript'
url: /el/java/postscript-gradient-addition/radial2/
weight: 13
---

.

Now ensure we keep all markdown formatting.

Let's construct final output.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Γέμισμα Σχήματος με Διαβάθμιση: Παράδειγμα Ακτινικού Gradient σε Java PostScript

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε πώς να **fill shape with gradient** δημιουργώντας ένα παράδειγμα ακτινικού gradient για ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page for Java. Θα περάσουμε από κάθε βήμα — από τη ρύθμιση του έργου μέχρι την απόδοση ενός κύκλου γεμάτου με ομαλό ακτινικό gradient — ώστε να μπορείτε να προσθέσετε εντυπωσιακά γραφικά στις Java εφαρμογές σας αμέσως.

## Γρήγορες Απαντήσεις
- **Τι δημιουργεί αυτό το tutorial;** A PostScript file (`.ps`) containing a circle filled with a radial gradient.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java (latest version).  
- **Πόσο διαρκεί η υλοποίηση;** Approximately 10‑15 minutes for a working example.  
- **Χρειάζομαι άδεια;** A temporary or full license is required for production use; a free trial works for development.  
- **Μπορώ να επαναχρησιμοποιήσω τον κώδικα για PDF ή SVG;** Yes—Aspose.Page supports multiple output formats with minimal changes.

## Πώς να Γεμίσετε Σχήμα με Διαβάθμιση σε PostScript
Πριν βυθιστούμε στον κώδικα, ας διευκρινίσουμε γιατί το “fill shape with gradient” είναι σημαντικό. Η χρήση gradients δίνει στα γραφικά σας μια επαγγελματική, τρισδιάστατη αίσθηση χωρίς την ανάγκη για raster εικόνες. Με το Aspose.Page μπορείτε να εφαρμόσετε την ίδια λογική gradient σε οποιοδήποτε διανυσματικό σχήμα — κύκλους, ορθογώνια ή προσαρμοσμένες διαδρομές — σε όλες τις υποστηριζόμενες μορφές εξόδου (PostScript, PDF, SVG).

## Τι Είναι το Ακτινικό Gradient;
Ένα ακτινικό gradient μεταβάλλει τα χρώματα από ένα κεντρικό σημείο προς τα έξω, δημιουργώντας μια ομαλή, κυκλική ανάμειξη. Είναι ιδανικό για επισημάνσεις, φόντο κουμπιών ή οποιοδήποτε οπτικό στοιχείο που χρειάζεται φυσικό εφέ “glow”.

## Γιατί να Χρησιμοποιήσετε το Aspose.Page για Ακτινικά Gradients;
- **Device‑independent rendering** – λειτουργεί το ίδιο σε PostScript, PDF, SVG και άλλα.  
- **Full Java integration** – χωρίς native κώδικα, μόνο απλά Java APIs.  
- **High‑quality output** – υποστηρίζει anti‑aliasing και έλεγχο χρωματικού χώρου.

## Προαπαιτούμενα
- Βασική εξοικείωση με προγραμματισμό Java.  
- JDK 8 ή νεότερο εγκατεστημένο στο σύστημα σας.  
- Aspose.Page for Java library (λήψη από την [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Εισαγωγή Πακέτων
Πρώτα, εισάγουμε τις κλάσεις που θα χρειαστούμε. Αυτές περιλαμβάνουν τυπικούς τύπους γραφικών AWT και το API του Aspose.Page.

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

## Βήμα 1: Ρύθμιση Καταλόγου Εγγράφου
Ορίστε το φάκελο όπου θα αποθηκευτεί το παραγόμενο αρχείο PostScript. Αντικαταστήστε το placeholder με μια πραγματική διαδρομή στο σύστημά σας.

```java
String dataDir = "Your Document Directory";
```

## Βήμα 2: Δημιουργία Ροής Εξόδου
Ανοίξτε ένα `FileOutputStream` που δείχνει στο στόχο `.ps` αρχείο. Αυτή η ροή τροφοδοτεί τα δυαδικά δεδομένα που δημιουργεί το Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Βήμα 3: Δημιουργία Επιλογών Αποθήκευσης
Δημιουργήστε ένα αντικείμενο `PsSaveOptions`. Μπορείτε να προσαρμόσετε το μέγεθος σελίδας, τη συμπίεση κ.λπ., αλλά οι προεπιλογές είναι επαρκείς για αυτό το παράδειγμα.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Βήμα 4: Δημιουργία Εγγράφου PS
Δημιουργήστε το αντικείμενο `PsDocument`, περνώντας τη ροή εξόδου και τις επιλογές αποθήκευσης. Η σημαία `false` λέει στο Aspose.Page να μην ανοίξει αυτόματα μια σελίδα (θα το κάνουμε χειροκίνητα).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Βήμα 5: Δημιουργία Κύκλου
Θα σχεδιάσουμε έναν κύκλο χρησιμοποιώντας το `Ellipse2D.Float`. Οι παράμετροι είναι `(x, y, width, height)`. Ορίζοντας το πλάτος = ύψος δημιουργείται ένας τέλειος κύκλος.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Πώς να Σχεδιάσετε Κύκλο με Gradient
Τώρα που έχουμε σχήμα, το επόμενο βήμα είναι να **draw circle with gradient**. Εφαρμόζοντας ένα `RadialGradientPaint` στον κύκλο, η λειτουργία γεμίσματος θα χρησιμοποιήσει αυτόματα το gradient που ορίζουμε.

## Βήμα 6: Ορισμός Χρωμάτων Gradient
Προετοιμάστε δύο πίνακες: έναν για τα χρώματα που θα εμφανιστούν στο gradient και έναν για τις αντίστοιχες κλασματικές θέσεις (0 = κέντρο, 1 = άκρη).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Βήμα 7: Δημιουργία AffineTransform
Το `AffineTransform` κλιμακώνει και μετατοπίζει το gradient ώστε να ταιριάζει στον κύκλο μας. Ο πίνακας `(scaleX, 0, 0, scaleY, translateX, translateY)` κάνει τη δουλειά.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Βήμα 8: Δημιουργία Radial Gradient Paint
Τώρα δημιουργούμε το αντικείμενο `RadialGradientPaint`. Παίρνει το κεντρικό σημείο, την ακτίνα, το σημείο εστίασης, τις κλασματικές τιμές, τον πίνακα χρωμάτων, τη μέθοδο κύκλου, το χρωματικό χώρο και το μετασχηματισμό που ορίσαμε.

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

## Βήμα 9: Ορισμός Paint και Γέμισμα Κύκλου
Εφαρμόστε το gradient paint στο έγγραφο και γεμίστε τον προηγουμένως ορισμένο κύκλο. Αυτό αποτελεί τον πυρήνα του **radial gradient example** και δείχνει πώς να **fill shape with gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Βήμα 10: Κλείσιμο Σελίδας και Αποθήκευση Εγγράφου
Ολοκληρώστε τη σελίδα, γράψτε το περιεχόμενο στο δίσκο και κλείστε τη ροή. Το αρχείο PostScript είναι έτοιμο για προβολή με οποιονδήποτε PS viewer.

```java
document.closePage();
document.save();
```

Συγχαρητήρια! Δημιουργήσατε επιτυχώς ένα παράδειγμα ακτινικού gradient σε Java PostScript χρησιμοποιώντας το Aspose.Page. Τώρα διαθέτετε ένα επαναχρησιμοποιήσιμο μοτίβο για **fill shape with gradient**, το οποίο μπορεί να προσαρμοστεί σε άλλα σχήματα και μορφές εξόδου.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|---------|----------|
| **FileNotFoundException** κατά το άνοιγμα της ροής εξόδου | Επαληθεύστε ότι το `dataDir` δείχνει σε έναν υπάρχοντα φάκελο και έχετε δικαιώματα εγγραφής. |
| Το gradient φαίνεται επίπεδο ή λείπει | Βεβαιωθείτε ότι ο πίνακας `fractions` ταιριάζει με το μήκος του πίνακα `colors` και ότι το `AffineTransform` κλιμακώνεται σωστά. |
| Τα χρώματα εμφανίζονται αντιστροφή | Αλλάξτε τη σειρά των χρωμάτων στον πίνακα `colors` ή προσαρμόστε τις συντεταγμένες του σημείου `focus`. |

## Συχνές Ερωτήσεις

**Ε: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page for Java;**  
Α: Η πλήρης αναφορά API είναι διαθέσιμη [εδώ](https://reference.aspose.com/page/java/).

**Ε: Πώς μπορώ να κατεβάσω το Aspose.Page for Java;**  
Α: Κατεβάστε το τελευταίο JAR από τη [σελίδα releases](https://releases.aspose.com/page/java/).

**Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
Α: Ναι — κατεβάστε μια δοκιμαστική έκδοση [εδώ](https://releases.aspose.com/).

**Ε: Μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
Α: Φυσικά, ζητήστε μία από τη [σελίδα προσωρινής άδειας](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω υποστήριξη από την κοινότητα;**  
Α: Συμμετέχετε στη συζήτηση στο [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39).

## Συμπέρασμα
Σε αυτόν τον οδηγό κατασκευάσαμε ένα πλήρες **radial gradient example** για ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page for Java. Ακολουθώντας τα βήματα, έχετε τώρα ένα επαναχρησιμοποιήσιμο μοτίβο για **fill shape with gradient**, το οποίο μπορείτε να προσαρμόσετε σε PDF, SVG ή οποιαδήποτε άλλη μορφή υποστηρίζεται από το Aspose.Page. Πειραματιστείτε με διαφορετικά χρώματα, ακτίνες και σχήματα για να εμπλουτίσετε τα Java γραφικά σας.

---

**Last Updated:** 2026-02-13  
**Δοκιμή με:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}