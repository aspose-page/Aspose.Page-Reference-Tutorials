---
date: 2026-01-20
description: Προσθέστε αβίαστα αριθμούς σελίδων σε PDF ενώ συγχωνεύετε έγγραφα XPS
  σε PDF υψηλής ποιότητας χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε τον
  βήμα‑βήμα οδηγό μας για τη μετατροπή XPS σε PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Προσθήκη αριθμών σελίδων PDF – Συγχώνευση XPS σε PDF χρησιμοποιώντας το Aspose.Page
url: /el/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Αριθμών Σελίδων PDF – Συγχώνευση XPS σε PDF με Aspose.Page

## Εισαγωγή

## Γρήγορες Απαντήσεις
- **Μπορώ να προσθέσω αριθμούς σελίδων κατά τη συγχώνευση XPS σε PDF;** Ναι – η ιδιότητα `PdfSaveOptions.PageNumbers` κάνει ακριβώς αυτό.  
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή;** Aspose.Page for .NET.  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται έγκυρη άδεια Aspose.Page· διατίθεται προσωρινή άδεια για δοκιμές.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+ και .NET 5/6+.  
- **Είναι δυνατή η εξαγωγή εικόνων υψηλής ποιότητας;** Απόλυτα – ορίστε `JpegQualityLevel` στο 100 και επιλέξτε `PdfImageCompression.Jpeg`.

## Προαπαιτούμενα

Πριν ξεκινήσετε το tutorial, βεβαιωθείτε ότι έχετε τα παρακάτω προαπαιτούμενα:

