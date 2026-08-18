---
date: 2026-02-23
description: Μάθετε πώς να προσθέτετε διαβάθμιση σε αρχεία PostScript, να αποθηκεύετε
  αρχείο PostScript με μέγεθος σελίδας A4 και να γεμίζετε ορθογώνιο με διαβάθμιση
  χρησιμοποιώντας το Aspose.Page για .NET.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Πώς να προσθέσετε διαβάθμιση – Διαγώνια διαβάθμιση σε PostScript (PS) με το
  Aspose.Page .NET
url: /el/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Διαβάθμιση: Διαγώνια Διαβάθμιση σε PostScript (PS) με Aspose.Page .NET

## Εισαγωγή

Η προσθήκη μιας διαγώνιας διαβάθμισης σε ένα έγγραφο PostScript (PS) μπορεί να βελτιώσει δραματικά την οπτική ελκυστικότητα, ειδικά όταν χρειάζεστε **how to add gradient** εφέ σε τεχνικές αναφορές, φυλλάδια ή εφαρμογές με έντονη γραφική απεικόνιση. Σε αυτό το tutorial θα δείτε ακριβώς πώς να προσθέσετε διαβάθμιση σε ένα αρχείο PostScript, να ορίσετε μέγεθος σελίδας A4 και να γεμίσετε ένα ορθογώνιο με ομαλή μετάβαση χρώματος χρησιμοποιώντας το Aspose.Page για .NET.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page for .NET  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **Μπορώ να αλλάξω την κατεύθυνση της διαβάθμισης;** Ναι – περιστρέψτε το μετασχηματισμό του πινέλου όπως φαίνεται στον κώδικα  
- **Πώς αποθηκεύω το αποτέλεσμα;** Χρησιμοποιήστε `PsDocument.Save()` που γράφει ένα αρχείο PostScript στο δίσκο  
- **Απαιτείται άδεια για παραγωγή;** Ναι, μια εμπορική άδεια ξεκλειδώνει πλήρη λειτουργικότητα  

## Τι είναι μια διαγώνια διαβάθμιση στο PostScript;

Μια διαγώνια διαβάθμιση είναι μια γραμμική μετάβαση χρώματος που τρέχει υπό γωνία (συνήθως 45°) μέσα από ένα σχήμα. Στο PostScript, αυτό επιτυγχάνεται εφαρμόζοντας ένα `LinearGradientBrush` με προσαρμοσμένο πίνακα μετασχηματισμού που περιστρέφει, κλιμακώνει και μετατοπίζει τη διαβάθμιση ώστε να ταιριάζει με το επιθυμητό ορθογώνιο.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για γεμίσματα διαβάθμισης;

Το Aspose.Page αφαιρεί την ανάγκη για χαμηλού επιπέδου εντολές PostScript, επιτρέποντάς σας να εργάζεστε με γνωστά αντικείμενα γραφικών .NET. Μπορείτε να δημιουργήσετε σύνθετα γεμίσματα, να ορίσετε διαστάσεις σελίδας και να εξάγετε απευθείας σε **save PostScript file** χωρίς να ασχοληθείτε με ακατέργαστη σύνταξη PS.

## Προαπαιτούμενα

