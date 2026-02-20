---
date: 2026-02-20
description: Μάθετε πώς να ορίζετε το χρώμα κειμένου σε Java χρησιμοποιώντας το Aspose.Page
  for Java, να αλλάζετε το μέγεθος γραμματοσειράς σε Java, να δημιουργείτε αρχείο
  PostScript, να γεμίζετε και να σχεδιάζετε κείμενο, και να χρησιμοποιείτε προσαρμοσμένες
  γραμματοσειρές σε Java κατά τη δημιουργία ενός εγγράφου PostScript.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Ορισμός χρώματος κειμένου σε Java με το Aspose.Page – Οδηγός χειρισμού κειμένου
url: /el/java/postscript-text-manipulation/add-text/
weight: 10
---

Be careful: Greek is left-to-right, not RTL. So no need for RTL.

Let's translate.

Start with shortcodes unchanged.

Proceed.

We'll translate each paragraph.

Let's craft Greek translation.

Note: Keep **bold** markers.

Let's do.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Χρώματος Κειμένου Java με Aspose.Page – Οδηγός Διαχείρισης Κειμένου

## Εισαγωγή
Καλώς ήρθατε στον βήμα‑βήμα οδηγό μας για **set text color java** κατά την εργασία με αρχεία PostScript χρησιμοποιώντας το Aspose.Page for Java. Το Aspose.Page for Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να **create postscript document** αρχεία, να διαχειρίζονται γραμματοσειρές και να μορφοποιούν το κείμενο με ακρίβεια. Σε αυτό το tutorial θα μάθετε πώς να προσθέτετε κείμενο, να αλλάζετε το χρώμα του, **change font size java**, και ακόμη **apply fill and stroke text** για ένα επαγγελματικό αποτέλεσμα.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη μου επιτρέπει να ορίσω χρώμα κειμένου σε Java;** Aspose.Page for Java.  
- **Μπορώ να χρησιμοποιήσω σύστημα γραμματοσειρών και προσαρμοσμένες γραμματοσειρές;** Ναι, και τα δύο υποστηρίζονται, και μπορείτε εύκολα να **use custom fonts java**.  
- **Πώς αλλάζω το μέγεθος του κειμένου;** Καθορίζοντας το μέγεθος γραμματοσειράς κατά τη δημιουργία του `Font` ή `DrFont`.  
- **Μπορώ να περιγράψω και να γεμίσω το κείμενο ταυτόχρονα;** Απόλυτα – χρησιμοποιήστε `fillAndStrokeText`.  
- **Τι μορφή εξόδου παράγει αυτό το tutorial;** Ένα έγγραφο PostScript (`.ps`), το οποίο μπορείτε να **generate postscript file** προγραμματιστικά.

## Τι είναι το “set text color java”;
Ο ορισμός του χρώματος κειμένου σε Java σημαίνει τον ορισμό του αντικειμένου `Color` που η μηχανή απόδοσης (εδώ, Aspose.Page) χρησιμοποιεί όταν σχεδιάζει χαρακτήρες σε μια σελίδα. Αυτή η λειτουργία είναι απαραίτητη για τη δημιουργία οπτικά διακριτών εγγράφων, ειδικά όταν χρειάζεται να **generate postscript file** προγραμματιστικά.

