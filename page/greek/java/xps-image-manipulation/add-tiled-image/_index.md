---
date: 2026-05-30
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS σε Java χρησιμοποιώντας το Aspose.Page
  και να προσθέσετε εικόνα σε πλακίδια εύκολα με αυτόν τον οδηγό βήμα‑βήμα. Πώς να
  δημιουργήσετε αρχεία XPS γρήγορα.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Προσθήκη εικόνας σε πλακίδια σε Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Πώς να δημιουργήσετε έγγραφο XPS με εικόνα σε πλακίδια σε Java
url: /el/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε έγγραφο XPS με εικόνα σε μοτίβο πλακιδίων σε Java

## Εισαγωγή
Η δημιουργία εγγράφων XPS προγραμματιστικά είναι μια βασική δεξιότητα για προγραμματιστές Java που χρειάζονται εκτυπώσιμη, ανεξάρτητη από τη συσκευή έξοδο. **Πώς να δημιουργήσετε XPS** αρχεία αποδοτικά απαντάται από το Aspose.Page for Java, το οποίο αφαιρεί τις λεπτομέρειες του χαμηλού επιπέδου XML Paper Specification και σας επιτρέπει να εστιάσετε στον οπτικό σχεδιασμό. Σε αυτόν τον οδηγό θα δείτε ακριβώς πώς να δημιουργήσετε ένα έγγραφο XPS, να προσθέσετε μια εικόνα σε μοτίβο πλακιδίων ως φόντο ή μοτίβο, και να αποθηκεύσετε το αποτέλεσμα — όλα με σύντομο, έτοιμο για παραγωγή κώδικα.

## Γρήγορες απαντήσεις
- **Τι κάνει το Aspose.Page;** Παρέχει ένα API υψηλού επιπέδου για τη δημιουργία και τη διαχείριση εγγράφων XPS σε Java.  
- **Μπορώ να τοποθετήσω μια εικόνα σε μοτίβο πλακιδίων;** Ναι – χρησιμοποιήστε `XpsImageBrush` με `XpsTileMode.Tile`.  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή εμπορική άδεια για χρήση σε παραγωγή.  
- **Ποια έκδοση Java υποστηρίζεται;** Οποιοδήποτε JDK 8+ είναι συμβατό.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10–15 λεπτά για ένα βασικό σενάριο εικόνας σε μοτίβο πλακιδίων.

## Τι είναι η «δημιουργία εγγράφου XPS»;
`XpsDocument` είναι το κορυφαίο αντικείμενο του Aspose.Page που αντιπροσωπεύει ένα μόνο αρχείο XPS στη μνήμη. Συμπεριλαμβάνει σελίδες, πόρους και μεταδεδομένα, επιτρέποντάς σας να δημιουργήσετε το έγγραφο προγραμματιστικά. Η δημιουργία ενός εγγράφου XPS σημαίνει η δημιουργία μιας στιγμής αυτής της κλάσης, η προσθήκη οπτικών στοιχείων και, τελικά, η κλήση του `save` για να γράψετε το αρχείο σταθερής διάταξης στο δίσκο. Αυτή η προσέγγιση εξαλείφει την χειροκίνητη διαχείριση XML και εγγυάται τη συμμόρφωση με το XML Paper Specification.

