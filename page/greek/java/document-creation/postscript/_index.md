---
date: 2026-06-20
description: Μάθετε πώς να ορίσετε το μέγεθος σελίδας A4, να δημιουργήσετε αρχεία
  PostScript σε Java και να προσθέσετε προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας
  το Aspose.Page. Δοκιμάστε τη δωρεάν δοκιμή σήμερα!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Δημιουργία εγγράφου σε Java με PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Πώς να ορίσετε το μέγεθος σελίδας A4 και να δημιουργήσετε PostScript σε Java
  με Aspose.Page
url: /el/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε το μέγεθος σελίδας A4 και να δημιουργήσετε PostScript σε Java με το Aspose.Page

## Εισαγωγή
Αν χρειάζεται να **ορίσετε το μέγεθος σελίδας a4** κατά τη δημιουργία αρχείων PostScript από Java, το Aspose.Page παρέχει ένα γρήγορο, αξιόπιστο API που κρύβει τις λεπτομέρειες χαμηλού επιπέδου. Σε αυτό το tutorial θα περάσουμε από όλη τη διαδικασία — δημιουργία εγγράφου PostScript, ρύθμιση των διαστάσεων σελίδας A4, και **προσθήκη προσαρμοσμένων γραμματοσειρών** όταν απαιτείται. Στο τέλος θα έχετε ένα έτοιμο κομμάτι κώδικα που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο Java.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί PostScript σε Java;** Aspose.Page for Java.  
- **Ποιο μέγεθος σελίδας στοχεύει αυτός ο οδηγός;** A4 (210 mm × 297 mm).  
- **Μπορώ να ενσωματώσω τις δικές μου γραμματοσειρές;** Yes – set the additional fonts folder in the save options.  
- **Χρειάζομαι άδεια για παραγωγή;** A commercial license is required; a free trial is available.  
- **Ποιες εκδόσεις Java υποστηρίζονται;** Java 8 and later.

## Πώς να ορίσετε το μέγεθος σελίδας a4 και να δημιουργήσετε postscript σε Java
Φορτώστε τη βιβλιοθήκη Aspose.Page, ρυθμίστε το `PsSaveOptions` με τις σταθερές A4 και γράψτε το έγγραφο σε αρχείο — όλα σε λιγότερο από δέκα γραμμές κώδικα. Αυτή η άμεση προσέγγιση εγγυάται τις σωστές διαστάσεις σελίδας και σας επιτρέπει να προσθέσετε προσαρμοσμένες γραμματοσειρές χωρίς επιπλέον ρυθμίσεις.

## Τι είναι το μέγεθος postscript a4;
Το μέγεθος PostScript A4 είναι το πρότυπο ISO 216 (210 mm × 297 mm) εκφρασμένο στη γλώσσα περιγραφής σελίδας PostScript. Ορίζει την εκτυπώσιμη περιοχή που ερμηνεύουν οι εκτυπωτές και οι προβολείς, εξασφαλίζοντας συνεπή διάταξη σε όλες τις πλατφόρμες. Επειδή το PostScript περιγράφει το περιεχόμενο της σελίδας με ανεξάρτητο από τη συσκευή τρόπο, η χρήση του μεγέθους A4 εγγυάται ότι το έγγραφο θα εμφανίζεται το ίδιο σε οποιονδήποτε εκτυπωτή ή προβολέα που υποστηρίζει A4 παγκοσμίως.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για να ορίσετε το μέγεθος σελίδας postscript;
Το Aspose.Page υποστηρίζει **30+ PostScript operators** και μπορεί να δημιουργήσει αρχεία έως **500 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη. Αυτό σας δίνει ακριβή έλεγχο των διαστάσεων της σελίδας ενώ διαχειρίζεται μεγάλες εργασίες αποδοτικά. Η βιβλιοθήκη επίσης αφαιρεί την πολυπλοκότητα της σύνταξης PostScript, διαχειρίζεται αυτόματα τους πόρους και παρέχει υψηλής απόδοσης streaming, καθιστώντας την ιδανική τόσο για απλά φυλλάδια μιας σελίδας όσο και για σύνθετες αναφορές πολλαπλών σελίδων.

