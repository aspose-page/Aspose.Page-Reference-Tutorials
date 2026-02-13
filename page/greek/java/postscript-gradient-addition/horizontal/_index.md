---
date: 2026-02-13
description: Μάθετε πώς να προσθέσετε διαβάθμιση σε Java PostScript χρησιμοποιώντας
  το Linear Gradient Paint Java με το Aspose.Page για Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Πώς να προσθέσετε διαβάθμιση σε Java PostScript με γραμμική βαφή διαβάθμισης
url: /el/java/postscript-gradient-addition/horizontal/
weight: 11
---

quisites" list.

"Import Packages" etc.

Then placeholders.

"Step 1: Create a Rectangle" etc.

"Step 2: Create Horizontal Linear Gradient Paint" etc.

"Step 3: Fill the Rectangle" etc.

"Step 4: Fill a Text with the Gradient" etc.

"Step 5: Stroke a Text with the Gradient" etc.

"Common Issues and Solutions" table.

Translate rows.

"Frequently Asked Questions" etc.

Each Q/A.

"Last Updated:" etc.

Now produce final markdown with same shortcodes.

Let's craft Greek translation.

Be careful with bold formatting (**text**) keep same.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε διαβάθμιση σε Java PostScript με Linear Gradient Paint

## Εισαγωγή
Σε αυτό το ολοκληρωμένο tutorial θα ανακαλύψετε **πώς να προσθέσετε διαβάθμιση** σε ένα έγγραφο PostScript χρησιμοποιώντας Java. Θα περάσουμε βήμα-βήμα τη δημιουργία μιας όμορφης οριζόντιας διαβάθμισης αξιοποιώντας το **Linear Gradient Paint Java**, μια κλάση που σας δίνει έλεγχο pixel‑perfect στις μεταβάσεις χρωμάτων. Με το Aspose.Page for Java μπορείτε να αποδώσετε διαβαθμίσεις τόσο σε σχήματα **και** σε κείμενο, προσφέροντας στα έγγραφά σας ένα επαγγελματικό, εντυπωσιακό στυλ που ξεχωρίζει.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java (υποστηρίζει Linear Gradient Paint Java).  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για μια βασική διαβάθμιση.  
- **Χρειάζεται άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια για χρήση σε παραγωγή.  
- **Ποια έκδοση JDK λειτουργεί;** Java 8 ή νεότερη.  
- **Μπορώ να χρησιμοποιήσω τη διαβάθμιση και σε σχήματα και σε κείμενο;** Ναι – μπορείτε να γεμίσετε σχήματα και να γεμίσετε ή να περιγράψετε κείμενο με την ίδια διαβάθμιση.

## Τι είναι η Οριζόντια Διαβάθμιση και γιατί να τη χρησιμοποιήσετε;
Μια οριζόντια διαβάθμιση ενώνει ομαλά χρώματα από αριστερά προς δεξιά σε ένα σχήμα ή κείμενο. Είναι ιδανική για τη δημιουργία σύγχρονων στοιχείων UI, επισημασμένων τίτλων ή ήπιων εφέ φόντου σε αναφορές. Χρησιμοποιώντας το **Linear Gradient Paint Java** μπορείτε να ορίσετε ακριβώς τα αρχικά‑και τελικά‑χρώματα, τη διαφάνεια και την κλίμακα, ώστε το αποτέλεσμα να είναι καθαρό σε οποιαδήποτε συσκευή.

## Προαπαιτούμενα
Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε τα εξής:

- Εγκατεστημένο Java Development Kit (JDK) στον υπολογιστή σας.  
- Βιβλιοθήκη Aspose.Page for Java. Μπορείτε να τη κατεβάσετε από την [τεκμηρίωση Aspose.Page Java](https://reference.aspose.com/page/java/).

## Εισαγωγή Πακέτων
Ξεκινήστε εισάγοντας τα απαραίτητα πακέτα στο έργο Java. Αυτές οι εισαγωγές σας δίνουν πρόσβαση σε γραφικά primitives, διαχείριση διαβαθμίσεων και το API του Aspose.Page.

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
Πρώτα, ρυθμίστε το output stream, το έγγραφο και ένα ορθογώνιο που θα φιλοξενήσει τη διαβάθμιση.

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
Τώρα γεμίζουμε το ορθογώνιο με τη διαβάθμιση που ορίσαμε.

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

## Βήμα 5: Περιγράψτε Κείμενο με τη Διαβάθμιση
Τέλος, περιγράψτε το κείμενο χρησιμοποιώντας τη διαβάθμιση ως χρώμα περιγράμματος.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| Η διαβάθμιση εμφανίζεται τεντωμένη | Λανθασμένη κλίμακα `AffineTransform` | Βεβαιωθείτε ότι το πλάτος και το ύψος του μετασχηματισμού ταιριάζουν με τις διαστάσεις του ορθογωνίου (200 × 100 στο παράδειγμα). |
| Τα χρώματα φαίνονται ξεθωριασμένα | Οι τιμές alpha είναι πολύ χαμηλές | Αυξήστε το συστατικό alpha (η τέταρτη τιμή στο `new Color(r,g,b,alpha)`). |
| Το κείμενο δεν είναι ορατό | Δεν έχει οριστεί το Paint πριν το σχεδιαστεί το κείμενο | Καλέστε `document.setPaint(paint)` **πριν** οποιαδήποτε κλήση `fillAndStrokeText` ή `outlineText`. |

## Συχνές Ερωτήσεις
**Ε:** Μπορώ να χρησιμοποιήσω το Aspose.Page for Java σε εμπορικά έργα;  
**Α:** Ναι, το Aspose.Page for Java μπορεί να χρησιμοποιηθεί σε εμπορικά έργα. Για λεπτομέρειες άδειας, επισκεφθείτε το [Aspose.Purchase](https://purchase.aspose.com/buy).

**Ε:** Υπάρχει διαθέσιμη δωρεάν δοκιμή;  
**Α:** Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Page for Java [εδώ](https://releases.aspose.com/).

**Ε:** Πού μπορώ να βρω πρόσθετη τεκμηρίωση και υποστήριξη;  
**Α:** Επισκεφθείτε την [τεκμηρίωση Aspose.Page Java](https://reference.aspose.com/page/java/) για πλήρεις πόρους. Για υποστήριξη της κοινότητας, δείτε το [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39).

**Ε:** Πώς μπορώ να αποκτήσω προσωρινή άδεια;  
**Α:** Μπορείτε να λάβετε προσωρινή άδεια από το [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**Ε:** Ποιες είναι οι απαιτήσεις συστήματος για το Aspose.Page for Java;  
**Α:** Ανατρέξτε στην [τεκμηρίωση](https://reference.aspose.com/page/java/) για λεπτομερείς απαιτήσεις συστήματος.

---

**Τελευταία ενημέρωση:** 2026-02-13  
**Δοκιμάστηκε με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}