## Γιατί να προσθέσετε μια εικόνα σε μοτίβο πλακιδίων;
Η τοποθέτηση (tiling) επαναλαμβάνει ένα γραφικό στοιχείο σε ορισμένη περιοχή, κάτι ιδανικό για φόντα, υδατογραφήματα ή γεμίσματα μοτίβων. Χρησιμοποιώντας το `XpsTileMode.Tile` η εικόνα επαναλαμβάνεται αυτόματα χωρίς χειροκίνητη αντιγραφή, εξοικονομώντας χρόνο ανάπτυξης και εξασφαλίζοντας συνεπή απόδοση σε οποιαδήποτε συσκευή. Οι εικόνες σε μοτίβο πλακιδίων διατηρούν επίσης μικρότερο μέγεθος αρχείου επειδή ο ίδιος πόρος bitmap επαναχρησιμοποιείται αντί να ενσωματώνεται πολλές φορές.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Page for Java** – κατεβάστε από την [website](https://releases.aspose.com/page/java/).  
3. **Ένας εγγράψιμος φάκελος** – όπου θα αποθηκευτεί το παραγόμενο αρχείο XPS.

## Εισαγωγή πακέτων
Στο έργο Java, εισάγετε τις απαραίτητες κλάσεις:

`XpsDocument` είναι το κύριο αντικείμενο που αντιπροσωπεύει ένα αρχείο XPS.  
`XpsImageBrush` ζωγραφίζει σχήματα χρησιμοποιώντας μια πηγή εικόνας.  
`XpsTileMode` καθορίζει πώς τοποθετείται μια εικόνα.  
`Rectangle2D` περιγράφει μια ορθογώνια περιοχή για τοποθέτηση.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Οδηγός βήμα προς βήμα

### Βήμα 1: Ρυθμίστε το έργο σας
Προσθέστε τα JAR αρχεία του Aspose.Page στο classpath του έργου σας και βεβαιωθείτε ότι οι δηλώσεις εισαγωγής συντάσσονται χωρίς σφάλματα.

### Βήμα 2: Δημιουργήστε έγγραφο XPS
`XpsDocument` είναι ο πυρήνας που περιέχει σελίδες, διαδρομές και πόρους. Δημιουργήστε μια στιγμιότυπο με το επιθυμητό μέγεθος σελίδας, ώστε να μπορείτε να αρχίσετε να προσθέτετε γραφικά στοιχεία.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Βήμα 3: Ορίστε τη διαδρομή της εικόνας σε μοτίβο πλακιδίων
Τοποθετήστε την εικόνα που θέλετε να χρησιμοποιήσετε σε μοτίβο (π.χ., `R08LN_NN.jpg`) μέσα στον φάκελο που αναφέρεται από το `dataDir`. Η εικόνα θα χρησιμοποιηθεί ως μοτίβο πινέλου.

### Βήμα 4: Προσθέστε εικόνα σε μοτίβο πλακιδίων
Δημιουργήστε μια ορθογώνια διαδρομή και γεμίστε την με ένα `XpsImageBrush`. Ορίζοντας το tile mode σε `Tile`, η εικόνα επαναλαμβάνεται σε όλο το ορθογώνιο. Ρυθμίστε τα ορθογώνια πηγής και προορισμού για να ελέγξετε το μέγεθος και τη θέση των πλακιδίων.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Βήμα 5: Αποθηκεύστε το έγγραφο
Αποθηκεύστε το αρχείο XPS στο δίσκο. Το αρχείο εξόδου θα περιέχει την εικόνα σε μοτίβο που μόλις ορίσατε και μπορεί να ανοιχθεί με οποιονδήποτε προβολέα XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Επαναλάβετε αυτά τα βήματα όποτε χρειαστεί να **προσθέσετε εικόνα σε μοτίβο πλακιδίων** σε άλλες σελίδες ή σχήματα εντός του ίδιου εγγράφου XPS.

## Κοινά προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| Η εικόνα δεν εμφανίζεται | Επαληθεύστε ότι η διαδρομή αρχείου (`dataDir + "R08LN_NN.jpg"`) είναι σωστή και ότι η εικόνα είναι προσβάσιμη. |
| Το μοτίβο πλακιδίων εμφανίζεται τεντωμένο | Προσαρμόστε τις τιμές του `Rectangle2D` πηγής και προορισμού για να ελέγξετε το μέγεθος των πλακιδίων. |
| Η αδιαφάνεια δεν έχει αποτέλεσμα | Βεβαιωθείτε ότι η αδιαφάνεια του πινέλου έχει οριστεί **μετά** τη ρύθμιση του tile mode. |

## Συχνές ερωτήσεις

**Q:** Είναι το Aspose.Page συμβατό με όλες τις εκδόσεις Java;  
**A:** Το Aspose.Page υποστηρίζει Java 8 έως Java 21· μπορείτε να βρείτε τον πλήρη πίνακα συμβατότητας [εδώ](https://reference.aspose.com/page/java/).

**Q:** Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;  
**A:** Ναι, απαιτείται εμπορική άδεια για χρήση σε παραγωγή. Οι επιλογές αγοράς αναφέρονται [εδώ](https://purchase.aspose.com/buy).

**Q:** Υπάρχει διαθέσιμη δωρεάν δοκιμή;  
**A:** Μπορείτε να κατεβάσετε μια πλήρως λειτουργική δωρεάν δοκιμή από τη σελίδα κυκλοφορίας του Aspose [εδώ](https://releases.aspose.com/).

**Q:** Πού μπορώ να βρω υποστήριξη από την κοινότητα;  
**A:** Εγγραφείτε στο φόρουμ κοινότητας Aspose.Page στο [forum](https://forum.aspose.com/c/page/39) για να κάνετε ερωτήσεις και να μοιραστείτε παραδείγματα.

**Q:** Πώς μπορώ να αποκτήσω προσωρινή άδεια για αξιολόγηση;  
**A:** Οι προσωρινές άδειες παρέχονται κατόπιν αιτήματος μέσω της πύλης Aspose [εδώ](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή ροή εργασίας για **πώς να δημιουργήσετε XPS** έγγραφα με εικόνες σε μοτίβο πλακιδίων χρησιμοποιώντας το Aspose.Page for Java. Εκμεταλλευόμενοι το `XpsImageBrush` και το `XpsTileMode.Tile`, μπορείτε να δημιουργήσετε πλούσια, επαναλαμβανόμενα γραφικά χωρίς να αυξήσετε το μέγεθος του αρχείου. Πειραματιστείτε με διαφορετικά μεγέθη πλακιδίων, επίπεδα αδιαφάνειας και σχήματα για να δημιουργήσετε σύνθετες διατάξεις εγγράφων. Στο επόμενο βήμα, εξερευνήστε την προσθήκη διανυσματικών σχημάτων ή κειμένου για περαιτέρω βελτίωση των αρχείων XPS σας.

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικές οδηγίες

- [Πώς να προσθέσετε εικόνα σε έγγραφα XPS Java – Ένας απλός οδηγός με Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Προσθήκη σελίδων σε οδηγό XPS](/page/java/xps-page-manipulation/add-page/)
- [Μετατροπή XPS σε PDF σε Java χρησιμοποιώντας Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}