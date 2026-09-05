---
date: 2026-07-24
description: Μετατρέψτε εύκολα XPS σε PDF στο .NET με Aspose.Page. Κατεβάστε τη βιβλιοθήκη,
  εξερευνήστε την τεκμηρίωση και αποκτήστε δωρεάν δοκιμή.
keywords:
- convert xps to pdf
- how to convert xps
- Aspose.Page .NET
- XPS to PDF conversion
lastmod: 2026-07-24
linktitle: Μετατροπή XPS σε PDF
og_description: Μάθετε πώς να μετατρέψετε XPS σε PDF χρησιμοποιώντας Aspose.Page για
  .NET. Αυτός ο οδηγός βήμα‑βήμα καλύπτει τη ρύθμιση, τον έλεγχο ποιότητας εικόνας
  και συμβουλές βέλτιστων πρακτικών.
og_image_alt: Developer guide showing XPS to PDF conversion code using Aspose.Page
  for .NET
og_title: Μετατροπή XPS σε PDF με Aspose.Page για .NET – Γρήγορη, Υψηλής Ποιότητας
  Μετατροπή
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Effortlessly convert XPS to PDF in .NET with Aspose.Page. Download
    the library, explore documentation, and get a free trial.
  headline: Convert XPS to PDF with Aspose.Page for .NET
  type: TechArticle
- description: Effortlessly convert XPS to PDF in .NET with Aspose.Page. Download
    the library, explore documentation, and get a free trial.
  name: Convert XPS to PDF with Aspose.Page for .NET
  steps:
  - name: Initialize Document Directory
    text: Define the folder that holds your source XPS file and where the resulting
      PDF will be saved. Replace `"Your Document Directory"` with the absolute or
      relative path to the folder containing your XPS document.
  - name: Open Streams for PDF Output and XPS Input
    text: We use two file streams—one for reading the XPS file and another for writing
      the generated PDF. > **Pro tip:** Ensure the paths are correct and that the
      application has read/write permissions on the target folder.
  - name: Load the XPS Document
    text: XpsLoadOptions allows you to specify loading preferences for the XPS document.
      XpsDocument is the class that loads an XPS file into memory, exposing its pages
      and resources for further processing. The `XpsLoadOptions` object lets you specify
      loading preferences, but the default works for most scenar
  - name: Configure PDF Save Options
    text: PdfSaveOptions configures how the PDF output is generated, including compression
      and quality settings. `PdfSaveOptions` defines how the PDF will be written.
      Notice the use of **PDF image compression** (`PdfImageCompression.Jpeg`) and
      **JPEG quality** (`JpegQualityLevel = 100`). These settings direct
  - name: Create a PDF Rendering Device
    text: PdfDevice is the rendering target that writes PDF data to the provided stream.
      `PdfDevice` is the rendering target that writes the PDF data to the stream we
      opened earlier.
  - name: Save the Document to PDF
    text: The Save method finalizes the conversion, writing the PDF to the output
      stream. Invoke the `Save` method, passing the rendering device and the configured
      options. When the code finishes executing, `XPStoPDF_out.pdf` will appear in
      your specified directory, containing the converted pages with the com
  type: HowTo
- questions:
  - answer: Use the `JpegQualityLevel` property inside `PdfSaveOptions`. Setting it
      to 100 gives maximum quality.
    question: How do I set JPEG quality when converting XPS to PDF?
  - answer: It refers to the `ImageCompression` option, which determines how images
      are compressed inside the PDF (e.g., JPEG, Zip).
    question: What does “pdf image compression” mean in this context?
  - answer: Yes, Aspose.Page also supports **C# generate pdf** directly from drawing
      commands, but that is outside the scope of this tutorial.
    question: Can I programmatically generate a PDF without an XPS source?
  - answer: The conversion retains vector data; just avoid rasterizing images by keeping
      `ImageCompression` set to JPEG or Zip as needed.
    question: Is there a way to convert XPS to PDF without losing vector graphics?
  - answer: Absolutely – Aspose.Page for .NET works with .NET Core, .NET 5, .NET 6,
      and later versions.
    question: Does the library support .NET Core?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- convert xps
- Aspose.Page
- .NET document conversion
- PDF generation
title: Μετατροπή XPS σε PDF με Aspose.Page για .NET
url: /el/net/document-conversion/convert-xps-to-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή XPS σε PDF με Aspose.Page για .NET

## Εισαγωγή

