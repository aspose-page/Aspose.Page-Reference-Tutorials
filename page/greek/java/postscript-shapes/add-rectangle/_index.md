---
date: 2026-02-18
description: Μάθετε πώς να σχεδιάζετε σχήματα ορθογωνίων σε Java PostScript χρησιμοποιώντας
  το Aspose.Page. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να ορίζετε το χρώμα γεμίσματος,
  πώς να ορίζετε το χρώμα του ορθογωνίου στη Java και πώς να δημιουργείτε ζωντανά
  γραφικά, εξηγώντας ταυτόχρονα πώς να σχεδιάζετε ορθογώνια αποτελεσματικά.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Πώς να σχεδιάσετε ένα ορθογώνιο σε Java PostScript με το Aspose.Page
url: /el/java/postscript-shapes/add-rectangle/
weight: 11
---

μένες φόρμες. Μη διστάσετε να πειραματιστείτε με διαφορετικά χρώματα, στυλ γραμμών και επιπλέον σχήματα AWT για να εμπλουτίσετε το αποτέλεσμα."

Then horizontal rule "---" keep.

Then "**Last Updated:** 2026-02-18" keep.

"**Tested With:** Aspose.Page for Java 24.12 (latest)" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Then backtop button shortcode unchanged.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Σχεδιάσετε Ορθογώνιο σε Java PostScript με Aspose.Page

## Εισαγωγή
Αν χρειάζεστε **how to draw rectangle** σχήματα μέσα σε ένα αρχείο Java PostScript, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από τη χρήση του Aspose.Page for Java για να προσθέσουμε πολύχρωμα ορθογώνια, να ελέγξουμε τη γέμιση και το περίγραμμα τους, και να αποθηκεύσουμε το αποτέλεσμα ως έγγραφο PostScript. Θα δείτε ακριβώς **how to set paint**, πώς να ορίσετε τη γεωμετρία του ορθογωνίου, και γιατί αυτή η προσέγγιση είναι ιδανική για τη δημιουργία εκτυπώσιμων γραφικών προγραμματιστικά. Στο τέλος του οδηγού θα κατανοήσετε επίσης το ευρύτερο πλαίσιο των τεχνικών **draw rectangle java** και πώς εντάσσονται στις ροές εργασίας **java awt rectangle drawing**.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java  
- **Μπορώ να αλλάξω τα χρώματα του ορθογωνίου;** Yes – use `setPaint` with any `java.awt.Color`  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for testing; a license is required for production  
- **Ποιο μέγεθος σελίδας χρησιμοποιείται στο παράδειγμα;** A4 (default `PsSaveOptions`)  
- **Είναι ο κώδικας συμβατός με Java 8+;** Absolutely – it uses standard AWT classes  

## Τι είναι το “How to Draw Rectangle” στο PostScript;
Η σχεδίαση ενός ορθογωνίου σε ένα έγγραφο PostScript σημαίνει τον ορισμό μιας ορθογώνιας περιοχής και είτε τη γέμιση, είτε το περίγραμμα, ή και τα δύο. Με το Aspose.Page μπορείτε να το κάνετε χρησιμοποιώντας γνωστές κλάσεις **java awt rectangle drawing**, κάτι που καθιστά τον κώδικα εύκολο στην ανάγνωση και συντήρηση.

## Γιατί να Χρησιμοποιήσετε το Aspose.Page για Γραφικά Ορθογωνίων;
- **Cross‑platform**: Δημιουργεί τυπικό PostScript που λειτουργεί σε οποιονδήποτε εκτυπωτή.  
- **Fine‑grained control**: Μπορείτε να ορίσετε χρώματα γέμισης, χρώματα περιγράμματος και πλάτη γραμμής ανεξάρτητα.  
- **No external dependencies**: Χρησιμοποιεί μόνο τις ενσωματωμένες κλάσεις γεωμετρίας AWT, έτσι δεν χρειάζεστε επιπλέον βιβλιοθήκες γραφικών.  

