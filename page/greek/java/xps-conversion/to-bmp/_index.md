---
date: 2026-03-08
description: Μάθετε πώς να μετατρέπετε XPS σε BMP σε Java και να ορίζετε την ανάλυση
  BMP χρησιμοποιώντας τη βιβλιοθήκη μετατροπής εικόνας Aspose.Page για Java. Αυτός
  ο οδηγός καλύπτει υψηλής ποιότητας έξοδο και συμβουλές φιλικές προς τη μνήμη.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Μετατροπή XPS σε BMP σε Java – Ορισμός ανάλυσης για υψηλής ποιότητας έξοδο
url: /el/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή XPS σε BMP σε Java

## Introduction
Καλώς ήρθατε σε αυτόν τον οδηγό βήμα‑βήμα για το πώς να **μετατρέψετε XPS σε BMP** σε Java και να ορίσετε την ανάλυση για βέλτιστη ποιότητα εικόνας χρησιμοποιώντας το Aspose.Page. Είτε δημιουργείτε μια αλυσίδα εκτύπωσης, παράγετε μικρογραφίες, είτε χρειάζεστε γραφικά υψηλής ανάλυσης, ο έλεγχος του DPI σας δίνει την ευελιξία να καλύψετε οποιαδήποτε απαίτηση.

## Quick Answers
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Το Aspose.Page for Java είναι η πιο πλήρης **java image conversion library** για XPS → BMP.  
- **Μπορώ να ελέγξω την ποιότητα της εικόνας;** Ναι – χρησιμοποιήστε το `BmpSaveOptions` για να **ορίσετε την ανάλυση BMP** και τη λειτουργία εξομάλυνσης.  
- **Πώς μπορώ να αποφύγω το OutOfMemoryError Java κατά την επεξεργασία μεγάλων αρχείων XPS;** Αποδώστε τις σελίδες σε τμήματα ή αυξήστε τη μνήμη heap της JVM (`-Xmx`).  
- **Χρειάζεται να μετατρέψω μόνο συγκεκριμένες σελίδες;** Απόλυτα, το `options.setPageNumbers()` σας επιτρέπει να επιλέξετε ακριβείς σελίδες.  
- **Ποιες εκδόσεις Java υποστηρίζονται;** Όλες οι σύγχρονες εκδόσεις Java (8 και άνω) λειτουργούν απρόσκοπτα.

## What is the purpose of setting resolution?
Η ανάλυση καθορίζει τον αριθμό των κουκίδων ανά ίντσα (DPI) στην παραγόμενη εικόνα BMP. Ένα υψηλότερο DPI παράγει πιο καθαρές εικόνες, κάτι που είναι απαραίτητο για εκτύπωση ή λεπτομερή γραφική εργασία. Η ρύθμιση της ανάλυσης σας δίνει πλήρη έλεγχο στην ποιότητα εξόδου της ροής εργασίας **convert xps to bmp**.

## Why use Aspose.Page for XPS → BMP conversion?
- **Υψηλή πιστότητα** – διατηρεί την διανυσματική ποιότητα του αρχικού XPS.  
- **Λεπτομερής έλεγχος** – μπορείτε να ορίσετε DPI, εξομάλυνση και ακόμη να επιλέξετε συγκεκριμένες σελίδες για μετατροπή.  
- **Χωρίς εξωτερικές εξαρτήσεις** – καθαρή Java, δεν απαιτούνται εγγενείς βιβλιοθήκες.  
- **Κλιμακώσιμο** – λειτουργεί για έγγραφα μιας σελίδας καθώς και για μεγάλα πολυσελιδικά αρχεία XPS.  

