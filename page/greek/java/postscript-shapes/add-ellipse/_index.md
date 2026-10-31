---
date: 2026-10-31
description: Μάθετε πώς να ορίσετε paint color και να γεμίσετε ellipse σε Java PostScript
  χρησιμοποιώντας Aspose.Page. Αυτός ο οδηγός δείχνει πώς να γεμίσετε ellipse, να
  σχεδιάσετε το περίγραμμα του ellipse και να ορίσετε stroke thickness με σαφή βήματα
  κώδικα.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Προσθήκη Ellipse σε Java PostScript
og_description: Μάθετε πώς να γεμίσετε ellipse και να ορίσετε paint color σε Java
  PostScript χρησιμοποιώντας Aspose.Page. Ακολουθήστε κώδικα βήμα‑βήμα για να σχεδιάσετε
  γεμάτα και περιγραμμένα ellipses σε δευτερόλεπτα.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Πώς να γεμίσετε ellipse και να ορίσετε paint color σε Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Πώς να γεμίσετε ellipse και να ορίσετε paint color σε Java PostScript
url: /el/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να γεμίσετε έλλειψη και να ορίσετε χρώμα βαφής σε Java PostScript

## Εισαγωγή
Αν χρειάζεστε να **ορίσετε χρώμα βαφής** ενώ σχεδιάζετε διανυσματικά γραφικά, η βιβλιοθήκη Aspose.Page for Java σας παρέχει πλήρη έλεγχο σε κάθε γραμμή και γέμισμα. Σε αυτό το tutorial θα ανακαλύψετε πώς να **ορίσετε χρώμα βαφής**, **γεμίσετε έλλειψη**, και **σχεδιάσετε το περίγραμμα της έλλειψης** χρησιμοποιώντας μια απλή, βήμα‑βήμα προσέγγιση. Στο τέλος, θα μπορείτε να προσθέσετε έλλειψεις υψηλής ποιότητας σε PostScript σε τιμολόγια, αναφορές ή οποιοδήποτε εκτυπώσιμο έγγραφο.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη είναι η καλύτερη για σχεδίαση γραφικών PostScript σε Java;** Aspose.Page for Java.  
- **Μπορώ να γεμίσω μια έλλειψη με ένα στερεό χρώμα;** Ναι – χρησιμοποιήστε `document.setPaint(Color.YOUR_COLOR)` πριν από `fill`.  
- **Πώς μπορώ να σχεδιάσω μόνο το περίγραμμα μιας έλλειψης;** Ορίστε το χρώμα βαφής και το στυλ γραμμής, μετά καλέστε `document.draw(...)`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται εμπορική άδεια· μια προσωρινή άδεια είναι διαθέσιμη για δοκιμές.  
- **Ποια έκδοση της Java υποστηρίζεται;** Οποιοδήποτε runtime Java 8+ λειτουργεί με την τρέχουσα έκδοση του Aspose.Page.

