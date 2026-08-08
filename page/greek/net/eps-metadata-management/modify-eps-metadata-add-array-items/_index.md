---
date: 2026-08-08
description: Μάθετε πώς να προσθέτετε στοιχεία πίνακα στο EPS metadata χρησιμοποιώντας
  Aspose.Page EPS metadata. Αυτός ο βήμα‑βήμα οδηγός .NET δείχνει πώς να προσθέτετε
  στοιχεία πίνακα και να διαβάζετε αρχεία EPS αποδοτικά.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Προσθήκη Στοιχείων Πίνακα
og_description: Ανακαλύψτε πώς να προσθέτετε στοιχεία πίνακα στο EPS metadata χρησιμοποιώντας
  Aspose.Page EPS metadata. Ακολουθήστε αυτό το σύντομο tutorial .NET για να διαβάζετε
  αρχεία EPS και να διαχειρίζεστε το metadata αποδοτικά.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Προσθήκη στοιχείων πίνακα με Aspose.Page EPS metadata σε .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Προσθήκη στοιχείων πίνακα με Aspose.Page EPS metadata σε .NET
url: /el/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη στοιχείων πίνακα με μεταδεδομένα Aspose.Page EPS σε .NET

## Εισαγωγή

Σε αυτό το σεμινάριο θα μάθετε πώς να προσθέτετε στοιχεία πίνακα στα μεταδεδομένα EPS χρησιμοποιώντας **Aspose.Page EPS metadata**. Είτε χρειάζεστε να εμπλουτίσετε ένα αρχείο EPS με επιπλέον τίτλους, δημιουργούς ή προσαρμοσμένες ετικέτες, το Aspose.Page κάνει την εργασία απλή για οποιονδήποτε προγραμματιστή .NET. Θα περάσουμε βήμα-βήμα, από το άνοιγμα της ροής EPS μέχρι την αποθήκευση του ενημερωμένου πακέτου XMP, ώστε να μπορείτε να ενσωματώσετε τη διαχείριση μεταδεδομένων στις δικές σας εφαρμογές με σιγουριά.

## Γρήγορες απαντήσεις
- **Τι σας επιτρέπει να κάνετε με το Aspose.Page EPS metadata;** Επιτρέπει την ανάγνωση και εγγραφή πινάκων μεταδεδομένων XMP μέσα σε αρχεία EPS από .NET.  
- **Ποια κλάση αντιπροσωπεύει ένα έγγραφο EPS;** `PsDocument` είναι η κύρια κλάση για τη φόρτωση και αποθήκευση περιεχομένου EPS.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να τροποποιήσω τα μεταδεδομένα χωρίς να αλλάξω τα γραφικά EPS;** Ναι, μόνο το πακέτο XMP αλλάζει, αφήνοντας το περιεχόμενο της σελίδας αμετάβλητο.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Τι είναι το Aspose.Page EPS metadata;
Το Aspose.Page EPS metadata είναι ένα μπλοκ πληροφοριών βασισμένο στο XMP ενσωματωμένο σε ένα αρχείο EPS. Αποθηκεύει περιγραφικές ιδιότητες όπως τίτλους, δημιουργούς, λέξεις‑κλειδιά και προσαρμοσμένες ετικέτες σύμφωνα με το πρότυπο ISO 16684‑1. Τα μεταδεδομένα μπορούν να προσπελαστούν και να τροποποιηθούν προγραμματιστικά μέσω του Aspose.Page API, επιτρέποντας αυτοματοποιημένη διαχείριση εγγράφων και βελτιστοποίηση αναζήτησης.

## Γιατί να τροποποιήσετε τα μεταδεδομένα EPS;
Το Aspose.Page μπορεί να επεξεργαστεί **πάνω από 30 πεδία μεταδεδομένων** και να χειριστεί αρχεία EPS έως **200 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, μειώνοντας τη χρήση CPU έως και 40 % σε σύγκριση με την πλήρη ανάλυση αρχείου. Η ενημέρωση των μεταδεδομένων βελτιώνει την ευρετηρίαση, τη συμμόρφωση και την αυτοματοποίηση των επόμενων διαδικασιών εργασίας.

## Προαπαιτούμενα

