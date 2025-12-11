---
date: 2025-12-07
description: Μάθετε πώς να προσθέσετε οριζόντια διαβάθμιση χρώματος σε Java PostScript
  χρησιμοποιώντας το Linear Gradient Paint Java με το Aspose.Page για Java.
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Προσθήκη διαβάθμισης σε Java PostScript χρησιμοποιώντας Linear Gradient Paint
  Java
url: /el/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Διαβάθμισης σε Java PostScript χρησιμοποιώντας Linear Gradient Paint Java

## Εισαγωγή
Σε αυτό το ολοκληρωμένο tutorial θα ανακαλύψετε πώς να δημιουργήσετε μια όμορφη οριζόντια διαβάθμιση σε ένα έγγραφο PostScript αξιοποιώντας **Linear Gradient Paint Java**. Το Aspose.Page for Java κάνει εύκολη τη δουλειά με PostScript, PDF και άλλες διανυσματικές μορφές, και η κλάση `LinearGradientPaint` σας παρέχει λεπτομερή έλεγχο των μεταβάσεων χρωμάτων. Στο τέλος αυτού του οδηγού, θα μπορείτε να αποδίδετε διαβάθμιση σε σχήματα **και** κείμενο, δίνοντας στα έγγραφά σας μια επαγγελματική, εντυπωσιακή εμφάνιση.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java (supports Linear Gradient Paint Java).  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για μια βασική διαβάθμιση.  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια για χρήση σε παραγωγή.  
- **Ποια έκδοση JDK λειτουργεί;** Java 8 ή νεότερη.  
- **Μπορώ να χρησιμοποιήσω τη διαβάθμιση και σε σχήματα και σε κείμενο;** Ναι – μπορείτε να γεμίσετε σχήματα και να σχεδιάσετε ή να γεμίσετε κείμενο με την ίδια διαβάθμιση.

## Προαπαιτούμενα
Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε τα παρακάτω:

- Java Development Kit (JDK) εγκατεστημένο στο μηχάνημά σας.  
- Aspose.Page for Java library. Μπορείτε να το κατεβάσετε από την [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Εισαγωγή Πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο Java σας. Αυτές οι εισαγωγές σας δίνουν πρόσβαση σε primitives γραφικών, διαχείριση διαβάθμισης και το API του Aspose.Page.

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

## Βήμα 1: Δημιουργία Ορθογωνίου
Πρώτα, ρυθμίστε το ρεύμα εξόδου, το έγγραφο και ένα ορθογώνιο που θα φιλοξενήσει τη διαβάθμιση.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Βήμα 2: Δημιουργία Οριζόντιας Linear Gradient Paint
Εδώ δημιουργούμε το αντικείμενο **Linear Gradient Paint Java** που ορίζει μια οριζόντια μετάβαση χρώματος. Το `AffineTransform` κλιμακώνει τη διαβάθμιση ώστε να ταιριάζει με το πλάτος και το ύψος του ορθογωνίου.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Βήμα 3: Γέμισμα του Ορθογωνίου
Τώρα γεμίστε το ορθογώνιο με τη διαβάθμιση που μόλις ορίσαμε.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Βήμα 4: Γέμισμα Κειμένου με τη Διαβάθμιση
Μπορείτε επίσης να εφαρμόσετε την ίδια διαβάθμιση σε κείμενο, δημιουργώντας ένα εντυπωσιακό οπτικό αποτέλεσμα.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Βήμα 5: Σχεδίαση Κειμένου με τη Διαβάθμιση
Τέλος, περιγράψτε το κείμενο χρησιμοποιώντας τη διαβάθμιση ως χρώμα περιγράμματος.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί Συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| Η διαβάθμιση εμφανίζεται τεντωμένη | Λανθασμένη κλιμάκωση `AffineTransform` | Βεβαιωθείτε ότι το πλάτος και το ύψος του μετασχηματισμού ταιριάζουν με τις διαστάσεις του ορθογωνίου (200 × 100 στο παράδειγμα). |
| Τα χρώματα φαίνονται ξεθωριασμένα | Οι τιμές alpha είναι πολύ χαμηλές | Αυξήστε το στοιχείο alpha (την τέταρτη τιμή στο `new Color(r,g,b,alpha)`). |
| Το κείμενο δεν είναι ορατό | Το Paint δεν έχει οριστεί πριν το σχεδιασμό του κειμένου | Καλέστε `document.setPaint(paint)` **πριν** από οποιαδήποτε κλήση `fillAndStrokeText` ή `outlineText`. |

## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page for Java σε εμπορικά έργα;
Ναι, το Aspose.Page for Java μπορεί να χρησιμοποιηθεί σε εμπορικά έργα. Για λεπτομέρειες αδειοδότησης, επισκεφθείτε [Aspose.Purchase](https://purchase.aspose.com/buy).

### Υπάρχει διαθέσιμη δωρεάν δοκιμή;
Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Page for Java [εδώ](https://releases.aspose.com/).

### Πού μπορώ να βρω πρόσθετη τεκμηρίωση και υποστήριξη;
Επισκεφθείτε την [τεκμηρίωση Aspose.Page Java](https://reference.aspose.com/page/java/) για ολοκληρωμένους πόρους. Για υποστήριξη της κοινότητας, δείτε το [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια;
Μπορείτε να αποκτήσετε προσωρινή άδεια από το [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Ποιες είναι οι απαιτήσεις συστήματος για το Aspose.Page for Java;
Ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/page/java/) για λεπτομερείς απαιτήσεις συστήματος.

---

**Τελευταία ενημέρωση:** 2025-12-07  
**Δοκιμή με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}