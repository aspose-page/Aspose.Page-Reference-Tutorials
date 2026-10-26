---
date: 2026-10-25
description: Μάθετε πώς να ορίζετε προσαρμοσμένο μέγεθος σελίδας και να προσθέτετε
  σελίδες σε έγγραφα Java PostScript χρησιμοποιώντας το Aspose.Page. Ακολουθήστε τον
  οδηγό βήμα‑βήμα για αδιάλειπτη διαχείριση εγγράφων.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Προσθήκη σελίδων σε PostScript
og_description: Μάθετε πώς να ορίζετε προσαρμοσμένο μέγεθος σελίδας σε PostScript
  χρησιμοποιώντας το Aspose.Page για Java. Ακολουθήστε οδηγίες βήμα‑βήμα για την προσθήκη
  σελίδων, τον καθορισμό διαστάσεων και την αποθήκευση του εγγράφου αποδοτικά.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Ορίστε προσαρμοσμένο μέγεθος σελίδας σε PostScript με Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Aspose.Page Java Tutorial – ορίστε προσαρμοσμένο μέγεθος σελίδας κατά την προσθήκη
  σελίδων σε PostScript
url: /el/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java Tutorial – ορισμός προσαρμοσμένου μεγέθους σελίδας κατά την προσθήκη σελίδων σε PostScript

## Εισαγωγή
Σε σύγχρονες εφαρμογές Java, η **ρύθμιση προσαρμοσμένου μεγέθους σελίδας** για έξοδο PostScript είναι συχνά απαραίτητη — είτε δημιουργείτε τιμολόγια, εισιτήρια ή προσαρμοσμένα γραφικά. Αυτό το μάθημα σας δείχνει πώς να ορίσετε προσαρμοσμένο μέγεθος σελίδας για κάθε σελίδα, να προσθέσετε πολλαπλές σελίδες και να δημιουργήσετε ένα αρχείο PostScript που ταιριάζει ακριβώς στις ανάγκες διάταξής σας. Θα λάβετε ένα πλήρες, εκτελέσιμο παράδειγμα που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο Java 8+.

## Γρήγορες απαντήσεις
- **Μπορώ να ορίσω διαφορετικά μεγέθη σελίδας για κάθε σελίδα;** Ναι — μπορείτε να ανοίξετε σελίδες με προσαρμοσμένες διαστάσεις χρησιμοποιώντας `document.openPage(width, height)`.  
- **Χρειάζεται άδεια για παραγωγική χρήση;** Απαιτείται έγκυρη άδεια Aspose.Page για μη‑αξιολογικές εκδόσεις.  
- **Ποιες εκδόσεις Java υποστηρίζονται;** Η βιβλιοθήκη λειτουργεί με Java 8 και νεότερες.  
- **Είναι το API thread‑safe;** Τα αντικείμενα Document δεν είναι thread‑safe· δημιουργήστε ξεχωριστό `PsDocument` ανά νήμα.  
- **Πόσο μεγάλο μπορεί να είναι ένα αρχείο PostScript;** Το Aspose.Page διαχειρίζεται αρχεία πολλαπλών megabytes αποδοτικά· η χρήση μνήμης κλιμακώνεται με το περιεχόμενο, όχι με τον αριθμό σελίδων.  
- **Μπορώ να χρησιμοποιήσω την υπερφόρτωση open page width/height;** Απόλυτα — `openPage(double width, double height)` σας επιτρέπει να καθορίσετε οποιεσδήποτε διαστάσεις σε points.  

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Βασική κατανόηση του προγραμματισμού Java.  
- Το Aspose.Page for Java προστιθέμενο στο έργο σας (Maven/Gradle ή χειροκίνητο JAR).  
- Περιβάλλον ανάπτυξης Java (IDE, JDK 8+).  

