---
date: 2026-02-07
description: Μάθετε πώς να κλιμακώνετε ένα ορθογώνιο με το Aspose.Page για Java, πώς
  να μετακινείτε το σχήμα και να εφαρμόζετε αφινικό μετασχηματισμό για τη δημιουργία
  εγγράφων PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Πώς να κλιμακώσετε το ορθογώνιο με το Aspose.Page για Java
url: /el/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να κλιμακώσετε ορθογώνιο με το Aspose.Page for Java

## Εισαγωγή
Καλώς ήρθατε σε έναν ολοκληρωμένο οδηγό για τη χρήση των ισχυρών δυνατοτήτων του **Aspose.Page for Java** για την εκτέλεση διαφόρων μετασχηματισμών σελίδων. Σε αυτό το tutorial θα μάθετε **πώς να κλιμακώσετε ορθογώνιο**, να μεταφράζετε σχήματα, να περιστρέφετε αντικείμενα και **να εφαρμόζετε τεχνικές affine transform** ενώ δημιουργείτε ένα **έγγραφο PostScript**. Αυτές οι δυνατότητες σας επιτρέπουν να δημιουργήσετε πλούσιες, γραφικά‑έντονες εφαρμογές Java χωρίς να ασχοληθείτε με κώδικα χαμηλού επιπέδου απόδοσης.

## Γρήγορες Απαντήσεις
- **Πώς κλιμακώνω ένα ορθογώνιο σε Java με το Aspose.Page;** Χρησιμοποιήστε τη μέθοδο `document.scale()` πριν σχεδιάσετε το σχήμα.  
- **Μπορώ να μετακινήσω (translate) ένα σχήμα χωρίς να επηρεάσω άλλα γραφικά;** Ναι—αποθηκεύστε την κατάσταση γραφικών, καλέστε `document.translate(x, y)`, σχεδιάστε, και στη συνέχεια επαναφέρετε την κατάσταση.  
- **Ποια κλάση δημιουργεί ένα αρχείο PostScript;** `PsDocument` μαζί με `PsSaveOptions`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται έγκυρη άδεια Aspose.Page για εμπορικές αναπτύξεις.  
- **Ποια έκδοση Java υποστηρίζεται;** Το Aspose.Page λειτουργεί με Java 8 και νεότερες.

## Προαπαιτούμενα
Πριν προχωρήσουμε στον βήμα‑βήμα οδηγό, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

