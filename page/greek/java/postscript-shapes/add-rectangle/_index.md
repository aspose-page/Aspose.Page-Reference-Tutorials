---
date: 2025-12-11
description: Μάθετε πώς να σχεδιάζετε σχήματα ορθογωνίων σε Java PostScript χρησιμοποιώντας
  το Aspose.Page. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να ορίσετε το χρώμα βαφής,
  να ορίσετε το χρώμα του ορθογωνίου στη Java και να δημιουργήσετε ζωντανά γραφικά.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Πώς να σχεδιάσετε ορθογώνιο σε Java PostScript με το Aspose.Page
url: /el/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Σχεδιάσετε Ορθογώνιο σε Java PostScript με το Aspose.Page

## Εισαγωγή
Αν χρειάζεστε **πώς να σχεδιάσετε ορθογώνιο** σχήματα μέσα σε ένα αρχείο Java PostScript, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από τη χρήση του Aspose.Page for Java για να προσθέσουμε πολύχρωμα ορθογώνια, να ελέγξουμε το γέμισμα και το περίγραμμα τους, και να αποθηκεύσουμε το αποτέλεσμα ως έγγραφο PostScript. Θα δείτε ακριβώς **πώς να ορίσετε το χρώμα**, πώς να ορίσετε τη γεωμετρία του ορθογωνίου, και γιατί αυτή η προσέγγιση είναι ιδανική για τη δημιουργία εκτυπώσιμων γραφικών προγραμματιστικά.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java  
- **Μπορώ να αλλάξω τα χρώματα του ορθογωνίου;** Yes – use `setPaint` with any `java.awt.Color`  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for testing; a license is required for production  
- **Ποιο μέγεθος σελίδας χρησιμοποιείται στο παράδειγμα;** A4 (default `PsSaveOptions`)  
- **Είναι ο κώδικας συμβατός με Java 8+;** Absolutely – it uses standard AWT classes  

## Προαπαιτούμενα
Πριν βυθιστείτε στο tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
- Βασική κατανόηση του προγραμματισμού Java.  
- Aspose.Page for Java library installed. If not, download it from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Ένα περιβάλλον ανάπτυξης Java εγκατεστημένο στον υπολογιστή σας.

## Εισαγωγή Πακέτων
Στο Java project σας, ξεκινήστε εισάγοντας τα απαραίτητα πακέτα:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Πώς να Σχεδιάσετε Ορθογώνιο σε Java PostScript
Παρακάτω είναι η πλήρης ροή εργασίας χωρισμένη σε σαφή βήματα. Κάθε βήμα περιλαμβάνει μια σύντομη εξήγηση ακολουθούμενη από το αρχικό μπλοκ κώδικα (αμετάβλητο).

### Βήμα 1: Ορισμός Χρώματος για Γέμισμα Ορθογωνίου  
**Πώς να ορίσετε το χρώμα** – επιλέγουμε ένα πορτοκαλί χρώμα γεμίσματος για το πρώτο ορθογώνιο.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Βήμα 2: Ορισμός Χρώματος για Περίγραμμα Ορθογωνίου  
**Ορισμός χρώματος ορθογωνίου java** – τώρα αλλάζουμε το χρώμα σε κόκκινο και ορίζουμε το πλάτος του περιγράμματος.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Βήμα 3: Κλείσιμο Τρέχουσας Σελίδας και Αποθήκευση Εγγράφου  
Μετά το σχεδιασμό, κλείνουμε τη σελίδα και αποθηκεύουμε το αρχείο.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Γιατί να Χρησιμοποιήσετε το Aspose.Page για Γραφικά Ορθογωνίων;
- **Cross‑platform**: Δημιουργεί τυπικό PostScript που λειτουργεί σε οποιονδήποτε εκτυπωτή.  
- **Fine‑grained control**: Μπορείτε να ορίσετε χρώματα γεμίσματος, χρώματα περιγράμματος και πλάτη γραμμής ανεξάρτητα.  
- **No external dependencies**: Χρησιμοποιεί μόνο τις ενσωματωμένες κλάσεις γεωμετρίας AWT.  

## Συχνά Προβλήματα & Συμβουλές
- **Σφάλματα διαδρομής αρχείου** – βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`).  
- **Εξαιρέσεις άδειας** – η δοκιμαστική έκδοση προσθέτει υδατογράφημα· αποκτήστε πλήρη άδεια για παραγωγική χρήση.  
- **Ορατότητα χρώματος** – ορισμένοι εκτυπωτές μπορεί να ερμηνεύσουν διαφορετικά κάποιες τιμές RGB· δοκιμάστε πρώτα ένα απλό μαύρο ορθογώνιο.  

## Συμπέρασμα
Σε αυτόν τον οδηγό δείξαμε **πώς να σχεδιάσετε ορθογώνιο** σχήματα σε ένα έγγραφο Java PostScript, καλύψαμε **πώς να ορίσετε το χρώμα**, και παρουσιάσαμε πώς να **ορίσετε χρώμα ορθογωνίου java** χρησιμοποιώντας το Aspose.Page. Μη διστάσετε να πειραματιστείτε με διαφορετικά σχήματα, χρώματα και στιλ γραμμών για να δημιουργήσετε πλούσια εκτυπώσιμα γραφικά για αναφορές, τιμολόγια ή προσαρμοσμένες εκτυπώσεις.

## Συχνές Ερωτήσεις

### Μπορώ να χρησιμοποιήσω το Aspose.Page για Java με άλλες γλώσσες προγραμματισμού;
Το Aspose.Page υποστηρίζει κυρίως τη Java, αλλά παρόμοιες βιβλιοθήκες είναι διαθέσιμες για άλλες γλώσσες.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση του Aspose.Page για Java;
Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Page for Java με την [δωρεάν δοκιμαστική έκδοση](https://releases.aspose.com/).

### Πού μπορώ να βρω επιπλέον βοήθεια και συζητήσεις;
Επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για να συνδεθείτε με την κοινότητα και να λάβετε βοήθεια.

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page για Java;
Αποκτήστε μια προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Πού μπορώ να αγοράσω μια αδειοδοτημένη έκδοση του Aspose.Page για Java;
Αγοράστε μια αδειοδοτημένη έκδοση [εδώ](https://purchase.aspose.com/buy).

**Additional Q&A**

**Ε:** *Μπορώ να αλλάξω το μέγεθος του ορθογωνίου δυναμικά;*  
**Α:** Ναι – απλώς τροποποιήστε τις παραμέτρους `Rectangle2D.Float(x, y, width, height)` πριν καλέσετε `fill` ή `draw`.

**Ε:** *Μπορεί να προστεθεί κείμενο μέσα στο ορθογώνιο;*  
**Α:** Απόλυτα. Μετά το σχεδιασμό του ορθογωνίου, χρησιμοποιήστε `document.drawString(...)` με τη ζητούμενη γραμματοσειρά και θέση.

**Ε:** *Υποστηρίζει το Aspose.Page άλλα σχήματα όπως κύκλους ή πολύγωνα;*  
**Α:** Ναι, το API παρέχει μεθόδους όπως `drawEllipse` και `drawPolygon` για μια ποικιλία διανυσματικών γραφικών.

---

**Τελευταία Ενημέρωση:** 2025-12-11  
**Δοκιμάστηκε Με:** Aspose.Page for Java 24.12 (latest)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}