- **Aspose.Page for .NET Library** – κατεβάστε το [εδώ](https://releases.aspose.com/page/net/).  
- **Document Directory** – ένας φάκελος όπου θα γραφτεί το παραγόμενο αρχείο `*.ps`.

Τώρα που καλύψαμε τα βασικά, ας προχωρήσουμε στην υλοποίηση βήμα προς βήμα.

## Εισαγωγή Ονομάτων Χώρων

Πρώτα, εισάγετε τα ονόματα χώρων που σας δίνουν πρόσβαση στη συσκευή EPS, τα βοηθητικά εργαλεία σχεδίασης και τις κλάσεις I/O.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Βήμα 1: Δημιουργία Ροής Εξόδου για Έγγραφο PostScript (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Βήμα 2: Ορισμός Μεγέθους Σελίδας A4 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Βήμα 3: Δημιουργία Νέου 1‑Σελίδας PS Εγγράφου

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Βήμα 4: Ορισμός Παραμέτρων Ορθογωνίου

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Βήμα 5: Δημιουργία Διαδρομής Γραφικών

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Βήμα 6: Δημιουργία Πινέλου Γραμμικής Διαβάθμισης (Fill Rectangle Gradient)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Βήμα 7: Δημιουργία Μετασχηματισμού για το Πινέλο

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Βήμα 8: Εφαρμογή Μετασχηματισμών στο Πινέλο (Rotate, Scale, Translate)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Βήμα 9: Ορισμός Μετασχηματισμού στο Πινέλο

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Βήμα 10: Ορισμός Χρώματος και Γέμισμα του Ορθογωνίου

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Βήμα 11: Κλείσιμο Τρέχουσας Σελίδας

```csharp
	//Close current page
	document.ClosePage();
```

## Βήμα 12: Αποθήκευση Εγγράφου (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## Πώς να Αποθηκεύσετε Αρχείο PostScript

Η κλήση `PsDocument.Save()` γράφει το πλήρως διαμορφωμένο περιεχόμενο PostScript στη ροή που ανοίξατε στο **Step 1**. Μετά την ολοκλήρωση του μπλοκ `using`, το αρχείο `DiagonaGradient_outPS.ps` θα είναι διαθέσιμο στον φάκελο που καθορίσατε.

## Συνηθισμένες Περιπτώσεις Χρήσης

- **Τεχνική τεκμηρίωση** που χρειάζεται ήπια σκίαση φόντου.  
- **Φυλλάδια μάρκετινγκ** όπου μια διαγώνια διαβάθμιση προσθέτει μοντέρνα εμφάνιση.  
- **Αυτοματοποιημένοι δημιουργοί αναφορών** που παράγουν εκτυπώσιμα αρχεία PS άμεσα.

## Αντιμετώπιση Προβλημάτων & Συμβουλές

- **Λανθασμένα χρώματα** – ελέγξτε ξανά τις τιμές ARGB που περνιούνται στο `LinearGradientBrush`.  
- **Η διαβάθμιση δεν είναι ορατή** – βεβαιωθείτε ότι ο πίνακας μετασχηματισμού περιστρέφει και κλιμακώνει σωστά· η κλήση `Rotate(-45)` ορίζει τη διαγώνια γωνία.  
- **Το αρχείο δεν δημιουργείται** – επαληθεύστε ότι το `dataDir` δείχνει σε υπάρχον φάκελο και ότι η εφαρμογή έχει δικαιώματα εγγραφής.

## Συχνές Ερωτήσεις

**Ε: Είναι το Aspose.Page συμβατό με όλα τα .NET frameworks;**  
Α: Το Aspose.Page υποστηρίζει ένα ευρύ φάσμα εκδόσεων .NET, από .NET Framework 4.5+ έως .NET 6+, εξασφαλίζοντας ευρεία συμβατότητα.

**Ε: Μπορώ να προσαρμόσω τα χρώματα της διαβάθμισης στο Aspose.Page;**  
Α: Ναι, μπορείτε να καθορίσετε οποιαδήποτε χρώματα ARGB κατά τη δημιουργία του `LinearGradientBrush`, δίνοντάς σας πλήρη έλεγχο πάνω στις αρχικές και τελικές αποχρώσεις.

**Ε: Υπάρχει δοκιμαστική έκδοση του Aspose.Page;**  
Α: Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Page κατεβάζοντας τη δοκιμαστική έκδοση [εδώ](https://releases.aspose.com/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Page;**  
Α: Αποκτήστε προσωρινή άδεια για το Aspose.Page [εδώ](https://purchase.aspose.com/temporary-license/) για να ξεκλειδώσετε πρόσθετες δυνατότητες κατά τη διάρκεια της αξιολόγησης.

**Ε: Πού μπορώ να βρω υποστήριξη κοινότητας για το Aspose.Page;**  
Α: Συμμετέχετε στην κοινότητα του Aspose.Page στο [φόρουμ](https://forum.aspose.com/c/page/39) για βοήθεια και συζητήσεις.

---

**Τελευταία ενημέρωση:** 2026-02-23  
**Δοκιμάστηκε με:** Aspose.Page for .NET (τελευταία σταθερή έκδοση)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}