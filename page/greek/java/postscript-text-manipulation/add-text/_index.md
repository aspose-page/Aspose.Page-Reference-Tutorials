---
date: 2025-12-14
description: Μάθετε πώς να ορίζετε το χρώμα κειμένου στη Java χρησιμοποιώντας το Aspose.Page
  for Java, να προσθέτετε κείμενο σε PostScript και να εφαρμόζετε περίγραμμα κειμένου
  για πλούσιο στυλ εγγράφου.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Ορισμός χρώματος κειμένου Java με το Aspose.Page – Οδηγός διαχείρισης κειμένου
url: /el/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός Χρώματος Κειμένου Java με Aspose.Page – Οδηγός Χειρισμού Κειμένου

## Εισαγωγή
Καλώς ήρθατε στον βήμα‑βήμα οδηγό μας για **set text color java** ενώ εργάζεστε με αρχεία PostScript χρησιμοποιώντας το Aspose.Page for Java. Το Aspose.Page for Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν και **να δημιουργούν αρχεία postscript** έγγραφα, να χειρίζονται γραμματοσειρές και να μορφοποιούν το κείμενο με ακρίβεια. Σε αυτό το tutorial θα μάθετε πώς να προσθέτετε κείμενο, να αλλάζετε το χρώμα του, να προσαρμόζετε το μέγεθος και ακόμη **να εφαρμόζετε stroke text** για ένα επαγγελματικό αποτέλεσμα.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη μου επιτρέπει να ορίσω το χρώμα κειμένου σε Java;** Aspose.Page for Java.
- **Μπορώ να χρησιμοποιήσω σύστημα γραμματοσειρών και προσαρμοσμένες γραμματοσειρές;** Ναι, και τα δύο υποστηρίζονται.
- **Πώς αλλάζω το μέγεθος του κειμένου;** Καθορίζοντας το μέγεθος γραμματοσειράς κατά τη δημιουργία του `Font` ή `DrFont`.
- **Είναι δυνατόν να περιγράψω και να γεμίσω το κείμενο ταυτόχρονα;** Απόλυτα – χρησιμοποιήστε το `fillAndStrokeText`.
- **Ποια μορφή εξόδου παράγει αυτό το tutorial;** Ένα έγγραφο PostScript (`.ps`).

## Τι είναι το “set text color java”;
Ο ορισμός του χρώματος κειμένου σε Java σημαίνει τον καθορισμό του αντικειμένου `Color` που χρησιμοποιεί η μηχανή απόδοσης (εδώ, Aspose.Page) κατά τη σχεδίαση χαρακτήρων σε μια σελίδα. Αυτή η λειτουργία είναι απαραίτητη για τη δημιουργία οπτικά διακριτών εγγράφων, ειδικά όταν δημιουργείτε **postscript documents** προγραμματιστικά.

## Γιατί να χρησιμοποιήσετε το Aspose.Page for Java;
- **Πλήρη έλεγχος** στη δημιουργία PostScript χωρίς την ανάγκη ενός εγγενούς ερμηνευτή PostScript.
- **Υποστήριξη τόσο για σύστημα όσο και για εξωτερικές γραμματοσειρές**, επιτρέποντάς σας να ενσωματώσετε οποιαδήποτε τυπογραφία χρειάζεστε.
- **Εύκολη API** για γέμισμα, περιγράμματα και **fill and stroke text**, παρέχοντάς σας ευελιξία στη μορφοποίηση.
- **Διαπλατφορμική** συμβατότητα – γράψτε μία φορά, τρέξτε όπου τρέχει η Java.

## Προαπαιτούμενα
Πριν βυθιστείτε, βεβαιωθείτε ότι έχετε:

