---
date: 2026-02-25
description: Βελτιώστε τα έγγραφα PostScript με ένα ορθογώνιο γραμμικού διαβάθμισης
  χρησιμοποιώντας το Aspose.Page για .NET. Ακολουθήστε τον βήμα‑βήμα οδηγό μας για
  να μάθετε τη γεμιστική διαβάθμιση κειμένου και τη διαβάθμιση περιγράμματος κειμένου.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Προσθήκη ορθογωνίου με γραμμική διαβάθμιση στο PostScript (PS) με το Aspose.Page
url: /el/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

;"

Answer translate, keep link.

Q5: "Where can I find community support?" -> "Πού μπορώ να βρω υποστήριξη από την κοινότητα;"

Answer translate, keep link.

Then footer:

**Last Updated:** 2026-02-25 (keep date)

**Tested With:** Aspose.Page 24.10 for .NET (keep)

**Author:** Aspose (keep)

Then closing shortcodes.

Finally backtop button shortcode.

Make sure to keep all markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Ορθογωνίου Γραμμικής Διαβάθμισης σε PostScript (PS) με το Aspose.Page

## Εισαγωγή

Καλώς ήρθατε σε αυτό το ολοκληρωμένο tutorial για την προσθήκη ενός **ορθογωνίου γραμμικής διαβάθμισης** σε έγγραφα PostScript (PS) χρησιμοποιώντας το Aspose.Page για .NET. Το Aspose.Page είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να δημιουργείτε, να τροποποιείτε και να αποδίδετε έγγραφα σε ποικίλες μορφές, και σήμερα θα εστιάσουμε στο πώς να φέρετε εντυπωσιακές διαβάθμιση στα αρχεία PS σας.

### Γρήγορες Απαντήσεις
- **Τι κάνει το ορθογώνιο γραμμικής διαβάθμισης;** Γεμίζει μια ορθογώνια περιοχή με ομαλή μετάβαση χρώματος από τη μία πλευρά στην άλλη.  
- **Ποιο API διαχειρίζεται το κείμενο με γέμισμα διαβάθμισης;** `LinearGradientBrush` σε συνδυασμό με `SetPaint` και `FillAndStrokeText`.  
- **Μπορώ να περιγράψω κείμενο με διαβάθμιση;** Ναι—χρησιμοποιήστε `SetStroke` με πινέλο διαβάθμισης και καλέστε `OutlineText`.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια Aspose.Page για μη‑αξιολογική χρήση.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

