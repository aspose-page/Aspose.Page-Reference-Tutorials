---
date: 2026-04-30
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS Java και να προσθέσετε μάσκα
  διαφάνειας χρησιμοποιώντας το Aspose.Page Java. Οδηγός βήμα‑βήμα με παραδείγματα
  κώδικα.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Ορισμός μάσκας αδιαφάνειας σε Java XPS
second_title: Aspose.Page Java API
title: Δημιουργία εγγράφου XPS Java – Ορισμός μάσκας αδιαφάνειας με το Aspose.Page
url: /el/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός μάσκας αδιαφάνειας σε Java XPS χρησιμοποιώντας το Aspose.Page Java

## Εισαγωγή
Σε αυτό το tutorial θα **δημιουργήσετε αρχεία XPS document Java** και θα μάθετε πώς να εφαρμόζετε μια μάσκα αδιαφάνειας που δίνει στα γραφικά σας μια γυαλισμένη, ημιδιαφανή εμφάνιση. Θα περάσουμε από όλη τη διαδικασία — από την αρχικοποίηση ενός εγγράφου XPS, την προσθήκη ενός καμβά, το σχεδιασμό ενός ορθογωνίου, μέχρι την προσθήκη μιας μάσκας αδιαφάνειας βασισμένης σε εικόνα — χρησιμοποιώντας το διαισθητικό Aspose.Page Java API. Στο τέλος, θα μπορείτε να δημιουργείτε επαγγελματικά αρχεία XPS προγραμματιστικά και να επαναχρησιμοποιείτε τη μάσκα σε οποιοδήποτε σχήμα χρειάζεστε.

## Γρήγορες απαντήσεις
- **What does an opacity mask do?** Ορίζει διαφορετικά επίπεδα διαφάνειας για ένα σχήμα, επιτρέποντας στο υποκείμενο περιεχόμενο να φαίνεται.  
- **Which library is required?** Aspose.Page for Java (aspose page java).  
- **Do I need a license?** Μια προσωρινή άδεια λειτουργεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **How many lines of code?** Περίπου 20 γραμμές Java συν μερικές δηλώσεις ρύθμισης.  
- **Can I reuse the mask on multiple shapes?** Ναι, μπορείτε να αντιστοιχίσετε το ίδιο `ImageBrush` σε πολλά paths.

## Τι είναι μια μάσκα αδιαφάνειας σε XPS;
Μια μάσκα αδιαφάνειας είναι ένα bitmap ή vector που ελέγχει το άλφα (διαφάνεια) κάθε pixel σε ένα σχήμα. Όταν εφαρμόζεται σε ένα ορθογώνιο, τμήματα του ορθογωνίου γίνονται πλήρως αδιαφανή, μερικώς διαφανή ή πλήρως διαφανή, δημιουργώντας σύνθετα οπτικά εφέ χωρίς επιπλέον στρώματα σχεδίασης.

## Γιατί να χρησιμοποιήσετε το Aspose.Page Java για **create XPS document java**;
- **Pure Java API** – Καθαρό Java API – Χωρίς εγγενείς εξαρτήσεις, έτσι ο ίδιος κώδικας εκτελείται σε Windows, Linux ή macOS.  
- **Full XPS spec compliance** – Πλήρης συμμόρφωση με το πρότυπο XPS – Οι μάσκες αποδίδονται ακριβώς όπως ορίζεται από το πρότυπο XPS.  
- **Object‑oriented design** – Σχεδίαση αντικειμενοστραφούς προγραμματισμού – Παρόμοια με .NET, καθιστώντας εύκολο το ξεκίνημα αν έχετε χρησιμοποιήσει το Aspose σε άλλες γλώσσες.  
- **High performance** – Υψηλή απόδοση – Βελτιστοποιημένο για μεγάλα έγγραφα και επεξεργασία παρτίδων.

## Κοινές περιπτώσεις χρήσης
- **Watermarking** – Εφαρμογή ημιδιαφανούς λογότυπου σε όλες τις σελίδες.  
- **Dynamic theming** – Δυναμική θεματοποίηση – Αλλαγή του οπτικού στυλ των στοιχείων UI σε παραγόμενες αναφορές.  
- **Print‑ready previews** – Προεπισκοπήσεις έτοιμες για εκτύπωση – Εμφάνιση του πώς θα φαίνεται ένα σχέδιο με διαφορετική διαφάνεια πριν την αποστολή σε εκτυπωτή.

