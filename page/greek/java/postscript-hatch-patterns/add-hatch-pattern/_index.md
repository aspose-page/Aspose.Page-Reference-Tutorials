---
date: 2026-08-18
description: Μάθετε πώς να προσθέσετε hatch pattern σε αρχεία Java PostScript χρησιμοποιώντας
  Aspose.Page Java. Αυτός ο οδηγός βήμα‑βήμα παρουσιάζει τον πλήρη κώδικα και συμβουλές.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Προσθήκη Hatch Pattern σε Java PostScript
og_description: Μάθετε πώς να προσθέσετε hatch pattern σε Java PostScript χρησιμοποιώντας
  Aspose.Page. Ακολουθήστε αυτό το βήμα‑βήμα tutorial για να δημιουργήσετε γραφικά
  γεμάτα με hatch γρήγορα.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Πώς να προσθέσετε hatch pattern σε Java PostScript – οδηγός Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Πώς να προσθέσετε hatch pattern σε Java PostScript
url: /el/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε μοτίβο hatch σε Java PostScript

## Εισαγωγή
Αν εργάζεστε με **Aspose.Page Java** και αναρωτιέστε **πώς να προσθέσετε μοτίβο hatch** στην έξοδο PostScript, τα μοτίβα hatch είναι μια γρήγορη και ευέλικτη λύση. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα **πώς να προσθέσετε σχέδια hatch** σε ένα έγγραφο PostScript, θα εξηγήσουμε γιατί είναι χρήσιμα, και θα σας δώσουμε ένα πλήρες, έτοιμο‑για‑εκτέλεση παράδειγμα κώδικα. Στο τέλος, θα μπορείτε να δημιουργήσετε οπτικά ελκυστικά σχήματα και κείμενο γεμάτα hatch με λίγες μόνο γραμμές Java.

## Γρήγορες απαντήσεις
- **Τι βιβλιοθήκη χρειάζομαι;** Aspose.Page for Java (το SDK “aspose page java”).  
- **Ποιο οπτικό εφέ προσθέτουμε;** Hatch patterns (π.χ., διαγώνιες γραμμές, διασταυρωμένο).  
- **Χρειάζομαι άδεια για να εκτελέσω το δείγμα;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται άδεια για παραγωγή.  
- **Πόσες γραμμές κώδικα;** Περίπου 70 γραμμές, χωρισμένες σε σαφή βήματα.  
- **Μπορώ να χρησιμοποιήσω την ίδια προσέγγιση για PDFs;** Ναι—το Aspose.Page υποστηρίζει πολλαπλές μορφές εξόδου, συμπεριλαμβανομένου του PDF.

## Τι είναι ένα μοτίβο hatch;
Ένα μοτίβο hatch είναι μια γεμιστική υφή βασισμένη σε διανύσματα που αποτελείται από επαναλαμβανόμενες γραμμές ή σχήματα που δημιουργούν εφέ υφής. Επειδή ορίζεται μαθηματικά, το μοτίβο κλιμακώνεται χωρίς απώλεια ποιότητας, καθιστώντας το ιδανικό για εκτύπωση υψηλής ανάλυσης και μονόχρωμη έξοδο.

## Γιατί να χρησιμοποιήσετε μοτίβα hatch με Aspose.Page Java;
Το Aspose.Page υποστηρίζει **πάνω από 10 μορφές εξόδου** (συμπεριλαμβανομένων των PostScript, PDF, EPS, SVG και XPS) και μπορεί να αποδώσει γεμίσματα hatch σε έγγραφα έως **500 σελίδες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Αυτό σημαίνει γρήγορη απόδοση, μικρό αποτύπωμα μνήμης και συνεπή οπτικά αποτελέσματα σε όλες τις υποστηριζόμενες μορφές.

## Πώς να προσθέσετε μοτίβο hatch – επισκόπηση
Τα μοτίβα hatch είναι υφές βασισμένες σε διανύσματα που αποδίδουν καθαρά σε οποιαδήποτε ανάλυση και λειτουργούν καλά σε μονόχρωμους εκτυπωτές. Χρησιμοποιώντας το Aspose.Page Java, μπορείτε να εφαρμόσετε αυτά τα μοτίβα σε σχήματα, διαδρομές και ακόμη και κείμενο χωρίς να ασχοληθείτε με εντολές PostScript χαμηλού επιπέδου.

