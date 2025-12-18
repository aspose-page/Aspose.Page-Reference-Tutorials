---
date: 2025-12-18
description: Μάθετε πώς να προσθέσετε πλέγμα και διαφανές ορθογώνιο σε έγγραφα Java
  XPS με το Aspose.Page. Οδηγός βήμα‑προς‑βήμα για την αποδοτική αποθήκευση εγγράφου
  XPS.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Πώς να προσθέσετε πλέγμα χρησιμοποιώντας Visual Brush στη Java
url: /el/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε πλέγμα χρησιμοποιώντας Visual Brush σε Java

## Εισαγωγή
Αν ψάχνετε **πώς να προσθέσετε πλέγμα** σε έγγραφα XPS που δημιουργούνται με Java, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα σας καθοδηγήσουμε στη δημιουργία πλέγματος με Visual Brush, στην προσθήκη ενός διαφανούς ορθογωνίου και, τέλος, στο **αποθήκευση εγγράφου XPS** χρησιμοποιώντας το Aspose.Page Java API. Στο τέλος θα έχετε ένα επαγγελματικό οπτικό αποτέλεσμα που μπορεί να επαναχρησιμοποιηθεί σε αναφορές, τιμολόγια ή οποιαδήποτε εφαρμογή με έντονη χρήση εγγράφων.

## Γρήγορες Απαντήσεις
- **Τι κάνει ένα Visual Brush;** Ζωγραφίζει μια καθορισμένη περιοχή με επαναχρησιμοποιήσιμο οπτικό περιεχόμενο, ιδανικό για επαναλαμβανόμενα μοτίβα όπως πλέγματα.  
- **Μπορώ να αλλάξω το χρώμα του πλέγματος;** Ναι – τροποποιήστε τις ρυθμίσεις του solid‑color brush.  
- **Πώς προσθέτω ένα διαφανές ορθογώνιο πάνω στο πλέγμα;** Χρησιμοποιήστε `setOpacity` σε ένα path γεμάτο με ένα στερεό χρώμα.  
- **Ποια μέθοδος αποθηκεύει το αρχείο;** Η `doc.save(...)` γράφει το αρχείο XPS στο δίσκο.  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή ή πλήρης άδεια για παραγωγική χρήση.

## Τι είναι το Visual Brush Grid;
Ένα Visual Brush σας επιτρέπει να ορίσετε ένα μικρό οπτικό (το μοτίβο του πλέγματος) και στη συνέχεια να το επαναλάβετε (tile) σε μια μεγαλύτερη περιοχή. Αυτή η προσέγγιση είναι πιο αποδοτική σε μνήμη από το να σχεδιάζετε κάθε γραμμή ξεχωριστά και προσφέρει τέλεια επαναληψιμότητα pixel‑perfect.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για αυτήν την εργασία;
- **Cross‑platform** – Λειτουργεί σε οποιοδήποτε OS που υποστηρίζει Java.  
- **Υψηλής πιστότητας απόδοση** – Ακριβής έλεγχος χρωμάτων, διαφάνειας και επαναλαμβανόμενης εμφάνισης.  
- **Χωρίς εξωτερικές εξαρτήσεις** – Όλα διαχειρίζονται μέσω της βιβλιοθήκης Aspose.Page.