- Βασικές γνώσεις προγραμματισμού Java.
- Εγκατεστημένη τη βιβλιοθήκη Aspose.Page for Java. Μπορείτε να την κατεβάσετε από τη [Aspose.Page for Java download page](https://releases.aspose.com/page/java/).
- Απαραίτητες γραμματοσειρές διαθέσιμες στον καθορισμένο φάκελο. Πρόσθετες λεπτομέρειες βρίσκονται στην [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).

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

## Πώς να Ορίσετε το Χρώμα Κειμένου Java Χρησιμοποιώντας Σύστημα Γραμματοσειράς
Τώρα δείχνουμε **set text color java** με μια σύστημα‑παρέχουσα γραμματοσειρά.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Συμβουλή:** Η μέθοδος `fillText` χρησιμοποιεί αυτόματα το τρέχον χρώμα εάν δεν περάσετε ένα όρισμα `Color`, το οποίο προεπιλεγμένα είναι μαύρο.

## Χρήση Προσαρμοσμένης Γραμματοσειράς και Αλλαγή Μεγέθους Κειμένου
Μπορείτε επίσης **να αλλάξετε το μέγεθος του κειμένου** και να χρησιμοποιήσετε μια προσαρμοσμένη γραμματοσειρά αποθηκευμένη στον φάκελο γραμματοσειρών σας.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Περιγράμμιση (Stroke) Κειμένου – Εφαρμογή Stroke Text
Η περιγράμμιση του κειμένου του δίνει μια καθαρή άκρη. Εδώ **εφαρμόζουμε stroke text** χρησιμοποιώντας ένα `BasicStroke`.

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
Η ίδια τεχνική λειτουργεί με προσαρμοσμένες γραμματοσειρές.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Βήμα 6: Αποθήκευση του Εγγράφου
Τέλος, κλείνουμε τη σελίδα και γράφουμε το αρχείο στο δίσκο.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Συχνά Προβλήματα & Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Γραμματοσειρά δεν βρέθηκε** | Βεβαιωθείτε ότι το αρχείο γραμματοσειράς βρίσκεται στο `necessary_fonts` και ότι η διαδρομή του φακέλου έχει προστεθεί σωστά μέσω `options.setAdditionalFontsFolders`. |
| **Το χρώμα δεν εφαρμόστηκε** | Επιβεβαιώστε ότι καλείτε την υπερφόρτωση της `fillText` ή `outlineText` που περιλαμβάνει ένα όρισμα `Color`. |
| **Το περίγραμμα είναι πολύ λεπτό** | Αυξήστε το πλάτος του `BasicStroke` (π.χ., `new BasicStroke(3)`). |
| **Το έγγραφο δεν ανοίγει** | Επιβεβαιώστε ότι το παραγόμενο αρχείο `.ps` αποθηκεύεται με τη σωστή επέκταση και ότι ο προβολέας σας υποστηρίζει PostScript. |

## Συχνές Ερωτήσεις

**Ε:** Μπορώ να χρησιμοποιήσω τις δικές μου προσαρμοσμένες γραμματοσειρές με το Aspose.Page for Java;  
**Α:** Ναι, μπορείτε να χρησιμοποιήσετε προσαρμοσμένες γραμματοσειρές καθορίζοντας το όνομα και το μέγεθος της γραμματοσειράς στην κλάση `DrFont`.

**Ε:** Πώς μπορώ να αλλάξω το χρώμα του κειμένου;  
**Α:** Μπορείτε να ορίσετε το επιθυμητό χρώμα χρησιμοποιώντας την κλάση `Color` κατά το γέμισμα ή την περιγραφή του κειμένου.

**Ε:** Είναι δυνατόν να προσθέσω πολλαπλές σελίδες σε ένα έγγραφο PostScript;  
**Α:** Απόλυτα! Μπορείτε να δημιουργήσετε πολλαπλές σελίδες επαναλαμβάνοντας τα βήματα δημιουργίας και αποθήκευσης του εγγράφου.

**Ε:** Ποιος είναι ο σκοπός της κλάσης `ExternalFontCache`;  
**Α:** Η `ExternalFontCache` χρησιμοποιείται για την ανάκτηση προσαρμοσμένων γραμματοσειρών, διασφαλίζοντας ότι είναι διαθέσιμες για τη διαχείριση κειμένου.

**Ε:** Μπορώ να εφαρμόσω διαφορετικά περιγράμματα στο περιγραμμένο κείμενο;  
**Α:** Ναι, μπορείτε να προσαρμόσετε το πλάτος και το χρώμα του περιγράμματος χρησιμοποιώντας την κλάση `Stroke` και την κλάση `Color`, αντίστοιχα.

## Συμπέρασμα
Συγχαρητήρια! Τώρα γνωρίζετε πώς να **set text color java**, να αλλάζετε τα μεγέθη γραμματοσειρών, να **apply stroke text**, και να **create postscript document** χρησιμοποιώντας το Aspose.Page for Java. Πειραματιστείτε με διαφορετικές γραμματοσειρές, χρώματα και στυλ περιγράμματος για να παράγετε επαγγελματικά αποτελέσματα PostScript.

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}