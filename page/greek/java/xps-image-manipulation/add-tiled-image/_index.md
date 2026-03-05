---
date: 2025-12-28
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS σε Java χρησιμοποιώντας το Aspose.Page
  και να προσθέσετε εύκολα εικόνα σε πλακίδια με αυτόν τον βήμα‑βήμα οδηγό.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Πώς να δημιουργήσετε έγγραφο XPS με εικόνα σε πλακίδια σε Java
url: /el/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εγγράφου XPS και προσθήκη ταμπλαρισμένης εικόνας σε Java

## Εισαγωγή
Στη σύγχρονη ανάπτυξη Java, η δυνατότητα **create XPS document** αρχείων προγραμματιστικά είναι μια πολύτιμη δεξιότητα, ειδικά όταν χρειάζεται να τα εμπλουτίσετε με γραφικά όπως ταμπλαρισμένες εικόνες. Το Aspose.Page for Java κάνει αυτή τη διαδικασία απλή, επιτρέποντάς σας να εστιάσετε στον οπτικό σχεδιασμό αντί για τη χαμηλού επιπέδου διαχείριση αρχείων. Σε αυτό το tutorial θα μάθετε ακριβώς πώς να δημιουργήσετε ένα έγγραφο XPS, **add tiled image**, και να αποθηκεύσετε το αποτέλεσμα, όλα με σαφή, βήμα‑βήμα παραδείγματα κώδικα.

## Γρήγορες Απαντήσεις
- **What does Aspose.Page do?** Παρέχει ένα υψηλού επιπέδου API για τη δημιουργία και τη διαχείριση εγγράφων XPS σε Java.  
- **Can I tile an image?** Ναι – χρησιμοποιήστε `XpsImageBrush` με `XpsTileMode.Tile`.  
- **Do I need a license?** Απαιτείται προσωρινή ή εμπορική άδεια για χρήση σε παραγωγή.  
- **What Java version is supported?** Οποιαδήποτε έκδοση JDK 8+ είναι συμβατή.  
- **How long does implementation take?** Περίπου 10–15 λεπτά για ένα βασικό σενάριο ταμπλαρισμένης εικόνας.

## Τι είναι η “create XPS document”;
Ένα αρχείο XPS (XML Paper Specification) είναι μια μορφή σταθερού layout παρόμοια με το PDF. Η δημιουργία ενός εγγράφου XPS προγραμματιστικά σας επιτρέπει να παράγετε εκτυπώσιμα, ανεξάρτητα από τη συσκευή αρχεία απευθείας από κώδικα Java.

## Γιατί να προσθέσετε ταμπλαρισμένη εικόνα;
Η ταμπλαρισμένη εικόνα επαναλαμβάνει το γραφικό σε μια καθορισμένη περιοχή, κάτι που είναι ιδανικό για φόντα, υδατογραφήματα ή γεμίσεις με μοτίβα. Χρησιμοποιώντας το `XpsTileMode.Tile` του Aspose.Page μπορείτε να το πετύχετε με λίγες μόνο γραμμές κώδικα.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – Εγκατεστημένο JDK 8 ή νεότερο.  
2. **Aspose.Page for Java** – Κατεβάστε το από την [website](https://releases.aspose.com/page/java/).  
3. **A writable directory** – όπου θα αποθηκευτεί το παραγόμενο αρχείο XPS.

## Εισαγωγή Πακέτων
Στο έργο Java, εισάγετε τις απαραίτητες κλάσεις:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: Ρύθμιση του έργου σας
Προσθέστε τα JAR του Aspose.Page στο classpath του έργου σας και βεβαιωθείτε ότι οι δηλώσεις εισαγωγής (import) μεταγλωττίζονται χωρίς σφάλματα.

### Βήμα 2: Δημιουργία εγγράφου XPS
Δημιουργήστε ένα νέο αντικείμενο `XpsDocument`. Αυτό είναι ο βασικός container που θα περιέχει όλες τις σελίδες, τα paths και τους πόρους.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Βήμα 3: Ορισμός διαδρομής ταμπλαρισμένης εικόνας
Τοποθετήστε την εικόνα που θέλετε να ταμπλαρίσετε (π.χ. `R08LN_NN.jpg`) μέσα στον φάκελο που αναφέρεται από το `dataDir`. Η εικόνα θα χρησιμοποιηθεί ως μοτίβο βούρτσας.

### Βήμα 4: Προσθήκη ταμπλαρισμένης εικόνας
Δημιουργήστε ένα ορθογώνιο path και γεμίστε το με ένα `XpsImageBrush`. Ορίζοντας το tile mode σε `Tile`, η εικόνα επαναλαμβάνεται σε όλο το ορθογώνιο.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Βήμα 5: Αποθήκευση του εγγράφου
Αποθηκεύστε το αρχείο XPS στο δίσκο. Το αρχείο εξόδου θα περιέχει την ταμπλαρισμένη εικόνα που ορίσατε.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Επαναλάβετε αυτά τα βήματα όποτε χρειαστεί να **add tiled image** σε άλλες σελίδες ή σχήματα εντός του ίδιου εγγράφου XPS.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| Image not showing | Επαληθεύστε ότι η διαδρομή αρχείου (`dataDir + "R08LN_NN.jpg"`) είναι σωστή και ότι η εικόνα είναι προσβάσιμη. |
| Tile pattern appears stretched | Προσαρμόστε τις τιμές `Rectangle2D` προέλευσης και προορισμού για να ελέγξετε το μέγεθος του μοτίβου. |
| Opacity has no effect | Βεβαιωθείτε ότι η διαφάνεια της βούρτσας έχει οριστεί **after** τη ρύθμιση του tile mode. |

## Συχνές Ερωτήσεις

### Είναι το Aspose.Page συμβατό με όλες τις εκδόσεις της Java;
Το Aspose.Page σχεδιάστηκε για να λειτουργεί με διάφορες εκδόσεις της Java. Εξασφαλίστε τη συμβατότητα ελέγχοντας την τεκμηρίωση [here](https://reference.aspose.com/page/java/).

### Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;
Ναι, το Aspose.Page προσφέρει εμπορικές άδειες. Αγοράστε τις [here](https://purchase.aspose.com/buy).

### Υπάρχει διαθέσιμη δωρεάν δοκιμή;
Ναι, εξερευνήστε τις δυνατότητες του Aspose.Page με μια δωρεάν δοκιμή [here](https://releases.aspose.com/).

### Πού μπορώ να βρω υποστήριξη κοινότητας και συζητήσεις;
Συμμετέχετε στην κοινότητα του Aspose.Page στο [forum](https://forum.aspose.com/c/page/39).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page;
Αποκτήστε μια προσωρινή άδεια [here](https://purchase.aspose.com/temporary-license/).

---

**Τελευταία ενημέρωση:** 2025-12-28  
**Δοκιμή με:** Aspose.Page for Java 24.12 (latest)  
**Συγγραφέας:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
