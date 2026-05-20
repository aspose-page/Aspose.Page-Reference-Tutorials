---
date: 2026-04-24
description: Μάθετε πώς να δημιουργήσετε έγγραφο XPS Java με έλλειψη ακτινικής διαβάθμισης.
  Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να ορίσετε το πάχος του περιγράμματος και να
  ορίσετε τη γεωμετρία διαδρομής χρησιμοποιώντας το Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Προσθήκη Έλλειψης στο Java XPS
second_title: Aspose.Page Java API
title: Δημιουργία εγγράφου XPS Java – Προσθήκη ελλειπτικού με ακτινική διαβάθμιση
url: /el/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Έλλειψης με Ακτινική Διαβάθμιση Gradient στο Aspose.Page

## Εισαγωγή
Σε αυτό το tutorial, θα μάθετε πώς να **create XPS document Java** με μια όμορφη έλλειψη με ακτινική διαβάθμιση γραμμής χρησιμοποιώντας το Aspose.Page για Java. Το Aspose.Page είναι μια ισχυρή βιβλιοθήκη που αφαιρεί τις λεπτομέρειες χαμηλού επιπέδου του XPS, επιτρέποντάς σας να εστιάσετε στο σχεδιασμό αντί στις ιδιαιτερότητες του μορφότυπου αρχείου. Στο τέλος αυτού του οδηγού θα έχετε ένα έτοιμο αρχείο XPS που μπορείτε να ενσωματώσετε σε αναφορές, τιμολόγια ή οποιαδήποτε ροή δημιουργίας εγγράφων.

## Γρήγορες Απαντήσεις
- **Τι παράγει αυτός ο κώδικας;** Ένα αρχείο XPS μονής σελίδας που περιέχει μια έλλειψη με γραμμή ακτινικής διαβάθμισης πολλαπλών χρωμάτων.  
- **Ποιο κύριο API χρησιμοποιείται;** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, κ.λπ.).  
- **Χρειάζομαι άδεια για την εκτέλεση του δείγματος;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιες είναι οι βασικές ιδιότητες που ορίζουμε;** Πινέλο γραμμής (ακτινική διαβάθμιση), μέθοδο εξάπλωσης, στάσεις διαβάθμισης και πάχος γραμμής.  
- **Μπορώ να αλλάξω το μέγεθος της έλλειψης;** Ναι – τροποποιήστε τη συμβολοσειρά γεωμετρίας διαδρομής ή τις συντεταγμένες του πινέλου διαβάθμισης.

## Τι είναι το “create XPS document Java”;
Η δημιουργία ενός εγγράφου XPS σε Java σημαίνει την προγραμματιστική παραγωγή ενός αρχείου XML Paper Specification (XPS) – ενός μορφότυπου σταθερής διάταξης παρόμοιου με το PDF – απευθείας από κώδικα Java. Το Aspose.Page παρέχει ένα υψηλού επιπέδου μοντέλο αντικειμένων (`XpsDocument`, `XpsCanvas`, κ.λπ.) που αφαιρεί το XML markup, καθιστώντας τη διαδικασία τόσο απλή όσο η εργασία με τυπικά αντικείμενα Java.

## Γιατί να χρησιμοποιήσετε μια έλλειψη με ακτινική διαβάθμιση;
Μια ακτινική διαβάθμιση προσφέρει τρισδιάστατη αίσθηση, ιδανική για οπτικές επισημάνσεις, λογότυπα ή διακοσμητικά στοιχεία σε αναφορές. Σε σύγκριση με μια γραμμή μονόχρωμη, η διαβάθμιση προσθέτει βάθος χωρίς να αυξάνει σημαντικά το μέγεθος του αρχείου, και η μορφή XPS διατηρεί την ποιότητα του διανύσματος για οποιαδήποτε κλιμάκωση.

