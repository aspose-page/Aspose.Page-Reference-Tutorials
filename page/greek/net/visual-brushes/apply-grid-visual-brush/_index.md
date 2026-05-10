---
date: 2026-04-03
description: Μάθετε πώς να προσθέσετε ένα διαφανές ορθογώνιο και να εφαρμόσετε ένα
  Grid Visual Brush στο .NET χρησιμοποιώντας το Aspose.Page για εντυπωσιακά έγγραφα
  XPS.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: Εφαρμογή Οπτικού Πινέλου Πλέγματος
second_title: Aspose.Page .NET API
title: Προσθήκη διαφανούς ορθογωνίου χρησιμοποιώντας το Grid Visual Brush (.NET)
url: /el/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη Διαφανούς Ορθογωνίου με Grid Visual Brush (.NET)

## Εισαγωγή

Αν θέλετε να **προσθέσετε ένα διαφανές ορθογώνιο** σε ένα έγγραφο XPS ενώ εφαρμόζετε επίσης ένα κομψό Grid Visual Brush, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα τις ακριβείς ενέργειες με το Aspose.Page for .NET, ώστε να δημιουργήσετε οπτικά πλούσια έγγραφα που ξεχωρίζουν. Στο τέλος θα έχετε ένα πλήρες, εκτελέσιμο παράδειγμα που δείχνει και τις δύο τεχνικές σε μια ενιαία, εύκολη στη χρήση ροή εργασίας.

## Γρήγορες Απαντήσεις
- **Τι κάνει ένα διαφανές ορθογώνιο;** Προσθέτει μια ημιδιαφανή επικάλυψη που επιτρέπει στο περιεχόμενο του παρασκηνίου να φαίνεται.  
- **Ποιο API δημιουργεί το brush;** `XpsDocument.CreateVisualBrush` δημιουργεί το Grid Visual Brush.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για ένα βασικό παράδειγμα.

## Τι είναι ένα Διαφανές Ορθογώνιο σε XPS;
Ένα διαφανές ορθογώνιο είναι απλώς ένα σχήμα του οποίου το χρώμα γεμίσματος περιλαμβάνει ένα στοιχείο άλφα μικρότερο από 1.0, επιτρέποντας στα υποκείμενα γραφικά να είναι μερικώς ορατά. Αυτό είναι ιδανικό για επισήμανση τμημάτων χωρίς να καλύπτεται εντελώς το παρασκήνιο.

## Γιατί να χρησιμοποιήσετε Grid Visual Brush;
Ένα Grid Visual Brush σας επιτρέπει να επαναλαμβάνετε ένα μικρό διανυσματικό γραφικό σε μεγαλύτερη περιοχή, δημιουργώντας μοτίβα όπως πλέγματα, διαγράμματα ή προσαρμοσμένες υφές. Συνδυάζοντάς το με ένα διαφανές ορθογώνιο, παίρνετε στρωμένα οπτικά εφέ που είναι ελαφριά και ανεξάρτητα από την ανάλυση.

## Προαπαιτούμενα

Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε:

