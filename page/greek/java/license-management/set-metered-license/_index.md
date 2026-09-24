---
date: 2026-09-24
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Page για να μετατρέψετε EPS σε
  PNG σε Java, να ρυθμίσετε μια metered license και να γράψετε αποδοτικό κώδικα Java
  για αρχείο PNG.
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: Ορισμός Metered License σε Java
og_description: Aspose.Page μετατροπή EPS σε PNG σε Java με metered license. Αυτός
  ο οδηγός δείχνει βήμα‑βήμα πώς να ρυθμίσετε την άδεια, να αποδώσετε EPS και να γράψετε
  κώδικα Java για αρχείο PNG.
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page μετατρέπει EPS σε PNG σε Java (metered license)
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page μετατρέπει EPS σε PNG σε Java (metered license)
url: /el/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page μετατρέπει EPS σε PNG σε Java (μετρημένη άδεια)

## Εισαγωγή
Αν χρειάζεστε να **αποθηκεύσετε EPS ως PNG** σε μια εφαρμογή Java ενώ διατηρείτε την άδεια απλή, βρίσκεστε στο σωστό μέρος. Αυτό το σεμινάριο σας καθοδηγεί στη ρύθμιση μιας **μετρημένης άδειας** για το Aspose.Page, στη φόρτωση ενός αρχείου EPS (Encapsulated PostScript) και στη μετατροπή του σε εικόνα PNG. Στο τέλος θα καταλάβετε πώς να **αποδώσετε EPS σε PNG αποδοτικά** και πώς να **γράψετε κώδικα Java για αρχείο PNG** που λειτουργεί αξιόπιστα σε παραγωγή.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “save EPS as PNG”;** Μετατρέπει ένα διανυσματικό αρχείο EPS σε μια ραστερ εικόνα PNG, διατηρώντας τη διαφάνεια και τη μη απωλεστική συμπίεση.  
- **Γιατί να χρησιμοποιήσω μια μετρημένη άδεια;** Πληρώνετε μόνο για τις σελίδες που επεξεργάζεστε, κάτι που είναι ιδανικό για μεταβλητά φορτία εργασίας.  
- **Χρειάζομαι σύνδεση στο διαδίκτυο;** Όχι, τα κλειδιά της μετρημένης άδειας επικυρώνονται τοπικά στη JVM.  
- **Ποια έκδοση της Java απαιτείται;** Η Java 8 ή νεότερη υποστηρίζεται πλήρως.  
- **Πόσο διαρκεί η ρύθμιση;** Περίπου 10 λεπτά για μια βασική υλοποίηση.

## Τι είναι το “save EPS to PNG”;
Η αποθήκευση EPS ως PNG μετατρέπει ένα διανυσματικό έγγραφο Encapsulated PostScript σε μια ραστερ εικόνα PNG, διατηρώντας τη διαφάνεια και προσφέροντας μη απωλεστική συμπίεση. Αυτή η μετατροπή είναι χρήσιμη όταν χρειάζεστε γραφικά έτοιμα για το web, μικρογραφίες ή εκτυπώσιμες προεπισκοπήσεις που μπορούν να εμφανιστούν σε οποιονδήποτε φυλλομετρητή χωρίς την ανάγκη ερμηνευτή PostScript.

## Γιατί να αποδώσετε EPS σε PNG με το Aspose.Page;
Το Aspose.Page παρέχει ένα καθαρό API Java που ραστεροποιεί αρχεία EPS με υψηλή πιστότητα, υποστηρίζει πάνω από 50 μορφές εξόδου και προσφέρει μετρημένη άδεια ώστε να πληρώνετε μόνο για ό,τι μετατρέπετε. Η βιβλιοθήκη μπορεί να επεξεργαστεί έγγραφα με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, παρέχοντας γρήγορη και ακριβή απόδοση σε οποιαδήποτε πλατφόρμα που υποστηρίζει τη JVM.