## Προαπαιτούμενα
Πριν προχωρήσουμε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού Java.  
- Εγκατεστημένη τη βιβλιοθήκη Aspose.Page – μπορείτε να τη κατεβάσετε από την [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 ή νεότερο εγκατεστημένο στο μηχάνημά σας.

## Εισαγωγή Πακέτων
Πρώτα, εισάγετε τις απαιτούμενες κλάσεις ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι τύποι που θα χρησιμοποιήσουμε:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Οδηγός Βήμα‑βήμα

### Βήμα 1: Ρύθμιση του Έργου σας
Δημιουργήστε ένα νέο αντικείμενο `XpsDocument` και ορίστε το φάκελο όπου θα αποθηκευτεί το αρχείο εξόδου.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Βήμα 2: Δημιουργία Magenta Grid Visual Brush
Ορίζουμε ένα μικρό σχήμα ματζέντας που θα επαναλαμβάνεται σε όλη την περιοχή του πλέγματος.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Βήμα 3: Ορισμός Γεωμετρίας για το Grid Brush
Ρυθμίστε την ορθογώνια περιοχή που θα λάβει το επαναλαμβανόμενο οπτικό.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Βήμα 4: Δημιουργία Νέου Καμβά για το Έγγραφο
Προσθέστε έναν καμβά στο έγγραφο και τοποθετήστε τον εκεί όπου θα εμφανιστεί το πλέγμα.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Βήμα 5: Προσθήκη του Πλέγματος στον Καμβά
Εφαρμόστε το visual brush στη γεωμετρία, ενεργοποιώντας την επαναλαμβανόμενη εμφάνιση.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Βήμα 6: Προσθήκη Διαφανούς Κόκκινου Ορθογωνίου (Δευτερεύουσα Λειτουργία)
Εδώ δείχνουμε **πώς να προσθέσετε διαφανές ορθογώνιο** πάνω στο πλέγμα για έμφαση.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Βήμα 7: Αποθήκευση του Παραγόμενου Εγγράφου XPS
Τέλος, γράψτε το έγγραφο στο δίσκο – αυτό είναι το βήμα **αποθήκευσης εγγράφου XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Ακολουθήστε αυτά τα βήματα και θα έχετε ένα επαγγελματικό πλέγμα με διαφανή επικάλυψη, όλα δημιουργημένα προγραμματιστικά.

## Συχνά Προβλήματα & Συμβουλές

- **Λάθος μέγεθος πλακιδίου:** Βεβαιωθείτε ότι το `Rectangle2D` που χρησιμοποιείται για το brush ταιριάζει με το επιθυμητό μέγεθος επανάληψης· διαφορετικά το μοτίβο μπορεί να παραμορφωθεί.  
- **Η διαφάνεια δεν εφαρμόζεται:** Θυμηθείτε να καλέσετε `setOpacity` στο path που θέλετε διαφανές· δεν επηρεάζει το ίδιο το brush.  
- **Το αρχείο δεν αποθηκεύεται:** Ελέγξτε ότι το `dataDir` δείχνει σε υπάρχον φάκελο και ότι η εφαρμογή σας έχει δικαιώματα εγγραφής.

## Συχνές Ερωτήσεις

**Ε: Είναι το Aspose.Page κατάλληλο για επαγγελματική δημιουργία εγγράφων;**  
Α: Ναι, το Aspose.Page είναι μια ισχυρή βιβλιοθήκη σχεδιασμένη για δημιουργία υψηλής ποιότητας XPS και PDF σε Java.

**Ε: Μπορώ να προσαρμόσω τα χρώματα του πλέγματος χρησιμοποιώντας Visual Brush;**  
Α: Απόλυτα! Αλλάξτε τις παραμέτρους του `createColor` στην κλήση `setFill` του brush σε οποιεσδήποτε τιμές RGBA χρειάζεστε.

**Ε: Πού μπορώ να βρω επιπλέον υποστήριξη για το Aspose.Page;**  
Α: Επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για βοήθεια από την κοινότητα και επίσημες απαντήσεις.

**Ε: Υπάρχει δωρεάν δοκιμή για το Aspose.Page;**  
Α: Ναι, μπορείτε να αποκτήσετε τη [δωρεάν δοκιμή](https://releases.aspose.com/) για να εξερευνήσετε όλες τις δυνατότητες πριν την αγορά.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
Α: Αποκτήστε μια [προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) που λειτουργεί για ανάπτυξη και αξιολόγηση.

---

**Τελευταία ενημέρωση:** 2025-12-18  
**Δοκιμάστηκε με:** Aspose.Page for Java 23.12 (τελευταία έκδοση)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}