---
title: Προσθέστε μεταδεδομένα σε XMP χρησιμοποιώντας Java
linktitle: Προσθέστε μεταδεδομένα σε XMP χρησιμοποιώντας Java
second_title: Aspose.Page Java API
description: Εξερευνήστε την απρόσκοπτη ενσωμάτωση του Aspose.Page για Java και μάθετε πώς να προσθέτετε μεταδεδομένα XMP στα αρχεία EPS σας χωρίς κόπο. Ανεβάστε το παιχνίδι διαχείρισης εγγράφων σας σήμερα!
weight: 11
url: /el/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθέστε μεταδεδομένα σε XMP χρησιμοποιώντας Java

## Εισαγωγή
Θέλετε να βελτιώσετε τα μεταδεδομένα του εγγράφου σας προσθέτοντας πληροφορίες XMP χρησιμοποιώντας Java; Μην ψάχνετε άλλο! Αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη διαδικασία προσθήκης μεταδεδομένων σε ένα αρχείο EPS χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για Java. Το Aspose.Page είναι ένα ισχυρό εργαλείο που απλοποιεί τις εργασίες χειρισμού εγγράφων σε εφαρμογές Java.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Page για Java. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/java/).
- Ένα αρχείο EPS που θέλετε να τροποποιήσετε.
## Εισαγωγή πακέτων
Αρχικά, εισαγάγετε τα απαραίτητα πακέτα στο πρόγραμμα Java σας:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Βήμα 1: Λήψη μεταδεδομένων XMP
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Αρχικοποίηση ροής αρχείων εισόδου EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Λάβετε μεταδεδομένα XMP. Εάν το αρχείο EPS δεν περιέχει μεταδεδομένα XMP, δημιουργείται ένα νέο χρησιμοποιώντας τιμές από σχόλια μεταδεδομένων PS (%%Creator, %%CreateDate, %%Title, κ.λπ.)
XmpMetadata xmp = document.getXmpMetadata();
```
Βεβαιωθείτε ότι έχετε αντικαταστήσει τον "Κατάλογο εγγράφων σας" με την πραγματική διαδρομή όπου είναι αποθηκευμένα τα έγγραφά σας.

## Βήμα 2: Ανάκτηση τιμής CreatorTool
```java
// Λάβετε την τιμή "CreatorTool".
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Βήμα 3: Ανακτήστε την τιμή CreateDate
```java
// Λάβετε την τιμή "CreateDate".
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Βήμα 4: Ανάκτηση τιμής τίτλου
```java
// Λάβετε την τιμή "Τίτλος".
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Βήμα 5: Ανάκτηση τιμής μορφής
```java
//Λάβετε την τιμή "μορφής".
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Βήμα 6: Ανάκτηση τιμής δημιουργού
```java
// Αποκτήστε αξία "δημιουργού".
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Βήμα 7: Ανάκτηση Μεταδεδομένων Ημερομηνία Τιμής
```java
// Λάβετε την τιμή "MetadataDate".
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Βήμα 8: Αποθήκευση εγγράφου με νέα μεταδεδομένα XMP
```java
// Αρχικοποίηση ροής αρχείου εξόδου EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Αποθήκευση εγγράφου με νέα μεταδεδομένα XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Τέλος, μην ξεχάσετε να κλείσετε τη ροή εισόδου EPS:
```java
// Κλείσιμο ροής EPS εισόδου
psStream.close();
```
Τώρα, προσθέσατε με επιτυχία μεταδεδομένα στο αρχείο EPS σας χρησιμοποιώντας το Aspose.Page για Java!
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τη διαδικασία προσθήκης μεταδεδομένων XMP σε ένα αρχείο EPS χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για Java. Αυτό το ισχυρό εργαλείο σάς δίνει τη δυνατότητα να χειρίζεστε έγγραφα απρόσκοπτα, βελτιώνοντας τη συνολική εμπειρία διαχείρισης εγγράφων.
## Συχνές ερωτήσεις
### Ε: Είναι το Aspose.Page για Java δωρεάν;
 Α: Το Aspose.Page για Java είναι ένα εμπορικό προϊόν. Μπορείτε να εξερευνήσετε τις δυνατότητές του μέσω μιας δωρεάν δοκιμής[εδώ](https://releases.aspose.com/).
### Ε: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page για Java;
 Α: Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/page/java/).
### Ε: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για Java;
 Α: Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Ε: Ποιες μορφές αρχείων υποστηρίζει το Aspose.Page για Java;
Α: Το Aspose.Page για Java υποστηρίζει διάφορες μορφές, όπως EPS, PDF και XPS.
### Ε: Μπορώ να αγοράσω το Aspose.Page για Java;
 Α: Ναι, μπορείτε να αγοράσετε το Aspose.Page για Java[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