## Προαπαιτούμενα
- Java Development Kit (JDK) εγκατεστημένο στον υπολογιστή σας.
- Βιβλιοθήκη Aspose.Page for Java ληφθείσα. Μπορείτε να την αποκτήσετε [εδώ](https://releases.aspose.com/page/java/).
- Ένας επεξεργαστής κώδικα της επιλογής σας (Eclipse, IntelliJ κ.λπ.) για τη συγγραφή και εκτέλεση κώδικα Java.

## Εισαγωγή Πακέτων
Βεβαιωθείτε ότι έχετε εισάγει τα απαραίτητα πακέτα στο έργο Java σας για να χρησιμοποιήσετε το Aspose.Page. Προσθέστε τις παρακάτω δηλώσεις import στην αρχή του αρχείου Java:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Βήμα 1: Ρύθμιση Καταλόγου Εγγράφου
Ορίστε τη διαδρομή προς τον κατάλογο του εγγράφου όπου θα αποθηκευτεί το αρχείο XPS:

```java
String dataDir = "Your Document Directory";
```

## Βήμα 2: Δημιουργία Εγγράφου XPS
Αρχικοποιήστε ένα νέο έγγραφο XPS χρησιμοποιώντας τον παρακάτω κώδικα:

```java
XpsDocument doc = new XpsDocument();
```

## Βήμα 3: Ορισμός Σταθμών Ακτινικής Διαβάθμισης
Δημιουργήστε μια λίστα σταθμών διαβάθμισης για την έλλειψη με ακτινική διαβάθμιση:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Βήμα 4: Δημιουργία Γεωμετρίας Διαδρομής
Ορίστε μια έλλειψη με ακτινική διαβάθμιση χρησιμοποιώντας γεωμετρία διαδρομής:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Βήμα 5: Προσθήκη Καμβά και Διαδρομής
Προσθέστε έναν νέο καμβά στο έγγραφο και επισυνάψτε τη διαδρομή με την ορισμένη γεωμετρία:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Βήμα 6: Ορισμός Στυλ Γραμμής και Διαβάθμισης
Ρυθμίστε τη γραμμή της διαδρομής με πινέλο ακτινικής διαβάθμισης:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Βήμα 7: Ορισμός Πάχους Γραμμής
Καθορίστε το **set stroke thickness** της διαδρομής:

```java
path.setStrokeThickness(12f);
```

## Βήμα 8: Αποθήκευση Εγγράφου
Αποθηκεύστε το παραγόμενο αρχείο XPS:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Συγχαρητήρια! Έχετε προσθέσει με επιτυχία μια έλλειψη με ακτινική διαβάθμιση γραμμής ενώ **create XPS document Java** με Aspose.Page.

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| **Η έλλειψη φαίνεται επίπεδη** | Χρήση του `XpsSpreadMethod.Pad` αντί του `Reflect` | Αλλάξτε τη μέθοδο εξάπλωσης σε `XpsSpreadMethod.Reflect` όπως φαίνεται στο Βήμα 6. |
| **Δεν δημιουργείται αρχείο εξόδου** | `dataDir` δείχνει σε μη υπάρχον φάκελο | Βεβαιωθείτε ότι ο φάκελος υπάρχει ή χρησιμοποιήστε απόλυτη διαδρομή. |
| **Τα χρώματα της διαβάθμισης φαίνονται λανθασμένα** | Λανθασμένη σειρά των σταθμών διαβάθμισης | Επαληθεύστε ότι οι τιμές `offset` (0 → 1) αυξάνονται μονοτονικά. |
| **Σφάλματα μεταγλώττισης** | Απουσία των JAR του Aspose.Page στο classpath | Προσθέστε το `aspose-page-xx.jar` στις εξαρτήσεις του έργου σας. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page for Java με άλλες βιβλιοθήκες Java;**  
Α: Ναι, το Aspose.Page for Java μπορεί να ενσωματωθεί με άλλες βιβλιοθήκες Java απρόσκοπτα.

**Ε: Είναι το Aspose.Page κατάλληλο για επεξεργασία εγγράφων μεγάλης κλίμακας;**  
Α: Απόλυτα! Το Aspose.Page έχει σχεδιαστεί για να διαχειρίζεται αποδοτικά επεξεργασία εγγράφων μεγάλης κλίμακας.

**Ε: Πού μπορώ να βρω περισσότερα tutorials και παραδείγματα για το Aspose.Page for Java;**  
Α: Επισκεφθείτε την [τεκμηρίωση Aspose.Page for Java](https://reference.aspose.com/page/java/) για ολοκληρωμένα tutorials και παραδείγματα.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;**  
Α: Μπορείτε να λάβετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Ε: Υπάρχουν φόρουμ κοινότητας για συζητήσεις σχετικά με το Aspose.Page;**  
Α: Ναι, συμμετέχετε στο [φόρουμ κοινότητας Aspose.Page](https://forum.aspose.com/c/page/39) για να αλληλεπιδράσετε με άλλους προγραμματιστές και να λάβετε βοήθεια.

---

**Τελευταία Ενημέρωση:** 2026-04-24  
**Δοκιμή με:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}