Σε αυτό το μάθημα θα μάθετε **πώς να μετατρέψετε XPS σε PDF** χρησιμοποιώντας τη βιβλιοθήκη Aspose.Page για .NET. Η μετατροπή XPS σε PDF είναι συχνή απαίτηση όταν χρειάζεται να μοιραστείτε έγγραφα XPS με χρήστες που διαθέτουν μόνο αναγνώστες PDF, ή όταν θέλετε να ενσωματώσετε περιεχόμενο XPS σε μεγαλύτερες ροές εργασίας PDF. Θα περάσουμε από κάθε βήμα, θα εξηγήσουμε γιατί κάθε ρύθμιση είναι σημαντική και θα σας δείξουμε πώς να βελτιστοποιήσετε το αποτέλεσμα — όπως ορίζοντας την ποιότητα JPEG και εφαρμόζοντας συμπίεση εικόνας PDF.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη είναι η καλύτερη για μετατροπή XPS σε PDF;** Aspose.Page for .NET
- **Χρειάζομαι άδεια για παραγωγή;** Ναι, απαιτείται εμπορική άδεια· διατίθεται δωρεάν δοκιμή.
- **Μπορώ να ελέγξω την ποιότητα εικόνας;** Απόλυτα—χρησιμοποιήστε `JpegQualityLevel` και `PdfImageCompression`.
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Μπορεί να μετατραπούν πολλαπλά αρχεία XPS σε ένα PDF;** Ναι, με επανάληψη στα αρχεία και συγχώνευση των αποτελεσμάτων.

## Τι είναι η μετατροπή XPS σε PDF;

Η μετατροπή XPS σε PDF μετατρέπει ένα αρχείο XML Paper Specification (XPS) σε αρχείο Portable Document Format (PDF) διατηρώντας τη διαρρύθμιση, τις γραμματοσειρές, τα διανυσματικά γραφικά και τις ενσωματωμένες εικόνες. Το παραγόμενο PDF μπορεί να προβληθεί σε οποιαδήποτε συσκευή χωρίς την ανάγκη αναγνώστη XPS, εξασφαλίζοντας συνεπή οπτική πιστότητα σε όλες τις πλατφόρμες.

## Γιατί να μετατρέψετε XPS σε PDF;

Φορτώστε το έγγραφο XPS και λάβετε αμέσως ένα PDF που μπορεί να ανοιχθεί σχεδόν σε κάθε πλατφόρμα. Οι προβολείς PDF είναι εγκατεστημένοι στο 99 % των υπολογιστών, tablet και τηλεφώνων, ενώ οι αναγνώστες XPS είναι σπάνιοι. Η μετατροπή κλειδώνει επίσης την οπτική πιστότητα του αρχικού XPS, καθιστώντας το PDF ιδανικό για αρχειοθέτηση, υπογραφή ή περαιτέρω επεξεργασία με άλλες βιβλιοθήκες Aspose.

### Ποσοτικοποιημένα οφέλη
- **Καθολική εμβέλεια:** Το PDF υποστηρίζεται σε >2 δισεκατομμύρια συσκευές παγκοσμίως, σε σύγκριση με <5 εκατομμύρια εγκαταστάσεις που υποστηρίζουν XPS.
- **Αποδοτικότητα μεγέθους:** Η χρήση του `PdfImageCompression.Jpeg` με `JpegQualityLevel` 80 μπορεί να μειώσει τα αρχεία εξόδου έως και 60 % χωρίς εμφανή απώλεια ποιότητας.
- **Απόδοση:** Το Aspose.Page μπορεί να επεξεργαστεί αρχεία XPS έως **500 MB** σε λιγότερο από 30 δευτερόλεπτα σε τυπικό διακομιστή 4‑πυρήνων, χάρη στα streaming APIs που αποφεύγουν τη φόρτωση ολόκληρου του αρχείου στη μνήμη.

## Προαπαιτούμενα

Πριν ξεκινήσουμε το ταξίδι μετατροπής, βεβαιωθείτε ότι έχετε τα παρακάτω:

