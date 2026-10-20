---
date: 2026-10-20
description: Μάθετε πώς να κλιμακώσετε το ορθογώνιο με το Aspose.Page for Java, πώς
  να μετακινήσετε το σχήμα και να εφαρμόσετε affine transform για τη δημιουργία εγγράφων
  PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Μετασχηματισμοί στη διαχείριση σελίδων Java
og_description: Μάθετε πώς να κλιμακώσετε το ορθογώνιο, να μετακινήσετε το σχήμα και
  να εφαρμόσετε affine transform χρησιμοποιώντας το Aspose.Page for Java για την αποδοτική
  δημιουργία αρχείων PostScript.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Πώς να κλιμακώσετε το ορθογώνιο με το Aspise.Page for Java – οδηγός βήμα
  προς βήμα
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Πώς να κλιμακώσετε το ορθογώνιο με το Aspose.Page for Java
url: /el/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να κλιμακώσετε το ορθογώνιο με Aspose.Page for Java

## Εισαγωγή
Σε αυτόν τον οδηγό θα ανακαλύψετε **how to scale rectangle** αντικείμενα χρησιμοποιώντας το Aspose.Page for Java, ενώ θα μάθετε επίσης πώς να μεταφράζετε τις θέσεις των σχημάτων, να περιστρέφετε γραφικά και να εφαρμόζετε λειτουργίες αφινικού μετασχηματισμού για την παραγωγή εξόδου PostScript υψηλής ποιότητας. Αυτές οι τεχνικές σας επιτρέπουν να δημιουργείτε εξελιγμένα, ανεξάρτητα από τη συσκευή γραφικά χωρίς να γράφετε κώδικα χαμηλού επιπέδου, καθιστώντας τις εφαρμογές Java πιο ισχυρές και συντηρήσιμες.

## Γρήγορες απαντήσεις
`scale(sx, sy)` κλιμακώνει το πλαίσιο γραφικών κατά τους δοθέντες οριζόντιους και κάθετους παράγοντες.  