## Προαπαιτούμενα
- **Περιβάλλον Ανάπτυξης Java** – JDK 8 ή νεότερο και ένα IDE της επιλογής σας.  
- **Βιβλιοθήκη Aspose.Page for Java** – Κατεβάστε το τελευταίο JAR από την επίσημη **σελίδα λήψης Aspose.Page for Java** [εδώ](https://releases.aspose.com/page/java/).  
- Μπορείτε επίσης να περιηγηθείτε σε άλλες κυκλοφορίες Aspose [εδώ](https://releases.aspose.com/).  
- **Δικαίωμα εγγραφής** σε φάκελο όπου θα αποθηκευτεί το παραγόμενο αρχείο PostScript.

## Εισαγωγή πακέτων
Οι παρακάτω εισαγωγές περιλαμβάνουν τις τυπικές κλάσεις Java AWT για γραφικά primitives όπως χρώματα, στυλ γραμμής και γεωμετρικά σχήματα, καθώς και τις κλάσεις Aspose.Page που παρέχουν το μοντέλο εγγράφου, ορισμούς hatch‑style και επιλογές αποθήκευσης που απαιτούνται για τη δημιουργία αρχείου PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Τι είναι η κλάση `Document`;
Η κλάση `Document` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Page που αντιπροσωπεύει ένα μοναδικό αρχείο PostScript στη μνήμη. Όλες οι λειτουργίες σχεδίασης εκτελούνται μέσω αυτού του αντικειμένου.

## Πώς να ρυθμίσετε το ρεύμα εξόδου;
Για να γράψετε την έξοδο, δημιουργήστε ένα `FileOutputStream` που δείχνει στη ζητούμενη διαδρομή αρχείου· αυτό το ρεύμα διαχειρίζεται τη χαμηλού επιπέδου εγγραφή byte. Το `PsSaveOptions` διαμορφώνει τον τρόπο αποθήκευσης του εγγράφου, συμπεριλαμβανομένου του μεγέθους σελίδας και της συμπίεσης. Στη συνέχεια, δημιουργήστε ένα αντικείμενο `Document` με ένα αντικείμενο `PsSaveOptions` που καθορίζει το μέγεθος σελίδας, τη συμπίεση και άλλες ρυθμίσεις ειδικές για PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Πώς να αποθηκεύσετε την κατάσταση γραφικών και να μεταφράσετε το αρχικό σημείο;
Η αποθήκευση της κατάστασης γραφικών καταγράφει τον τρέχοντα πίνακα μετασχηματισμού, την περιοχή αποκοπής και τα χαρακτηριστικά σχεδίασης, επιτρέποντάς σας να επαναφέρετε αργότερα. Μετά την αποθήκευση, καλέστε `translate(x, y)` στο αντικείμενο γραφικών για να μετακινήσετε το αρχικό σημείο σε μια βολική θέση για τη σχεδίαση του πλέγματος των τετραγώνων hatch.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Πώς να δημιουργήσετε ένα επαναχρησιμοποιήσιμο τετράγωνο για κάθε μοτίβο;
`Rectangle2D` αντιπροσωπεύει ένα ορθογώνιο σχήμα ορισμένο από τη θέση και το μέγεθός του. Δημιουργώντας μια μόνο παρουσία που ταιριάζει στις διαστάσεις του κελιού, μπορείτε να την επαναχρησιμοποιήσετε για κάθε τετράγωνο γεμάτο hatch, μειώνοντας την κατανομή αντικειμένων και διατηρώντας τον βρόχο σχεδίασης αποδοτικό.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Πώς να ρυθμίσετε ένα πέννα για το περίγραμμα του τετραγώνου μοτίβου;
`BasicStroke` περιγράφει το πάχος του περιγράμματος, το μοτίβο παύλας και τα άκρα για διανυσματικά σχήματα. Η χρήση ενός `BasicStroke` 2 σημείων παρέχει ένα σαφές περίγραμμα γύρω από κάθε κελί γεμάτο hatch, διασφαλίζοντας ότι το γέμισμα διαχωρίζεται οπτικά από τα γειτονικά τετράγωνα.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Πώς να επαναλάβετε μέσω των μοτίβων hatch;
`HatchStyle` είναι μια απαρίθμηση που καταγράφει όλα τα προ‑ορισμένα μοτίβα hatch όπως διαγώνια, διασταυρωμένα και διακεκομμένα στυλ. Η επανάληψη πάνω σε `HatchStyle.values()` σας επιτρέπει να εφαρμόσετε κάθε μοτίβο διαδοχικά, να γεμίσετε το ορθογώνιο με ένα `HatchBrush` και στη συνέχεια να σχεδιάσετε το περίγραμμά του.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Πώς να επαναφέρετε την κατάσταση γραφικών μετά το σκάρισμα;
Καλώντας `restore()` στο αντικείμενο γραφικών επαναφέρει τον πίνακα μετασχηματισμού και τις ρυθμίσεις σχεδίασης στην κατάσταση που αποθηκεύτηκε νωρίτερα, αποτρέποντας τις αθροιστικές μετατοπίσεις ή κλιμακώσεις να επηρεάσουν τις επόμενες λειτουργίες σχεδίασης. Αυτό διασφαλίζει ότι το μετέπειτα περιεχόμενο ξεκινά από το αρχικό σύστημα συντεταγμένων και χρησιμοποιεί τις προεπιλεγμένες ιδιότητες.  
```java
document.writeGraphicsRestore();
```

## Πώς να γεμίσετε κείμενο με μοτίβο hatch;
`TextFragment` αντιπροσωπεύει ένα κομμάτι κειμένου που μπορεί να τοποθετηθεί και να μορφοποιηθεί ανεξάρτητα. Αναθέτοντας ένα `HatchBrush` με ένα επιλεγμένο `HatchStyle` στο γέμισμα του τμήματος, οι χαρακτήρες του κειμένου αποδίδονται χρησιμοποιώντας την υφή hatch αντί για ένα στερεό χρώμα.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Πώς να περιγράψετε κείμενο με διαφορετικό στυλ hatch;
`HatchBrush` μπορεί επίσης να χρησιμοποιηθεί για σχεδίαση γραμμής. Για να σχεδιάσετε ένα περίγραμμα, ορίστε τη γραμμή του τμήματος σε ένα `HatchBrush` με διαφορετικό `HatchStyle` (π.χ., 70 % hatch) και αυξήστε το πάχος της γραμμής μέσω `setStrokeWidth`. Αυτό αποδίδει το περίγραμμα του κειμένου με το δικό του μοτίβο hatch διατηρώντας το γεμάτο εσωτερικό.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Πώς να κλείσετε και να αποθηκεύσετε το έγγραφο;
`document.save()` γράφει το έγγραφο στη μνήμη στο καθορισμένο ρεύμα εξόδου. Μετά την ολοκλήρωση όλων των εντολών σχεδίασης, καλέστε αυτή τη μέθοδο και στη συνέχεια κλείστε το `FileOutputStream` για να απελευθερώσετε τους πόρους του συστήματος και να διασφαλίσετε ότι το αρχείο έχει σωστά εκσυγχρονιστεί στο δίσκο.  
```java
document.closePage();
document.save();
```

Ακολουθήστε αυτά τα βήματα και θα έχετε ένα αρχείο PostScript που παρουσιάζει ένα πλήρες σύνολο μοτίβων hatch εφαρμοσμένων τόσο σε σχήματα όσο και σε κείμενο—όλα υποστηριζόμενα από **aspose page java**.

## Συνηθισμένα προβλήματα & συμβουλές
- **Σφάλματα διαδρομής αρχείου** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με το κατάλληλο διαχωριστικό αρχείου (`/` ή `\`).  
- **Μη υποστηριζόμενα χρώματα** – Ορισμένοι παλαιότεροι ερμηνευτές PostScript μπορεί να μην διαχειρίζονται ορισμένα χρωματικά διαστήματα· χρησιμοποιήστε βασικό RGB για μέγιστη συμβατότητα.  
- **Προειδοποιήσεις άδειας** – Η εκτέλεση του δείγματος χωρίς έγκυρη άδεια θα ενσωματώσει υδατογράφημα στην έξοδο.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page Java με άλλα πλαίσια Java;**  
A: Ναι, η βιβλιοθήκη είναι ανεξάρτητη από πλαίσια και λειτουργεί με Spring, Jakarta EE, Android (περιορισμένα) και απλό Java SE.

**Q: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Page Java;**  
A: Απόλυτα. Κατεβάστε μια δωρεάν δοκιμή 30 ημερών [Aspose trial download page](https://releases.aspose.com/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για ανάπτυξη;**  
A: Ζητήστε μια προσωρινή άδεια [temporary license request page](https://purchase.aspose.com/temporary-license/). Αφαιρεί τα υδατογραφήματα αξιολόγησης.

**Q: Πού μπορώ να βρω περισσότερα tutorials και υποστήριξη κοινότητας;**  
A: Επισκεφθείτε το επίσημο φόρουμ [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) για επιπλέον παραδείγματα και ερωτήσεις‑απαντήσεις.

**Q: Υπάρχει πλήρης τεκμηρίωση για όλες τις κλάσεις και μεθόδους;**  
A: Ναι, η πλήρης αναφορά API είναι διαθέσιμη [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Μπορώ να αποδώσω το ίδιο μοτίβο hatch σε PDF αντί για PostScript;**  
A: Απόλυτα. Αλλάξτε το `PsSaveOptions` σε `PdfSaveOptions` (ή το ισοδύναμο) και ο υπόλοιπος κώδικας παραμένει αμετάβλητος.

**Q: Τι πρέπει να κάνω αν το παραγόμενο αρχείο είναι κενό;**  
A: Επαληθεύστε ότι το ρεύμα εξόδου δείχνει σε έναν εγγράψιμο φάκελο και ότι το `document.save()` καλείται μετά από όλες τις λειτουργίες σχεδίασης.

**Τελευταία ενημέρωση:** 2026-08-18  
**Δοκιμή με:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose

## Σχετικές οδηγίες

- [Δημιουργία μοτίβου υφής σε PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Πώς να προσθέσετε διαβάθμιση: Διαγώνια διαβάθμιση σε Java PostScript χρησιμοποιώντας Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Πώς να μετατρέψετε PostScript σε PDF χρησιμοποιώντας το Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}