---
date: 2025-12-11
description: Μάθετε πώς να δημιουργήσετε έλλειψη PostScript σε Java χρησιμοποιώντας
  το Aspose.Page. Αυτός ο οδηγός βήμα‑προς‑βήμα σας δείχνει πώς να γεμίσετε την έλλειψη
  με χρώμα και να σχεδιάσετε την έλλειψη χρησιμοποιώντας τη Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Πώς να δημιουργήσετε έλλειψη PostScript σε Java με το Aspose.Page
url: /el/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε έλλειψη PostScript σε Java με το Aspose.Page

## Εισαγωγή
Η δημιουργία μιας **PostScript έλλειψης** προγραμματιστικά σας δίνει λεπτομερή έλεγχο πάνω στα διανυσματικά γραφικά σε αναφορές, τιμολόγια ή οποιοδήποτε εκτυπώσιμο έγγραφο. Σε αυτό το σεμινάριο θα μάθετε πώς να **δημιουργήσετε σχήματα PostScript έλλειψης** χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page for Java, να γεμίσετε μια έλλειψη με χρώμα και να σχεδιάσετε το περίγραμμα μιας έλλειψης. Στο τέλος θα είστε έτοιμοι να ενσωματώσετε προσαρμοσμένα γραφικά απευθείας στην έξοδο PostScript.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη είναι η καλύτερη για σχεδίαση γραφικών PostScript σε Java;** Aspose.Page for Java.  
- **Μπορώ να γεμίσω μια έλλειψη με ένα στερεό χρώμα;** Ναι – χρησιμοποιήστε `document.setPaint(Color.YOUR_COLOR)` πριν από το `fill`.  
- **Πώς σχεδιάζω μόνο το περίγραμμα μιας έλλειψης;** Ορίστε το χρώμα (paint) και το στυλ γραμμής (stroke), στη συνέχεια καλέστε `document.draw(...)`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται εμπορική άδεια· διατίθεται προσωρινή άδεια για δοκιμές.  
- **Ποια έκδοση της Java υποστηρίζεται;** Οποιοδήποτε runtime Java 8+ λειτουργεί με την τρέχουσα έκδοση του Aspose.Page.

