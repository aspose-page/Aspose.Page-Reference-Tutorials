---
title: Εύκολη ενσωμάτωση άδειας χρήσης με μέτρηση με Aspose.Page Java
linktitle: Ορισμός μετρημένης άδειας χρήσης σε Java
second_title: Aspose.Page Java API
description: Εξερευνήστε την απρόσκοπτη ενοποίηση του Aspose.Page με Java. Ρυθμίστε τις μετρημένες άδειες χωρίς κόπο και βελτιώστε τις δυνατότητες επεξεργασίας εγγράφων σας.
type: docs
weight: 10
url: /el/java/license-management/set-metered-license/
---
## Εισαγωγή
Καλώς ήρθατε στον περιεκτικό μας οδηγό για τη ρύθμιση μιας μετρημένης άδειας χρήσης σε Java χρησιμοποιώντας το Aspose.Page. Αν θέλετε να βελτιώσετε τις δυνατότητες επεξεργασίας εγγράφων σας και να διασφαλίσετε την απρόσκοπτη ενσωμάτωση με το Aspose.Page, βρίσκεστε στο σωστό μέρος. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία, αναλύοντας κάθε βήμα σε εύκολα εύπεπτα κομμάτια.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Page. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/page/java/).
- Μετρημένα δημόσια και ιδιωτικά κλειδιά, τα οποία μπορείτε να αποκτήσετε μέσω του λογαριασμού σας Aspose.
## Εισαγωγή πακέτων
Ας ξεκινήσουμε εισάγοντας τα απαραίτητα πακέτα για το πρόγραμμα Java μας. Βεβαιωθείτε ότι έχετε ενσωματωμένη τη βιβλιοθήκη Aspose.Page στο έργο σας.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Βήμα 1: Αρχικοποίηση εγγράφου και μορφής εικόνας
Το πρώτο βήμα είναι να ρυθμίσετε το έγγραφο και να ορίσετε την επιθυμητή μορφή εικόνας.
```java
// ορίστε μετρημένα δημόσια και ιδιωτικά κλειδιά
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Αποκτήστε πρόσβαση στην ιδιότητα setMeteredKey και περάστε τα δημόσια και ιδιωτικά κλειδιά ως παραμέτρους
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Βήμα 2: Εκκίνηση της ροής εισαγωγής PostScript
Σε αυτό το βήμα, αρχικοποιούμε τη ροή εισόδου PostScript για επεξεργασία.
```java
// Εκκίνηση ροής εισόδου PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Βήμα 3: Ελέγξτε την άδεια χρήσης εγγράφων
Πριν προχωρήσετε, είναι σημαντικό να επαληθεύσετε εάν το έγγραφο έχει τη σωστή άδεια χρήσης.
```java
// Ελέγξτε εάν το έγγραφο διαθέτει άδεια χρήσης
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Βήμα 4: Αρχικοποίηση επιλογών και συσκευής εικόνας
Τώρα, ας αρχικοποιήσουμε τις επιλογές και τη συσκευή εικόνας με προεπιλεγμένες παραμέτρους.
```java
// Αρχικοποίηση αντικειμένου επιλογών με προεπιλεγμένες παραμέτρους.
ImageSaveOptions options = new ImageSaveOptions();
// Αρχικοποίηση αντικειμένου ImageDevice με προεπιλεγμένες παραμέτρους.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Βήμα 5: Αποθηκεύστε το αρχείο EPS ως εικόνα
Αποθηκεύστε το αρχείο EPS ως εικόνα χρησιμοποιώντας τις καθορισμένες επιλογές και τη συσκευή.
```java
// Αποθηκεύστε το αρχείο EPS ως εικόνα
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Βήμα 6: Λήψη και αποθήκευση byte εικόνας
Ανακτήστε byte εικόνας και αποθηκεύστε τα σε ένα αρχείο.
```java
// Λάβετε byte εικόνων. Συστοιχία ενός byte για μία σελίδα. Στην περίπτωσή μας, έχουμε μία σελίδα.
byte[][] imagesBytes = device.getImagesBytes();
// Αποθήκευση byte εικόνας στο αρχείο
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## συμπέρασμα
Συγχαρητήρια! Ρυθμίσατε με επιτυχία μια μετρημένη άδεια χρήσης σε Java χρησιμοποιώντας το Aspose.Page. Αυτό το σεμινάριο παρείχε έναν οδηγό βήμα προς βήμα για να εξασφαλίσει μια ομαλή διαδικασία ολοκλήρωσης.
## Συχνές ερωτήσεις
### Ε: Πώς μπορώ να αποκτήσω μετρημένα δημόσια και ιδιωτικά κλειδιά;
Μπορείτε να αποκτήσετε αυτά τα κλειδιά μέσω του λογαριασμού σας Aspose.
### Ε: Είναι η βιβλιοθήκη Aspose.Page δωρεάν;
 Το Aspose.Page προσφέρει δωρεάν δοκιμαστικές και επί πληρωμή εκδόσεις. Επίσκεψη[εδώ](https://releases.aspose.com/) για δωρεάν δοκιμή.
### Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;
 Ναι, το Aspose.Page προσφέρει εμπορικές άδειες. Μπορείτε να τα αγοράσετε[εδώ](https://purchase.aspose.com/buy).
### Ε: Πού μπορώ να βρω πρόσθετη τεκμηρίωση;
 Ανατρέξτε στην τεκμηρίωση[εδώ](https://reference.aspose.com/page/java/).
### Ε: Πώς μπορώ να πάρω προσωρινές άδειες;
 Μπορούν να ληφθούν προσωρινές άδειες[εδώ](https://purchase.aspose.com/temporary-license/).