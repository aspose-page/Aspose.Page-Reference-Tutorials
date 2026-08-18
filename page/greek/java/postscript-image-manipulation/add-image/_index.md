---
date: 2026-02-15
description: Μάθετε πώς να δημιουργείτε έγγραφα PostScript Java και να παράγετε αρχεία
  εγγράφων PostScript με μετακίνηση και περιστροφή εικόνας χρησιμοποιώντας το Aspose.Page
  για Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Δημιουργία PostScript Java – Προσθήκη εικόνας σε Java PostScript
url: /el/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία PostScript Java – Προσθήκη εικόνας σε Java PostScript

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να **create postscript java** έγγραφα και να ενσωματώσετε εικόνες χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page for Java. Θα περάσουμε βήμα προς βήμα, από την αρχικοποίηση ενός νέου αρχείου PostScript μέχρι την εφαρμογή των μετασχηματισμών **translate and rotate image**. Στο τέλος, θα μπορείτε να δημιουργείτε αρχεία PostScript προγραμματιστικά και να ελέγχετε τη θέση των εικόνων με ακρίβεια pixel‑perfect — ιδανικό για αυτοματοποιημένες αναφορές, ροές εκτύπωσης ή οποιοδήποτε σενάριο όπου χρειάζεται να **generate postscript document** έξοδο από Java.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java  
- **Μπορώ να προσθέσω πολλαπλές εικόνες;** Yes – repeat the transform and draw steps  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for testing; a license is required for production  
- **Ποια έκδοση της Java υποστηρίζεται;** Java 8 and later  
- **Υποστηρίζεται η περιστροφή εικόνας;** Absolutely – use `AffineTransform.rotate()`

## Τι είναι το create postscript java;
Μια λειτουργία **create postscript java** παράγει ένα αρχείο περιγραφής σελίδας PostScript που κωδικοποιεί κείμενο, διανυσματικά γραφικά και ραστερ εικόνες. Με το Aspose.Page μπορείτε να δημιουργήσετε αυτά τα αρχεία απευθείας από κώδικα Java, παρέχοντάς σας πλήρη προγραμματιστικό έλεγχο πάνω στη διάταξη, την κλιμάκωση και την περιστροφή χωρίς την ανάγκη ξεχωριστού ερμηνευτή PostScript.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για επεξεργασία εικόνας;
- **High‑level API:** Αποσπά τις χαμηλού επιπέδου εντολές PostScript σε απλές μεθόδους Java.  
- **Cross‑platform:** Εκτελείται σε οποιοδήποτε OS που υποστηρίζει Java.  
- **Full graphics‑state control:** Επιτρέπει την αποθήκευση, επαναφορά, μετάφραση, κλιμάκωση και περιστροφή γραφικών όπως επιθυμείτε.  
- **No external dependencies:** Διαχειρίζεται τη φόρτωση εικόνας, τη μετατροπή μορφής και την ενσωμάτωση εσωτερικά.

## Προαπαιτούμενα
Πριν βυθιστούμε στον κώδικα, βεβαιωθείτε ότι έχετε:

- Java Development Kit (JDK) εγκατεστημένο στο σύστημα σας.  
- Βιβλιοθήκη Aspose.Page for Java. Μπορείτε να τη κατεβάσετε [εδώ](https://releases.aspose.com/page/java/).  
- Βασική κατανόηση του προγραμματισμού Java.

## Εισαγωγή Πακέτων
Για να ξεκινήσετε, εισάγετε τα απαραίτητα πακέτα στο έργο Java σας. Χρησιμοποιήστε το παρακάτω απόσπασμα κώδικα ως αναφορά:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Βήμα 1: Εγγραφή Αποθήκευσης Γραφικών
Το πρώτο βήμα περιλαμβάνει την εγγραφή της αποθήκευσης γραφικών στο έγγραφο. Αυτό εξασφαλίζει ότι τυχόν μετασχηματισμοί ή τροποποιήσεις που γίνονται αργότερα μπορούν να αναιρεθούν εάν χρειαστεί.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Βήμα 2: Μετάφραση και Μετασχηματισμός (translate and rotate image)
Στη συνέχεια, μεταφράστε το έγγραφο και δημιουργήστε ένα αντικείμενο `BufferedImage` από το αρχείο εικόνας. Εφαρμόστε μια σειρά μετασχηματισμών όπως κλιμάκωση και περιστροφή χρησιμοποιώντας `AffineTransform`. Εδώ πραγματοποιείται η λειτουργία **translate and rotate image**.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Βήμα 3: Προσθήκη Εικόνας στο Έγγραφο
Τώρα, προσθέστε τη μετασχηματισμένη εικόνα στο έγγραφο.

```java
document.drawImage(image, transform, null);
```

## Βήμα 4: Εγγραφή Επαναφοράς Γραφικών
Μετά την προσθήκη της εικόνας, γράψτε την επαναφορά γραφικών για να ολοκληρώσετε τις αλλαγές.

```java
document.writeGraphicsRestore();
```

## Βήμα 5: Κλείσιμο Τρέχουσας Σελίδας και Αποθήκευση
Κλείστε την τρέχουσα σελίδα και αποθηκεύστε το έγγραφο.

```java
document.closePage();
document.save();
```

Μπορείτε να επαναλάβετε αυτά τα βήματα για να προσθέσετε πολλαπλές εικόνες ή να προσαρμόσετε τους μετασχηματισμούς ανάλογα με τις απαιτήσεις σας.

## Κοινά Προβλήματα και Λύσεις
- **FileNotFoundException:** Βεβαιωθείτε ότι η διαδρομή `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`) και ότι το όνομα του αρχείου εικόνας ταιριάζει ακριβώς.  
- **ImageIO.read returns null:** Επαληθεύστε ότι η μορφή της εικόνας υποστηρίζεται (π.χ., JPEG, PNG).  
- **Incorrect rotation angle:** Η `AffineTransform.rotate` αναμένει ακτίνια. Μετατρέψτε τις μοίρες σε ακτίνια (`Math.toRadians(degrees)`) αν χρειάζεται.  

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες γλώσσες προγραμματισμού;**  
A: Το Aspose.Page υποστηρίζει κυρίως τη Java, αλλά υπάρχουν εκδόσεις διαθέσιμες και για άλλες γλώσσες προγραμματισμού.

**Q: Υπάρχει δωρεάν δοκιμαστική έκδοση για το Aspose.Page for Java;**  
A: Ναι, μπορείτε να αποκτήσετε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
A: Μπορείτε να λάβετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Πού μπορώ να βρω υποστήριξη κοινότητας και συζητήσεις σχετικά με το Aspose.Page for Java;**  
A: Επισκεφθείτε το [Aspose.Page Forum](https://forum.aspose.com/c/page/39) για υποστήριξη κοινότητας.

**Q: Υπάρχουν πρόσθετοι πόροι για την αγορά του Aspose.Page for Java;**  
A: Μπορείτε να αγοράσετε τη βιβλιοθήκη [εδώ](https://purchase.aspose.com/buy).

## Συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να **create postscript java** έγγραφα και να ενσωματώνετε εικόνες χρησιμοποιώντας το Aspose.Page for Java. Εξερευνήστε την [documentation](https://reference.aspose.com/page/java/) για πιο προχωρημένα χαρακτηριστικά και λειτουργίες, όπως διανυσματικά γραφικά, απόδοση κειμένου και προσαρμοσμένα μεγέθη σελίδας.

---

**Τελευταία Ενημέρωση:** 2026-02-15  
**Δοκιμάστηκε Με:** Aspose.Page for Java 23.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}