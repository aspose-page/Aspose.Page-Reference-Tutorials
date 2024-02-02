---
title: Αλλάξτε τις τιμές σε XMP χρησιμοποιώντας Java
linktitle: Αλλάξτε τις τιμές σε XMP χρησιμοποιώντας Java
second_title: Aspose.Page Java API
description: Βελτιώστε τα έγγραφα EPS με το Aspose.Page για Java. Τροποποιήστε αβίαστα τα μεταδεδομένα XMP για προσαρμοσμένο και επαγγελματικό περιεχόμενο. #JavaDevelopment
type: docs
weight: 17
url: /el/java/xmp-metadata-manipulation/change-values/
---
## Εισαγωγή
Στον τομέα της επεξεργασίας και χειρισμού εγγράφων, το Aspose.Page για Java ξεχωρίζει ως ένα ισχυρό εργαλείο. Αυτό το σεμινάριο εμβαθύνει στη διαδικασία αλλαγής των τιμών XMP (Extensible Metadata Platform) σε έγγραφα EPS (Encapsulated PostScript) χρησιμοποιώντας Java με τη βιβλιοθήκη Aspose.Page. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται, θα μάθετε πώς να τροποποιείτε αβίαστα τα μεταδεδομένα, διασφαλίζοντας ότι τα έγγραφά σας είναι προσαρμοσμένα στις συγκεκριμένες απαιτήσεις σας.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε ένα λειτουργικό περιβάλλον ανάπτυξης Java στον υπολογιστή σας.
2.  Aspose.Page για Java Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Page για Java. Μπορείτε να βρείτε το απαραίτητο πακέτο[εδώ](https://releases.aspose.com/page/java/).
## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τα απαιτούμενα πακέτα στο έργο σας Java. Αυτά τα πακέτα είναι ζωτικής σημασίας για την αλληλεπίδραση και τον χειρισμό εγγράφων EPS.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Βήμα 1: Λήψη μεταδεδομένων XMP
Ανάκτηση μεταδεδομένων XMP από το έγγραφο EPS. Εάν το αρχείο EPS δεν περιέχει μεταδεδομένα XMP, θα δημιουργηθεί ένα νέο με τιμές από σχόλια μεταδεδομένων PS, όπως %%Creator, %%CreateDate και %%Title.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Αρχικοποίηση ροής αρχείων εισόδου EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Λάβετε μεταδεδομένα XMP. Εάν το αρχείο EPS δεν περιέχει μεταδεδομένα XMP, δημιουργείται ένα νέο με τιμές από σχόλια μεταδεδομένων PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Βήμα 2: Αλλάξτε την τιμή "ModifyDate".
Τροποποιήστε την τιμή "ModifyDate" στα μεταδεδομένα XMP για να αντικατοπτρίζει την επιθυμητή ημερομηνία.
```java
// Αλλάξτε την τιμή "ModifyDate".
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Βήμα 3: Αλλάξτε την τιμή "Δημιουργός".
Ενημερώστε την τιμή "Δημιουργός" στα μεταδεδομένα XMP για να καθορίσετε τον δημιουργό του εγγράφου.
```java
// Αλλάξτε την τιμή "δημιουργός".
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Βήμα 4: Αλλάξτε την τιμή "Title".
Τροποποιήστε την τιμή "Title" στα μεταδεδομένα XMP για να ορίσετε έναν κατάλληλο τίτλο για το έγγραφο.
```java
//Αλλάξτε την τιμή "τίτλος".
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Βήμα 5: Αποθήκευση εγγράφου με Αλλαγμένα μεταδεδομένα XMP
Αποθηκεύστε το έγγραφο με τα ενημερωμένα μεταδεδομένα XMP σε ένα νέο αρχείο EPS.
```java
// Αρχικοποίηση ροής αρχείου εξόδου EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Αποθήκευση εγγράφου με αλλαγμένα μεταδεδομένα XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## συμπέρασμα
Συγχαρητήρια! Πραγματοποιήσατε με επιτυχία την πλοήγηση στη διαδικασία αλλαγής των τιμών XMP σε έγγραφα EPS χρησιμοποιώντας το Aspose.Page για Java. Αυτό το σεμινάριο σάς εξοπλίζει με τη γνώση για την τροποποίηση μεταδεδομένων, διασφαλίζοντας ότι τα έγγραφά σας ευθυγραμμίζονται απρόσκοπτα με τις συγκεκριμένες απαιτήσεις σας.
## Συχνές ερωτήσεις
### Ε: Πώς μπορώ να χειριστώ ζητήματα ζώνης ώρας όταν τροποποιώ τις τιμές XMP;
 Χρησιμοποιώ`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` για να διασφαλιστεί η συνέπεια στις ρυθμίσεις ζώνης ώρας.
### Ε: Μπορώ να αλλάξω πολλές τιμές XMP σε μία μόνο λειτουργία;
 Ναι, χρησιμοποιώντας το`put` μέθοδο για κάθε επιθυμητή τιμή, μπορείτε να τροποποιήσετε πολλές τιμές XMP ταυτόχρονα.
### Ε: Πού μπορώ να βρω πρόσθετη τεκμηρίωση για το Aspose.Page για Java;
 Εξερευνήστε την πλήρη τεκμηρίωση[εδώ](https://reference.aspose.com/page/java/).
### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Page για Java;
 Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Ε: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για Java;
 Λάβετε προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).