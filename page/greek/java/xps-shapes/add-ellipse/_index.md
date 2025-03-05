---
title: Προσθήκη Radial Gradient Ellipse με το Aspose.Page
linktitle: Προσθήκη Ellipse σε Java XPS
second_title: Aspose.Page Java API
description: Εξερευνήστε τον οδηγό βήμα προς βήμα για την προσθήκη μιας έλλειψης με ακτινωτή διαβάθμιση σε Java XPS χρησιμοποιώντας το Aspose.Page για Java. Βελτιώστε τη δημιουργία εγγράφων σας χωρίς κόπο.
type: docs
weight: 10
url: /el/java/xps-shapes/add-ellipse/
---
## Εισαγωγή
Καλώς ήρθατε στον αναλυτικό οδηγό μας για την προσθήκη μιας έλλειψης σε Java XPS χρησιμοποιώντας το Aspose.Page για Java. Το Aspose.Page είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να εργάζονται με έγγραφα XPS χωρίς κόπο. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας μιας έλλειψης με ακτινική κλίση και αποθήκευσης ως έγγραφο XPS.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο μηχάνημά σας.
-  Έγινε λήψη του Aspose.Page για τη βιβλιοθήκη Java. Μπορείς να το πάρεις[εδώ](https://releases.aspose.com/page/java/).
- Ένα πρόγραμμα επεξεργασίας κώδικα της επιλογής σας (Eclipse, IntelliJ, κ.λπ.) για τη σύνταξη και την εκτέλεση κώδικα Java.
## Εισαγωγή πακέτων
Βεβαιωθείτε ότι έχετε εισαγάγει τα απαραίτητα πακέτα στο έργο σας Java για να χρησιμοποιήσετε το Aspose.Page. Προσθέστε τις ακόλουθες δηλώσεις εισαγωγής στην κορυφή του αρχείου Java σας:
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
## Βήμα 1: Ρύθμιση καταλόγου εγγράφων
Καθορίστε τη διαδρομή προς τον κατάλογο εγγράφων σας όπου θα αποθηκευτεί το έγγραφο XPS:
```java
String dataDir = "Your Document Directory";
```
## Βήμα 2: Δημιουργία εγγράφου XPS
Αρχικοποιήστε ένα νέο έγγραφο XPS χρησιμοποιώντας τον ακόλουθο κώδικα:
```java
XpsDocument doc = new XpsDocument();
```
## Βήμα 3: Ορίστε στάσεις ακτινικής κλίσης
Δημιουργήστε μια λίστα με στάσεις κλίσης για την έλλειψη με ακτινική κλίση:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Βήμα 4: Δημιουργήστε γεωμετρία διαδρομής
Ορίστε μια έλλειψη με ακτινική κλίση χρησιμοποιώντας τη γεωμετρία διαδρομής:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Βήμα 5: Προσθέστε καμβά και διαδρομή
Προσθέστε έναν νέο καμβά στο έγγραφο και προσθέστε τη διαδρομή με την καθορισμένη γεωμετρία:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Βήμα 6: Ρύθμιση Stroke και Gradient
Διαμορφώστε τη διαδρομή της διαδρομής με ένα πινέλο ακτινικής κλίσης:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Βήμα 7: Ρυθμίστε το πάχος της διαδρομής
Καθορίστε το πάχος διαδρομής της διαδρομής:
```java
path.setStrokeThickness(12f);
```
## Βήμα 8: Αποθηκεύστε το έγγραφο
Αποθηκεύστε το έγγραφο XPS που προκύπτει:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Συγχαρητήρια! Προσθέσατε επιτυχώς μια έλλειψη με ακτινική διαβάθμιση σε Java XPS χρησιμοποιώντας το Aspose.Page για Java.
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τα βήματα για τη δημιουργία ενός εγγράφου XPS με μια οπτικά ελκυστική έλλειψη με ακτινική διαβάθμιση. Το Aspose.Page για Java απλοποιεί τον χειρισμό εγγράφων XPS, παρέχοντας στους προγραμματιστές ένα ισχυρό σύνολο εργαλείων.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page για Java με άλλες βιβλιοθήκες Java;
Ναι, το Aspose.Page για Java μπορεί να ενσωματωθεί απρόσκοπτα με άλλες βιβλιοθήκες Java.
### Είναι το Aspose.Page κατάλληλο για επεξεργασία εγγράφων μεγάλης κλίμακας;
Απολύτως! Το Aspose.Page έχει σχεδιαστεί για να χειρίζεται αποτελεσματικά την επεξεργασία εγγράφων μεγάλης κλίμακας.
### Πού μπορώ να βρω περισσότερα μαθήματα και παραδείγματα για το Aspose.Page για Java;
 Επισκέψου το[Aspose.Page για τεκμηρίωση Java](https://reference.aspose.com/page/java/)για ολοκληρωμένα σεμινάρια και παραδείγματα.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για Java;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Υπάρχουν φόρουμ κοινότητας για συζητήσεις Aspose.Page;
 Ναι, εγγραφείτε στο[Φόρουμ κοινότητας Aspose.Page](https://forum.aspose.com/c/page/39) για να συνεργαστείτε με άλλους προγραμματιστές και να λάβετε βοήθεια.