- **Aspose.Page for .NET** – μπορείτε να το κατεβάσετε [εδώ](https://releases.aspose.com/page/net/).
- Ένα περιβάλλον ανάπτυξης .NET (Visual Studio, VS Code ή οποιοδήποτε IDE προτιμάτε).
- Έναν φάκελο όπου θα αποθηκευτούν τα παραγόμενα αρχεία XPS.

## Εισαγωγή Namespaces

Στο αρχείο C#, εισάγετε τους απαιτούμενους χώρους ονομάτων:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Τώρα ας σπάσουμε τη λύση σε σαφή, αριθμημένα βήματα.

## Βήμα 1: Αρχικοποίηση XpsDocument

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

Ξεκινάμε δημιουργώντας μια παρουσία `XpsDocument`, η οποία θα κρατήσει όλες τις επόμενες λειτουργίες σχεδίασης.

## Βήμα 2: Δημιουργία Geometry Πλέγματος Ματζέντα

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

Αυτή η γεωμετρία ορίζει το περίγραμμα του πλέγματος που θα γεμίσει το visual brush.

## Βήμα 3: Σχεδίαση VisualBrush Πλέγματος Ματζέντα

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

Εδώ σχεδιάζουμε ένα μικρό ματζέντα πλακίδιο που θα επαναλαμβάνεται σε όλο το πλέγμα.

## Βήμα 4: Εφαρμογή VisualBrush στο Πλέγμα

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

Η κλήση `CreateVisualBrush` συνδέει το ματζέντα πλακίδιο με τη γεωμετρία του πλέγματος και ενεργοποιεί την επανάληψη.

## Βήμα 5: Προσθήκη Πλέγματος στο Καμβά

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

Τοποθετούμε το επαναλαμβανόμενο πλέγμα σε έναν καμβά και εφαρμόζουμε μια μεταφορά translation ώστε να εμφανίζεται στην επιθυμητή θέση.

## Βήμα 6: Προσθήκη Διαφανούς Ορθογωνίου

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

Σε αυτό το βήμα **προσθέτουμε ένα διαφανές ορθογώνιο** (το κόκκινο σχήμα με `Opacity = 0.7f`). Ρυθμίστε την τιμή της διαφάνειας για να ελέγξετε πόσο διαυγές θα είναι το ορθογώνιο.

## Βήμα 7: Αποθήκευση Εγγράφου

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

Το αρχείο XPS γράφεται στον φάκελο που καθορίσατε νωρίτερα.

## Κοινές Περιπτώσεις Χρήσης

- **Επισήμανση Αναφοράς:** Επικάλυψη ημιδιαφανούς ορθογωνίου για να τονίσετε ένα γράφημα ή πίνακα.  
- **Εφέ Υδατογραφήματος:** Συνδυάστε ένα επαναλαμβανόμενο πλέγμα με μια διαφανή επικάλυψη για διακριτική επωνυμία.  
- **Διαδραστικά PDFs/XPS:** Χρησιμοποιήστε το μοτίβο ως φόντο για πεδία φόρμας ενώ διατηρείτε την αναγνωσιμότητα του UI.

## Συμβουλές Επίλυσης Προβλημάτων

- **Η διαφάνεια δεν φαίνεται;** Βεβαιωθείτε ότι ο προβολέας σας υποστηρίζει διαφάνεια XPS· ορισμένοι παλαιότεροι προβολείς μπορεί να αγνοούν την ιδιότητα `Opacity`.  
- **Λάθος μέγεθος πλακιδίου;** Επαληθεύστε ότι το πηγαίο ορθογώνιο (`new RectangleF(0f, 0f, 10f, 10f)`) ταιριάζει με τις διαστάσεις του διανυσματικού πλακιδίου.  
- **Το αρχείο δεν αποθηκεύτηκε;** Ελέγξτε ξανά ότι το `dataDir` δείχνει σε έναν υπάρχοντα, εγγράψιμο φάκελο.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω Aspose.Page for .NET τόσο σε web όσο και σε desktop εφαρμογές;**  
Α: Ναι, η βιβλιοθήκη λειτουργεί σε όλους τους τύπους εφαρμογών .NET.

**Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση πριν από την αγορά;**  
Α: Απόλυτα, μπορείτε να αποκτήσετε τη δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

**Ε: Πού μπορώ να βρω επιπλέον υποστήριξη ή συζητήσεις κοινότητας;**  
Α: Επισκεφθείτε το [Aspose.Page Forum](https://forum.aspose.com/c/page/39) για βοήθεια από την κοινότητα και τους μηχανικούς της Aspose.

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για αξιολόγηση;**  
Α: Μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

**Ε: Ποια άλλη τεκμηρίωση είναι διαθέσιμη για το Aspose.Page for .NET;**  
Α: Εξερευνήστε την πλήρη τεκμηρίωση [εδώ](https://reference.aspose.com/page/net/).

---

**Τελευταία Ενημέρωση:** 2026-04-03  
**Δοκιμή Με:** Aspose.Page 24.12 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}