## Prerequisites
Πριν ξεκινήσετε τη διαδικασία μετατροπής, βεβαιωθείτε ότι διαθέτετε τα παρακάτω προαπαιτούμενα:
- **Περιβάλλον Ανάπτυξης Java** – Java 8 ή νεότερη εγκατεστημένη στο σύστημά σας.  
- **Βιβλιοθήκη Aspose.Page for Java** – Κατεβάστε και συμπεριλάβετε τη βιβλιοθήκη Aspose.Page for Java στο έργο σας. Μπορείτε να βρείτε τη βιβλιοθήκη [εδώ](https://releases.aspose.com/page/java/).  
- **Δείγμα αρχείου XPS** – Προετοιμάστε ένα δείγμα εγγράφου XPS που θέλετε να μετατρέψετε σε BMP.

## Import Packages
Συμπεριλάβετε τα απαραίτητα πακέτα Aspose.Page στον κώδικα Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## How to Set Resolution for XPS to BMP Conversion
Παρακάτω βρίσκεται ένας σύντομος, αριθμημένος οδηγός που δείχνει ακριβώς πού και πώς να ορίσετε την ανάλυση, καθώς και πώς να **μετατρέψετε συγκεκριμένες σελίδες**.

### Step 1: Load XPS Document
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Step 2: Initialize Options (Resolution & Page Selection)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Step 3: Create Rendering Device
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Step 4: Save Document Using Options
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Step 5: Iterate Through Rendered Images and Write Files
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Επαναλάβετε αυτά τα βήματα για οποιαδήποτε πρόσθετη προσαρμογή ή τροποποίηση που ενδέχεται να χρειαστείτε στη διαδικασία μετατροπής.

## How to Avoid OutOfMemoryError Java When Converting Large XPS Files
- **Επεξεργασία σε τμήματα** – Το παράδειγμα ήδη αποδίδει το έγγραφο σε τμήματα (`device.getResult()`), μειώνοντας την πίεση μνήμης.  
- **Αύξηση του heap της JVM** – Χρησιμοποιήστε τη σημαία `-Xmx` (π.χ., `-Xmx2g`) για να διαθέσετε περισσότερη μνήμη για μεγάλα έγγραφα.  
- **Καθαρισμός πόρων** – Καλέστε `document.close()` όταν τελειώσετε για να ελευθερώσετε τους εγγενείς πόρους.

## Common Issues and Solutions
| Πρόβλημα | Λύση |
|----------|------|
| **Έξοδος BMP χαμηλής ποιότητας** | Επαληθεύστε ότι το `options.setResolution()` είναι ορισμένο σε τιμή ≥ 300 DPI. |
| **Μόνο μέρος του εγγράφου μετατρέπεται** | Βεβαιωθείτε ότι το `options.setPageNumbers()` περιλαμβάνει όλους τους επιθυμητούς δείκτες σελίδων. |
| **OutOfMemoryError σε μεγάλα αρχεία XPS** | Επεξεργαστείτε το έγγραφο σε μικρότερα τμήματα ή αυξήστε το μέγεθος του heap της JVM (`-Xmx`). |
| **Αρχείο δεν βρέθηκε** | Ελέγξτε ξανά τη διαδρομή `dataDir` και ότι το αρχείο XPS εισόδου υπάρχει. |

## Frequently Asked Questions
### Q: Μπορώ να προσαρμόσω την ανάλυση των εικόνων BMP;
A: Ναι, μπορείτε να ρυθμίσετε την ανάλυση τροποποιώντας την παράμετρο `options.setResolution()` στον κώδικα.

### Q: Είναι το Aspose.Page συμβατό με διαφορετικές εκδόσεις Java;
A: Ναι, το Aspose.Page υποστηρίζει ένα ευρύ φάσμα εκδόσεων Java. Βεβαιωθείτε ότι έχετε εγκατεστημένη μια συμβατή έκδοση.

### Q: Πώς μπορώ να μετατρέψω αρχεία XPS από συγκεκριμένο εύρος σελίδων;
A: Χρησιμοποιήστε τη μέθοδο `options.setPageNumbers()` για να καθορίσετε τους αριθμούς σελίδων που θέλετε να μετατρέψετε.

### Q: Υπάρχουν άλλες μορφές εξόδου που υποστηρίζονται από το Aspose.Page;
A: Ναι, το Aspose.Page υποστηρίζει διάφορες μορφές εξόδου. Ανατρέξτε στην τεκμηρίωση για μια πλήρη λίστα.

### Q: Πού μπορώ να βρω πρόσθετη βοήθεια ή υποστήριξη;
A: Επισκεφθείτε το [Aspose.Page Forum](https://forum.aspose.com/c/page/39) για υποστήριξη της κοινότητας και συζητήσεις.

---

**Τελευταία ενημέρωση:** 2026-03-08  
**Δοκιμή με:** Aspose.Page for Java 24.12  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}