## Τι είναι μια έλλειψη PostScript;
Μια έλλειψη PostScript είναι ένα διανυσματικό σχήμα που ορίζεται από ένα περιοριστικό ορθογώνιο. Σε αντίθεση με τις ραστερ εικόνες, κλιμακώνεται χωρίς απώλεια ποιότητας, καθιστώντας το ιδανικό για εκτύπωση υψηλής ανάλυσης και μετατροπή σε PDF. Επειδή το σχήμα περιγράφεται μαθηματικά, μπορεί να αποδοθεί σε οποιοδήποτε μέγεθος ή ανάλυση διατηρώντας καθαρά άκρα και ομαλές καμπύλες.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για τη δημιουργία μιας έλλειψης PostScript;
Το Aspose.Page σας παρέχει ντετερμινιστικό έλεγχο σε κάθε primitive σχεδίασης. Υποστηρίζει **3 κύρια λειτουργικά συστήματα (Windows, Linux, macOS)**, **0 εγγενείς εξαρτήσεις**, και μπορεί να αποδώσει **50+ διανυσματικά primitives** ανά δευτερόλεπτο σε έναν τυπικό διακομιστή. Η βιβλιοθήκη είναι καθαρή Java, ώστε να μπορείτε να την ενσωματώσετε σε οποιαδήποτε εφαρμογή Java 8+ χωρίς πρόσθετες εγγενείς βιβλιοθήκες.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. Ένα λειτουργικό περιβάλλον ανάπτυξης Java (JDK 8 ή νεότερο).  
2. Η βιβλιοθήκη Aspose.Page for Java προστέθηκε στο έργο σας. Μπορείτε να την κατεβάσετε **[από τη σελίδα κυκλοφορίας του Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  

## Εισαγωγή πακέτων
Στο αρχείο πηγαίου κώδικα Java, εισάγετε τις κλάσεις που απαιτούνται για τη σχεδίαση και αποθήκευση περιεχομένου PostScript.

Το πακέτο `java.awt` παρέχει τους βασικούς τύπους γραφικών όπως `Color`, `Ellipse2D` και `BasicStroke`. Το πακέτο `com.aspose.page` παρέχει την κλάση `PsDocument` που γράφει έξοδο PostScript.

- **`Color`** – αντιπροσωπεύει ένα χρώμα sRGB που χρησιμοποιείται για βαφή.  
- **`Ellipse2D`** – περιγράφει ένα σχήμα έλλειψης που ορίζεται από ένα περιοριστικό ορθογώνιο.  
- **`BasicStroke`** – καθορίζει το πλάτος γραμμής, το μοτίβο παύλας και το στυλ άκρου για το σχεδιασμό περιγραμμάτων.  
- **`PsDocument`** – αντιπροσωπεύει ένα έγγραφο PostScript και παρέχει μεθόδους για τη σχεδίαση γραφικών και τη διαχείριση σελίδων.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Πώς να ορίσετε χρώμα βαφής για μια έλλειψη
Το πρώτο βήμα είναι να ενημερώσετε το έγγραφο ποιο χρώμα θα χρησιμοποιήσει για την επόμενη λειτουργία σχεδίασης. Η μέθοδος `setPaint` ορίζει ένα στερεό χρώμα που θα εφαρμοστεί είτε σε γέμισμα είτε σε γραμμή, ανάλογα με την επόμενη κλήση.

### Βήμα 1: Ρύθμιση του εγγράφου PostScript
Δημιουργήστε μια ροή εξόδου, διαμορφώστε το μέγεθος σελίδας και δημιουργήστε ένα αντικείμενο `PsDocument`.

`PsDocument` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο PostScript στη μνήμη. Όλες οι εντολές σχεδίασης περνούν μέσω αυτού του αντικειμένου, και διαχειρίζεται τη διάταξη σελίδων, τη διαχείριση πόρων και τη δημιουργία του τελικού αρχείου.

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

### Βήμα 2: Γέμισμα έλλειψης – χρήση χρώματος βαφής
Για **γέμισμα έλλειψης**, πρέπει πρώτα να καλέσετε `setPaint` με το επιθυμητό χρώμα γεμίσματος, στη συνέχεια να καλέσετε `fill` με ένα αντικείμενο `Ellipse2D`.

`setPaint` ορίζει το τρέχον χρώμα σχεδίασης που χρησιμοποιείται για τις επόμενες λειτουργίες γεμίσματος ή γραμμής.
`Ellipse2D` ορίζει τα γεωμετρικά όρια της έλλειψης· ο κατασκευαστής της δέχεται τις συντεταγμένες X‑Y της επάνω‑αριστερής γωνίας καθώς και το πλάτος και το ύψος.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Βήμα 3: Σχεδίαση περιγράμματος έλλειψης και ορισμός πάχους γραμμής
Μετά το γέμισμα, μπορείτε να αλλάξετε το χρώμα βαφής σε διαφορετικό χρώμα, να ορίσετε ένα `BasicStroke` για να ελέγξετε το πλάτος της γραμμής, και να σχεδιάσετε το περίγραμμα της έλλειψης.

`BasicStroke` καθορίζει το πλάτος γραμμής, το μοτίβο παύλας και το στυλ άκρου για το σχεδιασμό περιγραμμάτων. Με την προσαρμογή της ιδιότητας `width` ελέγχετε πόσο έντονο εμφανίζεται το περίγραμμα της έλλειψης.

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

Η κλήση `document.close()` εκκαθαρίζει όλες τις εκκρεμείς εντολές σχεδίασης και απελευθερώνει πόρους. Το προκύπτον αρχείο `.ps` μπορεί να ανοιχτεί με οποιονδήποτε προβολέα PostScript ή να μετατραπεί σε PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Τώρα έχετε ένα αρχείο PostScript που περιέχει δύο έλλειψεις—μία γεμάτη με πορτοκαλί και μια άλλη με περίγραμμα σε κόκκινο. Μη διστάσετε να πειραματιστείτε με διαφορετικές συντεταγμένες, μεγέθη και χρώματα για να ταιριάξουν με τις ανάγκες του σχεδίου σας.

## Κοινά προβλήματα και αντιμετώπιση σφαλμάτων
- **Λάθος διαδρομή αρχείου** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με έναν διαχωριστή (`/` ή `\\`) κατάλληλο για το λειτουργικό σας σύστημα.  
- **Λείπει άδεια** – Χωρίς έγκυρη άδεια, η βιβλιοθήκη λειτουργεί σε λειτουργία αξιολόγησης και μπορεί να προσθέσει υδατογραφήματα.  
- **Το χρώμα δεν εφαρμόζεται** – Θυμηθείτε να ορίσετε `document.setPaint(...)` *πριν* από κάθε κλήση `fill` ή `draw`; η ρύθμιση βαφής δεν παραμένει αυτόματα μεταξύ ξεχωριστών λειτουργιών.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες βιβλιοθήκες Java;**  
A: Ναι, το Aspose.Page for Java έχει σχεδιαστεί ώστε να ενσωματώνεται άψογα με άλλες βιβλιοθήκες Java.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
A: Αποκτήστε μια προσωρινή άδεια **[από τη σελίδα προσωρινής άδειας του Aspose](https://purchase.aspose.com/temporary-license/)** για δοκιμαστικούς σκοπούς.

**Q: Είναι το Aspose.Page κατάλληλο για εμπορικά έργα;**  
A: Απόλυτα! Επισκεφθείτε **[τη σελίδα αγοράς του Aspose](https://purchase.aspose.com/buy)** για να εξερευνήσετε τις επιλογές αδειοδότησης για εμπορική χρήση.

**Q: Πού μπορώ να ζητήσω βοήθεια ή να συζητήσω ερωτήματα σχετικά με το Aspose.Page;**  
A: Ενταχθείτε στην κοινότητα στο **[Φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39)** για συζητήσεις και βοήθεια.

**Q: Υπάρχουν δωρεάν πόροι για να μάθετε περισσότερα για το Aspose.Page for Java;**  
A: Χρησιμοποιήστε τη **[σελίδα δωρεάν δοκιμής του Aspose](https://releases.aspose.com/)** και εξερευνήστε παραδείγματα στην τεκμηρίωση.

## Συμπέρασμα
Το Aspose.Page for Java καθιστά εύκολο να **ορίσετε χρώμα βαφής**, **γεμίσετε έλλειψη** και **σχεδιάσετε το περίγραμμα της έλλειψης**—είτε χρειάζεστε ένα απλό γεμάτο σχήμα είτε ένα σύνθετο γραφικό με γραμμή. Με τα παραπάνω βήματα μπορείτε γρήγορα να προσθέσετε επαγγελματικού επιπέδου διανυσματικά γραφικά σε οποιοδήποτε εκτυπώσιμο έγγραφο. Για πιο βαθιά εξερεύνηση—όπως ο συνδυασμός πολλαπλών σχημάτων, η εφαρμογή διαβαθμίσεων ή η μετατροπή σε PDF—ανατρέξτε στην επίσημη **[τεκμηρίωση Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Σχετικές οδηγίες

- [Πώς να σχεδιάσετε ορθογώνιο σε Java PostScript με Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Πώς να προσθέσετε κείμενο Unicode σε Java PostScript με Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Δημιουργία ακτινικής διαβάθμισης σε PostScript με Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}