## Γιατί να χρησιμοποιήσετε Aspose.Page for Java;
- **Πλήρης έλεγχος** της δημιουργίας PostScript χωρίς ανάγκη εγγενούς ερμηνευτή.  
- **Υποστήριξη τόσο για σύστημα όσο και για εξωτερικές γραμματοσειρές**, επιτρέποντάς σας να ενσωματώσετε οποιαδήποτε τυπογραφία χρειάζεστε.  
- **Εύκολο API** για γεμίσματα, περιγράμματα και **fill and stroke text**, προσφέροντας ευελιξία στη μορφοποίηση.  
- **Διαλειτουργικότητα** – γράψτε μία φορά, τρέξτε όπου τρέχει Java.  

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού Java.  
- Την βιβλιοθήκη Aspose.Page for Java εγκατεστημένη. Μπορείτε να τη κατεβάσετε από τη [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).  
- Τις απαραίτητες γραμματοσειρές διαθέσιμες στον καθορισμένο φάκελο. Περισσότερες λεπτομέρειες υπάρχουν στην [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Εισαγωγή Πακέτων
Στο έργο Java σας, εισάγετε τα απαραίτητα πακέτα για το Aspose.Page for Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Βήμα 1: Ρύθμιση του Εγγράφου
Πρώτα, δημιουργούμε ένα νέο **PostScript document** και διαμορφώνουμε τις επιλογές εξόδου.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Πώς να Ορίσετε Χρώμα Κειμένου Java Χρησιμοποιώντας Σύστημα Γραμματοσειράς
Τώρα δείχνουμε **set text color java** με μια γραμματοσειρά που παρέχεται από το σύστημα.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Συμβουλή:** Η μέθοδος `fillText` χρησιμοποιεί αυτόματα το τρέχον χρώμα αν δεν περάσετε όρισμα `Color`, το οποίο προεπιλογή είναι το μαύρο.

## Χρήση Προσαρμοσμένης Γραμματοσειράς και Αλλαγή Μεγέθους Κειμένου
Μπορείτε επίσης να **change font size java** και να χρησιμοποιήσετε μια προσαρμοσμένη γραμματοσειρά που βρίσκεται στον φάκελο γραμματοσειρών σας.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Περιγράμμιση (Stroke) Κειμένου – Εφαρμογή Stroke Text
Η περιγράμμιση του κειμένου του δίνει καθαρή άκρη. Εδώ **apply stroke text** χρησιμοποιώντας ένα `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Περιγράμμιση Κειμένου με Προσαρμοσμένη Γραμματοσειρά
Η ίδια τεχνική λειτουργεί και με προσαρμοσμένες γραμματοσειρές.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Βήμα 6: Αποθήκευση του Εγγράφου
Τέλος, κλείστε τη σελίδα και γράψτε το αρχείο στο δίσκο.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Γιατί Είναι Σημαντικό
Η δυνατότητα **set text color java** και ο συνδυασμός γεμίσματος με περίγραμμα σας δίνει πλήρη καλλιτεχνικό έλεγχο πάνω στην τελική έξοδο PostScript. Είτε δημιουργείτε τιμολόγια, πιστοποιητικά ή προσαρμοσμένα γραφικά, η ικανότητα **create postscript document** με ακριβή μορφοποίηση μειώνει την ανάγκη για μετα-επεξεργασία σε προγράμματα γραφικών.

## Συνηθισμένα Προβλήματα & Λύσεις
| Issue | Solution |
|-------|----------|
| **Font not found** | Βεβαιωθείτε ότι το αρχείο γραμματοσειράς βρίσκεται στο `necessary_fonts` και ότι η διαδρομή του φακέλου έχει προστεθεί σωστά μέσω `options.setAdditionalFontsFolders`. |
| **Color not applied** | Επαληθεύστε ότι καλείτε την υπερφόρτωση της `fillText` ή `outlineText` που περιλαμβάνει όρισμα `Color`. |
| **Stroke appears too thin** | Αυξήστε το πλάτος του `BasicStroke` (π.χ., `new BasicStroke(3)`). |
| **Document not opening** | Επιβεβαιώστε ότι το παραγόμενο αρχείο `.ps` αποθηκεύεται με τη σωστή επέκταση και ότι ο προβολέας σας υποστηρίζει PostScript. |

## Συχνές Ερωτήσεις

**Q:** Μπορώ να χρησιμοποιήσω τις δικές μου προσαρμοσμένες γραμματοσειρές με το Aspose.Page for Java;  
A: Ναι, μπορείτε να **use custom fonts java** καθορίζοντας το όνομα και το μέγεθος της γραμματοσειράς στην κλάση `DrFont`.

**Q:** Πώς μπορώ να αλλάξω το χρώμα του κειμένου;  
A: Μπορείτε να ορίσετε το επιθυμητό χρώμα χρησιμοποιώντας την κλάση `Color` κατά το γέμισμα ή την περιγραφή του κειμένου.

**Q:** Είναι δυνατόν να προσθέσω πολλές σελίδες σε ένα έγγραφο PostScript;  
A: Απόλυτα! Μπορείτε να δημιουργήσετε πολλές σελίδες επαναλαμβάνοντας τα βήματα δημιουργίας και αποθήκευσης του εγγράφου.

**Q:** Ποιος είναι ο σκοπός της κλάσης `ExternalFontCache`;  
A: Η `ExternalFontCache` χρησιμοποιείται για την ανάκτηση προσαρμοσμένων γραμματοσειρών, εξασφαλίζοντας ότι είναι διαθέσιμες για τη διαχείριση κειμένου.

**Q:** Μπορώ να εφαρμόσω διαφορετικά περιγράμματα στο περιγραμμισμένο κείμενο;  
A: Ναι, μπορείτε να προσαρμόσετε το πλάτος και το χρώμα του περιγράμματος χρησιμοποιώντας τις κλάσεις `Stroke` και `Color`, αντίστοιχα.

## Συμπέρασμα
Συγχαρητήρια! Τώρα γνωρίζετε πώς να **set text color java**, **change font size java**, **apply fill and stroke text**, και **create postscript document** χρησιμοποιώντας το Aspose.Page for Java. Πειραματιστείτε με διαφορετικές γραμματοσειρές, χρώματα και στυλ περιγράμματος για να παράγετε επαγγελματικά αποτελέσματα PostScript.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}