## Τι είναι μια PostScript έλλειψη;
Μια PostScript έλλειψη είναι ένα διανυσματικό σχήμα που ορίζεται από ένα περιβάλλον ορθογώνιο. Σε αντίθεση με τις ραστερ εικόνες, κλιμακώνεται χωρίς απώλεια ποιότητας, καθιστώντας την ιδανική για εκτύπωση υψηλής ανάλυσης και μετατροπή σε PDF.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για τη δημιουργία μιας PostScript έλλειψης;
- **Πλήρης έλεγχος** πάνω στα primitives σχεδίασης (γραμμές, καμπύλες, έλλειψεις).  
- **Διαπλατφορμικό** – λειτουργεί σε Windows, Linux και macOS.  
- **Χωρίς εξωτερικές εξαρτήσεις** – καθαρό Java API, χωρίς εγγενή κώδικα.  
- **Εύκολη ενσωμάτωση** με υπάρχουσες εφαρμογές Java και εργαλεία κατασκευής.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. Ένα λειτουργικό περιβάλλον ανάπτυξης Java (JDK 8 ή νεότερο).  
2. Τη βιβλιοθήκη Aspose.Page for Java προστιθέμενη στο έργο σας. Μπορείτε να την κατεβάσετε **[εδώ](https://releases.aspose.com/page/java/)**.

## Εισαγωγή Πακέτων
Στο αρχείο πηγαίου κώδικα Java, εισάγετε τις κλάσεις που απαιτούνται για τη σχεδίαση και αποθήκευση περιεχομένου PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ρύθμιση του εγγράφου PostScript
Δημιουργήστε ένα ρεύμα εξόδου, διαμορφώστε το μέγεθος της σελίδας και δημιουργήστε ένα αντικείμενο `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Βήμα 2: Γέμισμα έλλειψης με χρώμα
Ορίστε το χρώμα (paint) στο επιθυμητό χρώμα γεμίσματος και καλέστε `fill` με ένα αντικείμενο `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Βήμα 3: Περίγραμμα έλλειψης με στυλ γραμμής
Αλλάξτε το χρώμα (paint) στο χρώμα του περιγράμματος, ορίστε ένα `BasicStroke` για το πάχος της γραμμής και σχεδιάστε το περίγραμμα της έλλειψης.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Βήμα 4: Κλείσιμο και αποθήκευση του εγγράφου
Ολοκληρώστε τη σελίδα και γράψτε το αρχείο PostScript στο δίσκο.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Τώρα έχετε ένα αρχείο PostScript που περιέχει δύο έλλειψεις — μία γεμισμένη με πορτοκαλί και μία άλλη με περίγραμμα σε κόκκινο. Μη διστάσετε να πειραματιστείτε με διαφορετικές συντεταγμένες, μεγέθη και χρώματα για να ταιριάξουν με τις ανάγκες του σχεδίου σας.

## Συνηθισμένα προβλήματα και αντιμετώπιση
- **Λανθασμένη διαδρομή αρχείου** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με έναν διαχωριστικό (`/` ή `\\`) κατάλληλο για το λειτουργικό σας σύστημα.  
- **Λείπει άδεια** – Χωρίς έγκυρη άδεια, η βιβλιοθήκη λειτουργεί σε λειτουργία αξιολόγησης και μπορεί να προσθέσει υδατογραφήματα.  
- **Το χρώμα δεν εφαρμόζεται** – Θυμηθείτε να ορίσετε `document.setPaint(...)` *πριν* από κάθε κλήση `fill` ή `draw`; η ρύθμιση του χρώματος δεν παραμένει αυτόματα μεταξύ διαφορετικών λειτουργιών.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες βιβλιοθήκες Java;**  
Α: Ναι, το Aspose.Page for Java έχει σχεδιαστεί ώστε να ενσωματώνεται άψογα με άλλες βιβλιοθήκες Java.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
Α: Αποκτήστε μια προσωρινή άδεια **[εδώ](https://purchase.aspose.com/temporary-license/)** για δοκιμαστικούς σκοπούς.

**Ε: Είναι το Aspose.Page κατάλληλο για εμπορικά έργα;**  
Α: Απόλυτα! Επισκεφθείτε **[εδώ](https://purchase.aspose.com/buy)** για να εξερευνήσετε τις επιλογές αδειοδότησης για εμπορική χρήση.

**Ε: Πού μπορώ να ζητήσω βοήθεια ή να συζητήσω ερωτήματα σχετικά με το Aspose.Page;**  
Α: Ενταχθείτε στην κοινότητα στο **[Φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39)** για συζητήσεις και βοήθεια.

**Ε: Υπάρχουν δωρεάν πόροι για να μάθω περισσότερα για το Aspose.Page for Java;**  
Α: Χρησιμοποιήστε τη **[δωρεάν δοκιμή](https://releases.aspose.com/)** και εξερευνήστε παραδείγματα στην τεκμηρίωση.

## Συμπέρασμα
Το Aspose.Page for Java καθιστά εύκολη τη **δημιουργία γραφικών PostScript έλλειψης**, είτε χρειάζεστε ένα απλό γεμάτο σχήμα είτε ένα σύνθετο περίγραμμα. Με τα παραπάνω βήματα μπορείτε γρήγορα να προσθέσετε γραφικά διανυσματικού επιπέδου σε οποιοδήποτε εκτυπώσιμο έγγραφο. Για πιο βαθιά εξερεύνηση — όπως ο συνδυασμός πολλαπλών σχημάτων, η εφαρμογή διαβαθμίσεων ή η μετατροπή σε PDF — ανατρέξτε στην επίσημη **[τεκμηρίωση](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία ενημέρωση:** 2025-12-11  
**Δοκιμή με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose