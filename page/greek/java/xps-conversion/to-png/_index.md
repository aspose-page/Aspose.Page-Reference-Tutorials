---
date: 2026-05-25
description: Μάθετε πώς να μετατρέψετε XPS σε PNG σε Java με το Aspose.Page, παρέχοντας
  μια αξιόπιστη, φιλική προς τους προγραμματιστές λύση για την απόδοση εγγράφων XPS
  σε εικόνες PNG υψηλής ποιότητας.
keywords:
- how to convert xps
- XPS to PNG conversion
- Aspose.Page Java
linktitle: Πώς να μετατρέψετε XPS σε PNG σε Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to convert XPS to PNG in Java with Aspose.Page, providing
    a reliable, developer‑friendly solution for rendering XPS documents to high‑quality
    PNG images.
  headline: How to Convert XPS to PNG in Java
  type: TechArticle
- description: Learn how to convert XPS to PNG in Java with Aspose.Page, providing
    a reliable, developer‑friendly solution for rendering XPS documents to high‑quality
    PNG images.
  name: How to Convert XPS to PNG in Java
  steps:
  - name: Set Document Directory
    text: Define the folders that contain the source XPS file and where the PNG files
      will be saved. This keeps your project organized and makes path handling straightforward.
  - name: Load XPS Document
    text: The `XpsDocument` class represents an XPS file and provides methods to access
      its pages for rendering.
  - name: Initialize Options
    text: '`PngSaveOptions` configures PNG output parameters such as resolution, compression,
      and selected pages.'
  - name: Create Rendering Device
    text: '`ImageDevice` is the rendering target that captures the bitmap data produced
      by Aspose.Page. It stores each page as a byte array ready to be written to a
      file.'
  - name: Save and Iterate
    text: 'Loop through the rendered pages, write each PNG byte array to the output
      directory, and release resources after each write. This pattern minimizes memory
      consumption even for multi‑hundred‑page XPS files. By following these five steps,
      you can effortlessly render XPS to PNG images using Aspose.Page '
  type: HowTo
- questions:
  - answer: Absolutely. Use the `setPageNumbers` method in `PngSaveOptions` to specify
      the pages you want to render.
    question: Can I convert only selected pages of an XPS file?
  - answer: A resolution of **300 dpi** balances clarity and file size, but you can
      adjust it via `options.setResolution()` to suit your needs.
    question: What image resolution is recommended for high‑quality PNGs?
  - answer: Yes. You can invoke the conversion logic in parallel threads, each handling
      a different page or document partition, to speed up processing.
    question: Does the API support multi‑threaded conversion for large documents?
  - answer: Process pages one at a time and release the `FileOutputStream` after each
      write, as demonstrated in the step‑by‑step guide.
    question: How do I handle memory usage when converting very large XPS files?
  - answer: While `PngSaveOptions` does not expose metadata fields directly, you can
      post‑process the PNG with standard image libraries (e.g., Apache Commons Imaging)
      to embed custom tags.
    question: Is there a way to add custom metadata to the generated PNG files?
  type: FAQPage
second_title: Aspose.Page Java API
title: Πώς να μετατρέψετε XPS σε PNG σε Java
url: /el/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Μετατρέψετε XPS σε PNG σε Java

## Εισαγωγή
Στον δυναμικό κόσμο της ανάπτυξης λογισμικού, η εκμάθηση **πώς να μετατρέψετε XPS** σε PNG (XML Paper Specification σε Portable Network Graphics) είναι συχνή απαίτηση. Το Aspose.Page for Java παρέχει έναν γρήγορο, αποδοτικό σε μνήμη τρόπο για την απόδοση σελίδων XPS ως εικόνες PNG χωρίς απώλειες, καθιστώντας το ιδανικό για προεπισκοπήσεις ιστού, αναφορές και δημιουργία μικρογραφιών.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή;** Aspose.Page for Java  
- **Ποιοι μορφές εμπλέκονται;** XPS (πηγή) → PNG (έξοδος)  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται εμπορική άδεια  
- **Μπορώ να ορίσω την ανάλυση της εικόνας;** Ναι, μέσω `PngSaveOptions.setResolution()`  
- **Είναι δυνατόν να επιλέξετε συγκεκριμένες σελίδες;** Απόλυτα – δώστε τους αριθμούς σελίδων στο αντικείμενο επιλογών  

## Γιατί να Μετατρέψετε XPS σε PNG;
Η μετατροπή XPS σε PNG επιτρέπει οπτικά υλικά υψηλής ποιότητας, χωρίς απώλειες, που εμφανίζονται σταθερά σε όλα τα προγράμματα περιήγησης. Το Aspose.Page υποστηρίζει **30+ μορφές εξόδου εικόνας** και μπορεί να αποδώσει ένα έγγραφο XPS 500 σελίδων σε λιγότερο από 30 δευτερόλεπτα σε έναν τυπικό διακομιστή, εξαλείφοντας την ανάγκη για βαριές μηχανές απόδοσης.

## Προαπαιτούμενα
Πριν προχωρήσουμε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Page for Java** – Κατεβάστε τη βιβλιοθήκη από την επίσημη ιστοσελίδα **[εδώ](https://releases.aspose.com/page/java/)**.  
3. **IDE** – IntelliJ IDEA, Eclipse ή οποιοδήποτε περιβάλλον συμβατό με Java που προτιμάτε.  

## Πώς να Μετατρέψετε XPS σε PNG σε Java

Η διαδικασία μετατροπής περιλαμβάνει τη φόρτωση του εγγράφου XPS, τη διαμόρφωση των ρυθμίσεων εξόδου PNG, την απόδοση κάθε σελίδας σε συσκευή εικόνας και την εγγραφή των παραγόμενων δεδομένων PNG σε αρχεία. Ακολουθώντας αυτά τα πέντε σύντομα βήματα, μπορείτε να μετατρέψετε αποδοτικά οποιοδήποτε αρχείο XPS σε εικόνες PNG υψηλής ποιότητας, διατηρώντας χαμηλή χρήση μνήμης.

### Βήμα 1: Ορισμός Καταλόγου Εγγράφου
Ορίστε τους φακέλους που περιέχουν το αρχείο XPS προέλευσης και όπου θα αποθηκευτούν τα αρχεία PNG. Αυτό διατηρεί το έργο σας οργανωμένο και καθιστά τη διαχείριση διαδρομών απλή.

### Βήμα 2: Φόρτωση Εγγράφου XPS
Η κλάση `XpsDocument` αντιπροσωπεύει ένα αρχείο XPS και παρέχει μεθόδους για πρόσβαση στις σελίδες του για απόδοση.

### Βήμα 3: Αρχικοποίηση Επιλογών
`PngSaveOptions` διαμορφώνει τις παραμέτρους εξόδου PNG όπως ανάλυση, συμπίεση και επιλεγμένες σελίδες.

### Βήμα 4: Δημιουργία Συσκευής Απόδοσης
`ImageDevice` είναι ο στόχος απόδοσης που συλλαμβάνει τα δεδομένα bitmap που παράγονται από το Aspose.Page. Αποθηκεύει κάθε σελίδα ως πίνακα byte έτοιμο για εγγραφή σε αρχείο.

### Βήμα 5: Αποθήκευση και Επανάληψη
Επαναλάβετε τις αποδομένες σελίδες, γράψτε κάθε πίνακα byte PNG στον φάκελο εξόδου και απελευθερώστε τους πόρους μετά από κάθε εγγραφή. Αυτό το μοτίβο ελαχιστοποιεί την κατανάλωση μνήμης ακόμη και για αρχεία XPS με εκατοντάδες σελίδες.

Ακολουθώντας αυτά τα πέντε βήματα, μπορείτε εύκολα να αποδώσετε εικόνες XPS σε PNG χρησιμοποιώντας το Aspose.Page for Java.

## Συχνά Προβλήματα και Λύσεις
- **Αιχμές μνήμης σε τεράστια αρχεία XPS** – Επεξεργαστείτε τις σελίδες διαδοχικά και κλείστε το `FileOutputStream` μετά από κάθε εγγραφή.  
- **Λανθασμένα χρώματα ή anti‑aliasing** – Βεβαιωθείτε ότι το `PngSaveOptions.setSmoothingMode(SmoothingMode.HighQuality)` είναι ενεργοποιημένο.  
- **Απουσία γραμματοσειρών** – Ενσωματώστε τις απαιτούμενες γραμματοσειρές στην πηγή XPS ή εγκαταστήστε τις στον διακομιστή πριν από τη μετατροπή.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να μετατρέψω μόνο επιλεγμένες σελίδες ενός αρχείου XPS;**  
Α: Απόλυτα. Χρησιμοποιήστε τη μέθοδο `setPageNumbers` στο `PngSaveOptions` για να καθορίσετε τις σελίδες που θέλετε να αποδώσετε.

**Ε: Ποια ανάλυση εικόνας συνιστάται για PNG υψηλής ποιότητας;**  
Α: Μια ανάλυση **300 dpi** ισορροπεί την καθαρότητα και το μέγεθος του αρχείου, αλλά μπορείτε να την προσαρμόσετε μέσω `options.setResolution()` ανάλογα με τις ανάγκες σας.

**Ε: Υποστηρίζει το API μετατροπή πολλαπλών νημάτων για μεγάλα έγγραφα;**  
Α: Ναι. Μπορείτε να εκτελέσετε τη λογική μετατροπής σε παράλληλα νήματα, το καθένα να διαχειρίζεται διαφορετική σελίδα ή τμήμα εγγράφου, για να επιταχύνετε την επεξεργασία.

**Ε: Πώς να διαχειριστώ τη χρήση μνήμης όταν μετατρέπω πολύ μεγάλα αρχεία XPS;**  
Α: Επεξεργαστείτε τις σελίδες μία τη φορά και απελευθερώστε το `FileOutputStream` μετά από κάθε εγγραφή, όπως δείχνεται στον οδηγό βήμα‑βήμα.

**Ε: Υπάρχει τρόπος να προσθέσω προσαρμοσμένα μεταδεδομένα στα παραγόμενα αρχεία PNG;**  
Α: Παρόλο που το `PngSaveOptions` δεν εκθέτει πεδία μεταδεδομένων άμεσα, μπορείτε να επεξεργαστείτε μεταγενέστερα το PNG με τυπικές βιβλιοθήκες εικόνας (π.χ., Apache Commons Imaging) για να ενσωματώσετε προσαρμοσμένες ετικέτες.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

## Σχετικά Μαθήματα

- [Μετατροπή XPS σε PDF σε Java χρησιμοποιώντας Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)
- [Μετατροπή XSP σε TIFF σε Java χρησιμοποιώντας Aspose.Page Java](/page/java/xps-conversion/to-tiff/)
- [Πώς να Συγχωνεύσετε Αρχεία XPS σε Java με Aspose.Page](/page/java/file-merging/xps-to-xps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}