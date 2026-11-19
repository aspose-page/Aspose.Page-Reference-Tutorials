---
date: 2026-11-19
description: Μάθετε πώς να δημιουργήσετε αρχεία PostScript σε Java, ορίστε το μέγεθος
  σελίδας A4 και προσθέστε προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας το Aspose.Page.
  Δοκιμάστε τη δωρεάν δοκιμή σήμερα!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: Δημιουργία εγγράφου σε Java με PostScript
og_description: Μάθετε πώς να δημιουργήσετε αρχείο PostScript σε Java, ορίστε το μέγεθος
  σελίδας A4 και προσθέστε προσαρμοσμένες γραμματοσειρές με το Aspose.Page. Οδηγός
  γρήγορης εκκίνησης για προγραμματιστές.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: Δημιουργία αρχείου PostScript σε Java με μέγεθος A4 χρησιμοποιώντας το Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: Πώς να δημιουργήσετε αρχείο PostScript σε Java με μέγεθος A4
url: /el/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε αρχείο PostScript σε Java με μέγεθος A4

## Εισαγωγή
Αν χρειάζεστε **create PostScript file Java** ενώ ορίζετε τις τυπικές διαστάσεις σελίδας A4, το Aspose.Page for Java σας παρέχει ένα σύντομο, υψηλής απόδοσης API που αφαιρεί τη χαμηλού επιπέδου σύνταξη PostScript. Σε αυτό το tutorial θα περάσουμε βήμα προς βήμα—από τη φόρτωση της βιβλιοθήκης και τη διαμόρφωση του `PsSaveOptions` μέχρι την ενσωμάτωση των δικών σας γραμματοσειρών TrueType ή OpenType. Στο τέλος θα έχετε ένα έτοιμο κομμάτι κώδικα που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο Java.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί PostScript σε Java;** Aspose.Page for Java.  
- **Ποιο μέγεθος σελίδας στοχεύει αυτό το οδηγό;** A4 (210 mm × 297 mm).  
- **Μπορώ να ενσωματώσω τις δικές μου γραμματοσειρές;** Ναι – ορίστε το πρόσθετο φάκελο γραμματοσειρών στις επιλογές αποθήκευσης.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια· διατίθεται δωρεάν δοκιμή.  
- **Ποιες εκδόσεις Java υποστηρίζονται;** Java 8, 11 και 17 υποστηρίζονται πλήρως.

## Πώς να ορίσετε μέγεθος σελίδας A4 και να δημιουργήσετε PostScript σε Java;
Φορτώστε τη βιβλιοθήκη Aspose.Page, διαμορφώστε το `PsSaveOptions` με τις σταθερές A4 και γράψτε το έγγραφο σε αρχείο – όλα σε λιγότερο από δέκα γραμμές κώδικα. Αυτή η προσέγγιση εγγυάται τις σωστές διαστάσεις σελίδας και σας επιτρέπει να προσθέσετε προσαρμοσμένες γραμματοσειρές χωρίς επιπλέον ρύθμιση.

## Τι είναι το μέγεθος PostScript A4;
Το μέγεθος PostScript A4 είναι το πρότυπο ISO 216 (210 mm × 297 mm) που εκφράζεται στη γλώσσα περιγραφής σελίδων PostScript. Ορίζει την εκτυπώσιμη περιοχή που ερμηνεύουν οι εκτυπωτές και οι προβολείς, εξασφαλίζοντας συνεπή διάταξη σε όλες τις πλατφόρμες. Επειδή το PostScript περιγράφει το περιεχόμενο της σελίδας με ανεξάρτητο από τη συσκευή τρόπο, η χρήση του μεγέθους A4 εγγυάται ότι το έγγραφο θα εμφανίζεται το ίδιο σε οποιονδήποτε εκτυπωτή ή προβολέα που υποστηρίζει A4 παγκοσμίως.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για να ορίσετε το μέγεθος σελίδας PostScript;
Το Aspose.Page υποστηρίζει πάνω από 30 τελεστές PostScript και μπορεί να δημιουργήσει αρχεία έως 500 MB χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη. Επεξεργάζεται ένα έγγραφο 200 σελίδων σε λιγότερο από 2 δευτερόλεπτα, παρέχοντας ακριβή έλεγχο των διαστάσεων της σελίδας ενώ διαχειρίζεται μεγάλες εργασίες αποδοτικά. Η βιβλιοθήκη επίσης αφαιρεί την πολυπλοκότητα της σύνταξης PostScript και διαχειρίζεται αυτόματα τους πόρους, καθιστώντας την ιδανική τόσο για απλά φυλλάδια όσο και για σύνθετες αναφορές πολλαπλών σελίδων.