## Εισαγωγή πακέτων
Απαιτούνται οι ακόλουθες κλάσεις: `FileOutputStream` για εγγραφή αρχείων, `PsDocument` για δημιουργία εγγράφων PostScript και `PsSaveOptions` για διαμόρφωση επιλογών εξόδου.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Βήμα 1: δημιουργία πολυσελιδικού εγγράφου postscript
`PsDocument` είναι η βασική κλάση που αντιπροσωπεύει ένα έγγραφο PostScript το οποίο μπορεί να περιέχει πολλαπλές σελίδες.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Βήμα 2: προσθήκη περιεχομένου στην πρώτη σελίδα
Με το έγγραφο έτοιμο, μπορείτε να προσθέσετε όποιο περιεχόμενο χρειάζεστε στην πρώτη σελίδα. Όταν τελειώσετε, κλείστε τη σελίδα για να κλειδώσετε το περιεχόμενό της.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Πώς να ορίσετε προσαρμοσμένο μέγεθος σελίδας
Ορίζετε ένα προσαρμοσμένο μέγεθος σελίδας καλώντας `document.openPage(width, height)` με τις επιθυμητές διαστάσεις σε points πριν σχεδιάσετε οποιοδήποτε περιεχόμενο. Η `openPage(width, height)` ανοίγει μια νέα σελίδα με το καθορισμένο πλάτος και ύψος, δίνοντάς σας πλήρη έλεγχο του καμβά της σελίδας. Εάν το προεπιλεγμένο μέγεθος σελίδας δεν είναι αυτό που χρειάζεστε, μπορείτε **να ορίσετε προσαρμοσμένο μέγεθος σελίδας** κατά το άνοιγμα μιας νέας σελίδας. Αυτό είναι χρήσιμο για αποδείξεις, ετικέτες ή οποιαδήποτε μη‑τυπική διάταξη.

## Βήμα 3: προσθήκη δεύτερης σελίδας με διαφορετικό μέγεθος
Παρακάτω ανοίγουμε μια δεύτερη σελίδα και παρέχουμε ρητά ένα προσαρμοσμένο πλάτος και ύψος (σε points). Αυτό δείχνει πώς να ορίσετε προσαρμοσμένο μέγεθος σελίδας για μεμονωμένες σελίδες, δίνοντάς σας τη δυνατότητα να εργάζεστε με **διαφορετικά μεγέθη σελίδας** μέσα στο ίδιο έγγραφο.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Βήμα 4: αποθήκευση του εγγράφου
Τέλος, διατηρήστε τις αλλαγές αποθηκεύοντας το έγγραφο. Όλες οι σελίδες — συμπεριλαμβανομένων εκείνων με προσαρμοσμένα μεγέθη — γράφονται στο αρχείο εξόδου.

```java
// Save the document
document.save();
```

Ακολουθώντας αυτά τα βήματα, μπορείτε να προσθέσετε σελίδες και **να ορίσετε προσαρμοσμένο μέγεθος σελίδας** σε ένα έγγραφο Java PostScript χρησιμοποιώντας το Aspose.Page, αποκτώντας πλήρη έλεγχο της διάταξης κάθε σελίδας.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για ορισμό προσαρμοσμένου μεγέθους σελίδας;
Το Aspose.Page παρέχει ακριβή έλεγχο των διαστάσεων της σελίδας, επιτρέποντάς σας να ορίσετε οποιοδήποτε πλάτος και ύψος σε points, να συνδυάσετε πολλαπλά μεγέθη σε ένα μόνο έγγραφο και να μεταδίδετε το περιεχόμενο αποδοτικά για υψηλής απόδοσης δημιουργία PostScript. Αυτό το καθιστά ιδανικό για τιμολόγια, εισιτήρια και μεγάλου όγκου επεξεργασία παρτίδων όπου η χρήση μνήμης πρέπει να παραμένει χαμηλή.

Το Aspose.Page σας επιτρέπει να ορίζετε ακριβείς διαστάσεις σελίδας σε points, να συνδυάζετε πολλαπλά μεγέθη σε ένα αρχείο και να μεταδίδετε το περιεχόμενο αποδοτικά, προσφέροντας ακριβή έλεγχο και υψηλή απόδοση για τη δημιουργία PostScript.  
- **Ακρίβεια:** Οι διαστάσεις ορίζονται σε points, έτσι έχετε ακριβή έλεγχο του πλάτους και του ύψους της σελίδας.  
- **Ευελιξία:** Συνδυάστε **διαφορετικά μεγέθη σελίδας** σε ένα μόνο αρχείο PostScript.  
- **Απόδοση:** Η βιβλιοθήκη μεταδίδει το περιεχόμενο απευθείας στο αρχείο εξόδου, διαχειριζόμενη αρχεία έως 500 MB διατηρώντας τη χρήση heap κάτω από 100 MB, καθιστώντας την κατάλληλη για μεγάλης κλίμακας **δημιουργία αρχείου PostScript**.  
- **Πλούσιο API:** Υποστηρίζει πάνω από 30 γραφικά primitives, 10 μορφές εικόνας και απεριόριστα αντικείμενα κειμένου ανά σελίδα — όλα ενώ τηρεί τις προσαρμοσμένες διαστάσεις που έχετε ορίσει.