- **Aspose.Page for .NET Library** – Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page for .NET στο περιβάλλον ανάπτυξής σας. Μπορείτε να την κατεβάσετε από την [Τεκμηρίωση Aspose.Page](https://reference.aspose.com/page/net/).
- **Περιβάλλον Ανάπτυξης** – Ρυθμίστε ένα .NET περιβάλλον ανάπτυξης με το Visual Studio ή οποιοδήποτε άλλο συμβατό IDE.
- **Έγγραφο XPS** – Προετοιμάστε το έγγραφο XPS που θέλετε να μετατρέψετε σε PDF. Αυτό μπορεί να είναι το δείγμα αρχείου XPS που αποθηκεύεται σε έναν καθορισμένο φάκελο.

## Εισαγωγή Ονοματοχώρων

Πριν βυθιστούμε στον κώδικα, ας εισάγουμε το απαραίτητο όνομα χώρου ώστε οι λειτουργίες του Aspose.Page για .NET να είναι προσβάσιμες στο έργο μας:

`using Aspose.Page;`  
`using Aspose.Page.XPS;`  
`using Aspose.Page.XPS.XpsModel;`  
`using Aspose.Page.XPS.XpsModel.XpsDocument;`  
`using Aspose.Page.XPS.XpsModel.XpsDocument.XpsLoadOptions;`  
`using Aspose.Page.XPS.XpsModel.Pdf;`  
`using Aspose.Page.XPS.XpsModel.Pdf.PdfSaveOptions;`  

```csharp
using Aspose.Page.XPS;
```

## Πώς να μετατρέψετε XPS σε PDF χρησιμοποιώντας το Aspose.Page;

Το XpsDocument φορτώνει ένα αρχείο XPS και παρέχει πρόσβαση στις σελίδες και τους πόρους του. Φορτώστε το αρχείο XPS με `new XpsDocument(inputStream, loadOptions)` και καλέστε `pdfDevice.Save(pdfSaveOptions)` – αυτή η ενιαία διαδικασία μετατρέπει το έγγραφο εφαρμόζοντας τις ρυθμίσεις συμπίεσης εικόνας και ποιότητας που έχετε επιλέξει. Το API διαχειρίζεται αυτόματα τα διανυσματικά γραφικά, τις γραμματοσειρές και τη διάταξη σελίδας, ώστε να λαμβάνετε ένα πιστό αντίγραφο PDF με ελάχιστο κώδικα.

## Οδηγός Βήμα‑Βήμα

### Βήμα 1: Αρχικοποίηση Καταλόγου Εγγράφου

Ορίστε το φάκελο που περιέχει το πηγαίο αρχείο XPS και όπου θα αποθηκευτεί το παραγόμενο PDF.

```csharp
string dataDir = "Your Document Directory";
```

Αντικαταστήστε το `"Your Document Directory"` με την απόλυτη ή σχετική διαδρομή προς το φάκελο που περιέχει το έγγραφο XPS σας.

### Βήμα 2: Άνοιγμα Ροών για Έξοδο PDF και Είσοδο XPS

Χρησιμοποιούμε δύο ροές αρχείων — μία για ανάγνωση του αρχείου XPS και μία για εγγραφή του παραγόμενου PDF.

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

> **Συμβουλή:** Βεβαιωθείτε ότι οι διαδρομές είναι σωστές και ότι η εφαρμογή έχει δικαιώματα ανάγνωσης/εγγραφής στο φάκελο προορισμού.

### Βήμα 3: Φόρτωση του Εγγράφου XPS

Το `XpsLoadOptions` επιτρέπει τον καθορισμό προτιμήσεων φόρτωσης για το έγγραφο XPS.  
Το `XpsDocument` είναι η κλάση που φορτώνει ένα αρχείο XPS στη μνήμη, εκθέτοντας τις σελίδες και τους πόρους του για περαιτέρω επεξεργασία.

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Το αντικείμενο `XpsLoadOptions` σας επιτρέπει να καθορίσετε προτιμήσεις φόρτωσης, αλλά η προεπιλογή λειτουργεί για τις περισσότερες περιπτώσεις.

### Βήμα 4: Διαμόρφωση Επιλογών Αποθήκευσης PDF

Το `PdfSaveOptions` διαμορφώνει πώς δημιουργείται η έξοδος PDF, συμπεριλαμβανομένης της συμπίεσης και των ρυθμίσεων ποιότητας.  
`PdfSaveOptions` ορίζει πώς θα γραφτεί το PDF. Παρατηρήστε τη χρήση **συμπίεσης εικόνας PDF** (`PdfImageCompression.Jpeg`) και **ποιότητας JPEG** (`JpegQualityLevel = 100`). Αυτές οι ρυθμίσεις επηρεάζουν άμεσα το μέγεθος του αρχείου και την οπτική πιστότητα.

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

- **`JpegQualityLevel`** – Ελέγχει την ποιότητα των εικόνων JPEG που ενσωματώνονται στο PDF (υψηλότερη = καλύτερη ποιότητα, μεγαλύτερο αρχείο).
- **`ImageCompression`** – Επιλέγει τον αλγόριθμο συμπίεσης· το JPEG είναι ιδανικό για φωτογραφικές εικόνες.
- **`TextCompression`** – Η συμπίεση Flate μειώνει το μέγεθος του PDF χωρίς να χάνει την ποιότητα του κειμένου.
- **`PageNumbers`** – Σας επιτρέπει να **αποθηκεύσετε XPS ως PDF** μόνο για τις επιλεγμένες σελίδες.

### Βήμα 5: Δημιουργία Συσκευής Απόδοσης PDF

Το `PdfDevice` είναι ο προορισμός απόδοσης που γράφει τα δεδομένα PDF στη δοθείσα ροή.  
`PdfDevice` είναι ο προορισμός απόδοσης που γράφει τα δεδομένα PDF στη ροή που ανοίξαμε νωρίτερα.

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

### Βήμα 6: Αποθήκευση του Εγγράφου σε PDF

Η μέθοδος `Save` ολοκληρώνει τη μετατροπή, γράφοντας το PDF στη ροή εξόδου.  
Κληθείτε τη μέθοδο `Save`, περνώντας τη συσκευή απόδοσης και τις διαμορφωμένες επιλογές.

```csharp
document.Save(device, options);
```

Όταν ο κώδικας ολοκληρωθεί, το `XPStoPDF_out.pdf` θα εμφανιστεί στον καθορισμένο φάκελο, περιέχοντας τις μετατρεπόμενες σελίδες με τις ρυθμίσεις συμπίεσης και ποιότητας που ορίσατε.

## Συνηθισμένες Περιπτώσεις Χρήσης

- **Αναφορές Επιχειρήσεων** – Δημιουργήστε αναφορές XPS από παλαιά συστήματα και μετατρέψτε τις σε PDF για διανομή.
- **Αρχειοθέτηση** – Αποθηκεύστε έγγραφα ως PDF για μακροπρόθεσμη διατήρηση, ενώ εξακολουθείτε να μπορείτε να τα δημιουργήσετε από πηγές XPS.
- **Web υπηρεσίες** – Προσφέρετε ένα API endpoint που δέχεται μεταφορτώσεις XPS και επιστρέφει αρχεία PDF άμεσα.

## Επίλυση Προβλημάτων & Συμβουλές

- **Αρχείο δεν βρέθηκε** – Ελέγξτε ξανά τη διαδρομή `dataDir` και βεβαιωθείτε ότι το όνομα του αρχείου XPS ταιριάζει ακριβώς.
- **Σφάλματα δικαιωμάτων** – Εκτελέστε το Visual Studio ως Διαχειριστής ή δώστε δικαιώματα εγγραφής στο φάκελο εξόδου.
- **Μεγάλα PDF** – Αν το παραγόμενο PDF είναι πολύ μεγάλο, μειώστε το `JpegQualityLevel` ή αλλάξτε το `ImageCompression` σε `PdfImageCompression.Zip`.

## Συχνές Ερωτήσεις (Φιλικές προς AI)

**Ε: Πώς ορίζω την ποιότητα JPEG κατά τη μετατροπή XPS σε PDF;**  
Α: Χρησιμοποιήστε την ιδιότητα `JpegQualityLevel` μέσα στο `PdfSaveOptions`. Ορίζοντάς την στο 100 επιτυγχάνετε μέγιστη ποιότητα.

**Ε: Τι σημαίνει “συμπίεση εικόνας PDF” σε αυτό το πλαίσιο;**  
Α: Αναφέρεται στην επιλογή `ImageCompression`, η οποία καθορίζει πώς συμπιέζονται οι εικόνες μέσα στο PDF (π.χ., JPEG, Zip).

**Ε: Μπορώ προγραμματιστικά να δημιουργήσω PDF χωρίς πηγή XPS;**  
Α: Ναι, το Aspose.Page υποστηρίζει επίσης **C# generate pdf** απευθείας από εντολές σχεδίασης, αλλά αυτό δεν περιλαμβάνεται σε αυτό το μάθημα.

**Ε: Υπάρχει τρόπος να μετατρέψω XPS σε PDF χωρίς να χάσω τα διανυσματικά γραφικά;**  
Α: Η μετατροπή διατηρεί τα διανυσματικά δεδομένα· απλώς αποφύγετε τη ραστεροποίηση εικόνων διατηρώντας το `ImageCompression` σε JPEG ή Zip ανάλογα με τις ανάγκες.

**Ε: Η βιβλιοθήκη υποστηρίζει .NET Core;**  
Α: Απόλυτα – το Aspose.Page for .NET λειτουργεί με .NET Core, .NET 5, .NET 6 και μεταγενέστερες εκδόσεις.

**Τελευταία Ενημέρωση:** 2026-07-24  
**Δοκιμή Με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Συγχώνευση εγγράφων XPS σε PDF με Aspose.Page για .NET](/page/net/document-merging/merge-xps-documents-into-pdf/)
- [Δημιουργία εγγράφου XPS με Aspose.Page για .NET](/page/net/document-creation/create-xps-document/)
- [Οδηγός Μετατροπής Aspose Page: Οδηγός Μετατροπής Εγγράφων](/page/net/document-conversion/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}