## Πώς να προσθέσετε προσαρμοσμένες γραμματοσειρές java
Η ενσωμάτωση των δικών σας γραμματοσειρών εξασφαλίζει ότι το παραγόμενο έγγραφο θα εμφανίζεται ακριβώς όπως σχεδιάστηκε σε οποιονδήποτε εκτυπωτή ή προβολέα, και το Aspose.Page εντοπίζει αυτόματα τις γραμματοσειρές που τοποθετούνται στον καθορισμένο φάκελο. Με την καταχώριση ενός πρόσθετου φακέλου γραμματοσειρών, μπορείτε να χρησιμοποιήσετε οποιαδήποτε γραμματοσειρά TrueType ή OpenType, να αποφύγετε τις εναλλακτικές αντικαταστάσεις και να διατηρήσετε τη συνέπεια του brand σε όλες τις συσκευές εξόδου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Καλή γνώση προγραμματισμού Java.  
- Aspose.Page for Java εγκατεστημένο. Μπορείτε να το κατεβάσετε [εδώ](https://releases.aspose.com/page/java/).  
- Έναν φάκελο με όνομα `necessary_fonts` (ή οποιοδήποτε όνομα προτιμάτε) που περιέχει τις προσαρμοσμένες γραμματοσειρές που θέλετε να ενσωματώσετε.

## Εισαγωγή Πακέτων
Στο έργο Java, εισάγετε τις απαιτούμενες κλάσεις του Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Τώρα ας χωρίσουμε το παράδειγμα σε σαφή, αριθμημένα βήματα.

### Βήμα 1: Ορίστε τον Κατάλογο Εγγράφου
Η σταθερά `OUTPUT_DIR` λέει στη βιβλιοθήκη πού να γράψει το παραγόμενο αρχείο.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Βήμα 2: Ορίστε τον Φάκελο Γραμματοσειρών
`FONTS_FOLDER` δείχνει στον κατάλογο που περιέχει τις προσαρμοσμένες γραμματοσειρές TrueType ή OpenType.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Βήμα 3: Δημιουργήστε Ροή Εξόδου για το Έγγραφο PostScript
`FileOutputStream` ανοίγει μια ροή που θα λάβει το τελικό PostScript A4 output.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Βήμα 4: Δημιουργήστε Επιλογές Αποθήκευσης με Μέγεθος A4
`PsSaveOptions` σας επιτρέπει να καθορίσετε το επιθυμητό μέγεθος σελίδας.  
**Definition:** `PsPageSize` είναι μια απαρίθμηση που περιέχει σταθερές τυπικών μεγεθών σελίδας όπως A4, Letter και Legal.  
Η ρύθμιση `options.setPageSize(PsPageSize.A4)` διαμορφώνει το έγγραφο για τις τυπικές διαστάσεις A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Βήμα 5: Ορίστε τα Περιθώρια Σελίδας και Προσθέστε Φάκελο Προσαρμοσμένων Γραμματοσειρών
`options.setMargins(0, 0, 0, 0)` αφαιρεί όλα τα περιθώρια για πλήρη εκτύπωση, και `options.setAdditionalFontsFolder(FONTS_FOLDER)` καταχωρεί τις προσαρμοσμένες γραμματοσειρές σας.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Βήμα 6: Δημιουργήστε Έγγραφο PS Πολλαπλών ή Μονής Σελίδας
`PsDocument document = new PsDocument(outputStream, options)` δημιουργεί το έγγραφο. Το `PsDocument` αντιπροσωπεύει ένα έγγραφο PostScript που μπορεί να περιέχει μία ή πολλές σελίδες. Ορίστε `multiPaged` σε `true` για έξοδο πολλαπλών σελίδων.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Βήμα 7: Κλείστε την Τρέχουσα Σελίδα και Αποθηκεύστε το Έγγραφο
Καλώντας `document.close()` ολοκληρώνεται το αρχείο και γράφεται η **PostScript A4 size** έξοδος στο δίσκο.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Συχνά Προβλήματα & Συμβουλές
- **Font not appearing?** Verify the font file is a supported TrueType or OpenType format and that `FONTS_FOLDER` ends with a slash (`/`).  
- **Margins still showing?** Call `options.setMargins(...)` **before** constructing the `PsDocument`.  
- **Multi‑page output looks blank?** Remember to invoke `document.newPage()` for each additional page you need.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω προσαρμοσμένες γραμματοσειρές στο έγγραφο PostScript μου;**  
Α: Yes, set the additional fonts folder in the save options (see Step 5) and Aspose.Page will embed the fonts automatically.

**Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Page for Java;**  
Α: Yes, you can get a free trial [here](https://releases.aspose.com/).

**Ε: Πώς μπορώ να έχω πρόσβαση στην πλήρη αναφορά API;**  
Α: Refer to the documentation [here](https://reference.aspose.com/page/java/).

**Ε: Πού μπορώ να αγοράσω άδεια για το Aspose.Page for Java;**  
Α: You can buy a license [here](https://purchase.aspose.com/buy).

**Ε: Πού μπορώ να ζητήσω βοήθεια από την κοινότητα;**  
Α: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).

**Ε: Μπορώ να δημιουργήσω αρχεία PostScript πολλαπλών σελίδων;**  
Α: Absolutely—set `multiPaged` to `true` in Step 6 and call `document.newPage()` for each extra page.

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε **πώς να ορίσετε το μέγεθος σελίδας a4** και να δημιουργήσετε αρχεία **PostScript** σε Java με το Aspose.Page, ενώ μπορείτε επίσης να **προσθέσετε προσαρμοσμένες γραμματοσειρές java** και να ελέγξετε τις επιλογές μεγέθους σελίδας. Το Aspose.Page αναλαμβάνει το δύσκολο μέρος, ώστε εσείς να εστιάσετε στο περιεχόμενο των εγγράφων σας.

---

**Τελευταία Ενημέρωση:** 2026-06-20  
**Δοκιμάστηκε με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Aspose.Page Java Tutorial – ορίστε προσαρμοσμένο μέγεθος σελίδας ενώ Προσθέτετε Σελίδες σε PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Πώς να Προσθέσετε Κείμενο σε PostScript με το Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Μετατροπή PostScript σε PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```