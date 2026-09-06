---
date: 2026-08-13
description: Μάθετε πώς να χρησιμοποιείτε το Aspose.Page για να αλλάξετε τιμές EPS
  σε εφαρμογές .NET, συμπεριλαμβανομένων των ενημερώσεων XMP metadata step‑by‑step.
keywords:
- aspose.page change eps values
- modify eps metadata
- xmp metadata .net
- eps file manipulation
lastmod: 2026-08-13
linktitle: Αλλαγή τιμών
og_description: Το tutorial Aspose.Page change eps values σας δείχνει πώς να τροποποιήσετε
  XMP metadata μέσα σε αρχεία EPS χρησιμοποιώντας .NET. Ακολουθήστε τον step‑by‑step
  οδηγό για να ενημερώσετε creator, title και modify date άμεσα.
og_image_alt: Guide showing how to change EPS metadata values using Aspose.Page for
  .NET
og_title: Aspose.Page αλλαγή τιμών EPS με .NET tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  headline: Aspose.Page change eps values with .NET – tutorial
  type: TechArticle
- description: Learn how to use Aspose.Page to change EPS values in .NET applications,
    including step‑by‑step XMP metadata updates.
  name: Aspose.Page change eps values with .NET – tutorial
  steps:
  - name: initialize EPS file input stream
    text: Create a read‑only `FileStream` that points to the source EPS file.
  - name: create PsDocument instance from stream
    text: '`PsDocument` is the top‑level object representing an EPS document in memory.
      It gives you access to both the page content and the embedded XMP metadata.'
  - name: get XMP metadata
    text: The `XmpMetadata` property returns an `XmpPacket` object that you can query
      and edit.
  - name: modify XMP metadata values
    text: 'Now you’ll change three common fields: **ModifyDate**, **Creator**, and
      **Title**.'
  - name: '1: change ModifyDate value'
    text: Set the `ModifyDate` to the current UTC timestamp.
  - name: '2: change Creator value'
    text: Replace the existing creator with your application name.
  - name: '3: change Title value'
    text: Update the title to reflect the new content purpose.
  - name: save EPS file with changed XMP metadata
    text: After editing, write the document back out.
  - name: '1: create output stream'
    text: Open a `FileStream` for the destination EPS file.
  - name: '2: save EPS file'
    text: Call `Save` on the `PsDocument` instance, passing the output stream. Finally,
      close the input stream to release the file handle. Congratulations! You have
      successfully **aspose.page change eps values** by updating the XMP metadata
      inside an EPS file.
  type: HowTo