## Προαπαιτούμενα
- Βασική εμπειρία ανάπτυξης Java.  
- Η βιβλιοθήκη Aspose.Page ληφθεί από τη [σελίδα λήψης Aspose.Page Java](https://releases.aspose.com/page/java/).  
- Ένα ζεύγος μετρημένων δημόσιων και ιδιωτικών κλειδιών από τον λογαριασμό σας στο Aspose.  

## Εισαγωγή πακέτων
Οι δηλώσεις `import` φέρνουν τις απαιτούμενες κλάσεις στο πεδίο ορατότητας. Διατηρήστε αυτό το τμήμα ακριβώς όπως φαίνεται ώστε ο κώδικας να μεταγλωττιστεί χωρίς αλλαγές.

Οι κλάσεις `java.io` διαχειρίζονται τις ροές αρχείων, ενώ οι κλάσεις του Aspose.Page διαχειρίζονται την άδεια, τη φόρτωση εγγράφων και την απόδοση εικόνας.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Πώς να αποθηκεύσετε EPS ως PNG χρησιμοποιώντας Aspose.Page Java
Ακολουθεί ο οδηγός βήμα‑βήμα που συνδυάζει την άδεια, τη φόρτωση, την απόδοση και τη γραφή του τελικού αρχείου PNG.

### Άμεση απάντηση
Φορτώστε το αρχείο EPS, εφαρμόστε μια μετρημένη άδεια, διαμορφώστε το `ImageSaveOptions` για PNG, αποδώστε το έγγραφο σε ένα `ImageDevice` και, τέλος, γράψτε τον προκύπτοντα πίνακα byte στο δίσκο. Αυτή η ακολουθία ολοκληρώνει τη ροή εργασίας **save EPS as PNG** με λίγες μόνο γραμμές κώδικα Java.

### Βήμα 1: αρχικοποίηση εγγράφου και μορφής εικόνας
Πρώτα, ορίστε τα μετρημένα κλειδιά και καθορίστε τη μορφή εξόδου (PNG). Αυτό δημιουργεί τη βάση για τη μετατροπή.

Η κλάση `MeteredLicense` αποθηκεύει τα δημόσια και ιδιωτικά κλειδιά σας, ενώ το `ImageSaveOptions` ενημερώνει το Aspose.Page να παράγει έξοδο PNG.

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

### Βήμα 2: αρχικοποίηση ροής εισόδου PostScript
Ανοίξτε το αρχείο EPS που θέλετε να μετατρέψετε. Η ροή τροφοδοτεί το έγγραφο στο Aspose.Page.

Το `FileInputStream` διαβάζει το αρχείο EPS από το δίσκο, επιτρέποντας στον κατασκευαστή `Document` να αναλύσει τα δεδομένα PostScript.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Βήμα 3: έλεγχος άδειας εγγράφου
Πάντα επαληθεύστε ότι η μετρημένη άδεια εφαρμόστηκε σωστά πριν από την επεξεργασία.

Η μέθοδος `isLicensed()` επιστρέφει `true` μόνο όταν τα παρεχόμενα κλειδιά είναι έγκυρα, αποτρέποντας τυχαία χρήση μιας μη αδειοδοτημένης βιβλιοθήκης.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Βήμα 4: αρχικοποίηση επιλογών και συσκευής εικόνας
Δημιουργήστε το αντικείμενο επιλογών που ελέγχει τις ρυθμίσεις μετατροπής και τη συσκευή που θα λάβει την αποδιδόμενη εικόνα.

Το `ImageDevice` καταγράφει την ραστερική έξοδο στη μνήμη, ενώ το `ImageSaveOptions` σας επιτρέπει να ρυθμίσετε το DPI, το επίπεδο συμπίεσης και το βάθος χρώματος.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Βήμα 5: αποθήκευση αρχείου EPS ως εικόνα
Αυτή είναι η κύρια κλήση **save EPS as PNG**. Το έγγραφο αποδίδεται στη συσκευή εικόνας χρησιμοποιώντας τις επιλογές που διαμορφώσαμε.

Η μέθοδος `document.save(device, options)` εκτελεί τη ραστεροποίηση σε ένα μόνο βήμα.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Βήμα 6: λήψη και αποθήκευση byte εικόνας
Εξάγετε τα byte PNG από τη συσκευή και γράψτε τα σε αρχείο στο δίσκο. Αυτό το βήμα δείχνει πώς να **γράψετε αρχείο PNG Java** με ασφάλεια.

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` αποθηκεύει την εικόνα χωρίς πρόσθετες βιβλιοθήκες.

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

## Συχνά προβλήματα και λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| **Η άδεια δεν αναγνωρίζεται** | Τα κλειδιά είναι εσφαλμένα ή το `setMeteredKey` καλείται μετά την επεξεργασία του εγγράφου. | Ελέγξτε ξανά τις αλφαριθμητικές συμβολοσειρές των δημόσιων/ιδιωτικών κλειδιών και βεβαιωθείτε ότι το `setMeteredKey` εκτελείται πριν από οποιαδήποτε κλήση στο Aspose.Page. |
| **Το αρχείο εξόδου είναι κενό** | `device.getImagesBytes()` επέστρεψε `null` επειδή το αρχείο EPS δεν μπόρεσε να αναλυθεί. | Επιβεβαιώστε ότι το αρχείο EPS είναι έγκυρο και ότι το `ImageSaveOptions` καθορίζει μέγεθος καμβά μη μηδενικό. |
| **OutOfMemoryError σε μεγάλα EPS** | Η απόδοση μεγάλων διανυσματικών αρχείων καταναλώνει πολύ μνήμη heap. | Επεξεργαστείτε τις σελίδες μία‑μία ή αυξήστε τη μνήμη heap της JVM (`-Xmx2g`). |

## Συχνές ερωτήσεις

**Ε: Πώς μπορώ να αποκτήσω τα δημόσια και ιδιωτικά κλειδιά της μετρημένης άδειας;**  
Α: Συνδεθείτε στον λογαριασμό σας στο Aspose, μεταβείτε στην ενότητα **Metered License** και αντιγράψτε τα παραγόμενα δημόσια και ιδιωτικά κλειδιά.

**Ε: Είναι η βιβλιοθήκη Aspose.Page δωρεάν;**  
Α: Το Aspose.Page προσφέρει δωρεάν δοκιμή με πλήρη λειτουργικότητα· η χρήση σε παραγωγή απαιτεί πληρωμένη άδεια. Κατεβάστε τη δοκιμή από τη [σελίδα δοκιμής Aspose](https://releases.aspose.com/).

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;**  
Α: Ναι, μια εμπορική άδεια επιτρέπει την ανάπτυξη σε περιβάλλοντα παραγωγής. Αγοράστε άδεια από τη [σελίδα αγοράς Aspose](https://purchase.aspose.com/buy).

**Ε: Πού μπορώ να βρω πρόσθετη τεκμηρίωση;**  
Α: Η πλήρης αναφορά API είναι διαθέσιμη στη [αναφορά Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για αξιολόγηση;**  
Α: Προσωρινές άδειες παρέχονται μέσω της πύλης Aspose στη [σελίδα προσωρινής άδειας Aspose](https://purchase.aspose.com/temporary-license/).

**Ε: Τι γίνεται αν χρειαστεί να μετατρέψω αρχεία EPS πολλαπλών σελίδων;**  
Α: Επανάληψη σε κάθε σελίδα χρησιμοποιώντας το `device.getImagesBytes()` και γράψτε κάθε πίνακα byte σε ξεχωριστό αρχείο PNG.

**Ε: Μπορώ να αλλάξω την ποιότητα ή το βάθος χρώματος του PNG;**  
Α: Ναι, διαμορφώστε το `ImageSaveOptions` (π.χ., `options.setCompressionLevel(9)`) πριν καλέσετε το `document.save(...)`.

---

**Τελευταία ενημέρωση:** 2026-09-24  
**Δοκιμή με:** Aspose.Page 24.12 for Java (latest)  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Πώς να ορίσετε άδεια για το Aspose.Page Java API – License Management](/page/java/license-management/)
- [Μετατροπή PS σε PNG με το Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Αλλαγή μεγέθους EPS χρησιμοποιώντας Aspose.Page – Java EPS Manipulation](/page/java/manipulation-eps/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}