- Βασικές γνώσεις προγραμματισμού Java.  
- Βιβλιοθήκη Aspose.Page for Java εγκατεστημένη. Μπορείτε να τη κατεβάσετε από την [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Ένα περιβάλλον ανάπτυξης Java (IDE) εγκατεστημένο στον υπολογιστή σας.

## Εισαγωγή Πακέτων
Στο έργο Java σας, εισάγετε τα απαραίτητα πακέτα για να χρησιμοποιήσετε το Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Τι σημαίνει “πώς να κλιμακώσετε ορθογώνιο” στο Aspose.Page;
Η κλιμάκωση ενός ορθογωνίου αλλάζει το μέγεθός του κατά τους άξονες X και Y διατηρώντας το σχήμα του. Το Aspose.Page εκθέτει τη μέθοδο `scale(float sx, float sy)`, η οποία εφαρμόζει μια **affine transform** στην τρέχουσα κατάσταση γραφικών. Αυτή είναι η βασική τεχνική πίσω από τη λέξη‑κλειδί **πώς να κλιμακώσετε ορθογώνιο**.

## Πώς να μεταφράσετε σχήμα με το Aspose.Page
Η μετάφραση μετακινεί ένα σχήμα σε νέα θέση χωρίς να αλλάζει τις διαστάσεις του. Αυτό αποτελεί την ουσία του **πώς να μεταφράσετε σχήμα**. Αποθηκεύοντας την κατάσταση γραφικών, εφαρμόζοντας `translate(dx, dy)`, σχεδιάζοντας και στη συνέχεια επαναφέροντας την κατάσταση, διατηρείτε τα άλλα αντικείμενα αμετάβλητα.

## Παράδειγμα 1: Χωρίς Μετασχηματισμούς
Το πρώτο παράδειγμα σχεδιάζει ένα απλό ορθογώνιο χωρίς καμία εφαρμοσμένη μετατροπή. Αυτό χρησιμεύει ως βάση σύγκρισης με τα επόμενα παραδείγματα.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Παράδειγμα 2: Μετάφραση
Εδώ δείχνουμε **πώς να μεταφράσετε σχήμα** μετακινώντας το πλαίσιο γραφικών 250 μονάδες προς τα δεξιά πριν σχεδιάσουμε ένα δεύτερο ορθογώνιο.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Παράδειγμα 3: Κλιμάκωση
Αυτό το παράδειγμα απαντά στην κύρια ερώτηση **πώς να κλιμακώσετε ορθογώνιο**. Συρρικνώνουμε το ορθογώνιο στο 50 % του αρχικού πλάτους και στο 75 % του αρχικού ύψους.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Πώς να περιστρέψετε σχήμα Java (rotate shape java)
Η περιστροφή είναι μια άλλη κοινή affine λειτουργία. Αν και τα αποσπάσματα κώδικα για περιστροφή παραλείπονται για συντομία, το μοτίβο είναι το ίδιο: αποθηκεύστε την κατάσταση γραφικών, καλέστε `document.rotate(angle)`, σχεδιάστε το σχήμα, και στη συνέχεια επαναφέρετε. Αυτό δείχνει **rotate shape java** και **πώς να περιστρέψετε ορθογώνιο** στην πράξη.

## Γιατί είναι σημαντικό – Πλεονεκτήματα στον πραγματικό κόσμο
- **Ανεξαρτησία συσκευής** – Γράψτε μία φορά και δημιουργήστε PostScript ή XPS χωρίς ειδικές ρυθμίσεις πλατφόρμας.  
- **Λεπτομερής έλεγχος** – Συνδυάστε μετάφραση, κλιμάκωση, παραμόρφωση και περιστροφή για να καλύψετε ακριβείς απαιτήσεις διάταξης.  
- **Απόδοση‑προσανατολισμένη** – API χαμηλής υπερφόρτωσης ιδανικό για μαζική επεξεργασία μεγάλων εγγράφων.  

## Συνηθισμένες Περιπτώσεις Χρήσης
- Δημιουργία εκτυπώσιμων τιμολογίων – π.χ., μια λύση **printable invoice java** που τοποθετεί λογότυπα και barcode με ακρίβεια.  
- Κατασκευή τεχνικών διαγραμμάτων όπου απαιτούνται ακριβείς κλιμακώσεις και τοποθετήσεις.  
- Αυτοματοποίηση παραγωγής πολυ‑σελίδων αναφορών σε μορφή PostScript.

## Συνηθισμένα Προβλήματα και Λύσεις
- **Η μετατροπή δεν επαναφέρεται** – Συμπεριλάβετε πάντα το `document.writeGraphicsSave()` με το `document.writeGraphicsRestore()` για να αποφύγετε ανεπιθύμητες κληρονομήσεις.  
- **Απρόσμενα χρώματα** – Βεβαιωθείτε ότι ορίζετε το χρώμα μετά από κάθε μετασχηματισμό· η κατάσταση γραφικών δεν διατηρεί τις προηγούμενες ρυθμίσεις χρώματος μετά την επαναφορά.  
- **Το μέγεθος αρχείου είναι πολύ μεγάλο** – Χρησιμοποιήστε το `PsSaveOptions` για να ενεργοποιήσετε συμπίεση ή να μειώσετε την ανάλυση εικόνας όταν ενσωματώνετε ραστερ γραφικά.

## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page for Java για άλλες μορφές εγγράφων;
Το Aspose.Page εστιάζει κυρίως στη διαχείριση σελίδων για μορφές PostScript και XPS.

### Πού μπορώ να βρω περισσότερα παραδείγματα και τεκμηρίωση για το Aspose.Page for Java;
Επισκεφθείτε την [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) για πλήρεις πληροφορίες.

### Υπάρχει δωρεάν δοκιμή για το Aspose.Page for Java;
Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;
Αποκτήστε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

### Πού μπορώ να βρω υποστήριξη κοινότητας ή να κάνω ερωτήσεις σχετικά με το Aspose.Page for Java;
Επισκεφθείτε το [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) για συζητήσεις της κοινότητας.

## Συχνές Ερωτήσεις

**Q: Ποια είναι η διαφορά μεταξύ `translate` και `scale`;**  
A: Το `translate` μετακινεί το αρχικό σημείο του συστήματος συντεταγμένων, ενώ το `scale` αλλάζει το μέγεθος των σχεδιασμένων αντικειμένων κατά τους άξονες X και/ή Y.

**Q: Μπορώ να συνδυάσω πολλαπλούς μετασχηματισμούς σε μία κατάσταση γραφικών;**  
A: Ναι—καλώντας διαδοχικά `translate`, `scale`, `rotate` ή `shear` πριν το σχεδιασμό, δημιουργείτε έναν συνδυασμένο affine μετασχηματισμό.

**Q: Πώς επαναφέρω τους μετασχηματισμούς μετά το σχεδιασμό ενός σχήματος;**  
A: Χρησιμοποιήστε `document.writeGraphicsRestore()` για να επιστρέψετε στην προηγούμενη κατάσταση γραφικών.

**Q: Είναι δυνατόν να περιστρέψω ένα ορθογώνιο γύρω από το κέντρο του;**  
A: Απόλυτα. Μεταφέρετε το ορθογώνιο στο αρχικό σημείο, εφαρμόστε `rotate(angle)`, και στη συνέχεια μεταφέρετε το πίσω πριν το σχεδιάσετε.

**Q: Υποστηρίζει το Aspose.Page anti‑aliasing για πιο ομαλά γραφικά;**  
A: Ναι—ορίστε τις κατάλληλες επιλογές απόδοσης στο `PsSaveOptions` για να ενεργοποιήσετε anti‑aliasing.

---

**Τελευταία ενημέρωση:** 2026-02-07  
**Δοκιμασμένο με:** Aspose.Page for Java 24.12  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}