- Aspose.Page for .NET Library: Βεβαιωθείτε ότι η βιβλιοθήκη είναι αναφορά στο έργο σας. Μπορείτε να τη κατεβάσετε από την [τεκμηρίωση Aspose.Page για .NET](https://reference.aspose.com/page/net/).
- Document Directory: Δημιουργήστε έναν φάκελο στο δίσκο όπου θα αποθηκευτεί το παραγόμενο αρχείο PS και αντικαταστήστε το **«Your Document Directory»** στον κώδικα με αυτή τη διαδρομή.

## Εισαγωγή Χώρων Ονομάτων

Για να ξεκινήσετε, εισάγετε τους χώρους ονομάτων που σας δίνουν πρόσβαση στις κλάσεις σχεδίασης και ειδικές για PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Τι είναι ένα Ορθογώνιο Γραμμικής Διαβάθμισης;

Ένα **ορθογώνιο γραμμικής διαβάθμισης** είναι απλώς ένα ορθογώνιο σχήμα του οποίου το εσωτερικό βαφτίζεται με γραμμική διαβάθμιση—τα χρώματα μεταβαίνουν ομαλά κατά μήκος μιας ευθείας γραμμής, συνήθως από αριστερά προς δεξιά (οριζόντια) ή από πάνω προς τα κάτω (κάθετη). Στο Aspose.Page το επιτυγχάνετε συνδυάζοντας ένα `GraphicsPath` που ορίζει το ορθογώνιο με ένα `LinearGradientBrush` που περιγράφει τη μετάβαση χρώματος.

## Γιατί να Χρησιμοποιήσετε Γέμισμα Κειμένου με Διαβάθμιση και Διαβάθμιση Περιγράμματος Κειμένου;

- **Οπτική Έλξη:** Το κείμενο γεμάτο διαβάθμιση προσθέτει βάθος και σύγχρονο στυλ σε αναφορές, τιμολόγια ή προωθητικό υλικό.  
- **Συνεπής Επωνυμία:** Ταιριάξτε τα εταιρικά χρώματα με ακριβείς τιμές ARGB.  
- **Πολυμορφία:** Το ίδιο πινέλο μπορεί να επαναχρησιμοποιηθεί για γέμισμα σχημάτων, γέμισμα κειμένου και διαβάθμιση περιγράμματος, μειώνοντας την επανάληψη κώδικα.

## Βήμα 1: Ρύθμιση του Εγγράφου

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Βήμα 2: Ορισμός Ορθογωνίου Διαβάθμισης και Χρωμάτων

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Βήμα 3: Ορισμός Μετασχηματισμού για το Πινέλο

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Βήμα 4: Ορισμός Paint και Γέμισμα του Ορθογωνίου

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Πώς να Εφαρμόσετε Γέμισμα Κειμένου με Διαβάθμιση

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Χρήση Διαβάθμισης Περιγράμματος Κειμένου

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Βήμα 7: Κλείσιμο της Τρέχουσας Σελίδας και Αποθήκευση του Εγγράφου

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Συγχαρητήρια! Προσθέσατε με επιτυχία ένα **ορθογώνιο γραμμικής διαβάθμισης** σε ένα έγγραφο PostScript και χρησιμοποιήσατε το ίδιο πινέλο για **γέμισμα κειμένου με διαβάθμιση** και **διαβάθμιση περιγράμματος κειμένου**.

## Συνηθισμένες Περιπτώσεις Χρήσης & Συμβουλές

- **Κεφαλίδες Αναφορών:** Γεμίστε μεγάλα τμήματα κειμένου με διαβάθμιση για να τονίσετε τίτλους ενοτήτων.  
- **Λογότυπα Εταιρείας:** Αναδημιουργήστε σχήματα λογοτύπων με γεμιστά διαβάθμιση σχήματα για συνεπή επωνυμία.  
- **Pro Tip:** Επαναχρησιμοποιήστε το ίδιο αντικείμενο `LinearGradientBrush` για πολλαπλές κλήσεις σχεδίασης ώστε τα χρώματα να παραμένουν τέλεια ευθυγραμμισμένα μεταξύ σχημάτων και κειμένου.

## Συχνές Ερωτήσεις

### Q1: Μπορώ να εφαρμόσω διαβάθμιση σε άλλα σχήματα εκτός από ορθογώνια;
**A:** Ναι, μπορείτε να εφαρμόσετε διαβάθμιση σε οποιοδήποτε σχήμα ορίζεται από ένα `GraphicsPath`. Απλώς προσθέστε κύκλους, πολύγωνα ή προσαρμοσμένες διαδρομές πριν καλέσετε `document.Fill(path)`.

### Q2: Πώς μπορώ να αλλάξω τα χρώματα της διαβάθμισης;
**A:** Τροποποιήστε τις τιμές `Color.FromArgb` κατά την κατασκευή του `LinearGradientBrush`. Το πρώτο χρώμα είναι το αρχικό, το δεύτερο είναι το τελικό της διαβάθμισης.

### Q3: Είναι το Aspose.Page συμβατό με διαφορετικές μορφές εγγράφων;
**A:** Απόλυτα. Το Aspose.Page υποστηρίζει XPS, PS, PDF και αρκετές άλλες διανυσματικές μορφές. Ελέγξτε την επίσημη τεκμηρίωση για την πλήρη λίστα.

### Q4: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;
**A:** Ναι, η εμπορική άδεια είναι διαθέσιμη. Δείτε τη σελίδα αγοράς για λεπτομέρειες: [here](https://purchase.aspose.com/buy).

### Q5: Πού μπορώ να βρω υποστήριξη από την κοινότητα;
**A:** Συμμετέχετε στο φόρουμ κοινότητας Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}