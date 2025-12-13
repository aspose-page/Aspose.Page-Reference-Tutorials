---
date: 2025-12-13
description: Μάθετε πώς να προσθέσετε κείμενο σε σελίδα ASP με Java, να ορίσετε το
  στυλ γραμματοσειράς σε Java και πώς να προσθέσετε κείμενο Unicode χρησιμοποιώντας
  το Aspose.Page. Ακολουθήστε τον βήμα‑βήμα οδηγό μας.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Σελίδα ASP προσθήκη κειμένου – Unicode σε Java PostScript
url: /el/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode σε Java PostScript

## Εισαγωγή
Αν χρειάζεστε **asp page add text** σε μια ροή εργασίας Java PostScript ενώ διατηρείτε χαρακτήρες Unicode, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από την προσθήκη κειμένου Unicode, τον καθορισμό του στυλ γραμματοσειράς και την αποθήκευση του αποτελέσματος χρησιμοποιώντας **Aspose.Page for Java**. Στο τέλος θα κατανοήσετε πώς να ρυθμίσετε το στυλ γραμματοσειράς java και πώς να προσθέσετε κείμενο Unicode αποδοτικά στα έργα σας.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη μπορεί να προσθέσει κείμενο Unicode σε Java PostScript;** Aspose.Page for Java.  
- **Ποια κύρια μέθοδος προσθέτει κείμενο;** `doc.addGlyphs(...)` with a `XpsGlyphs` object.  
- **Χρειάζομαι ειδική γραμματοσειρά για Unicode;** Any TrueType/OpenType font that supports the required code points (e.g., Arial).  
- **Μπορώ να αλλάξω το στυλ γραμματοσειράς;** Yes, using `XpsFontStyle` (Regular, Bold, Italic, etc.).  
- **Απαιτείται άδεια για παραγωγή;** Yes, a valid Aspose.Page license is needed for non‑trial use.

## Τι είναι το asp page add text;
`asp page add text` αναφέρεται στη διαδικασία εισαγωγής αλφαριθμητικών σε ένα έγγραφο PostScript ή XPS χρησιμοποιώντας το API του Aspose.Page. Το API αφαιρεί τις χαμηλού επιπέδου εντολές PostScript, επιτρέποντάς σας να εργάζεστε με αντικείμενα υψηλού επιπέδου όπως το `XpsGlyphs`.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για να ορίσετε το στυλ γραμματοσειράς java και να προσθέσετε κείμενο Unicode;
- **Πλήρης υποστήριξη Unicode** – Διαχειρίζεται γραφές από δεξιά προς αριστερά και σύνθετα γλύφους.  
- **Απλό API** – Κλήσεις μίας γραμμής για την προσθήκη κειμένου και την εφαρμογή στυλ.  
- **Διαπλατφορμικό** – Λειτουργεί σε οποιοδήποτε περιβάλλον συμβατό με Java.  
- **Χωρίς εξωτερικές εξαρτήσεις** – Δεν απαιτούνται πρόσθετες μηχανές απόδοσης.

## Προαπαιτούμενα
Πριν ξεκινήσουμε το tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

1. **Java Development Kit (JDK)** – Βεβαιωθείτε ότι η Java είναι εγκατεστημένη στον υπολογιστή σας.  
2. **Aspose.Page for Java** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Aspose.Page από το [download link](https://releases.aspose.com/page/java/).  
3. **Integrated Development Environment (IDE)** – Επιλέξτε το προτιμώμενο Java IDE σας, όπως IntelliJ IDEA ή Eclipse.

## Εισαγωγή Πακέτων
Στο Java project σας, εισάγετε τα απαραίτητα πακέτα για το Aspose.Page. Προσθέστε τις παρακάτω γραμμές στον κώδικά σας:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Βήμα 1: Ρύθμιση του Project σας
Δημιουργήστε ένα νέο Java project στο IDE σας και ρυθμίστε τη δομή του project. Βεβαιωθείτε ότι έχετε συμπεριλάβει τη βιβλιοθήκη Aspose.Page στις εξαρτήσεις του project.

## Βήμα 2: Αρχικοποίηση του XPS Document
Ξεκινήστε με την αρχικοποίηση ενός νέου XPS εγγράφου μέσα στο project σας:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Βήμα 3: Προσθήκη Κειμένου Unicode
Τώρα, ας προσθέσουμε κείμενο Unicode στο XPS έγγραφό σας χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page. Χρησιμοποιήστε το παρακάτω απόσπασμα κώδικα:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Αυτό το τμήμα κώδικα προσθέτει το κείμενο Unicode **"AVAJ rof SPX.esopsA"** στο XPS έγγραφο στις συντεταγμένες (400, 200) με τη συγκεκριμένη γραμματοσειρά και στυλ. Παρατηρήστε πώς η κλήση `setBidiLevel(1)` ενεργοποιεί την απόδοση από δεξιά προς αριστερά για σωστή εμφάνιση Unicode.

## Βήμα 4: Αποθήκευση του Εγγράφου
Αποθηκεύστε το παραγόμενο XPS έγγραφο χρησιμοποιώντας τον παρακάτω κώδικα:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Συμπέρασμα
Συγχαρητήρια! Έχετε επιτυχώς **asp page add text** και ορίσει το στυλ γραμματοσειράς σε ένα σενάριο Java PostScript χρησιμοποιώντας το Aspose.Page. Αυτή η μέθοδος σας παρέχει λεπτομερή έλεγχο της απόδοσης και του στυλ Unicode, καθιστώντας την ιδανική για διεθνή αναφορές, τιμολόγια και γραφικά.

Μη διστάσετε να εξερευνήσετε περισσότερες δυνατότητες και χαρακτηριστικά του Aspose.Page στην [documentation](https://reference.aspose.com/page/java/).

## Συχνές Ερωτήσεις

**Q:** Μπορώ να χρησιμοποιήσω το Aspose.Page για Java με άλλες γλώσσες προγραμματισμού;  
**A:** Το Aspose.Page είναι κυρίως σχεδιασμένο για Java, αλλά η Aspose παρέχει βιβλιοθήκες για διάφορες γλώσσες προγραμματισμού.

**Q:** Υπάρχει διαθέσιμη δωρεάν δοκιμή;  
**A:** Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Page [εδώ](https://releases.aspose.com/).

**Q:** Πού μπορώ να βρω υποστήριξη και συζητήσεις σχετικά με το Aspose.Page;  
**A:** Επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για υποστήριξη και συζητήσεις.

**Q:** Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page;  
**A:** Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Q:** Ποια στυλ γραμματοσειράς είναι διαθέσιμα στο Aspose.Page;  
**A:** Το Aspose.Page υποστηρίζει στυλ γραμματοσειράς όπως Regular, Bold, Italic και BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2025-12-13  
**Δοκιμή με:** Aspose.Page for Java (latest)  
**Συγγραφέας:** Aspose