## Προαπαιτούμενα
- Βασική κατανόηση του προγραμματισμού Java.  
- Βιβλιοθήκη Aspose.Page for Java εγκατεστημένη. Μπορείτε να τη κατεβάσετε **[here](https://releases.aspose.com/page/java/)**.  
- Έγκυρη άδεια για το Aspose.Page. Αν δεν έχετε, αποκτήστε μια προσωρινή άδεια **[here](https://purchase.aspose.com/temporary-license/)**.  
- Περιβάλλον ανάπτυξης ικανό να μεταγλωττίζει και να εκτελεί εφαρμογές Java (π.χ., IntelliJ IDEA, Eclipse ή VS Code).

## Εισαγωγή πακέτων
Ξεκινήστε εισάγοντας τις απαραίτητες κλάσεις από τη βιβλιοθήκη Aspose.Page. Αυτό εξασφαλίζει ότι το API είναι διαθέσιμο στο έργο σας.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Δημιουργία νέου εγγράφου XPS
Πρώτα, δημιουργήστε ένα νέο έγγραφο XPS που θα περιέχει όλα τα γραφικά μας.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Βήμα 2: Προσθήκη καμβά
Ένας καμβάς λειτουργεί ως επιφάνεια σχεδίασης μέσα στη σελίδα XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Βήμα 3: Προσθήκη ορθογωνίου και εφαρμογή γεμίσματος στερεού χρώματος
Εδώ δημιουργούμε μια διαδρομή ορθογωνίου και του δίνουμε γεμιστό κόκκινο χρώμα. Αυτό το ορθογώνιο θα λάβει αργότερα τη μάσκα αδιαφάνειας.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Βήμα 4: Προσθήκη μάσκας αδιαφάνειας χρησιμοποιώντας ImageBrush
Φορτώνουμε μια εικόνα TIFF, ορίζουμε τα ορθογώνια προέλευσης και προορισμού, και ρυθμίζουμε το πινέλο σε λειτουργία επαναλαμβανόμενου (tile) ώστε η μάσκα να επαναλαμβάνεται αν χρειαστεί.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Βήμα 5: Αποθήκευση του παραγόμενου εγγράφου XPS
Τέλος, αποθηκεύστε το έγγραφο στο δίσκο. Το αρχείο εξόδου θα περιέχει το ορθογώνιο με την εφαρμοσμένη μάσκα αδιαφάνειας.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Ακολουθήστε αυτά τα βήματα προσεκτικά για να ενσωματώσετε τη λειτουργία **add opacity mask** στο Java XPS έγγραφό σας χρησιμοποιώντας το Aspose.Page.

## Κοινά προβλήματα & αντιμετώπιση σφαλμάτων
- **Image not found** – Επαληθεύστε ότι το `dataDir` δείχνει στο σωστό φάκελο και ότι το `R08SY_NN.tif` υπάρχει.  
- **Mask appears solid** – Βεβαιωθείτε ότι η εικόνα προέλευσης περιέχει πραγματικά διαφορετικές τιμές άλφα· μια πλήρως αδιαφανής εικόνα δεν θα εμφανίσει διαφάνεια.  
- **Tile mode not respected** – Η λειτουργία tile δεν εφαρμόζεται – Το ορθογώνιο προορισμού πρέπει να είναι μικρότερο από το ορθογώνιο προέλευσης για να είναι εμφανής η επανάληψη.

## Συχνές ερωτήσεις

**Q: Είναι το Aspose.Page συμβατό με όλα τα περιβάλλοντα ανάπτυξης Java;**  
A: Ναι, το Aspose.Page έχει σχεδιαστεί ώστε να λειτουργεί άψογα με διάφορα IDE Java και εργαλεία κατασκευής.

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page χωρίς άδεια;**  
A: Αν και μπορείτε να αξιολογήσετε τη βιβλιοθήκη με προσωρινή άδεια, απαιτείται πλήρης άδεια για χρήση σε παραγωγή.

**Q: Υπάρχουν περιορισμοί στην δοκιμαστική έκδοση;**  
A: Η δοκιμαστική έκδοση μπορεί να επιβάλλει περιορισμούς μεγέθους ή λειτουργιών· συμβουλευτείτε την επίσημη τεκμηρίωση για λεπτομέρειες.

**Q: Πώς μπορώ να λάβω υποστήριξη για το Aspose.Page;**  
A: Επισκεφθείτε το **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** για βοήθεια από την κοινότητα ή αγοράστε άδεια για premium υποστήριξη.

**Q: Υπάρχει εγγύηση επιστροφής χρημάτων για το Aspose.Page;**  
A: Ανατρέξτε στη **[purchase page](https://purchase.aspose.com/buy)** για πληροφορίες σχετικά με τις πολιτικές επιστροφής χρημάτων.

---

**Τελευταία ενημέρωση:** 2026-04-30  
**Δοκιμή με:** Aspose.Page Java 24.11 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}