## Προαπαιτούμενα
Πριν βυθιστείτε στο tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:
- Βασική κατανόηση του προγραμματισμού Java.  
- Εγκατεστημένη η βιβλιοθήκη Aspose.Page for Java. Αν δεν είναι, κατεβάστε την από την [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Ένα περιβάλλον ανάπτυξης Java εγκατεστημένο στον υπολογιστή σας.

## Εισαγωγή Πακέτων
Στο έργο Java σας, ξεκινήστε εισάγοντας τα απαραίτητα πακέτα. Αυτές οι εισαγωγές σας δίνουν πρόσβαση στις κλάσεις `Color`, `BasicStroke` και `Rectangle2D` του AWT, καθώς και στις βασικές κλάσεις διαχείρισης εγγράφων του Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Οδηγός Βήμα‑Βήμα για Σχεδίαση Ορθογωνίου σε Java PostScript

### Βήμα 1: Ορισμός Paint για Γέμιση Ορθογωνίου  
**How to set paint** – επιλέγουμε ένα πορτοκαλί χρώμα γέμισης για το πρώτο ορθογώνιο. Αυτό δείχνει τη δυνατότητα **set rectangle color java**.

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

### Βήμα 2: Ορισμός Paint για Περίγραμμα Ορθογωνίου  
**Set rectangle color java** – τώρα αλλάζουμε το paint σε κόκκινο και ορίζουμε το πλάτος του περιγράμματος. Αυτό το μέρος του παραδείγματος δείχνει πώς να **draw rectangle java** με προσαρμοσμένο πάχος γραμμής.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Βήμα 3: Κλείσιμο Τρέχουσας Σελίδας και Αποθήκευση Εγγράφου  
Μετά το σχεδιασμό, κλείνουμε τη σελίδα και αποθηκεύουμε το αρχείο. Το κλείσιμο της σελίδας εξασφαλίζει ότι όλες οι εντολές σχεδίασης έχουν αποσταλεί στο ρεύμα PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Συνηθισμένες Χρήσεις για Σχεδίαση Ορθογωνίων
- **Invoice or receipt generation** – τα ορθογώνια λειτουργούν ως περιγράμματα ή επισημαίνουν ενότητες.  
- **Label creation** – σχεδιάστε χρωματιστά κουτιά για να διαχωρίσετε πληροφορίες προϊόντος.  
- **Simple charts** – χρησιμοποιήστε γεμιστά ορθογώνια ως στοιχεία γραφήματος ραβδών.  
- **Custom printable forms** – συνδυάστε ορθογώνια με κείμενο για να δημιουργήσετε πεδία φόρμας.  

## Συνηθισμένα Προβλήματα & Συμβουλές
- **File path errors** – βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`).  
- **License exceptions** – η δοκιμαστική έκδοση προσθέτει υδατογράφημα· αποκτήστε πλήρη άδεια για παραγωγική χρήση.  
- **Color visibility** – ορισμένοι εκτυπωτές μπορεί να ερμηνεύσουν διαφορετικά κάποιες τιμές RGB· δοκιμάστε πρώτα με ένα απλό μαύρο ορθογώνιο.  
- **Memory usage** – για μεγάλα έγγραφα, σκεφτείτε να εκκενώνετε το ρεύμα μετά από κάθε σελίδα (`document.closePage()`).

## Συχνές Ερωτήσεις

**Q:** *Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες γλώσσες προγραμματισμού;*  
A: Το Aspose.Page υποστηρίζει κυρίως Java, αλλά παρόμοιες βιβλιοθήκες είναι διαθέσιμες για άλλες γλώσσες.

**Q:** *Υπάρχει διαθέσιμη δοκιμαστική έκδοση του Aspose.Page for Java;*  
A: Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Page for Java με τη [free trial version](https://releases.aspose.com/).

**Q:** *Πού μπορώ να βρω επιπλέον βοήθεια και συζητήσεις;*  
A: Επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για να αλληλεπιδράσετε με την κοινότητα και να λάβετε βοήθεια.

**Q:** *Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;*  
A: Αποκτήστε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Q:** *Πού μπορώ να αγοράσω μια αδειοδοτημένη έκδοση του Aspose.Page for Java;*  
A: Αγοράστε μια αδειοδοτημένη έκδοση [εδώ](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Μπορώ να αλλάξω το μέγεθος του ορθογωνίου δυναμικά;*  
A: Ναι – απλώς τροποποιήστε τις παραμέτρους `Rectangle2D.Float(x, y, width, height)` πριν καλέσετε `fill` ή `draw`.

**Q:** *Μπορεί να προστεθεί κείμενο μέσα στο ορθογώνιο;*  
A: Απόλυτα. Μετά το σχεδιασμό του ορθογωνίου, χρησιμοποιήστε `document.drawString(...)` με τη ζητούμενη γραμματοσειρά και θέση.

**Q:** *Υποστηρίζει το Aspose.Page άλλα σχήματα όπως κύκλους ή πολύγωνα;*  
A: Ναι, το API παρέχει μεθόδους όπως `drawEllipse` και `drawPolygon` για μια ποικιλία διανυσματικών γραφικών.

## Συμπέρασμα
Σε αυτόν τον οδηγό δείξαμε **how to draw rectangle** σχήματα σε ένα έγγραφο Java PostScript, καλύψαμε **how to set paint**, και παρουσιάσαμε πώς να **set rectangle color java** χρησιμοποιώντας το Aspose.Page. Τώρα έχετε μια σταθερή βάση για τη δημιουργία ζωντανών εκτυπώσιμων γραφικών, είτε δημιουργείτε τιμολόγια, ετικέτες ή προσαρμοσμένες φόρμες. Μη διστάσετε να πειραματιστείτε με διαφορετικά χρώματα, στυλ γραμμών και επιπλέον σχήματα AWT για να εμπλουτίσετε το αποτέλεσμα.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}