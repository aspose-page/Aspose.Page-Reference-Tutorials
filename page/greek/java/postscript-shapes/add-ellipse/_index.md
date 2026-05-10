---
date: 2026-02-18
description: Μάθετε πώς να ορίζετε το χρώμα βαφής και να δημιουργείτε μια έλλειψη
  PostScript σε Java χρησιμοποιώντας το Aspose.Page. Αυτός ο οδηγός δείχνει πώς να
  γεμίζετε μια έλλειψη στη Java, να σχεδιάζετε το περίγραμμα της έλλειψης και να ορίζετε
  το πάχος της γραμμής.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Ορισμός χρώματος ζωγραφικής για τη σχεδίαση έλλειψης PostScript σε Java
url: /el/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός χρώματος βαφής για σχεδίαση ελλειψοειδούς PostScript σε Java

## Εισαγωγή
Αν χρειάζεστε **να ορίσετε χρώμα βαφής** κατά τη σχεδίαση διανυσματικών γραφικών, η βιβλιοθήκη Aspose.Page for Java σας παρέχει πλήρη έλεγχο σε κάθε στίγμα και γέμισμα. Σε αυτό το tutorial θα ανακαλύψετε πώς να **ορίσετε χρώμα βαφής**, **fill ellipse Java**, και **draw ellipse outline** χρησιμοποιώντας μια απλή, βήμα‑βήμα προσέγγιση. Στο τέλος, θα μπορείτε να προσθέσετε υψηλής ποιότητας ελλειψοειδείς PostScript σε τιμολόγια, αναφορές ή οποιοδήποτε εκτυπώσιμο έγγραφο.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη είναι η καλύτερη για σχεδίαση γραφικών PostScript σε Java;** Aspose.Page for Java.  
- **Μπορώ να γεμίσω έναν ελλειψοειδή με ένα στερεό χρώμα;** Ναι – χρησιμοποιήστε `document.setPaint(Color.YOUR_COLOR)` πριν από το `fill`.  
- **Πώς μπορώ να σχεδιάσω μόνο το περίγραμμα ενός ελλειψοειδούς;** Ορίστε το χρώμα βαφής και το στίγμα, έπειτα καλέστε `document.draw(...)`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται εμπορική άδεια· διατίθεται προσωρινή άδεια για δοκιμές.  
- **Ποια έκδοση της Java υποστηρίζεται;** Οποιοδήποτε runtime Java 8+ λειτουργεί με την τρέχουσα έκδοση του Aspose.Page.

## Τι είναι ένας ελλειψοειδής PostScript;
Ένας ελλειψοειδής PostScript είναι ένα διανυσματικό σχήμα που ορίζεται από ένα ορθογώνιο περιβάλλον. Σε αντίθεση με τις raster εικόνες, κλιμακώνεται χωρίς απώλεια ποιότητας, καθιστώντας το ιδανικό για εκτυπώσεις υψηλής ανάλυσης και μετατροπή σε PDF.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για τη δημιουργία ελλειψοειδούς PostScript;
- **Full control** – πλήρης έλεγχος πάνω στα primitives σχεδίασης (γραμμές, καμπύλες, ελλειψοειδείς).  
- **Cross‑platform** – λειτουργεί σε Windows, Linux και macOS.  
- **No external dependencies** – καθαρό Java API, χωρίς κώδικα native.  
- **Easy integration** – εύκολη ενσωμάτωση σε υπάρχουσες εφαρμογές Java και εργαλεία κατασκευής.

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

## Πώς να ορίσετε το χρώμα βαφής για έναν ελλειψοειδή
Ο ορισμός του χρώματος βαφής είναι το πρώτο βήμα πριν από οποιαδήποτε λειτουργία γεμίσματος ή στίγματος. Η μέθοδος `setPaint` καθορίζει το χρώμα που θα χρησιμοποιηθεί για την επόμενη εντολή σχεδίασης.

### Βήμα 1: Ρύθμιση του εγγράφου PostScript
Δημιουργήστε ένα output stream, διαμορφώστε το μέγεθος σελίδας και δημιουργήστε ένα `PsDocument`.

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

