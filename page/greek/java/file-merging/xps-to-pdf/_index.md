---
date: 2025-11-29
description: Μάθετε πώς να αποθηκεύετε XPS ως PDF σε Java με το Aspose.Page Java.
  Ακολουθήστε τον βήμα‑βήμα οδηγό μας για αποδοτική μετατροπή XPS σε PDF και ρυθμίσεις
  συμπίεσης PDF.
linktitle: Convert XPS to PDF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: Μετατροπή XPS σε PDF σε Java χρησιμοποιώντας το Aspose.Page Java
url: /el/java/file-merging/xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή XPS σε PDF σε Java χρησιμοποιώντας το Aspose.Page Java

## Εισαγωγή
Σε αυτό το tutorial, θα μάθετε **πώς να μετατρέψετε XPS σε PDF σε Java χρησιμοποιώντας το Aspose.Page Java**, μια ισχυρή βιβλιοθήκη σχεδιασμένη για μετατροπή εγγράφων σε Java. Είτε χρειάζεστε μαζική επεξεργασία τιμολογίων, δημιουργία εκτυπώσιμων αναφορών, είτε απλώς τη μεταφορά παλαιών αρχείων XPS, το Aspose.Page Java κάνει τη δουλειά γρήγορη, αξιόπιστη και πλήρως παραμετροποιήσιμη.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή XPS σε PDF;** Aspose.Page Java  
- **Πόσο διαρκεί μια βασική μετατροπή;** Συνήθως κάτω από ένα δευτερόλεπτο για ένα αρχείο XPS μίας σελίδας.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται άδεια για παραγωγή.  
- **Μπορώ να ελέγξω τη συμπίεση του PDF;** Ναι – χρησιμοποιήστε το `PdfSaveOptions` για να ορίσετε τη συμπίεση εικόνας και κειμένου.  
- **Ποια έκδοση Java απαιτείται;** Java 8 ή νεότερη (συνιστάται JDK 11+).

## Τι είναι το Aspose.Page Java;
Το Aspose.Page Java είναι ένα **υψηλής απόδοσης API** που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να μετατρέπουν έγγραφα XPS προγραμματιστικά. Υποστηρίζει την απόδοση XPS σε PDF, PNG, JPEG και άλλες μορφές, παρέχοντας λεπτομερή έλεγχο των ρυθμίσεων εξόδου όπως **set PDF compression**.

## Γιατί να χρησιμοποιήσετε το Aspose.Page Java για μετατροπή XPS‑σε‑PDF;
- **Απόδοση χωρίς εξαρτήσεις** – χωρίς εγγενείς βιβλιοθήκες ή εξωτερικά εργαλεία.  
- **Ακριβής διατήρηση διάταξης** – το PDF που παράγεται αντικατοπτρίζει την αρχική εμφάνιση του XPS.  
- **Πλήρης έλεγχος εξόδου PDF** – μπορείτε να ρυθμίσετε την ποιότητα εικόνας, να επιλέξετε αλγόριθμους συμπίεσης και να ορίσετε συγκεκριμένες σελίδες προς απόδοση.  
- **Διαπλατφορμική** – λειτουργεί σε Windows, Linux και macOS με οποιοδήποτε τυπικό JDK.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK) 8+** – συνιστάται η τελευταία έκδοση για καλύτερη απόδοση και ασφάλεια.  
2. **Βιβλιοθήκη Aspose.Page for Java** – κατεβάστε το JAR από την επίσημη [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).  
3. Ένα **IDE** (IntelliJ IDEA, Eclipse, VS Code) ή έναν απλό επεξεργαστή κειμένου συν συνόδευση εργαλείων γραμμής εντολών (Maven/Gradle).  

## Εισαγωγή Πακέτων
Προσθέστε τις απαιτούμενες εισαγωγές στην κλάση Java ώστε να μπορείτε να εργάζεστε με έγγραφα XPS και έξοδο PDF.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.rendering.pdf.PdfDevice;
import com.aspose.xps.rendering.pdf.PdfSaveOptions;
import com.aspose.xps.rendering.pdf.PdfImageCompression;
import com.aspose.xps.rendering.pdf.PdfTextCompression;
import java.io.FileOutputStream;
```

## Οδηγός Βήμα‑Βήμα

### Βήμα 1: Ορισμός Διαδρομής Φακέλου Εγγράφου
Ορίστε το φάκελο που περιέχει το πηγαίο αρχείο XPS και όπου θα αποθηκευτεί το PDF.

```java
String dataDir = "C:/MyDocuments/XpsFiles/";   // <-- replace with your actual path
```

### Βήμα 2: Αρχικοποίηση Ροής Εξόδου PDF
Δημιουργήστε ένα `FileOutputStream` που δείχνει στο αρχείο PDF προορισμού.

```java
FileOutputStream pdfStream = new FileOutputStream(dataDir + "XPStoPDF.pdf");
```

> **Συμβουλή:** Χρησιμοποιήστε `try‑with‑resources` για αυτόματο κλείσιμο της ροής και αποφυγή διαρροών πόρων.

### Βήμα 3: Φόρτωση Εγγράφου XPS
Δημιουργήστε ένα αντικείμενο `XpsDocument` φορτώνοντας το πηγαίο αρχείο XPS.

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Βήμα 4: Αρχικοποίηση Επιλογών Αποθήκευσης PDF (Set PDF Compression)
Ρυθμίστε πώς θα συμπιεστεί το PDF. Αυτό το βήμα σας επιτρέπει να **set PDF compression** για εικόνες και κείμενο, μειώνοντας το μέγεθος του αρχείου χωρίς να θυσιάζεται η ποιότητα.

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setJpegQualityLevel(100);                         // maximum JPEG quality
options.setImageCompression(PdfImageCompression.Jpeg);   // compress images as JPEG
options.setTextCompression(PdfTextCompression.Flate);    // compress text streams
options.setPageNumbers(new int[] { 1, 2, 6 });            // optional: export only selected pages
```