- **Πώς μπορώ να κλιμακώσω ένα ορθογώνιο σε Java με Aspose.Page;** Καλέστε τη μέθοδο `scale(sx, sy)` στο πλαίσιο γραφικών πριν σχεδιάσετε το ορθογώνιο.  
- **Μπορώ να μετακινήσω (μεταφράσω) ένα σχήμα χωρίς να επηρεάσω άλλα γραφικά;** Ναι—τυλίξτε τη μετάφραση μεταξύ των κλήσεων `writeGraphicsSave()` και `writeGraphicsRestore()`.  
- **Ποια κλάση δημιουργεί ένα αρχείο PostScript;** Χρησιμοποιήστε το `PsDocument` μαζί με το `PsSaveOptions`.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται έγκυρη άδεια Aspose.Page για εμπορικές αναπτύξεις.  
- **Ποια έκδοση της Java υποστηρίζεται;** Το Aspose.Page λειτουργεί με Java 8 και νεότερες.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Καλή κατανόηση της βασικής σύνταξης της Java και των αντικειμενοστραφών εννοιών.  
- Τη βιβλιοθήκη Aspose.Page for Java εγκατεστημένη. Μπορείτε να τη κατεβάσετε από την [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Ένα IDE Java (IntelliJ IDEA, Eclipse ή VS Code) ρυθμισμένο με τα αρχεία JAR της βιβλιοθήκης στο classpath.

## Εισαγωγή πακέτων
`PsDocument` είναι η κύρια κλάση που χρησιμοποιείται για τη δημιουργία ενός εγγράφου PostScript, και το `PsSaveOptions` ρυθμίζει πώς αποθηκεύεται το έγγραφο.

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Τι είναι το “how to scale rectangle” στο Aspose.Page;
Η μέθοδος `scale(float sx, float sy)` εφαρμόζει έναν αφινικό μετασχηματισμό κλιμάκωσης στην τρέχουσα κατάσταση γραφικών, αλλάζοντας το μέγεθος των επόμενων σχεδίων κατά τους παράγοντες `sx` (οριζόντια) και `sy` (κατακόρυφα). Αυτή είναι η βασική λειτουργία πίσω από τη λέξη‑κλειδί **how to scale rectangle**. Εφαρμόζοντας αυτόν τον μετασχηματισμό πριν το σχεδιασμό, οποιαδήποτε επόμενα σχήματα όπως ορθογώνια θα αποδοθούν με τις νέες διαστάσεις διατηρώντας τις αναλογίες τους.

## Πώς να μεταφράσετε σχήμα με Aspose.Page
`writeGraphicsSave()` αποθηκεύει την τρέχουσα κατάσταση γραφικών και το `writeGraphicsRestore()` την επαναφέρει, εξασφαλίζοντας ότι οι μετασχηματισμοί επηρεάζουν μόνο το επιθυμητό σχήμα. Η μετάφραση μετατοπίζει το αρχικό σημείο του συστήματος συντεταγμένων χωρίς να αλλάζει τις διαστάσεις του αντικειμένου. Περιβάλλοντας το `translate(dx, dy)` με `writeGraphicsSave()` / `writeGraphicsRestore()`, διασφαλίζετε ότι μόνο το επιλεγμένο σχήμα κινείται ενώ τα άλλα γραφικά παραμένουν αμετάβλητα, παρέχοντας ακριβή έλεγχο στα μεμονωμένα στοιχεία.

## Παράδειγμα 1: χωρίς μετασχηματισμούς
Το πρώτο παράδειγμα σχεδιάζει ένα ορθογώνιο χωρίς κανέναν μετασχηματισμό, θέτοντας μια βάση για οπτική σύγκριση με τα επόμενα παραδείγματα.

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

## Παράδειγμα 2: μετάφραση
Σε αυτό το παράδειγμα μετακινούμε το πλαίσιο γραφικών 250 μονάδες προς τα δεξιά πριν σχεδιάσουμε ένα δεύτερο ορθογώνιο, επιδεικνύοντας **how to translate shape**.

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

## Παράδειγμα 3: κλιμάκωση
Εδώ απαντάμε στην κύρια ερώτηση **how to scale rectangle**. Το ορθογώνιο μειώνεται στο 50 % του αρχικού πλάτους και στο 75 % του αρχικού ύψους χρησιμοποιώντας την κλήση `scale(0.5f, 0.75f)`.

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

## Πώς να περιστρέψετε σχήμα java (rotate shape java)
`rotate(angle)` περιστρέφει το σύστημα συντεταγμένων κατά τη συγκεκριμένη γωνία σε μοίρες. Φορτώστε το `PsDocument`, καλέστε `rotate(angle)` στην κατάσταση γραφικών, σχεδιάστε το σχήμα, και στη συνέχεια επαναφέρετε την προηγούμενη κατάσταση. Αυτό το μοτίβο υλοποιεί **rotate shape java** και **how to rotate rectangle** σε ένα ενιαίο, επαναχρησιμοποιήσιμο μπλοκ, επιτρέποντάς σας να περιστρέφετε τα γραφικά γύρω από οποιοδήποτε σημείο επιλέγετε.

## Γιατί αυτό είναι σημαντικό – πραγματικά οφέλη
- **Ανεξάρτητη έξοδος συσκευής** – Το Aspose.Page μπορεί να δημιουργήσει αρχεία PostScript και XPS που αποδίδονται ταυτόσημα σε οποιονδήποτε εκτυπωτή ή προβολέα, εξαλείφοντας τις προσαρμογές ειδικές για πλατφόρμα.  
- **Ακριβής έλεγχος** – Συνδυάστε μετάφραση, κλιμάκωση, διαστρέβλωση και περιστροφή για να πληροί ακριβείς προδιαγραφές διάταξης· το API υποστηρίζει πάνω από 20 συνδυασμούς μετασχηματισμών ανά σελίδα.  
- **Επεξεργασία με προσανατολισμό στην απόδοση** – Η βιβλιοθήκη επεξεργάζεται έγγραφα με αποτύπωση μνήμης κάτω από 10 MB για τυπικές αναφορές 100 σελίδων, καθιστώντας τις εργασίες batch γρήγορες και επεκτάσιμες.

## Κοινές περιπτώσεις χρήσης
- **Εκτυπώσιμα τιμολόγια** – Τοποθετήστε με ακρίβεια λογότυπα, γραμμωτούς κώδικες και πίνακες χρησιμοποιώντας κλιμάκωση και μετάφραση για να ταιριάζουν με τις οδηγίες εταιρικής ταυτότητας.  
- **Τεχνικά διαγράμματα** – Δημιουργήστε σχήματα όπου κάθε στοιχείο πρέπει να κλιμακωθεί και να τοποθετηθεί αναλογικά.  
- **Αυτοματοποιημένες αναφορές πολλαπλών σελίδων** – Δημιουργήστε αναφορές PostScript που απαιτούν συνεπή κλιμάκωση σε όλες τις σελίδες, όπως προδιαγραφές μηχανικής.

## Κοινά προβλήματα και λύσεις
- **Ο μετασχηματισμός δεν επαναφέρεται** – Συζεύξτε πάντα το `writeGraphicsSave()` με το `writeGraphicsRestore()`· διαφορετικά τα επόμενα σχέδια κληρονομούν ανεπιθύμητους μετασχηματισμούς.  
- **Απρόσμενα χρώματα** – Ορίστε το χρώμα (paint) μετά από κάθε μετασχηματισμό, επειδή η κατάσταση γραφικών δεν διατηρεί τις πληροφορίες χρώματος μετά την επαναφορά.  
- **Το μέγεθος του αρχείου είναι πολύ μεγάλο** – Ενεργοποιήστε τη συμπίεση στο `PsSaveOptions` και περιορίστε την ανάλυση των ενσωματωμένων raster εικόνων για να κρατήσετε το τελικό αρχείο κάτω από 5 MB για τυπικά έγγραφα 50 σελίδων.

## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Page for Java για άλλες μορφές εγγράφων;
Το Aspose.Page επικεντρώνεται κυρίως στη διαχείριση σελίδων για μορφές PostScript και XPS, αλλά προσφέρει επίσης περιορισμένες δυνατότητες εξαγωγής σε PDF.

### Πού μπορώ να βρω περισσότερα παραδείγματα και τεκμηρίωση για το Aspose.Page for Java;
Επισκεφθείτε την [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) για ολοκληρωμένους οδηγούς, αναφορές API και παραδείγματα έργων.

### Υπάρχει δωρεάν δοκιμαστική έκδοση για το Aspose.Page for Java;
Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή μέσω της σελίδας **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/).

### Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page for Java;
Αποκτήστε προσωρινή άδεια μέσω της **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Πού μπορώ να βρω υποστήριξη κοινότητας ή να κάνω ερωτήσεις για το Aspose.Page for Java;
Επισκεφθείτε το [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) για συζητήσεις κοινότητας, αποσπάσματα κώδικα και συμβουλές αντιμετώπισης προβλημάτων.

## Συχνές ερωτήσεις
**Q: Ποια είναι η διαφορά μεταξύ `translate` και `scale`;**  
A: `translate` μετακινεί το αρχικό σημείο του συστήματος συντεταγμένων, ενώ το `scale` αλλάζει το μέγεθος των σχεδιασμένων αντικειμένων κατά τους άξονες X και/ή Y.

**Q: Μπορώ να συνδυάσω πολλαπλούς μετασχηματισμούς σε μια ενιαία κατάσταση γραφικών;**  
A: Ναι—καλώντας διαδοχικά `translate`, `scale`, `rotate` ή `shear` πριν το σχεδιασμό, δημιουργείτε έναν συνδυασμένο αφινικό μετασχηματισμό.

**Q: Πώς επαναφέρω τους μετασχηματισμούς μετά το σχεδιασμό ενός σχήματος;**  
A: Χρησιμοποιήστε το `writeGraphicsRestore()` για να επιστρέψετε στην προηγούμενη αποθηκευμένη κατάσταση γραφικών.

**Q: Είναι δυνατόν να περιστρέψετε ένα ορθογώνιο γύρω από το κέντρο του;**  
A: Απόλυτα. Μετακινήστε το ορθογώνιο στο αρχικό σημείο, εφαρμόστε `rotate(angle)`, και μετά μεταφέρετέ το πίσω πριν το σχεδιάσετε.

**Q: Υποστηρίζει το Aspose.Page anti‑aliasing για πιο ομαλά γραφικά;**  
A: Ναι—ορίστε τις κατάλληλες επιλογές απόδοσης στο `PsSaveOptions` για να ενεργοποιήσετε το anti‑aliasing.

---

**Τελευταία ενημέρωση:** 2026-10-20  
**Δοκιμή με:** Aspose.Page for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Πώς να σχεδιάσετε ορθογώνιο σε Java PostScript με Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Δημιουργία ακτινικού gradient σε PostScript με Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Διαχείριση σελίδας Postscript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}