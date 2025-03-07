---
title: Προσθήκη οριζόντιας κλίσης στο Java PostScript
linktitle: Προσθήκη οριζόντιας κλίσης στο Java PostScript
second_title: Aspose.Page Java API
description: Μάθετε πώς μπορείτε να προσθέσετε μια οριζόντια κλίση στο Java PostScript με το Aspose.Page για Java. Δημιουργήστε οπτικά εντυπωσιακά έγγραφα χωρίς κόπο.
weight: 11
url: /el/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη οριζόντιας κλίσης στο Java PostScript

## Εισαγωγή
Καλώς ήρθατε σε αυτό το περιεκτικό σεμινάριο για την προσθήκη οριζόντιας διαβάθμισης στο Java PostScript χρησιμοποιώντας το Aspose.Page για Java. Το Aspose.Page είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να εργάζονται με PostScript και άλλες μορφές εγγράφων. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός εγγράφου PostScript με οριζόντια κλίση χρησιμοποιώντας παραδείγματα βήμα προς βήμα.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο μηχάνημά σας.
- Aspose.Page για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από το[Aspose.Page τεκμηρίωση Java](https://reference.aspose.com/page/java/).
## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο σας Java. Αυτά τα πακέτα είναι ζωτικής σημασίας για τη συνεργασία με το Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Βήμα 1: Δημιουργήστε ένα ορθογώνιο
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία ροής εξόδου για έγγραφο PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Δημιουργήστε επιλογές αποθήκευσης με μέγεθος Α4
PsSaveOptions options = new PsSaveOptions();
// Δημιουργήστε νέο έγγραφο PS με ανοιχτή τη σελίδα
PsDocument document = new PsDocument(outPsStream, options, false);
//Δημιουργήστε ένα ορθογώνιο
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Βήμα 2: Δημιουργήστε οριζόντια γραμμική κλίση
```java
// Δημιουργήστε οριζόντια γραμμική ντεγκραντέ βαφή. Τα στοιχεία κλίμακας στον μετασχηματισμό πρέπει να είναι ίσα με το πλάτος και το ύψος του ορθογωνίου.
// Τα στοιχεία μετάφρασης είναι μετατοπίσεις του ορθογωνίου.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Σετ βαφής
document.setPaint(paint);
```
## Βήμα 3: Γεμίστε το Ορθογώνιο
```java
// Συμπληρώστε το ορθογώνιο
document.fill(rectangle);
```
## Βήμα 4: Συμπληρώστε ένα κείμενο με το Gradient
```java
// Συμπληρώστε ένα κείμενο με τη διαβάθμιση
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Βήμα 5: Χαράξτε ένα κείμενο με το Gradient
```java
// Χαράξτε ένα κείμενο με τη διαβάθμιση
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## συμπέρασμα
Συγχαρητήρια! Προσθέσατε με επιτυχία μια οριζόντια διαβάθμιση στο Java PostScript χρησιμοποιώντας το Aspose.Page για Java. Αυτό το σεμινάριο σάς παρέχει έναν λεπτομερή οδηγό βήμα προς βήμα για να σας βοηθήσει να δημιουργήσετε οπτικά ελκυστικά έγγραφα PostScript.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page για Java σε εμπορικά έργα;
Ναι, το Aspose.Page για Java μπορεί να χρησιμοποιηθεί σε εμπορικά έργα. Για λεπτομέρειες αδειοδότησης, επισκεφθείτε[Aspose.Purchase](https://purchase.aspose.com/buy).
### Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να έχετε πρόσβαση σε μια δωρεάν δοκιμή του Aspose.Page για Java[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω πρόσθετη τεκμηρίωση και υποστήριξη;
 Επισκέψου το[Aspose.Page τεκμηρίωση Java](https://reference.aspose.com/page/java/) για ολοκληρωμένους πόρους. Για υποστήριξη της κοινότητας, ελέγξτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39).
### Πώς μπορώ να αποκτήσω προσωρινή άδεια;
 Μπορείτε να αποκτήσετε προσωρινή άδεια από[Aspose.Purchase](https://purchase.aspose.com/temporary-license/).
### Ποιες είναι οι απαιτήσεις συστήματος για το Aspose.Page για Java;
 Αναφέρομαι στο[τεκμηρίωση](https://reference.aspose.com/page/java/) για λεπτομερείς απαιτήσεις συστήματος.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