### Βήμα 2: Πώς να γεμίσετε ελλειψοειδή – χρησιμοποιήστε το set paint color
Για **fill ellipse**, πρέπει πρώτα να καλέσετε `setPaint` με το επιθυμητό χρώμα γεμίσματος, έπειτα να καλέσετε `fill` με ένα αντικείμενο `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Βήμα 3: Σχεδίαση περιγράμματος ελλειψοειδούς και ορισμός πάχους γραμμής
Μετά το γέμισμα, μπορείτε να αλλάξετε το χρώμα βαφής σε διαφορετικό χρώμα, να ορίσετε ένα `BasicStroke` για τον έλεγχο του πλάτους της γραμμής και να σχεδιάσετε το περίγραμμα του ελλειψοειδούς.

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

Τώρα έχετε ένα αρχείο PostScript που περιέχει δύο ελλειψοειδείς — ένας γεμάτος με πορτοκαλί και ένας με περίγραμμα σε κόκκινο. Μη διστάσετε να πειραματιστείτε με διαφορετικές συντεταγμένες, μεγέθη και χρώματα ώστε να ταιριάζουν στις ανάγκες του σχεδίου σας.

## Συνηθισμένα προβλήματα και αντιμετώπιση
- **Incorrect file path** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό (`/` ή `\\`) κατάλληλο για το λειτουργικό σας σύστημα.  
- **Missing license** – Χωρίς έγκυρη άδεια, η βιβλιοθήκη λειτουργεί σε λειτουργία αξιολόγησης και μπορεί να προσθέσει υδατογραφήματα.  
- **Color not applied** – Θυμηθείτε να ορίσετε `document.setPaint(...)` *πριν* από κάθε κλήση `fill` ή `draw`; η ρύθμιση βαφής δεν παραμένει αυτόματα μεταξύ ξεχωριστών λειτουργιών.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες βιβλιοθήκες Java;**  
Α: Ναι, το Aspose.Page for Java σχεδιάστηκε για άψογη ενσωμάτωση με άλλες βιβλιοθήκες Java.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
Α: Αποκτήστε μια προσωρινή άδεια **[εδώ](https://purchase.aspose.com/temporary-license/)** για δοκιμαστικούς σκοπούς.

**Ε: Είναι το Aspose.Page κατάλληλο για εμπορικά έργα;**  
Α: Απόλυτα! Επισκεφθείτε **[εδώ](https://purchase.aspose.com/buy)** για να εξερευνήσετε τις επιλογές αδειοδότησης για εμπορική χρήση.

**Ε: Πού μπορώ να ζητήσω βοήθεια ή να συζητήσω ερωτήματα σχετικά με το Aspose.Page;**  
Α: Ενταχθείτε στην κοινότητα στο **[Φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39)** για συζητήσεις και υποστήριξη.

**Ε: Υπάρχουν δωρεάν πόροι για να μάθετε περισσότερα για το Aspose.Page for Java;**  
Α: Χρησιμοποιήστε τη **[δωρεάν δοκιμή](https://releases.aspose.com/)** και εξερευνήστε παραδείγματα στην τεκμηρίωση.

## Συμπέρασμα
Το Aspose.Page for Java καθιστά απλό το **set paint color**, **fill ellipse**, και **draw ellipse outline** — είτε χρειάζεστε ένα απλό γεμάτο σχήμα είτε ένα σύνθετο στίγμα γραφικών. Με τα παραπάνω βήματα μπορείτε γρήγορα να προσθέσετε επαγγελματικού επιπέδου διανυσματικά γραφικά σε οποιοδήποτε εκτυπώσιμο έγγραφο. Για πιο βαθιά εξερεύνηση — όπως ο συνδυασμός πολλαπλών σχημάτων, η εφαρμογή διαβαθμίσεων ή η μετατροπή σε PDF — ανατρέξτε στην επίσημη **[τεκμηρίωση](https://reference.aspose.com/page/java/)**.

---

**Τελευταία ενημέρωση:** 2026-02-18  
**Δοκιμάστηκε με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}