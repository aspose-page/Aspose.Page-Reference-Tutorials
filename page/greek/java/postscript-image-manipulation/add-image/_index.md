---
date: 2026-08-23
description: Μάθετε πώς να χρησιμοποιήσετε το aspose.page image manipulation java
  για να ενσωματώσετε και να περιστρέψετε εικόνες σε αρχεία PostScript με σαφή παραδείγματα
  Java.
keywords:
- aspose.page image manipulation java
- add image postscript java
- java postscript image rotation
- aspose.page java tutorial
- image embedding java
lastmod: 2026-08-23
linktitle: Προσθήκη εικόνας σε Java PostScript
og_description: Μάθετε πώς να χρησιμοποιήσετε το aspose.page image manipulation java
  για να ενσωματώσετε και να περιστρέψετε εικόνες σε αρχεία PostScript, με βήμα-βήμα
  παραδείγματα κώδικα Java.
og_image_alt: Guide showing Java code to add and rotate images in PostScript using
  Aspose.Page
og_title: Πώς να χρησιμοποιήσετε το aspose.page image manipulation java για να προσθέσετε
  εικόνα
schemas:
- author: Aspose
  dateModified: '2026-08-23'
  description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  headline: How to use aspose.page image manipulation java to add image
  type: TechArticle
- description: Learn how to use aspose.page image manipulation java to embed and rotate
    images in PostScript files with clear Java examples.
  name: How to use aspose.page image manipulation java to add image
  steps:
  - name: write graphics save
    text: Saving the graphics state isolates your transformations so you can revert
      later. This is equivalent to the `gsave` operator in raw PostScript.
  - name: translate and transform (translate and rotate image)
    text: First, create a `BufferedImage` from the source file, then build an `AffineTransform`
      that translates the image to the desired coordinates and rotates it around its
      centre. `AffineTransform.rotate` expects an angle in radians, so convert degrees
      with `Math.toRadians(degrees)`. **AffineTransform** is
  - name: add image to document
    text: After configuring the transform, draw the image onto the current page. The
      library automatically converts the `BufferedImage` into an appropriate PostScript
      image stream.
  - name: write graphics restore
    text: Calling restore (`grestore`) returns the graphics state to what it was before
      the save, ensuring subsequent drawing commands are not affected by the previous
      transformation.
  - name: close current page and save
    text: Finish the page, close the document, and write the output file to disk.
      You can repeat the above sequence to embed additional images, adjusting the
      translation coordinates and rotation angle each time.
  type: HowTo
