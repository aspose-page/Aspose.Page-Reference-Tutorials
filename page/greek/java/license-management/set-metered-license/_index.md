---
date: 2025-12-03
description: Μάθετε πώς να αποθηκεύετε EPS ως PNG χρησιμοποιώντας το Aspose.Page για
  Java, ενώ ρυθμίζετε μια μετρημένη άδεια. Οδηγός βήμα‑προς‑βήμα με πλήρες παράδειγμα
  κώδικα.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Αποθήκευση EPS ως PNG με το Aspose.Page Java (Μετρημένη Άδεια)
url: /el/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποθήκευση EPS ως PNG με Aspose.Page Java (Μετρημένη Άδεια)

## Εισαγωγή
Αν χρειάζεστε **αποθήκευση EPS ως PNG** σε εφαρμογή Java και θέλετε έναν απλό τρόπο διαχείρισης της άδειας, βρίσκεστε στο σωστό σημείο. Αυτό το tutorial σας καθοδηγεί στη ρύθμιση μιας μετρημένης άδειας για το Aspose.Page, τη φόρτωση ενός αρχείου PostScript (EPS) και τη μετατροπή του σε εικόνα PNG — όλα με σαφή, βήμα-βήμα οδηγίες που μπορείτε να ακολουθήσετε αμέσως.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “αποθήκευση EPS ως PNG”;** Μετατρέπει ένα διανυσματικό αρχείο EPS σε μια ραστερ εικόνα PNG.  
- **Γιατί να χρησιμοποιήσω μετρημένη άδεια;** Σας επιτρέπει να πληρώνετε μόνο για τις σελίδες που επεξεργάζεστε, ιδανικό για μεταβλητά φορτία εργασίας.  
- **Χρειάζεται σύνδεση στο διαδίκτυο;** Όχι, τα μετρημένα κλειδιά επικυρώνονται τοπικά.  
- **Ποια έκδοση της Java απαιτείται;** Java 8 ή νεότερη.  
- **Πόσο διαρκεί η ρύθμιση;** Περίπου 10 λεπτά για μια βασική υλοποίηση.

## Τι είναι η “αποθήκευση EPS ως PNG”;
Η αποθήκευση EPS ως PNG μετατρέπει ένα κλιμακώσιμο Encapsulated PostScript έγγραφο σε μια ευρέως υποστηριζόμενη μορφή bitmap. Το PNG διατηρεί τη διαφάνεια και προσφέρει συμπίεση χωρίς απώλειες, καθιστώντας το ιδανικό για γραφικά web, μικρογραφίες και προεπισκοπήσεις εκτύπωσης.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για αυτήν την εργασία;
- **Καθαρό Java API** – χωρίς εξαρτήσεις native.  
- **Υψηλή πιστότητα** – τα διανυσματικά γραφικά αποδίδονται με ακρίβεια.  
- **Μετρημένη άδεια** – πληρώνετε μόνο για ό,τι μετατρέπετε.  
- **Υποστήριξη πολλαπλών μορφών εξόδου** – PNG, JPEG, TIFF κ.λπ.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού Java.  
- Βιβλιοθήκη Aspose.Page εγκατεστημένη – κατεβάστε την από [εδώ](https://releases.aspose.com/page/java/).  
- Μετρημένα δημόσια και ιδιωτικά κλειδιά, τα οποία μπορείτε να αποκτήσετε μέσω του λογαριασμού σας στο Aspose.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις κλάσεις που θα χρειαστείτε. Διατηρήστε το μπλοκ εισαγωγών ακριβώς όπως φαίνεται ώστε ο κώδικας να μεταγλωττιστεί χωρίς αλλαγές.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Βήμα 1: Αρχικοποίηση Εγγράφου και Μορφής Εικόνας
Εδώ ορίζουμε τα μετρημένα κλειδιά και ορίζουμε τη μορφή εξόδου (PNG). Αυτό αποτελεί τη βάση για τη λειτουργία **αποθήκευση EPS ως PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

## Βήμα 2: Αρχικοποίηση Ροής Εισόδου PostScript
Ανοίξτε το αρχείο EPS που θέλετε να μετατρέψετε. Η ροή τροφοδοτεί το έγγραφο στο Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Βήμα 3: Έλεγχος Άδειας Εγγράφου
Πάντα επαληθεύετε ότι η μετρημένη άδεια εφαρμόστηκε σωστά πριν από την επεξεργασία.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Βήμα 4: Αρχικοποίηση Επιλογών και Συσκευής Εικόνας
Δημιουργήστε το αντικείμενο επιλογών που ελέγχει τις ρυθμίσεις μετατροπής και τη συσκευή που θα λάβει την αποδοθείσα εικόνα.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Βήμα 5: Αποθήκευση Αρχείου EPS ως Εικόνα
Αυτή είναι η κεντρική κλήση **αποθήκευση EPS ως PNG**. Το έγγραφο αποδίδεται στη συσκευή εικόνας χρησιμοποιώντας τις ρυθμίσεις που διαμορφώσαμε.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Βήμα 6: Λήψη και Αποθήκευση Byte Εικόνας
Εξάγετε τα byte PNG από τη συσκευή και γράψτε τα σε αρχείο στο δίσκο.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| **Η άδεια δεν αναγνωρίζεται** | Τα κλειδιά είναι λανθασμένα ή τοποθετημένα με λάθος σειρά. | Ελέγξτε ξανά τις συμβολοσειρές δημόσιου/ιδιωτικού κλειδιού και βεβαιωθείτε ότι το `setMeteredKey` καλείται πριν από οποιαδήποτε επεξεργασία εγγράφου. |
| **Το αρχείο εξόδου είναι κενό** | Η μέθοδος `device.getImagesBytes()` επέστρεψε `null`. | Βεβαιωθείτε ότι το αρχείο EPS είναι έγκυρο και ότι το `ImageSaveOptions` δεν έχει οριστεί σε καμβά μηδενικού μεγέθους. |
| **OutOfMemoryError σε μεγάλο EPS** | Η απόδοση μεγάλων διανυσματικών αρχείων καταναλώνει πολύ μνήμη. | Επεξεργαστείτε τις σελίδες μία‑μια ή αυξήστε το heap της JVM (`-Xmx2g`). |

## Συχνές Ερωτήσεις

**Ε: Πώς μπορώ να αποκτήσω τα μετρημένα δημόσια και ιδιωτικά κλειδιά;**  
Α: Μπορείτε να τα λάβετε μέσω του λογαριασμού σας στο Aspose.

**Ε: Η βιβλιοθήκη Aspose.Page είναι δωρεάν;**  
Α: Το Aspose.Page προσφέρει τόσο δωρεάν δοκιμαστική έκδοση όσο και πληρωμένες εκδόσεις. Επισκεφθείτε [εδώ](https://releases.aspose.com/) για δωρεάν δοκιμή.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page σε εμπορικά έργα;**  
Α: Ναι, το Aspose.Page προσφέρει εμπορικές άδειες. Μπορείτε να τις αγοράσετε [εδώ](https://purchase.aspose.com/buy).

**Ε: Πού μπορώ να βρω πρόσθετη τεκμηρίωση;**  
Α: Ανατρέξτε στην τεκμηρίωση [εδώ](https://reference.aspose.com/page/java/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινές άδειες;**  
Α: Οι προσωρινές άδειες μπορούν να ληφθούν [εδώ](https://purchase.aspose.com/temporary-license/).

---

**Τελευταία ενημέρωση:** 2025-12-03  
**Δοκιμή με:** Aspose.Page 24.12 for Java  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}