## Κοινά προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|-------|----------|
| **Οι διαστάσεις της σελίδας εμφανίζονται ανταλλαγμένες** | Θυμηθείτε ότι η `openPage(width, height)` απαιτεί πρώτα το πλάτος και μετά το ύψος (και τα δύο σε points). |
| **Το περιεχόμενο υπερβαίνει τη σελίδα** | Χρησιμοποιήστε το σύστημα συντεταγμένων `PsGraphics` για να τοποθετήσετε στοιχεία εντός των προσαρμοσμένων ορίων ή κλιμακώστε το σχέδιό σας. |
| **Σφάλματα Out‑of‑memory σε τεράστια έγγραφα** | Ενεργοποιήστε τη ροή δεδομένων γράφοντας απευθείας σε ένα `FileOutputStream` όπως φαίνεται, και αποφύγετε τη φόρτωση μεγάλων εικόνων στη μνήμη ταυτόχρονα. |

## Συχνές ερωτήσεις
### Μπορώ να προσθέσω σελίδες διαφορετικών μεγεθών σε ένα μόνο έγγραφο PostScript;
Ναι, όπως δείχνει αυτό το μάθημα, μπορείτε να προσθέσετε σελίδες με διαφορετικά μεγέθη σε ένα πολυσελιδικό έγγραφο PostScript.  

### Υπάρχουν περιορισμοί στον αριθμό των σελίδων που μπορώ να προσθέσω;
Το Aspose.Page υποστηρίζει την προσθήκη πρακτικά απεριόριστου αριθμού σελίδων σε ένα έγγραφο.  

### Μπορώ να προσθέσω προσαρμοσμένο περιεχόμενο, όπως εικόνες ή γραφικά, στις σελίδες;
Απόλυτα! Το Aspose.Page επιτρέπει την προσθήκη ευρείας γκάμας περιεχομένου, συμπεριλαμβανομένου κειμένου, εικόνων και άλλων γραφικών στοιχείων.  

### Είναι το Aspose.Page κατάλληλο για τη διαχείριση μεγάλων εγγράφων;
Ναι, το Aspose.Page έχει σχεδιαστεί για να διαχειρίζεται αποδοτικά τόσο μικρά όσο και μεγάλα έγγραφα.  

### Πού μπορώ να βρω πρόσθετους πόρους και υποστήριξη για το Aspose.Page;
Εξερευνήστε την [τεκμηρίωση Aspose.Page](https://reference.aspose.com/page/java/), ή επισκεφθείτε το [φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39) για υποστήριξη από την κοινότητα.  

**Πρόσθετες ερωτήσεις & απαντήσεις**

**Ε:** *Τι μορφές εικόνας υποστηρίζονται όταν σχεδιάζετε σε μια σελίδα PostScript;*  
**Α:** Μπορείτε να ενσωματώσετε απευθείας εικόνες PNG, JPEG, BMP και GIF χρησιμοποιώντας το API σχεδίασης.  

**Ε:** *Πώς αλλάζω το προεπιλεγμένο DPI για το έγγραφο;*  
**Α:** Ορίστε το `PsSaveOptions.setResolution(int dpi)` πριν δημιουργήσετε το `PsDocument`.  

**Ε:** *Μπορώ να κρυπτογραφήσω ένα αρχείο PostScript με κωδικό πρόσβασης;*  
**Α:** Το PostScript από μόνο του δεν υποστηρίζει κρυπτογράφηση, αλλά μπορείτε να τυλίξετε το αποτέλεσμα σε PDF και να εφαρμόσετε ρυθμίσεις ασφαλείας εάν χρειάζεται.

---

**Τελευταία ενημέρωση:** 2026-10-25  
**Δοκιμή με:** Aspose.Page for Java 24.10  
**Συγγραφέας:** Aspose  

---

## Σχετικά μαθήματα

- [Πώς να ορίσετε μέγεθος σελίδας A4 και να δημιουργήσετε PostScript σε Java με Aspose.Page](/page/java/document-creation/postscript/)
- [Πώς να μετατρέψετε PostScript σε PDF χρησιμοποιώντας το Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Πώς να σχεδιάσετε ορθογώνιο σε Java PostScript με Aspose.Page](/page/java/postscript-shapes/add-rectangle/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}