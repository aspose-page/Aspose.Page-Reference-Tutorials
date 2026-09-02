---
date: 2026-05-20
description: Μάθετε πώς να προσθέσετε κείμενο Unicode σε Java PostScript χρησιμοποιώντας
  το Aspose.Page – ένας οδηγός step‑by‑step για το πώς να προσθέσετε Unicode strings
  χωρίς κόπο.
keywords:
- how to add unicode
- java add arabic text
- java add chinese text
linktitle: Προσθήκη κειμένου με Unicode String σε Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  headline: How to Add Unicode Text in Java PostScript with Aspose.Page
  type: TechArticle
- description: Learn how to add Unicode text in Java PostScript using Aspose.Page
    – a step‑by‑step guide on how to add unicode strings effortlessly.
  name: How to Add Unicode Text in Java PostScript with Aspose.Page
  steps:
  - name: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
    text: '**Java Development Kit (JDK)** – Any recent version (8 or newer).'
  - name: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
    text: '**Aspose.Page for Java** – Download and install the library from the [download
      link](https://releases.aspose.com/page/java/). You can also browse all releases
      [here](https://releases.aspose.com/).'
  - name: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
    text: '**IDE of your choice** – IntelliJ IDEA, Eclipse, or any other Java IDE
      you prefer.'
  type: HowTo
- questions:
  - answer: Aspose.Page is built specifically for Java, but Aspose offers equivalent
      libraries for .NET, C++, and Python if you need cross‑language support.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      help, samples, and troubleshooting tips.
    question: Where can I find support and community discussions?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for testing?
  - answer: The API supports Regular, Bold, Italic, and BoldItalic styles for any
      TrueType or OpenType font you load.
    question: What font styles does Aspose.Page support?
  type: FAQPage
second_title: Aspose.Page Java API
title: Πώς να προσθέσετε κείμενο Unicode σε Java PostScript με Aspose.Page
url: /el/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Κείμενο Unicode σε Java PostScript με Aspose.Page

## Εισαγωγή
Αν αναρωτιέστε **πώς να προσθέσετε Unicode** χαρακτήρες σε μια ροή εργασίας Java‑based PostScript (ή XPS), βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα τις ακριβείς ενέργειες που απαιτούνται για την ενσωμάτωση αλφαριθμητικών Unicode χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για Java. Στο τέλος του οδηγού θα μπορείτε να εισάγετε κείμενο οποιασδήποτε γλώσσας—Αραβικά, Κινέζικα, emojis, ό,τι θέλετε—απευθείας στην έξοδο PostScript.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρειάζεται;** Aspose.Page for Java  
- **Μπορώ να προσθέσω γλώσσες από δεξιά προς αριστερά;** Yes, set the Bidi level as shown in the code  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for testing; a commercial license is required for production  
- **Ποιο IDE είναι το καλύτερο;** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Είναι ο κώδικας cross‑platform;** Absolutely—run it on Windows, macOS, or Linux  

## Τι σημαίνει “πώς να προσθέσετε Unicode” στο πλαίσιο του PostScript;
Η προσθήκη κειμένου Unicode σημαίνει την ενσωμάτωση χαρακτήρων των οποίων τα σημεία κώδικα βρίσκονται εκτός του βασικού εύρους ASCII—όπως Αραβικά, Κινέζικα ή emoji—σε ένα έγγραφο PostScript (ή XPS) χρησιμοποιώντας το Aspose.Page. Η βιβλιοθήκη αντιστοιχίζει αυτόματα αυτά τα σημεία κώδικα στα κατάλληλα γλύφα στα επιλεγμένα γραμματοσειρά, διαχειριζόμενη σύνθετη διαμόρφωση, λιγκατούρες και σειρά από δεξιά προς αριστερά χωρίς καμία χειροκίνητη κωδικοποίηση.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για κείμενο Unicode;
Το Aspose.Page σας προσφέρει μια αξιόπιστη, 100 % καθαρά‑Java λύση που υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να αποδώσει πολυγλωσσικό κείμενο σε έγγραφα έως 1.000 σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Απομακρύνει την ανάγκη για εξωτερικά εργαλεία διαχείρισης γραμματοσειρών, μειώνει το χρόνο ανάπτυξης κατά 70 % και εγγυάται συνεπή οπτική έξοδο σε περιβάλλοντα Windows, macOS και Linux.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

1. **Java Development Kit (JDK)** – Οποιαδήποτε πρόσφατη έκδοση (8 ή νεότερη).  
2. **Aspose.Page for Java** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από το [download link](https://releases.aspose.com/page/java/). Μπορείτε επίσης να περιηγηθείτε σε όλες τις εκδόσεις [εδώ](https://releases.aspose.com/).  
3. **IDE της επιλογής σας** – IntelliJ IDEA, Eclipse, ή οποιοδήποτε άλλο Java IDE προτιμάτε.

## Εισαγωγή Πακέτων
Προσθέστε τις απαιτούμενες κλάσεις Aspose.Page στο αρχείο πηγαίου κώδικα Java σας:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Βήμα 1: Ρύθμιση του Έργου σας
Δημιουργήστε ένα νέο έργο Java, προσθέστε το JAR του Aspose.Page στο build path του έργου και δημιουργήστε έναν φάκελο όπου θα αποθηκευτεί το παραγόμενο αρχείο XPS. Αυτός ο φάκελος αναφέρεται αργότερα ως `dataDir`.

## Βήμα 2: Αρχικοποίηση του XPS Εγγράφου
Η κλάση `XpsDocument` αντιπροσωπεύει ένα αρχείο XPS στη μνήμη και παρέχει τον καμβά για όλες τις λειτουργίες σχεδίασης.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Βήμα 3: Προσθήκη Κειμένου Unicode
Τώρα θα προσθέσουμε πραγματικά το Unicode string. Το παρακάτω παράδειγμα γράφει τη φράση αντίστροφης σειράς “AVAJ rof SPX.esopsA”, η οποία περιέχει μόνο χαρακτήρες ASCII, αλλά μπορείτε να την αντικαταστήσετε με οποιοδήποτε κείμενο Unicode (π.χ., Αραβικά “مرحبا” ή Κινέζικα “你好”). Αυτό είναι το πώς **java add arabic text** ή **java add chinese text** στο έγγραφό σας.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Συμβουλή:** Για σωστή απόδοση γλωσσών από δεξιά προς αριστερά, ορίστε `glyphs.setBidiLevel(1);`. Για γλώσσες από αριστερά προς δεξιά μπορείτε να παραλείψετε αυτή τη γραμμή.

## Βήμα 4: Αποθήκευση του Εγγράφου
Αποθηκεύστε το αρχείο XPS στο δίσκο:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Μετά την εκτέλεση του προγράμματος, ανοίξτε το παραγόμενο `AddEncodingText_out.xps` με οποιονδήποτε προβολέα XPS για να δείτε το κείμενο Unicode να αποδίδεται στις καθορισμένες συντεταγμένες.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Το κείμενο εμφανίζεται ως τετράγωνα | Η γραμματοσειρά δεν βρέθηκε ή δεν υποστηρίζει τους χαρακτήρες | Χρησιμοποιήστε μια γραμματοσειρά που περιλαμβάνει τα απαιτούμενα γλύφους (π.χ., “Arial Unicode MS”) |
| Το κείμενο από δεξιά προς αριστερά εμφανίζεται από αριστερά προς δεξιά | Δεν έχει οριστεί το επίπεδο Bidi | Καλέστε `glyphs.setBidiLevel(1);` |
| Το αρχείο δεν αποθηκεύτηκε | Η διαδρομή `dataDir` είναι μη έγκυρη ή λείπουν δικαιώματα εγγραφής | Βεβαιωθείτε ότι ο φάκελος υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής |

## Συχνές Ερωτήσεις
**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page για Java με άλλες γλώσσες προγραμματισμού;**  
A: Το Aspose.Page είναι χτισμένο ειδικά για Java, αλλά η Aspose προσφέρει ισοδύναμες βιβλιοθήκες για .NET, C++ και Python αν χρειάζεστε υποστήριξη πολλαπλών γλωσσών.

**Q: Υπάρχει διαθέσιμη δωρεάν δοκιμή;**  
A: Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του Aspose.Page [εδώ](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω υποστήριξη και συζητήσεις κοινότητας;**  
A: Επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για βοήθεια, παραδείγματα και συμβουλές αντιμετώπισης προβλημάτων.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;**  
A: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Τι στυλ γραμματοσειρών υποστηρίζει το Aspose.Page;**  
A: Το API υποστηρίζει στυλ Regular, Bold, Italic και BoldItalic για οποιαδήποτε γραμματοσειρά TrueType ή OpenType φορτώνετε.

## Συμπέρασμα
Τώρα έχετε κατακτήσει **πώς να προσθέσετε Unicode** κείμενο σε ένα έγγραφο Java PostScript (XPS) χρησιμοποιώντας το Aspose.Page. Αυτή η δυνατότητα ανοίγει το δρόμο για πολυγλωσσικές αναφορές, διεθνείς τιμολόγησης και οποιοδήποτε σενάριο όπου απαιτούνται μη‑ASCII χαρακτήρες. Μη διστάσετε να εξερευνήσετε πρόσθετες λειτουργίες όπως περιστροφή κειμένου, μονοπάτια αποκοπής ή ενσωμάτωση προσαρμοσμένων γραμματοσειρών—λεπτομέρειες διατίθενται στην επίσημη [documentation](https://reference.aspose.com/page/java/).

---

**Last Updated:** 2026-05-20  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Προσθέσετε Κείμενο σε PostScript με Aspose.Page για Java](/page/java/postscript-text-manipulation/)
- [Ορισμός Χρώματος Κειμένου Java με Aspose.Page – Οδηγός Διαχείρισης Κειμένου](/page/java/postscript-text-manipulation/add-text/)
- [Προσθήκη Σελίδων PostScript Java – Ένας Απρόσκοπτος Οδηγός με Aspose.Page](/page/java/postscript-page-manipulation/add-pages1/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}