> **Γιατί είναι σημαντικό:** Η ρύθμιση της ποιότητας JPEG και των τύπων συμπίεσης μπορεί να μειώσει ένα PDF 10 MB σε κάτω από 2 MB διατηρώντας την οπτική πιστότητα που χρειάζεστε.

### Βήμα 5: Δημιουργία Συσκευής Απόδοσης για Μορφή PDF
Το `PdfDevice` μεταβιβάζει τις αποδομένες σελίδες στη ροή εξόδου PDF.

```java
PdfDevice device = new PdfDevice(pdfStream);
```

### Βήμα 6: Αποθήκευση Εγγράφου
Τέλος, αποδώστε το περιεχόμενο XPS σε PDF χρησιμοποιώντας τις ρυθμισμένες επιλογές.

```java
document.save(device, options);
```

> **Αποτέλεσμα:** Μετά την εκτέλεση, το `XPStoPDF.pdf` θα εμφανιστεί στο φάκελο `dataDir`, περιέχοντας τις μετατρεπόμενες σελίδες με τις ρυθμίσεις συμπίεσης που καθορίσατε.

## Συχνά Προβλήματα & Λύσεις
| Πρόβλημα | Αιτία | Λύση |
|-------|-------|----------|
| **`FileNotFoundException`** | Λανθασμένη διαδρομή `dataDir` | Επαληθεύστε ότι ο φάκελος υπάρχει και ότι η εφαρμογή έχει δικαιώματα ανάγνωσης/εγγραφής. |
| **Κενές σελίδες PDF** | Έλλειψη αρχικοποίησης `PdfDevice` | Βεβαιωθείτε ότι το `PdfDevice` δημιουργείται με το ίδιο `FileOutputStream` που χρησιμοποιείται για την έξοδο. |
| **Μεγάλο μέγεθος PDF** | Η προεπιλεγμένη συμπίεση είναι χαμηλή | Αυξήστε το `setJpegQualityLevel` ή αλλάξτε σε `PdfImageCompression.Jpeg` με χαμηλότερο επίπεδο ποιότητας. |
| **Εμφανίζονται μόνο ορισμένες σελίδες** | Το φίλτρο `setPageNumbers` αποκλείει σελίδες | Προσαρμόστε τον πίνακα ώστε να περιλαμβάνει όλους τους απαιτούμενους αριθμούς σελίδων ή αφαιρέστε την κλήση για εξαγωγή όλων των σελίδων. |

## Συχνές Ερωτήσεις

**Ε: Είναι το Aspose.Page Java συμβατό με διαφορετικές εκδόσεις Java;**  
Α: Ναι, το Aspose.Page Java υποστηρίζει Java 8 έως Java 21, συμπεριλαμβανομένων των διανομών Oracle και OpenJDK.

**Ε: Μπορώ να προσαρμόσω τις ρυθμίσεις συμπίεσης για το μετατρεπόμενο PDF;**  
Α: Απόλυτα. Χρησιμοποιήστε το `PdfSaveOptions` για να ορίσετε την ποιότητα JPEG, τον τύπο συμπίεσης εικόνας και τη συμπίεση κειμένου όπως φαίνεται στο Βήμα 4.

**Ε: Πού μπορώ να βρω επιπλέον υποστήριξη ή συζητήσεις κοινότητας;**  
Α: Επισκεφθείτε το [Aspose.Page Forum](https://forum.aspose.com/c/page/39) για βοήθεια από την κοινότητα, παραδείγματα κώδικα και συμβουλές αντιμετώπισης προβλημάτων.

**Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Page;**  
Α: Ναι, μπορείτε να κατεβάσετε μια πλήρως λειτουργική δοκιμή από τη [σελίδα λήψης του Aspose](https://releases.aspose.com/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page;**  
Α: Μια προσωρινή άδεια μπορεί να ζητηθεί [εδώ](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
Με την αξιοποίηση του **Aspose.Page Java**, μπορείτε εύκολα να **αποθηκεύσετε XPS ως PDF** και να ελέγξετε κάθε πτυχή της εξόδου, από την επιλογή σελίδων μέχρι τη συμπίεση. Αυτό το tutorial κάλυψε όλα όσα χρειάζεστε για να ενσωματώσετε τη μετατροπή XPS‑σε‑PDF στις εφαρμογές Java, είτε δημιουργείτε ένα μοναδικό εργαλείο είτε μια μεγάλης κλίμακας γραμμή επεξεργασίας εγγράφων.

---

**Τελευταία ενημέρωση:** 2025-11-29  
**Δοκιμασμένο με:** Aspose.Page for Java 24.10  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}