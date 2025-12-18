---
date: 2025-12-18
description: Μάθετε πώς να προσθέτετε μεταδεδομένα εισάγοντας στοιχεία πίνακα στα
  μεταδεδομένα XMP αρχείων EPS χρησιμοποιώντας το Aspose.Page για Java. Ακολουθήστε
  τον βήμα‑βήμα οδηγό μας.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Πώς να προσθέσετε μεταδεδομένα – Προσθήκη στοιχείων πίνακα στο XMP (Java)
url: /el/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Στοιχείων Πίνακα σε XMP Metadata χρησιμοποιώντας Java

## Πώς να Προσθέσετε Metadata
Καλώς ήρθατε στον βήμα‑βήμα οδηγό μας για **πώς να προσθέσετε metadata** σε αρχεία EPS με το Aspose.Page for Java. Σε αυτό το tutorial θα σας δείξουμε πώς να προσθέτετε στοιχεία πίνακα στο XMP metadata—μια συνηθισμένη απαίτηση όταν χρειάζεται να εμπλουτίσετε τις πληροφορίες του εγγράφου, όπως τίτλους ή δημιουργούς. Στο τέλος, θα κατανοήσετε γιατί το XMP είναι πολύτιμο, πώς να το χειρίζεστε προγραμματιστικά και πώς να αποθηκεύσετε το ενημερωμένο αρχείο EPS.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρησιμοποιείται;** Aspose.Page for Java  
- **Ποια μορφή αρχείου στοχεύεται;** EPS (Encapsulated PostScript)  
- **Μπορώ να προσθέσω πολλούς τίτλους;** Ναι, χρησιμοποιήστε `xmp.addArrayItem("dc:title", ...)` επανειλημμένα  
- **Χρειάζεται άδεια για παραγωγή;** Ναι, απαιτείται έγκυρη άδεια Aspose.Page  
- **Είναι ο κώδικας συμβατός με Java 8+;** Απόλυτα, λειτουργεί με όλες τις σύγχρονες εκδόσεις της Java  

## Προαπαιτούμενα
Πριν ξεκινήσουμε το tutorial, βεβαιωθείτε ότι έχετε τα εξής:
- Βιβλιοθήκη Aspose.Page for Java εγκατεστημένη.  
- Βασική κατανόηση του προγραμματισμού σε Java.  
- Ένα έγκυρο αρχείο EPS με υπάρχον XMP metadata ή σχόλια PS metadata.  

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, πρέπει να εισάγετε τα απαραίτητα πακέτα για εργασία με το Aspose.Page. Συμπεριλάβετε τις παρακάτω γραμμές στην αρχή του αρχείου Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Βήμα 1: Λήψη XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Σε αυτό το βήμα, ανακτούμε το υπάρχον XMP metadata από το αρχείο EPS. Εάν το αρχείο EPS δεν περιέχει ήδη XMP metadata, το Aspose.Page δημιουργεί ένα νέο και το γεμίζει με τιμές από τα σχόλια PS metadata.  

## Βήμα 2: Προσθήκη Στοιχείου Πίνακα "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Τώρα, προσθέτουμε ένα νέο στοιχείο πίνακα στην ιδιότητα **dc:title** του XMP metadata. Αντικαταστήστε το `"NewTitle"` με τον επιθυμητό τίτλο.  

## Βήμα 3: Προσθήκη Στοιχείου Πίνακα "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Ανάλογα, προσθέτουμε ένα νέο στοιχείο πίνακα στην ιδιότητα **dc:creator** του XMP metadata. Αντικαταστήστε το `"NewCreator"` με τις επιθυμητές πληροφορίες δημιουργού.  

## Βήμα 4: Αρχικοποίηση Ροής Εξόδου Αρχείου EPS
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Προετοιμάστε τη ροή εξόδου του αρχείου EPS όπου θα αποθηκευτεί το τροποποιημένο έγγραφο με το ενημερωμένο XMP metadata.  

## Βήμα 5: Αποθήκευση Εγγράφου με Τροποποιημένο XMP Metadata
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Αποθηκεύστε το έγγραφο με το ενημερωμένο XMP metadata στο αρχείο εξόδου EPS.  

## Συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία **πώς να προσθέσετε metadata** εισάγοντας στοιχεία πίνακα στο XMP metadata χρησιμοποιώντας το Aspose.Page for Java. Αυτή η ισχυρή βιβλιοθήκη απλοποιεί τη διαδικασία χειρισμού αρχείων EPS και παρέχει εκτεταμένες λειτουργίες επεξεργασίας εγγράφων.  

## Συχνές Ερωτήσεις

### Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες μορφές εγγράφων;
Ναι, το Aspose.Page υποστηρίζει διάφορες μορφές εγγράφων, συμπεριλαμβανομένων των EPS, PDF και XPS.  

### Υπάρχει δωρεάν δοκιμή για το Aspose.Page for Java;
Ν να αποκτήσετε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).  

### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page for Java;
Η τεκμηρίωση είναι διαθέσιμη [εδώ](https://reference.aspose.com/page/java/).  

### Πώς μπορώ να αγοράσω το Aspose.Page for Java;
Μπορείτε να αγοράσετε το προϊόν [εδώ](https://purchase.aspose.com/buy).  

### Διατίθενται προσωρινές άδειες για το Aspose.Page for Java;
Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).  

## Πρόσθετες Συχνές Ερωτήσεις

**Ε: Μπορώ να προσθέσω περισσότερα από ένα στοιχεία πίνακα στην ίδια ιδιότητα;**  
Α: Απολύτως. Καλέστε `xmp.addArrayItem` πολλές φορές για την ίδια ιδιότητα ώστε να δημιουργήσετε μια λίστα τιμών.  

**Ε: Λειτουργεί αυτή η προσέγγιση με υπάρχοντα σχήματα XMP εκτός του Dublin Core;**  
Α: Ναι, μπορείτε να προσθέσετε στοιχεία πίνακα σε οποιαδήποτε ιδιότητα XMP εφόσον το namespace αναφέρεται σωστά.  

**Ε: Πώς μπορώ να επαληθεύσω ότι τα metadata προστέθηκαν σωστά;**  
Α: Ανοίξτε το παραγόμενο αρχείο EPS σε έναν προβολέα που υποστηρίζει XMP (π.χ., Adobe Bridge) ή εξάγετε τα metadata προγραμματιστικά χρησιμοποιώντας τις μεθόδους `XmpMetadata`.  

---

**Τελευταία Ενημέρωση:** 2025-12-18  
**Δοκιμή Με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}