- Aspose.Page for .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page. Μπορείτε να την κατεβάσετε από [here](https://releases.aspose.com/page/net/).
- Αρχεία Εγγράφου: Έχετε το XPS έγγραφο (`input.xps`) έτοιμο στον καθορισμένο φάκελό σας.

## Εισαγωγή Ονομάτων Χώρων

Στο .NET project σας, συμπεριλάβετε τα απαραίτητα namespaces για εργασία με Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Αυτό το βήμα διασφαλίζει ότι έχετε πρόσβαση στις κλάσεις και τις μεθόδους που απαιτούνται για τη μετατροπή του εγγράφου.

## Πώς να προσθέσετε αριθμούς σελίδων PDF κατά τη συγχώνευση εγγράφων XPS

Η συλλογή `PdfSaveOptions.PageNumbers` σας επιτρέπει να καθορίσετε ακριβώς ποιες σελίδες (ή περιοχές σελίδων) πρέπει να εμφανιστούν στο τελικό PDF. Συμπληρώνοντας την με τους αριθμούς σελίδων που επιθυμείτε, το Aspose.Page εισάγει αυτόματα τη σωστή αρίθμηση.

### Βήμα 1: Αρχικοποίηση Ροών

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Αυτό το βήμα περιλαμβάνει τη ρύθμιση των ροών εισόδου και εξόδου για τα αρχεία XPS και PDF. Βεβαιωθείτε ότι χρησιμοποιούνται οι σωστές διαδρομές και ονόματα αρχείων.

### Βήμα 2: Φόρτωση Εγγράφου XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Εδώ, φορτώνουμε το έγγραφο XPS στο αντικείμενο `XpsDocument`, προετοιμάζοντάς το για περαιτέρω επεξεργασία.

### Βήμα 3: Αρχικοποίηση Επιλογών Αποθήκευσης (συγχώνευση xps σε pdf)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Προσαρμόστε το αντικείμενο `PdfSaveOptions` σύμφωνα με τις προτιμήσεις σας, καθορίζοντας παραμέτρους όπως συμπίεση εικόνας, συμπίεση κειμένου και τους **αριθμούς σελίδων** που θέλετε να εμφανίζονται στο τελικό PDF. Ορίζοντας το `JpegQualityLevel` στο 100 εξασφαλίζει **εικόνες PDF υψηλής ποιότητας**.

### Βήμα 4: Δημιουργία Συσκευής Απόδοσης

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

Η `PdfDevice` είναι το εργαλείο που είναι υπεύθυνο για την απόδοση του εγγράφου XPS σε μορφή PDF.

### Βήμα 5: Αποθήκευση Εγγράφου (c# xps σε pdf)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Τέλος, αποθηκεύστε το έγγραφο χρησιμοποιώντας τη συσκευή απόδοσης και τις καθορισμένες επιλογές. Το παραγόμενο PDF θα περιέχει τις επιλεγμένες σελίδες με αυτόματα προστιθέμενους αριθμούς σελίδων.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για αυτή τη μετατροπή;

- **Αξιοπιστία** – Διαχειρίζεται σύνθετες δυνατότητες XPS χωρίς απώλεια πιστότητας.  
- **Απόδοση** – Η επεξεργασία με ροές αποφεύγει τη φόρτωση ολόκληρων αρχείων στη μνήμη.  
- **Ευελιξία** – Λεπτομερής έλεγχος της ποιότητας εικόνας, της συμπίεσης και της αρίθμησης σελίδων.  
- **Διαπλατφορμική** – Λειτουργεί σε Windows, Linux και macOS με .NET Core.

## Συνηθισμένα Προβλήματα και Λύσεις

| Πρόβλημα | Λύση |
|----------|------|
| **Το PDF εξόδου είναι κενό** | Επιβεβαιώστε ότι η διαδρομή του αρχείου XPS είναι σωστή και ότι το αρχείο δεν είναι κατεστραμμένο. |
| **Οι αριθμοί σελίδων δεν εμφανίζονται** | Βεβαιωθείτε ότι το `PageNumbers` έχει οριστεί στα σωστά μηδενικά (zero‑based) ευρετήρια σελίδων (π.χ., `new int[] {1,2,6}`). |
| **Εικόνες χαμηλής ποιότητας** | Αυξήστε το `JpegQualityLevel` και επιλέξτε `PdfImageCompression.Jpeg`. |
| **Μεγάλα αρχεία XPS προκαλούν πίεση μνήμης** | Επεξεργαστείτε το XPS σε μικρότερα τμήματα ή αυξήστε το όριο μνήμης της εφαρμογής. |

## Συχνές Ερωτήσεις

### Ε1: Μπορώ να συγχωνεύσω πολλά αρχεία XPS σε ένα ενιαίο PDF;

A1: Ναι, μπορείτε. Απλώς προσαρμόστε την παράμετρο `PageNumbers` στο `PdfSaveOptions` ώστε να περιλαμβάνει τις επιθυμητές σελίδες από διαφορετικά αρχεία XPS, ή φορτώστε κάθε XPS διαδοχικά και καλέστε `document.Save` στην ίδια `PdfDevice`.

### Ε2: Διατίθεται προσωρινή άδεια για το Aspose.Page for .NET;

A2: Ναι, μπορείτε να αποκτήσετε μια προσωρινή άδεια [here](https://purchase.aspose.com/temporary-license/) για δοκιμαστικούς σκοπούς.

### Ε3: Υπάρχουν περιορισμοί στο μέγεθος αρχείου κατά τη χρήση του Aspose.Page για μετατροπή εγγράφων;

A3: Το Aspose.Page for .NET δεν επιβάλλει αυστηρούς περιορισμούς στο μέγεθος των αρχείων, αλλά η βέλτιστη απόδοση επιτυγχάνεται με αρχεία λογικού μεγέθους. Για πολύ μεγάλα έγγραφα XPS, σκεφτείτε την επεξεργασία τους σε ροές για μείωση της κατανάλωσης μνήμης.

### Ε4: Μπορώ να προσαρμόσω περαιτέρω το παραγόμενο PDF, π.χ. προσθέτοντας υδατογραφήματα ή σημειώσεις;

A4: Ναι, το Aspose.Page for .NET παρέχει εκτενείς δυνατότητες διαχείρισης PDF. Μετά τη μετατροπή, μπορείτε να χρησιμοποιήσετε τη βιβλιοθήκη Aspose.PDF για να προσθέσετε υδατογραφήματα, σημειώσεις ή άλλες βελτιώσεις.

### Ε5: Υποστηρίζει το Aspose.Page for .NET ανάπτυξη διαπλατφορμικά;

A5: Ναι, το Aspose.Page for .NET έχει σχεδιαστεί ώστε να λειτουργεί απρόσκοπτα σε διάφορες πλατφόρμες, συμπεριλαμβανομένων των Windows, Linux και macOS, όταν χρησιμοποιείται με .NET Core ή .NET 5/6.

---

**Τελευταία Ενημέρωση:** 2026-01-20  
**Δοκιμάστηκε Με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}