- questions:
  - answer: Yes, the library supports over 30 formats including PDF, SVG, and AI,
      but the XMP editing APIs are specific to EPS and PDF.
    question: Can I use Aspose.Page for .NET with other graphic formats?
  - answer: Yes, you can try out Aspose.Page for .NET with the free trial available
      on the Aspose releases page [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The comprehensive Aspose.Page .NET API reference can be found [here](https://reference.aspose.com/page/net/).
    question: Where can I find detailed documentation?
  - answer: You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: Absolutely! Visit the Aspose.Page purchase page [here](https://purchase.aspose.com/buy)
      for licensing options.
    question: Can I purchase Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- eps metadata
- .net document processing
- xmp editing
title: Aspose.Page αλλαγή τιμών EPS με .NET – tutorial
url: /el/net/eps-metadata-management/modify-eps-metadata-change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page αλλαγή τιμών eps με .NET – οδηγός

## Εισαγωγή

Σε αυτόν τον οδηγό θα ανακαλύψετε πώς να **aspose.page change eps values** επεξεργάζοντας τα ενσωματωμένα μεταδεδομένα XMP σε ένα αρχείο EPS. Είτε χρειάζεστε να ενημερώσετε το όνομα δημιουργού, να προσαρμόσετε τον τίτλο ή να διορθώσετε την ημερομηνία τροποποίησης, το Aspose.Page για .NET σας παρέχει ένα καθαρό, κώδικα‑πρώτο API που λειτουργεί σε Windows, Linux και macOS. Στο τέλος του οδηγού θα έχετε ένα επαναχρησιμοποιήσιμο απόσπασμα κώδικα που μπορείτε να ενσωματώσετε σε οποιαδήποτε υπηρεσία ή κονσόλα .NET.

## Γρήγορες απαντήσεις
- **Τι καλύπτει ο οδηγός;** Αλλαγή μεταδεδομένων XMP (δημιουργός, τίτλος, ημερομηνία τροποποίησης) μέσα σε αρχεία EPS χρησιμοποιώντας το Aspose.Page για .NET.  
- **Ποια έκδοση της βιβλιοθήκης απαιτείται;** Οποιαδήποτε έκδοση του Aspose.Page για .NET που υποστηρίζει XMP (v24.10+).  
- **Χρειάζομαι άδεια;** Απαιτείται προσωρινή άδεια για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη.  
- **Μπορώ να το τρέξω σε .NET Core;** Ναι – το API είναι συμβατό με .NET 5, .NET 6 και .NET Core 3.1+.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 5‑10 λεπτά για μια βασική ενημέρωση μεταδεδομένων.

## Τι είναι τα μεταδεδομένα XMP;

Τα μεταδεδομένα XMP είναι ένα τυποποιημένο μπλοκ XML που αποθηκεύει περιγραφικές πληροφορίες (συγγραφέας, τίτλος, ημερομηνίες) μέσα σε αρχεία EPS και άλλες μορφές γραφικών. Ενσωματώνονται απευθείας στην κεφαλίδα του αρχείου και μπορούν να διαβαστούν από πολλά εργαλεία σχεδίασης και δημοσίευσης, επιτρέποντας συνεπή διαχείριση μεταδεδομένων σε διαφορετικές πλατφόρμες. Η ενημέρωση του XMP επιτρέπει στις εφαρμογές downstream να εμφανίζουν σωστές ιδιότητες εγγράφου χωρίς να αλλάζουν το οπτικό περιεχόμενο.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για μεταδεδομένα EPS;

Το Aspose.Page μπορεί να επεξεργαστεί **30+** μορφές γραφικών και διαχειρίζεται αρχεία EPS έως **1 GB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας **70 %** μείωση στη χρήση RAM σε σύγκριση με την απλή ανάλυση ροής. Η βιβλιοθήκη επίσης εγγυάται ότι η οπτική απόδοση του EPS παραμένει αμετάβλητη μετά τις επεμβάσεις στα μεταδεδομένα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι τα παρακάτω είναι έτοιμα:

1. **Aspose.Page for .NET library** – κατεβάστε την από τη σελίδα των επίσημων εκδόσεων Aspose.Page for .NET [εδώ](https://releases.aspose.com/page/net/). Μπορείτε επίσης να εξερευνήσετε άλλες εκδόσεις προϊόντων Aspose [εδώ](https://releases.aspose.com/).  
2. **Document directory** – δημιουργήστε έναν φάκελο στον υπολογιστή σας όπου θα αποθηκευτούν τα πηγαία αρχεία EPS και τα αρχεία εξόδου.

Τώρα που το περιβάλλον είναι έτοιμο, ας εισάγουμε τα ονόματα χώρου που θα χρειαστείτε.

## Εισαγωγή ονομάτων χώρου

Το όνομα χώρου `Aspose.Page` παρέχει τις βασικές κλάσεις, ενώ το `System.IO` σας δίνει δυνατότητες διαχείρισης ροών.

```text
using Aspose.Page;
using Aspose.Page.XMP;
using System.IO;
```

## Πώς να αλλάξετε τις τιμές μεταδεδομένων EPS;

Φορτώστε το αρχείο EPS, ανακτήστε το πακέτο XMP, τροποποιήστε τα απαιτούμενα πεδία και γράψτε το ενημερωμένο EPS ξανά στο δίσκο. Η διαδικασία δεν απαιτεί απόδοση του περιεχομένου της σελίδας, επομένως είναι γρήγορη και αποδοτική ως προς τη μνήμη. Ακολουθήστε τα αναλυτικά βήματα για να δείτε παραδείγματα κώδικα για κάθε λειτουργία. Αυτή η ολοκληρωμένη ροή καλύπτεται στα παρακάτω βήματα.

### Βήμα 1: αρχικοποίηση ροής εισόδου αρχείου EPS

Δημιουργήστε ένα `FileStream` μόνο για ανάγνωση που δείχνει στο πηγαίο αρχείο EPS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Βήμα 2: δημιουργία αντικειμένου PsDocument από τη ροή

Το `PsDocument` είναι το αντικείμενο υψηλού επιπέδου που αντιπροσωπεύει ένα έγγραφο EPS στη μνήμη. Σας δίνει πρόσβαση τόσο στο περιεχόμενο της σελίδας όσο και στα ενσωματωμένα μεταδεδομένα XMP.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

### Βήμα 3: λήψη μεταδεδομένων XMP

Η ιδιότητα `XmpMetadata` επιστρέφει ένα αντικείμενο `XmpPacket` που μπορείτε να ερωτήσετε και να επεξεργαστείτε.

```csharp
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

### Βήμα 4: τροποποίηση τιμών μεταδεδομένων XMP

Τώρα θα αλλάξετε τρία κοινά πεδία: **ModifyDate**, **Creator** και **Title**.

#### Βήμα 4.1: αλλαγή τιμής ModifyDate

Ορίστε το `ModifyDate` στην τρέχουσα χρονική σήμανση UTC.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.GetXmpMetadata();
```

#### Βήμα 4.2: αλλαγή τιμής Creator

Αντικαταστήστε τον υπάρχοντα δημιουργό με το όνομα της εφαρμογής σας.

```csharp
// Change ModifyDate value
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

#### Βήμα 4.3: αλλαγή τιμής Title

Ενημερώστε τον τίτλο ώστε να αντανακλά το νέο σκοπό του περιεχομένου.

```csharp
// Change Creator value
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Βήμα 5: αποθήκευση αρχείου EPS με τροποποιημένα μεταδεδομένα XMP

Μετά την επεξεργασία, γράψτε το έγγραφο έξω.

#### Βήμα 5.1: δημιουργία ροής εξόδου

Ανοίξτε ένα `FileStream` για το αρχείο EPS προορισμού.

```csharp
// Change Title value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

#### Βήμα 5.2: αποθήκευση αρχείου EPS

Καλέστε τη μέθοδο `Save` στο αντικείμενο `PsDocument`, περνώντας τη ροή εξόδου.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

Τέλος, κλείστε τη ροή εισόδου για να απελευθερώσετε το χειριστή του αρχείου.

```csharp
// Save EPS file
document.Save(outPsStream);
```

Συγχαρητήρια! Έχετε ολοκληρώσει επιτυχώς την **aspose.page change eps values** ενημερώνοντας τα μεταδεδομένα XMP μέσα σε ένα αρχείο EPS.

## Συχνά προβλήματα και αντιμετώπιση

- **Empty XMP packet** – Ορισμένα αρχεία EPS δημιουργούνται χωρίς XMP. Σε αυτήν την περίπτωση, δημιουργήστε ένα νέο `XmpPacket` μέσω `new XmpPacket()` πριν αναθέσετε τιμές.  
- **Large files** – Για EPS μεγαλύτερα από 500 MB, ενεργοποιήστε την προσωρινή αποθήκευση ροής ορίζοντας `PsDocumentOptions.UseMemoryMappedFiles = true` για να αποφύγετε `OutOfMemoryException`.  
- **Incorrect date format** – Το XMP απαιτεί ISO 8601. Χρησιμοποιήστε `DateTime.UtcNow.ToString("o")` για να δημιουργήσετε μια συμβατή συμβολοσειρά.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page για .NET με άλλες μορφές γραφικών;**  
A: Ναι, η βιβλιοθήκη υποστηρίζει πάνω από 30 μορφές, συμπεριλαμβανομένων PDF, SVG και AI, αλλά τα API επεξεργασίας XMP είναι συγκεκριμένα για EPS και PDF.

**Q: Διατίθεται δοκιμαστική έκδοση;**  
A: Ναι, μπορείτε να δοκιμάσετε το Aspose.Page για .NET με τη δωρεάν δοκιμή που διατίθεται στη σελίδα εκδόσεων Aspose [εδώ](https://releases.aspose.com/).

**Q: Πού μπορώ να βρω λεπτομερή τεκμηρίωση;**  
A: Η πλήρης αναφορά API του Aspose.Page .NET μπορεί να βρεθεί [εδώ](https://reference.aspose.com/page/net/).

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια;**  
A: Μπορείτε να λάβετε μια προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Q: Μπορώ να αγοράσω το Aspose.Page για .NET;**  
A: Φυσικά! Επισκεφθείτε τη σελίδα αγοράς του Aspose.Page [εδώ](https://purchase.aspose.com/buy) για επιλογές αδειοδότησης.

---

**Τελευταία ενημέρωση:** 2026-08-13  
**Δοκιμάστηκε με:** Aspose.Page 24.10 for .NET  
**Συγγραφέας:** Aspose

```csharp
finally
{
    psStream.Close();
}
```

## Σχετικά Μαθήματα

- [Add Metadata to EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Extract Metadata from EPS Document with Aspose.Page for .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)
- [Change Named Value with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}