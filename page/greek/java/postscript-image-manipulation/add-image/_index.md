---
date: 2025-12-09
description: Μάθετε πώς να δημιουργείτε έγγραφο PostScript σε Java και να μετατοπίζετε
  και να περιστρέφετε την εικόνα χρησιμοποιώντας το Aspose.Page για αδιάλειπτη επεξεργασία
  εικόνας.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Δημιουργία εγγράφου PostScript σε Java – Προσθήκη εικόνας σε PostScript Java
url: /el/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εγγράφου PostScript Java – Προσθήκη εικόνας σε Java PostScript

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να **δημιουργήσετε ένα έγγραφο PostScript Java** και να ενσωματώσετε εικόνες χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page for Java. Θα περάσουμε βήμα προς βήμα, από τη ρύθμιση του εγγράφου μέχρι την εφαρμογή μετασχηματισμών όπως οι λειτουργίες **μετάφραση και περιστροφή εικόνας**. Στο τέλος, θα μπορείτε να δημιουργείτε πλούσια αρχεία PostScript προγραμματιστικά και να προσαρμόζετε τη θέση των εικόνων ώστε να ταιριάζει ακριβώς με τις ανάγκες διάταξης σας.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java  
- **Μπορώ να προσθέσω πολλαπλές εικόνες;** Ναι – επαναλάβετε τα βήματα μετασχηματισμού και σχεδίασης  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται άδεια για παραγωγή  
- **Ποια έκδοση της Java υποστηρίζεται;** Java 8 και μεταγενέστερες  
- **Υποστηρίζεται η περιστροφή εικόνας;** Απόλυτα – χρησιμοποιήστε `AffineTransform.rotate()`  

## Τι είναι η δημιουργία εγγράφου PostScript σε Java;
Ένα έγγραφο PostScript είναι ένα αρχείο γλώσσας περιγραφής σελίδας που περιγράφει κείμενο, γραφικά και εικόνες. Χρησιμοποιώντας το Aspose.Page, μπορείτε να δημιουργείτε προγραμματιστικά αυτά τα αρχεία σε Java, παρέχοντάς σας πλήρη έλεγχο της διάταξης, της κατάστασης των γραφικών και της διαχείρισης εικόνων χωρίς την ανάγκη ερμηνευτή PostScript.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για επεξεργασία εικόνας;
- **API υψηλού επιπέδου:** Απλοποιεί σύνθετες εντολές PostScript.  
- **Διαπλατφορμικό:** Λειτουργεί σε οποιοδήποτε λειτουργικό σύστημα που υποστηρίζει Java.  
- **Πλήρης έλεγχος κατάστασης γραφικών:** Εύκολη αποθήκευση, επαναφορά, μετάφραση, κλιμάκωση και περιστροφή γραφικών.  
- **Χωρίς εξωτερικές εξαρτήσεις:** Διαχειρίζεται τη φόρτωση και τη μετατροπή εικόνων εσωτερικά.  

## Προαπαιτούμενα
Πριν βουτήξουμε στον κώδικα, βεβαιωθείτε ότι έχετε:

- Java Development Kit (JDK) εγκατεστημένο στο σύστημά σας.  
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
Το πρώτο βήμα περιλαμβάνει την εγγραφή της αποθήκευσης των γραφικών στο έγγραφο. Αυτό εξασφαλίζει ότι τυχόν μετασχηματισμοί ή τροποποιήσεις που γίνονται μετά μπορούν να αναιρεθούν εάν χρειαστεί.

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

## Βήμα 2: Μετάφραση και Μετασχηματισμός (μετάφραση και περιστροφή εικόνας)
Στη συνέχεια, μεταφράστε το έγγραφο και δημιουργήστε ένα αντικείμενο `BufferedImage` από το αρχείο εικόνας. Εφαρμόστε μια σειρά μετασχηματισμών όπως κλιμάκωση και περιστροφή χρησιμοποιώντας το `AffineTransform`. Εδώ πραγματοποιείται η λειτουργία **μετάφραση και περιστροφή εικόνας**.

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
Μετά την προσθήκη της εικόνας, γράψτε την επαναφορά των γραφικών για να ολοκληρώσετε τις αλλαγές που έγιναν.

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

## Συνηθισμένα Προβλήματα και Λύσεις
- **FileNotFoundException:** Βεβαιωθείτε ότι η διαδρομή `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`) και ότι το όνομα του αρχείου εικόνας ταιριάζει ακριβώς.  
- **ImageIO.read επιστρέφει null:** Επαληθεύστε ότι η μορφή της εικόνας υποστηρίζεται (π.χ., JPEG, PNG).  
- **Λανθασμένη γωνία περιστροφής:** Η `AffineTransform.rotate` αναμένει ακτίνια. Μετατρέψτε τις μοίρες σε ακτίνια (`Math.toRadians(degrees)`) εάν χρειάζεται.  

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες γλώσσες προγραμματισμού;**  
Α: Το Aspose.Page υποστηρίζει κυρίως τη Java, αλλά υπάρχουν εκδόσεις διαθέσιμες και για άλλες γλώσσες προγραμματισμού.

**Ε: Υπάρχει δωρεάν δοκιμή διαθέσιμη για το Aspose.Page for Java;**  
Α: Ναι, μπορείτε να αποκτήσετε πρόσβαση στη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
Α: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Ε: Πού μπορώ να βρω υποστήριξη κοινότητας και συζητήσεις σχετικά με το Aspose.Page for Java;**  
Α: Επισκεφθείτε το [Φόρουμ Aspose.Page](https://forum.aspose.com/c/page/39) για υποστήριξη κοινότητας.

**Ε: Υπάρχουν πρόσθετοι πόροι για την αγορά του Aspose.Page for Java;**  
Α: Μπορείτε να αγοράσετε τη βιβλιοθήκη [εδώ](https://purchase.aspose.com/buy).

## Συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να **δημιουργήσετε ένα έγγραφο PostScript Java** και να ενσωματώσετε εικόνες χρησιμοποιώντας το Aspose.Page for Java. Εξερευνήστε την [τεκμηρίωση](https://reference.aspose.com/page/java/) για πιο προχωρημένα χαρακτηριστικά και λειτουργίες, όπως διανυσματικά γραφικά, απόδοση κειμένου και προσαρμοσμένα μεγέθη σελίδας.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}