---
title: Aspose.Page Χειρισμός κειμένου Java
linktitle: Προσθήκη κειμένου σε Java PostScript
second_title: Aspose.Page Java API
description: Εξερευνήστε τη δύναμη του Aspose.Page για Java στο σεμινάριο μας σχετικά με την προσθήκη κειμένου σε έγγραφα PostScript. Μάθετε να χρησιμοποιείτε εύκολα το σύστημα και τις προσαρμοσμένες γραμματοσειρές.
type: docs
weight: 10
url: /el/java/postscript-text-manipulation/add-text/
---
## Εισαγωγή
Καλώς ήρθατε στον αναλυτικό οδηγό μας για την προσθήκη κειμένου σε Java PostScript χρησιμοποιώντας το Aspose.Page για Java. Το Aspose.Page για Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να χειρίζονται έγγραφα PostScript με ευκολία. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης κειμένου, χρήσης συστήματος και προσαρμοσμένων γραμματοσειρών, περιγραφής κειμένου και ενσωμάτωσης πινελιών για ένα οπτικά ελκυστικό αποτέλεσμα.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
-  Εγκαταστάθηκε το Aspose.Page για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από το[Σελίδα λήψης Aspose.Page για Java](https://releases.aspose.com/page/java/).
-  Οι απαραίτητες γραμματοσειρές είναι διαθέσιμες στον καθορισμένο φάκελο. Μπορείτε να βρείτε επιπλέον πληροφορίες στο[Aspose.Page για τεκμηρίωση Java](https://reference.aspose.com/page/java/).
## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα για το Aspose.Page για Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Βήμα 1: Ρύθμιση του εγγράφου
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Δημιουργία ροής εξόδου για έγγραφο PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Δημιουργήστε επιλογές αποθήκευσης με μέγεθος Α4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Ένα κείμενο για εγγραφή στο αρχείο PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Δημιουργία νέου εγγράφου PS 1 σελίδας
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Βήμα 2: Χρήση γραμματοσειράς συστήματος για τη συμπλήρωση κειμένου
```java
// Χρήση γραμματοσειράς συστήματος για τη συμπλήρωση κειμένου
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Συμπλήρωση κειμένου με προεπιλεγμένο ή ήδη καθορισμένο χρώμα (μαύρο)
document.fillText(str, font, 50, 100);
// Συμπληρώστε το κείμενο με μπλε χρώμα
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Βήμα 3: Χρήση προσαρμοσμένης γραμματοσειράς για τη συμπλήρωση κειμένου
```java
// Χρήση προσαρμοσμένης γραμματοσειράς για τη συμπλήρωση κειμένου
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Συμπλήρωση κειμένου με προεπιλεγμένο ή ήδη καθορισμένο χρώμα (μαύρο)
document.fillText(str, drFont, 50, 200);
// Συμπληρώστε το κείμενο με μπλε χρώμα
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Βήμα 4: Περίγραμμα κειμένου με γραμματοσειρά συστήματος
```java
// Χρήση γραμματοσειράς συστήματος για περίγραμμα κειμένου
document.outlineText(str, font, 50, 300);
// Κείμενο περιγράμματος με στυλό πλάτους 2 σημείων μπλε-βιολετί
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Συμπληρώστε το κείμενο με πορτοκαλί χρώμα και πινελιά με μπλε στυλό πλάτους 2 σημείων
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Βήμα 5: Περίγραμμα κειμένου με προσαρμοσμένη γραμματοσειρά
```java
// Χρήση προσαρμοσμένης γραμματοσειράς για περίγραμμα κειμένου
document.outlineText(str, drFont, 50, 450);
// Κείμενο περιγράμματος με στυλό πλάτους 2 σημείων μπλε-βιολετί
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Συμπληρώστε το κείμενο με πορτοκαλί χρώμα και πινελιά με μπλε στυλό πλάτους 2 σημείων
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Βήμα 6: Αποθηκεύστε το έγγραφο
```java
// Κλείστε την τρέχουσα σελίδα
document.closePage();
// Αποθηκεύστε το έγγραφο
document.save();
```
## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να προσθέτετε κείμενο στο Java PostScript χρησιμοποιώντας το Aspose.Page για Java. Πειραματιστείτε με διαφορετικές γραμματοσειρές, χρώματα και επιλογές περιγράμματος για να βελτιώσετε περαιτέρω το έγγραφό σας.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω τις δικές μου προσαρμοσμένες γραμματοσειρές με το Aspose.Page για Java;
 Ναι, μπορείτε να χρησιμοποιήσετε προσαρμοσμένες γραμματοσειρές καθορίζοντας το όνομα και το μέγεθος της γραμματοσειράς στο`DrFont` τάξη.
### Πώς μπορώ να αλλάξω το χρώμα του κειμένου;
 Μπορείτε να ορίσετε το επιθυμητό χρώμα χρησιμοποιώντας το`Color` τάξη κατά τη συμπλήρωση ή την περιγραφή του κειμένου.
### Είναι δυνατή η προσθήκη πολλών σελίδων σε ένα έγγραφο PostScript;
Απολύτως! Μπορείτε να δημιουργήσετε πολλές σελίδες επαναλαμβάνοντας τα βήματα δημιουργίας και αποθήκευσης εγγράφου.
###  Ποιος είναι ο σκοπός του`ExternalFontCache` class?
`ExternalFontCache` χρησιμοποιείται για τη λήψη προσαρμοσμένων γραμματοσειρών, διασφαλίζοντας ότι είναι διαθέσιμες για επεξεργασία κειμένου.
### Μπορώ να εφαρμόσω διαφορετικές πινελιές στο περιγραφόμενο κείμενο;
 Ναι, μπορείτε να προσαρμόσετε το πλάτος και το χρώμα της διαδρομής χρησιμοποιώντας το`Stroke` τάξη και`Color` τάξη, αντίστοιχα.