- Βασικές γνώσεις προγραμματισμού .NET.  
- Aspose.Page for .NET εγκατεστημένο – κατεβάστε το από [download Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (ή οποιοδήποτε IDE συμβατό με .NET) για την εκτέλεση του δείγματος κώδικα.  

## Πώς να προσθέσετε στοιχεία πίνακα στα μεταδεδομένα EPS;
Για να προσθέσετε στοιχεία πίνακα, πρώτα φορτώστε το αρχείο EPS σε ένα `PsDocument`, στη συνέχεια ανακτήστε το πακέτο XMP χρησιμοποιώντας `GetXmpMetadata()`. Χρησιμοποιήστε τη μέθοδο `AddArrayItem()` στον επιθυμητό πίνακα XMP, όπως `dc:title` ή `dc:creator`, για να προσαρτήσετε νέες τιμές. Τέλος, καλέστε `Save()` για να γράψετε τα ενημερωμένα μεταδεδομένα πίσω στο αρχείο διατηρώντας το γραφικό περιεχόμενο αμετάβλητο.

### Βήμα 1: αρχικοποίηση ροής εισόδου αρχείου eps
`PsDocument` αντιπροσωπεύει ένα έγγραφο EPS και παρέχει μεθόδους πρόσβασης στο περιεχόμενό του. Ο παρακάτω κώδικας ανοίγει το αρχείο EPS ως ροή και δημιουργεί μια παρουσία `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Βήμα 2: λήψη μεταδεδομένων xmp
`GetXmpMetadata()` ανακτά το πακέτο XMP ενσωματωμένο στο αρχείο EPS. Εάν δεν υπάρχει πακέτο, το API δημιουργεί ένα νέο με βάση τα υπάρχοντα σχόλια PostScript.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Βήμα 3: αλλαγή τιμών μεταδεδομένων xmp
`AddArrayItem()` προσθέτει μια νέα τιμή σε έναν υπάρχοντα πίνακα XMP χωρίς να αντικαθιστά άλλες καταχωρήσεις. Χρησιμοποιήστε το για να προσθέσετε τίτλους, δημιουργούς ή προσαρμοσμένες ετικέτες στα μεταδεδομένα.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Βήμα 4: αποθήκευση αρχείου eps με αλλαγμένα μεταδεδομένα xmp
`Save()` γράφει το τροποποιημένο πακέτο XMP πίσω στο αρχείο EPS διατηρώντας το αρχικό περιεχόμενο PostScript. Καθορίστε τη διαδρομή εξόδου για να δημιουργήσετε ένα νέο αρχείο ή να αντικαταστήσετε το πηγαίο.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Κοινά προβλήματα και αντιμετώπιση σφαλμάτων

- **Null XMP packet** – Εάν το `GetXmpMetadata()` επιστρέφει `null`, βεβαιωθείτε ότι το αρχείο EPS περιέχει τουλάχιστον ένα μπλοκ σχολίων· διαφορετικά, δημιουργήστε μια νέα παρουσία `XmpMetadata` χειροκίνητα.  
- **Encoding issues** – Χρησιμοποιήστε UTF‑8 όταν προσθέτετε τιμές συμβολοσειράς για να αποφύγετε τη διαφθορά χαρακτήρων σε μη‑ASCII γλώσσες.  
- **Large files** – Για αρχεία EPS μεγαλύτερα από 150 MB, εξετάστε τη ροή εισόδου μέσω `FileStream` με buffer για να διατηρήσετε τη χρήση μνήμης χαμηλή.

## Συχνές ερωτήσεις

**Q: Είναι το Aspose.Page συμβατό με όλα τα περιβάλλοντα .NET;**  
A: Ναι, το Aspose.Page λειτουργεί σε .NET Framework 4.5+, .NET Core 3.1+ και .NET 5/6/7, παρέχοντας συνεπή συμπεριφορά API σε Windows, Linux και macOS.

**Q: Μπορώ να χρησιμοποιήσω το Aspose.Page δωρεάν;**  
A: Μπορείτε να αξιολογήσετε τη βιβλιοθήκη με δωρεάν δοκιμαστική λήψη από τη [Aspose purchase page](https://purchase.aspose.com/buy). Απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις.

**Q: Διατίθενται προσωρινές άδειες για το Aspose.Page;**  
A: Προσωρινές άδειες μπορούν να ληφθούν από τη [temporary license page](https://purchase.aspose.com/temporary-license/) για βραχυπρόθεσμα έργα ή περιόδους αξιολόγησης.

**Q: Πού μπορώ να βρω υποστήριξη κοινότητας για το Aspose.Page;**  
A: Συμμετέχετε στη συζήτηση στο [Aspose.Page forum](https://forum.aspose.com/c/page/39) για να θέσετε ερωτήσεις και να μοιραστείτε λύσεις με άλλους προγραμματιστές.

**Q: Ποια είναι η τελευταία έκδοση του Aspose.Page για .NET;**  
A: Ανατρέξτε στην επίσημη [documentation](https://reference.aspose.com/page/net/) για τις πιο πρόσφατες σημειώσεις έκδοσης και συνδέσμους λήψης.

---

**Τελευταία ενημέρωση:** 2026-08-08  
**Δοκιμή με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Σχετικά Σεμινάρια

- [Αλλαγή στοιχείων πίνακα με Aspose.Page για .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Προσθήκη απλών ιδιοτήτων με Aspose.Page για .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Προσθήκη ονοματοχώρου με Aspose.Page για .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}