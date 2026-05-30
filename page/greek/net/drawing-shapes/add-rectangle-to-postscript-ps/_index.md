---
date: 2026-01-18
description: Μάθετε πώς να δημιουργείτε έγγραφο PostScript .NET και να προσθέτετε
  ορθογώνια χρησιμοποιώντας το Aspose.Page για .NET. Οδηγός βήμα‑βήμα με παραδείγματα
  κώδικα.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Δημιουργία εγγράφου PostScript .NET – Προσθήκη ορθογωνίου με Aspose.Page
url: /el/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Ορθογωνίου στο PostScript (PS) με Aspose.Page για .NET

## Εισαγωγή

Αν ψάχνετε να **create postscript document .net**, το Aspose.Page παρέχει μια ισχυρή λύση για τη διαχείριση αρχείων PostScript. Σε αυτό το tutorial, θα σας καθοδηγήσουμε στη προσθήκη ορθογωνίων σε ένα έγγραφο PostScript χρησιμοποιώντας το Aspose.Page για .NET, παρέχοντάς σας μια σταθερή βάση για πιο πλούσια δημιουργία γραφικών.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρειάζομαι;** Aspose.Page for .NET.
- **Μπορώ να δημιουργήσω ένα έγγραφο PostScript από το μηδέν;** Ναι – το API σας επιτρέπει να δημιουργήσετε αρχεία PS προγραμματιστικά.
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Χρειάζεται άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται άδεια για παραγωγή.
- **Πόσο διαρκεί η υλοποίηση;** Συνήθως κάτω από 10 λεπτά για βασικά σχήματα.

## Τι είναι η δημιουργία εγγράφου postscript .net;
Η δημιουργία ενός εγγράφου PostScript σε .NET σημαίνει την προγραμματιστική παραγωγή ενός αρχείου .ps που περιγράφει το περιεχόμενο της σελίδας—κείμενο, γραφικά ή σχήματα—χρησιμοποιώντας το API του Aspose.Page. Αυτή η προσέγγιση είναι ιδανική για δημιουργία γραφικών στο διακομιστή, αυτοματοποιημένη δημιουργία αναφορών ή οποιοδήποτε σενάριο που απαιτεί ακριβή έλεγχο του μορφότυπου εξόδου.

## Γιατί να χρησιμοποιήσετε το Aspose.Page για .NET;
- **Πλήρης έλεγχος των γραφικών** – σχεδιάστε σχήματα, ορίστε χρώματα και εφαρμόστε περιγράμματα χωρίς να ασχοληθείτε με τη χαμηλού επιπέδου σύνταξη PS.
- **Διασυνοριακό** – λειτουργεί σε Windows, Linux και macOS.
- **Χωρίς εξωτερικές εξαρτήσεις** – η βιβλιοθήκη διαχειρίζεται όλη τη δημιουργία PS εσωτερικά.
- **Πλούσια τεκμηρίωση & παραδείγματα** – ξεκινήστε γρήγορα.

## Προαπαιτούμενα

- **Aspose.Page for .NET Library** – κατεβάστε και εγκαταστήστε από [here](https://releases.aspose.com/page/net/).
- **Περιβάλλον Ανάπτυξης** – Visual Studio, VS Code ή οποιοδήποτε IDE συμβατό με .NET.

## Εισαγωγή Namespaces

Πριν ξεκινήσετε τον κώδικα, εισάγετε τους χώρους ονομάτων που εκθέτουν τις απαιτούμενες κλάσεις:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Τώρα ας χωρίσουμε το παράδειγμα σε σαφή, αριθμημένα βήματα.

## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφου σας

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Αντικαταστήστε `"Your Document Directory"` με το φάκελο όπου θέλετε να αποθηκευτεί το παραγόμενο αρχείο PS.

## Βήμα 2: Δημιουργήστε Ροή Εξόδου για το Έγγραφο PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Αυτή η ροή δείχνει στο **AddRectangle_outPS.ps**. Μπορείτε να μετονομάσετε το αρχείο ή να αλλάξετε την τοποθεσία όπως χρειάζεται.

## Βήμα 3: Ορίστε Επιλογές Αποθήκευσης και Δημιουργήστε το Έγγραφο PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Εδώ λέμε στο Aspose.Page να χρησιμοποιήσει μέγεθος σελίδας A4 και να δημιουργήσει ένα έγγραφο μονής σελίδας.

## Βήμα 4: Προσθέστε Ένα Γεμισμένο Ορθογώνιο

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Ορίζουμε ένα ορθογώνιο στο (250, 100) με πλάτος 150 και ύψος 100, ορίζουμε μια πορτοκαλί πινέλο και γεμίζουμε το σχήμα.

## Βήμα 5: Προσθέστε Ένα Περιγραμμισμένο Ορθογώνιο

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Δημιουργείται ένα δεύτερο ορθογώνιο χαμηλότερα στη σελίδα, αυτή τη φορά με κόκκινο περίγραμμα 3 σημείων.

## Βήμα 6: Κλείστε τη Σελίδα και Αποθηκεύστε το Έγγραφο

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Το κλείσιμο της σελίδας ολοκληρώνει το σχέδιο, και η μέθοδος `Save()` γράφει το αρχείο PS στο δίσκο.

## Συχνά Προβλήματα & Συμβουλές

- **Λανθασμένη διαδρομή αρχείου** – Βεβαιωθείτε ότι το `dataDir` τελειώνει με διαχωριστικό διαδρομής (`\\` ή `/`) ή χρησιμοποιήστε `Path.Combine`.
- **Έλλειψη άδειας** – Σε περιβάλλον παραγωγής, εφαρμόστε την άδεια Aspose πριν δημιουργήσετε το έγγραφο για να αποφύγετε υδατογραφήματα αξιολόγησης.
- **Ορατότητα χρώματος** – Αν το ορθογώνιο εμφανίζεται κενό, ελέγξτε ότι τα χρώματα του πινέλου ή του στυλό αντιτίθενται στο φόντο της σελίδας.

## Συχνές Ερωτήσεις

**Q:** Μπορώ να προσαρμόσω τα χρώματα των ορθογωνίων;  
**A:** Απόλυτα. Αλλάξτε τις τιμές `Color.Orange` ή `Color.Red` στους κατασκευαστές `SolidBrush` και `Pen` σε οποιοδήποτε `System.Drawing.Color` προτιμάτε.

**Q:** Είναι το Aspose.Page συμβατό με άλλες μορφές εγγράφων;  
**A:** Ναι. Εκτός από PostScript, το Aspose.Page υποστηρίζει επίσης δημιουργία XPS και EPS.

**Q:** Πώς μπορώ να προσθέσω κείμενο στο ίδιο έγγραφο;  
**A:** Χρησιμοποιήστε την κλάση `TextFragment` για να τοποθετήσετε κείμενο στις επιθυμητές συντεταγμένες, έπειτα καλέστε `document.Draw(textFragment)`.

**Q:** Πού μπορώ να βρω επιπλέον παραδείγματα και πλήρη αναφορά API;  
**A:** Εξερευνήστε την τεκμηρίωση [here](https://reference.aspose.com/page/net/) και συμμετέχετε στην κοινότητα στο [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Μπορώ να δοκιμάσω το Aspose.Page πριν το αγοράσω;  
**A:** Ναι, κατεβάστε μια δωρεάν δοκιμή [here](https://releases.aspose.com/). Για εκτεταμένη αξιολόγηση, σκεφτείτε μια [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Τελευταία Ενημέρωση:** 2026-01-18  
**Δοκιμή με:** Aspose.Page 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}