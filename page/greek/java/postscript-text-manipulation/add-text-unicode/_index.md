---
date: 2025-12-17
description: Μάθετε πώς να προσθέσετε κείμενο Unicode σε Java PostScript χρησιμοποιώντας
  το Aspose.Page – ένας βήμα‑βήμα οδηγός για το πώς να προσθέσετε αλφαριθμητικά Unicode
  με ευκολία.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Πώς να προσθέσετε κείμενο Unicode σε Java PostScript με το Aspose.Page
url: /el/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε κείμενο Unicode σε Java PostScript με το Aspose.Page

## Introduction
Αν αναρωτιέστε **πώς να προσθέσετε Unicode** χαρακτήρες σε μια ροή εργασίας Java‑based PostScript (ή XPS), βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα τις ακριβείς ενέργειες που απαιτούνται για την ενσωμάτωση αλφαριθμητικών Unicode χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για Java. Στο τέλος του οδηγού θα μπορείτε να εισάγετε κείμενο οποιασδήποτε γλώσσας—Αραβικά, Κινέζικα, emojis, ό,τι θέλετε—απευθείας στην έξοδο PostScript.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I add right‑to‑left scripts?** Yes, set the Bidi level as shown in the code  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production  
- **Which IDE works best?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans)  
- **Is the code cross‑platform?** Absolutely—run it on Windows, macOS, or Linux

## What is “how to add Unicode” in the context of PostScript?
Η προσθήκη Unicode σημαίνει την εισαγωγή χαρακτήρων που αντιπροσωπεύονται από κωδικούς σημείων πέρα από το βασικό σύνολο ASCII. Το Aspose.Page αφαιρεί τις λεπτομέρειες κωδικοποίησης χαμηλού επιπέδου, επιτρέποντάς σας να εστιάσετε στο περιεχόμενο του κειμένου και στην οπτική του τοποθέτηση.

## Why use Aspose.Page for Unicode text?
- **Full Unicode support** – Διαχειρίζεται σύνθετα σενάρια, συνδέσεις γραμμάτων και γλώσσες από δεξιά προς αριστερά.  
- **No external dependencies** – Δεν χρειάζεται να διαχειρίζεστε χειροκίνητα αρχεία γραμματοσειρών· το API λειτουργεί με τις γραμματοσειρές του συστήματος.  
- **Straight‑forward API** – Μερικές κλήσεις μεθόδων αρκούν για την απόδοση πολυγλωσσικού κειμένου.

## Prerequisites
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω:

1. **Java Development Kit (JDK)** – Οποιαδήποτε πρόσφατη έκδοση (8 ή νεότερη).  
2. **Aspose.Page for Java** – Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη από το [download link](https://releases.aspose.com/page/java/).  
3. **IDE of your choice** – IntelliJ IDEA, Eclipse ή οποιοδήποτε άλλο Java IDE προτιμάτε.

## Import Packages
Προσθέστε τις απαιτούμενες κλάσεις Aspose.Page στο αρχείο πηγαίου κώδικα Java:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
Δημιουργήστε ένα νέο έργο Java, προσθέστε το JAR του Aspose.Page στη διαδρομή κατασκευής του έργου και δημιουργήστε έναν φάκελο όπου θα αποθηκευτεί το παραγόμενο αρχείο XPS. Αυτός ο φάκελος αναφέρεται αργότερα ως `dataDir`.

## Step 2: Initialize XPS Document
Δημιουργήστε ένα κενό έγγραφο XPS που θα περιέχει το περιεχόμενο:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
Τώρα θα προσθέσουμε πραγματικά τη συμβολοσειρά Unicode. Το παρακάτω παράδειγμα γράφει την αντίστροφη φράση “AVAJ rof SPX.esopsA”, η οποία περιέχει μόνο χαρακτήρες ASCII, αλλά μπορείτε να την αντικαταστήσετε με οποιοδήποτε κείμενο Unicode (π.χ., Αραβικά “مرحبا” ή Κινέζικα “你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Pro tip:** Για σωστή απόδοση γλωσσών από δεξιά προς αριστερά, ορίστε `glyphs.setBidiLevel(1);`. Για γλώσσες από αριστερά προς δεξιά μπορείτε να παραλείψετε αυτή τη γραμμή.

## Step 4: Save the Document
Αποθηκεύστε το αρχείο XPS στον δίσκο:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Μετά την εκτέλεση του προγράμματος, ανοίξτε το παραγόμενο `AddEncodingText_out.xps` με οποιονδήποτε προβολέα XPS για να δείτε το κείμενο Unicode να εμφανίζεται στις καθορισμένες συντεταγμένες.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Text appears as squares | Font not found or does not support the characters | Use a font that includes the required glyphs (e.g., “Arial Unicode MS”) |
| Right‑to‑left text displays left‑to‑right | Bidi level not set | Call `glyphs.setBidiLevel(1);` |
| File not saved | `dataDir` path invalid or missing write permissions | Ensure the directory exists and the application has write access |

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page is primarily designed for Java, but Aspose provides libraries for various programming languages.

### Is there a free trial available?
Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).

### Where can I find support and discussions about Aspose.Page?
Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for support and discussions.

### How can I obtain a temporary license for Aspose.Page?
You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### What are the available font styles in Aspose.Page?
Aspose.Page supports font styles such as Regular, Bold, Italic, and BoldItalic.

## Conclusion
You’ve now mastered **how to add Unicode** text to a Java PostScript (XPS) document using Aspose.Page. This capability opens the door to multilingual reporting, internationalized invoices, and any scenario where non‑ASCII characters are required. Feel free to explore additional features like text rotation, clipping paths, or embedding custom fonts—details are available in the official [documentation](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία ενημέρωση:** 2025-12-17  
**Δοκιμάστηκε με:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

---