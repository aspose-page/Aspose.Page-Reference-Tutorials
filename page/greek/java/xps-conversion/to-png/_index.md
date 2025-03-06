---
title: Μετατροπή XPS σε PNG σε Java
linktitle: Μετατροπή XPS σε PNG σε Java
second_title: Aspose.Page Java API
description: Μετατρέψτε εύκολα XPS σε PNG σε Java χρησιμοποιώντας το Aspose.Page. Βελτιώστε τις εργασίες εγγράφων με αυτήν την αξιόπιστη και φιλική προς τους προγραμματιστές λύση.
weight: 13
url: /el/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή XPS σε PNG σε Java

## Εισαγωγή
Στον δυναμικό κόσμο της ανάπτυξης λογισμικού, εμφανίζεται συχνά η ανάγκη μετατροπής εγγράφων XPS (XML Paper Specification) σε εικόνες PNG (Portable Network Graphics). Για την απρόσκοπτη ολοκλήρωση αυτής της εργασίας σε Java, το Aspose.Page παρέχει μια ισχυρή λύση. Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία μετατροπής XPS σε PNG χρησιμοποιώντας το Aspose.Page για Java.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας.
2.  Aspose.Page για Java: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Page. Μπορείτε να βρείτε τον σύνδεσμο λήψης[εδώ](https://releases.aspose.com/page/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Επιλέξτε ένα IDE συμβατό με Java όπως το IntelliJ IDEA ή το Eclipse.
## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα για να χρησιμοποιήσετε τις λειτουργίες Aspose.Page. Προσθέστε τις ακόλουθες δηλώσεις εισαγωγής στην αρχή του αρχείου Java:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Βήμα 1: Ορισμός καταλόγου εγγράφων
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
```
## Βήμα 2: Φόρτωση εγγράφου XPS
```java
// Φόρτωση εγγράφου XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Βήμα 3: Αρχικοποίηση επιλογών
```java
// Αρχικοποίηση αντικειμένου επιλογών με τις απαραίτητες παραμέτρους.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Βήμα 4: Δημιουργία συσκευής απόδοσης
```java
// Δημιουργία συσκευής απόδοσης για μορφή PDF
ImageDevice device = new ImageDevice();
```
## Βήμα 5: Αποθήκευση και Επανάληψη
```java
// Αποθηκεύστε το έγγραφο XPS σε PNG χρησιμοποιώντας επιλογές και συσκευή
document.save(device, options);
//Επανάληψη μέσω διαμερισμάτων εγγράφων (σταθερά έγγραφα, με όρους XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Επανάληψη μέσω σελίδων διαμερισμάτων
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Αρχικοποίηση ροής εξόδου εικόνας
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Γράψτε εικόνα
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Κλείστε το Stream
        imageStream.close();
    }
}
```
Ακολουθώντας αυτά τα βήματα, μπορείτε να μετατρέψετε αβίαστα έγγραφα XPS σε εικόνες PNG χρησιμοποιώντας το Aspose.Page για Java.
## συμπέρασμα
Συμπερασματικά, το Aspose.Page για Java απλοποιεί τη διαδικασία μετατροπής XPS σε PNG, παρέχοντας στους προγραμματιστές ένα αξιόπιστο και αποτελεσματικό εργαλείο. Ενσωματώστε αυτήν τη βιβλιοθήκη στα έργα σας Java για να απλοποιήσετε τις εργασίες χειρισμού εγγράφων.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page για Java σε εμπορικά έργα;
 Ναι, το Aspose.Page είναι ένα εμπορικό προϊόν. Μπορείτε να βρείτε πληροφορίες αδειοδότησης[εδώ](https://purchase.aspose.com/buy).
### Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page για Java;
 Η πλήρης τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/page/java/).
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για σκοπούς δοκιμής;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Υπάρχουν φόρουμ κοινότητας για συζητήσεις Aspose.Page;
 Ναι, επισκεφτείτε τα φόρουμ της κοινότητας[εδώ](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