## Πώς να προσθέσετε προσαρμοσμένες γραμματοσειρές Java
Η ενσωμάτωση των δικών σας τύπων γραμματοσειρών εξασφαλίζει ότι το παραγόμενο έγγραφο φαίνεται ακριβώς όπως σχεδιάστηκε σε οποιονδήποτε εκτυπωτή ή προβολέα, και το Aspose.Page εντοπίζει αυτόματα τις γραμματοσειρές που τοποθετούνται στον καθορισμένο φάκελο. Με την καταχώριση ενός πρόσθετου φακέλου γραμματοσειρών, μπορείτε να χρησιμοποιήσετε οποιαδήποτε γραμματοσειρά TrueType ή OpenType, να αποφύγετε τις εναλλακτικές αντικαταστάσεις και να διατηρήσετε τη συνοχή της μάρκας σε όλες τις συσκευές εξόδου.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Μια λειτουργική γνώση του προγραμματισμού Java.  
- Το Aspose.Page for Java εγκατεστημένο. Μπορείτε να το κατεβάσετε από τη [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Ένα φάκελο με όνομα `necessary_fonts` (ή οποιοδήποτε όνομα προτιμάτε) που περιέχει τις προσαρμοσμένες γραμματοσειρές που θέλετε να ενσωματώσετε.

## Εισαγωγή πακέτων
Στο έργο Java σας, εισάγετε τις απαιτούμενες κλάσεις του Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Τώρα ας χωρίσουμε το παράδειγμα σε σαφή, αριθμημένα βήματα.

### Βήμα 1: ορίστε τον φάκελο εγγράφου
Η σταθερά `OUTPUT_DIR` λέει στη βιβλιοθήκη πού να γράψει το παραγόμενο αρχείο.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Βήμα 2: ορίστε το φάκελο γραμματοσειρών
`FONTS_FOLDER` δείχνει στον κατάλογο που περιέχει τις προσαρμοσμένες γραμματοσειρές TrueType ή OpenType.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Βήμα 3: δημιουργήστε ροή εξόδου για το έγγραφο PostScript
`FileOutputStream` ανοίγει μια ροή που θα λάβει την τελική έξοδο PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Βήμα 4: δημιουργήστε επιλογές αποθήκευσης με μέγεθος A4
`PsSaveOptions` ορίζει πώς αποθηκεύεται το έγγραφο PostScript, συμπεριλαμβανομένου του μεγέθους σελίδας, των περιθωρίων και της συμπίεσης.  
**Ορισμός:** `PsPageSize` είναι μια απαρίθμηση που περιέχει σταθερές τυπικών μεγεθών σελίδας όπως A4, Letter και Legal.  
Ορίζοντας `options.setPageSize(PsPageSize.A4)` ρυθμίζει το έγγραφο στις τυπικές διαστάσεις A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Βήμα 5: ορίστε τα περιθώρια σελίδας και προσθέστε φάκελο προσαρμοσμένων γραμματοσειρών
`options.setMargins(0, 0, 0, 0)` αφαιρεί όλα τα περιθώρια για σελίδα πλήρους εκτύπωσης, και `options.setAdditionalFontsFolder(FONTS_FOLDER)` καταχωρίζει τις προσαρμοσμένες γραμματοσειρές σας.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Βήμα 6: δημιουργήστε ένα πολυσελιδικό ή μονοσέλιδο έγγραφο PS
`PsDocument` αντιπροσωπεύει ένα έγγραφο PostScript που μπορεί να περιέχει μία ή πολλές σελίδες. Η δημιουργία του με `new PsDocument(outputStream, options)` δημιουργεί το αντικείμενο εγγράφου. Ορίστε `multiPaged` σε `true` για έξοδο πολλαπλών σελίδων, στη συνέχεια καλέστε `document.newPage()` για κάθε επιπλέον σελίδα που χρειάζεστε.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Βήμα 7: κλείστε την τρέχουσα σελίδα και αποθηκεύστε το έγγραφο
Καλώντας το `document.close()` ολοκληρώνεται το αρχείο και γράφει την έξοδο **PostScript A4 size** στον δίσκο.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Κοινά προβλήματα & συμβουλές
- **Η γραμματοσειρά δεν εμφανίζεται;** Επαληθεύστε ότι το αρχείο γραμματοσειράς είναι σε υποστηριζόμενη μορφή TrueType ή OpenType και ότι το `FONTS_FOLDER` τελειώνει με κάθετο (`/`).  
- **Τα περιθώρια εξακολουθούν να εμφανίζονται;** Καλέστε το `options.setMargins(...)` **πριν** τη δημιουργία του `PsDocument`.  
- **Η έξοδος πολλαπλών σελίδων φαίνεται κενή;** Θυμηθείτε να καλέσετε `document.newPage()` για κάθε επιπλέον σελίδα που χρειάζεστε.  
- **Τα μεγάλα αρχεία προκαλούν σφάλματα έλλειψης μνήμης;** Το Aspose.Page μεταδίδει δεδομένα σε ροή, έτσι μπορείτε με ασφάλεια να δημιουργήσετε αρχεία έως 500 MB· απλώς βεβαιωθείτε ότι η μνήμη heap του JVM είναι τουλάχιστον 1 GB για πολύ μεγάλα φορτία εργασίας.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω προσαρμοσμένες γραμματοσειρές στο έγγραφο PostScript μου;**  
A: Ναι, ορίστε το πρόσθετο φάκελο γραμματοσειρών στις επιλογές αποθήκευσης (δείτε το Βήμα 5) και το Aspose.Page θα ενσωματώσει τις γραμματοσειρές αυτόματα.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Page for Java;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή στη [Aspose.Page free trial page](https://releases.aspose.com/).

**Q: Πώς μπορώ να έχω πρόσβαση στην πλήρη τεκμηρίωση API;**  
A: Ανατρέξτε στην τεκμηρίωση [API reference documentation](https://reference.aspose.com/page/java/).

**Q: Πού μπορώ να αγοράσω άδεια για το Aspose.Page for Java;**  
A: Μπορείτε να αγοράσετε άδεια στη [license purchase page](https://purchase.aspose.com/buy).

**Q: Πού μπορώ να ζητήσω βοήθεια από την κοινότητα;**  
A: Επισκεφθείτε το φόρουμ της κοινότητας Aspose.Page [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

**Q: Μπορώ να δημιουργήσω αρχεία PostScript πολλαπλών σελίδων;**  
A: Απόλυτα—ορίστε το `multiPaged` σε `true` στο Βήμα 6 και καλέστε `document.newPage()` για κάθε επιπλέον σελίδα.

## Συμπέρασμα
Ακολουθώντας αυτά τα βήματα, τώρα γνωρίζετε **how to create PostScript file Java** και πώς να ορίσετε **A4 page size** χρησιμοποιώντας το Aspose.Page, ενώ μπορείτε επίσης να **add custom fonts java** και να ελέγξετε τις επιλογές μεγέθους σελίδας. Το Aspose.Page αναλαμβάνει το δύσκολο κομμάτι, ώστε να μπορείτε να εστιάσετε στο περιεχόμενο των εγγράφων σας αντί στις λεπτομέρειες της γλώσσας PostScript.

---

**Τελευταία ενημέρωση:** 2026-11-19  
**Δοκιμή με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose  

## Σχετικές οδηγίες

- [Aspose.Page Java Tutorial – ορίστε προσαρμοσμένο μέγεθος σελίδας ενώ προσθέτετε σελίδες σε PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Πώς να προσθέσετε κείμενο σε PostScript με Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Μετατροπή PostScript σε PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}