- questions:
  - answer: The core library is Java‑only, but Aspose provides equivalent APIs for
      .NET, C++, and Python, each tailored to its platform.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access the free trial **[Aspose.Page free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for community assistance.
    question: Where can I find community support and discussions related to Aspose.Page
      for Java?
  - answer: You can buy the library **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.
    question: Are there any additional resources for purchasing Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image manipulation
- postscript
- image rotation
- java tutorial
title: Πώς να χρησιμοποιήσετε το aspose.page image manipulation java για να προσθέσετε
  εικόνα
url: /el/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε το aspose.page image manipulation java για να προσθέσετε εικόνα

## Εισαγωγή
Σε αυτό το tutorial θα μάθετε πώς να **χρησιμοποιήσετε το aspose.page image manipulation java** για να δημιουργήσετε αρχεία PostScript, να ενσωματώσετε ραστερ εικόνες και να εφαρμόσετε μετασχηματισμούς μετάφρασης‑και‑περιστροφής. Στο τέλος του οδηγού θα μπορείτε να δημιουργήσετε έξοδο PostScript με τέλεια pixel από Java — ιδανικό για αυτοματοποιημένες αναφορές, εκτυπώσεις ή οποιαδήποτε ροή εργασίας που απαιτεί ακριβή τοποθέτηση εικόνας μέσα σε ένα έγγραφο PostScript.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for Java  
- **Μπορώ να προσθέσω πολλαπλές εικόνες;** Ναι – επαναλάβετε τα βήματα μετασχηματισμού και σχεδίασης για κάθε εικόνα  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται άδεια για παραγωγή  
- **Ποια έκδοση Java υποστηρίζεται;** Java 8 και νεότερες  
- **Υποστηρίζεται η περιστροφή εικόνας;** Απόλυτα – χρησιμοποιήστε `AffineTransform.rotate()`  

## Τι είναι το aspose.page image manipulation java;
`aspose.page image manipulation java` είναι το API Aspose.Page που σας επιτρέπει να δημιουργείτε, επεξεργάζεστε και αποδίδετε έγγραφα PostScript προγραμματιστικά από κώδικα Java, με πλήρη έλεγχο της τοποθέτησης, κλιμάκωσης και περιστροφής εικόνων. Με αυτό το API αποφεύγετε τη χαμηλού επιπέδου σύνταξη PostScript και αφήνετε τη βιβλιοθήκη να διαχειρίζεται εσωτερικά τη μετατροπή μορφών και την ενσωμάτωση.

## Γιατί να χρησιμοποιήσετε το aspose.page για χειρισμό εικόνας;
Aspose.Page παρέχει **50+ μορφές εικόνας** (συμπεριλαμβανομένων JPEG, PNG, BMP, TIFF) και μπορεί να τις ενσωματώσει σε PostScript χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, επιτρέποντας την επεξεργασία αρχείων με εκατοντάδες σελίδες ενώ η χρήση μνήμης παραμένει κάτω από 100 MB σε τυπικό διακομιστή. Το υψηλού επιπέδου API αφαιρεί την πολυπλοκότητα των εντολών PostScript, ώστε να γράφετε σύντομο κώδικα Java αντί για ακατέργαστους τελεστές PS.

## Προαπαιτούμενα
- Java Development Kit (JDK) 8 ή νεότερο εγκατεστημένο.  
- Βιβλιοθήκη Aspose.Page for Java – κατεβάστε την **[Aspose.Page for Java download page](https://releases.aspose.com/page/java/)**.  
- Βασική εξοικείωση με τη σύνταξη της Java και τον αντικειμενοστραφή προγραμματισμό.

## Τι είναι η δημιουργία postscript java;
Η δημιουργία ενός αρχείου PostScript από Java σημαίνει την προγραμματιστική παραγωγή ενός εγγράφου `.ps` που περιγράφει τη διάταξη σελίδας, τα διανυσματικά γραφικά και τις ραστερ εικόνες χρησιμοποιώντας τη γλώσσα PostScript. Το Aspose.Page μετατρέπει τις κλήσεις Java σε έγκυρες εντολές PostScript, επιτρέποντάς σας να παράγετε αρχεία έτοιμα για εκτύπωση χωρίς ξεχωριστό διερμηνέα PostScript.

## Πώς να προσθέσετε μια εικόνα με μετάφραση και περιστροφή βήμα προς βήμα

Φορτώστε την εικόνα σας, εφαρμόστε ένα `AffineTransform` και σχεδιάστε την στη σελίδα. Τα παρακάτω βήματα περιγράφουν τη ακριβή ακολουθία που πρέπει να ακολουθήσετε.

### Βήμα 1: αποθήκευση γραφικών
Η αποθήκευση της κατάστασης γραφικών απομονώνει τους μετασχηματισμούς σας ώστε να μπορείτε να επανέλθετε αργότερα. Αυτό είναι ισοδύναμο με τον τελεστή `gsave` σε ακατέργαστο PostScript.

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Βήμα 2: μετάφραση και μετασχηματισμός (μετάφραση και περιστροφή εικόνας)
Πρώτα, δημιουργήστε ένα `BufferedImage` από το αρχείο πηγής, έπειτα δημιουργήστε ένα `AffineTransform` που μεταφράζει την εικόνα στις επιθυμητές συντεταγμένες και την περιστρέφει γύρω από το κέντρο της. Η `AffineTransform.rotate` αναμένει γωνία σε ακτίνια, οπότε μετατρέψτε τις μοίρες με `Math.toRadians(degrees)`.

**AffineTransform** είναι μια κλάση Java που αντιπροσωπεύει 2‑Δ μετασχηματισμό, όπως μετάφραση, περιστροφή, κλιμάκωση ή παραμόρφωση.  
**BufferedImage** είναι μια κλάση Java που αποθηκεύει μια εικόνα στη μνήμη ως ραστερ εικονοστοιχείων.

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

### Βήμα 3: προσθήκη εικόνας στο έγγραφο
Αφού διαμορφώσετε τον μετασχηματισμό, σχεδιάστε την εικόνα στην τρέχουσα σελίδα. Η βιβλιοθήκη μετατρέπει αυτόματα το `BufferedImage` σε κατάλληλο ρεύμα εικόνας PostScript.

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

### Βήμα 4: επαναφορά γραφικών
Η κλήση επαναφοράς (`grestore`) επιστρέφει την κατάσταση γραφικών στην κατάσταση πριν την αποθήκευση, εξασφαλίζοντας ότι οι επόμενες εντολές σχεδίασης δεν επηρεάζονται από τον προηγούμενο μετασχηματισμό.

```java
document.drawImage(image, transform, null);
```

### Βήμα 5: κλείσιμο τρέχουσας σελίδας και αποθήκευση
Ολοκληρώστε τη σελίδα, κλείστε το έγγραφο και γράψτε το αρχείο εξόδου στο δίσκο.

```java
document.writeGraphicsRestore();
```

Μπορείτε να επαναλάβετε τη παραπάνω ακολουθία για να ενσωματώσετε επιπλέον εικόνες, προσαρμόζοντας τις συντεταγμένες μετάφρασης και τη γωνία περιστροφής κάθε φορά.

## Συχνά προβλήματα και λύσεις
- **FileNotFoundException:** Επαληθεύστε ότι το `dataDir` τελειώνει με διαχωριστικό αρχείου (`/` ή `\\`) και ότι το όνομα αρχείου της εικόνας ταιριάζει ακριβώς.  
- **ImageIO.read returns null:** Βεβαιωθείτε ότι η μορφή της εικόνας βρίσκεται στη λίστα υποστηριζόμενων (JPEG, PNG, BMP, GIF, TIFF).  
- **Incorrect rotation angle:** Η `AffineTransform.rotate` λειτουργεί με ακτίνια· χρησιμοποιήστε `Math.toRadians(degrees)` για μετατροπή από μοίρες.  
- **Memory spikes on large pages:** Χρησιμοποιήστε `Document.save` με `saveOptions.setCompress(true)` για μείωση της μνήμης.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες γλώσσες προγραμματισμού;**  
A: Η κύρια βιβλιοθήκη είναι μόνο για Java, αλλά η Aspose παρέχει ισοδύναμα API για .NET, C++ και Python, το καθένα προσαρμοσμένο στην πλατφόρμα του.

**Q: Υπάρχει δωρεάν δοκιμαστική έκδοση για το Aspose.Page for Java;**  
A: Ναι, μπορείτε να αποκτήσετε πρόσβαση στη δωρεάν δοκιμή **[Aspose.Page free trial page](https://releases.aspose.com/)**.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
A: Μπορείτε να λάβετε προσωρινή άδεια **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

**Q: Πού μπορώ να βρω υποστήριξη κοινότητας και συζητήσεις σχετικά με το Aspose.Page for Java;**  
A: Επισκεφθείτε το **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** για βοήθεια από την κοινότητα.

**Q: Υπάρχουν πρόσθετοι πόροι για την αγορά του Aspose.Page for Java;**  
A: Μπορείτε να αγοράσετε τη βιβλιοθήκη **[Aspose.Page purchase page](https://purchase.aspose.com/buy)**.

## Συμπέρασμα
Τώρα έχετε ένα πλήρες, ολοκληρωμένο παράδειγμα **aspose.page image manipulation java** που δημιουργεί αρχείο PostScript, μεταφράζει και περιστρέφει μια εικόνα και αποθηκεύει το αποτέλεσμα. Εξερευνήστε την πλήρη **[documentation](https://reference.aspose.com/page/java/)** για να ανακαλύψετε προχωρημένα χαρακτηριστικά όπως διανυσματικά γραφικά, προσαρμοσμένα μεγέθη σελίδας και απόδοση κειμένου.

---

**Last Updated:** 2026-08-23  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  








```java
document.closePage();
document.save();
```

## Σχετικά Μαθήματα

- [Πώς να μετατρέψετε το PostScript σε PDF χρησιμοποιώντας το Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Πώς να προσθέσετε διαβάθμιση: Διαγώνια διαβάθμιση σε Java PostScript χρησιμοποιώντας το Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Πώς να προσθέσετε μοτίβο γραμμών σε Java PostScript με το Aspose.Page](/page/java/postscript-hatch-patterns/add-hatch-pattern/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}