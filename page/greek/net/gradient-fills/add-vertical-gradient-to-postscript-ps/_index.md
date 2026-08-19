---
date: 2026-02-25
description: Μάθετε πώς να χρησιμοποιείτε ένα πινέλο γραμμικού διαβάθμισης C# για
  να προσθέσετε διαβάθμιση σε αρχεία PS και να γεμίσετε ένα ορθογώνιο με διαβάθμιση
  χρησιμοποιώντας το Aspose.Page για .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Πινέλο Γραμμικής Διαβάθμισης – Προσθήκη Κατακόρυφης Διαβάθμισης στο PostScript
  (PS) με το Aspose.Page
url: /el/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Προσθήκη Κατακόρυφου Gradient σε PostScript (PS) με Aspose.Page

## Εισαγωγή

Στον χώρο της διαχείρισης και δημιουργίας εγγράφων, **Aspose.Page for .NET** ξεχωρίζει ως ένα ισχυρό εργαλείο για προγραμματιστές. Σε αυτόν τον οδηγό θα ανακαλύψετε πώς να **προσθέσετε gradient σε PS** αρχεία χρησιμοποιώντας ένα **C# linear gradient brush** για **fill rectangle with gradient**. Στο τέλος του tutorial, θα έχετε μια σαφή, βήμα‑βήμα κατανόηση του απαιτούμενου κώδικα και του γιατί αυτή η τεχνική παράγει μια ομαλή κατακόρυφη διαβάθμιση στην έξοδο PostScript.

## Γρήγορες Απαντήσεις
- **Τι κάνει ένα C# linear gradient brush;** Δημιουργεί μια ομαλή μετάβαση μεταξύ πολλών χρωμάτων σε ένα σχήμα.
- **Μπορώ να το χρησιμοποιήσω με οποιαδήποτε έκδοση .NET;** Ναι, το Aspose.Page υποστηρίζει .NET Framework 4.5+ και .NET Core/5+.
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια για μη‑αξιολογικές εκδόσεις.
- **Η διαβάθμιση είναι πραγματικά κατακόρυφη;** Το πινέλο περιστρέφεται κατά 90°, εξασφαλίζοντας κατακόρυφη ροή.
- **Πού αποθηκεύεται το αποτέλεσμα;** Στη διαδρομή που καθορίζετε στο `dataDir` (π.χ., `VerticalGradient_outPS.ps`).

## Τι είναι ένα C# Linear Gradient Brush;
Ένα **C# linear gradient brush** είναι ένα αντικείμενο GDI+ (`LinearGradientBrush`) που ζωγραφίζει μια γραμμική μετάβαση χρώματος μεταξύ καθορισμένων σημείων. Όταν συνδυάζεται με το API σχεδίασης του Aspose.Page, σας επιτρέπει να αποδίδετε σύνθετες διαβαθμίσεις απευθείας σε ένα έγγραφο PostScript (PS).

## Γιατί να χρησιμοποιήσετε Linear Gradient Brush για PostScript;
- **Υψηλής ποιότητας έξοδος:** Οι διαβαθμίσεις αποδίδονται σε επίπεδο εκτυπωτή, διατηρώντας την πιστότητα.
- **Πλήρης έλεγχος:** Μπορείτε να ορίσετε προσαρμοσμένα χρώματα διακοπής, περιστροφή και κλιμάκωση.
- **Επαναχρησιμοποιήσιμος κώδικας:** Η ίδια λογική πινέλου λειτουργεί για PDF, SVG και άλλες μορφές που υποστηρίζει το Aspose.Page.

## Προαπαιτούμενα

Πριν ξεκινήσετε το tutorial, βεβαιωθείτε ότι έχετε τα εξής:

- Aspose.Page for .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page. Μπορείτε να βρείτε τους απαραίτητους πόρους και την τεκμηρίωση [εδώ](https://reference.aspose.com/page/net/).
- Περιβάλλον Ανάπτυξης: Ρυθμίστε ένα κατάλληλο περιβάλλον ανάπτυξης, συμπεριλαμβανομένου ενός ολοκληρωμένου περιβάλλοντος ανάπτυξης (IDE) για .NET.
- Βασική Κατανόηση: Εξοικειωθείτε με τα βασικά της ανάπτυξης .NET, συμπεριλαμβανομένης της εργασίας με ροές, γραφικές διαδρομές και χειρισμό χρωμάτων.

## Εισαγωγή Namespaces

Στο έργο C#, συμπεριλάβετε τα απαιτούμενα namespaces στην αρχή του αρχείου κώδικα:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Βήμα 1: Ρύθμιση του Καταλόγου Εγγράφου

Ξεκινήστε καθορίζοντας τη διαδρομή προς τον κατάλογο του εγγράφου σας. Αυτή είναι η θέση όπου θα αποθηκευτεί το PS έγγραφό σας.

```csharp
string dataDir = "Your Document Directory";
```

## Βήμα 2: Δημιουργία Ροής Εξόδου για το Έγγραφο PostScript

Δημιουργήστε μια ροή εξόδου για το έγγραφο PostScript χρησιμοποιώντας την κλάση `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Βήμα 3: Δημιουργία Επιλογών Αποθήκευσης και Εγγράφου PS

Δημιουργήστε επιλογές αποθήκευσης με μέγεθος A4 και αρχικοποιήστε ένα νέο έγγραφο PS με 1 σελίδα.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Βήμα 4: Ορισμός Διαστάσεων Ορθογωνίου

Καθορίστε τις διαστάσεις και τη θέση του ορθογωνίου όπου θα εφαρμοστεί η κατακόρυφη διαβάθμιση.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Βήμα 5: Δημιουργία Graphics Path

Δημιουργήστε ένα graphics path από το ορισμένο ορθογώνιο.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Βήμα 6: Ορισμός Χρωμάτων Παρεμβολής

Καθορίστε έναν πίνακα χρωμάτων παρεμβολής και θέσεων για τη διαβάθμιση.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Βήμα 7: Δημιουργία Linear Gradient Brush

Δημιουργήστε ένα linear gradient brush με το ορθογώνιο ως όρια, χρώματα έναρξης και λήξης.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Βήμα 8: Ορισμός Transform για το Brush

Ορίστε ένα transform για το brush, διασφαλίζοντας ότι τα στοιχεία κλίμακας X και Y ταιριάζουν με το πλάτος και το ύψος του ορθογωνίου.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Βήμα 9: Ορισμός Paint και Γέμισμα του Ορθογωνίου

Ορίστε το paint για το έγγραφο και **fill rectangle with gradient** χρησιμοποιώντας τη προηγουμένως ορισμένη διαδρομή.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Βήμα 10: Κλείσιμο της Τρέχουσας Σελίδας και Αποθήκευση του Εγγράφου

Κλείστε την τρέχουσα σελίδα και αποθηκεύστε το έγγραφο PostScript.

```csharp
document.ClosePage();
document.Save();
```

Συγχαρητήρια! Έχετε προσθέσει επιτυχώς **κατακόρυφη διαβάθμιση σε έγγραφο PostScript** χρησιμοποιώντας ένα **C# linear gradient brush** με το Aspose.Page για .NET. Πειραματιστείτε με διαφορετικές παραμέτρους και χρώματα για να πετύχετε διάφορα οπτικά εφέ στα έγγραφά σας.

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Γιατί συμβαίνει | Πώς να διορθώσετε |
|----------|----------------|-------------------|
| Η διαβάθμιση εμφανίζεται οριζόντια | Δεν εφαρμόστηκε η περιστροφή του brush | Ensure `brushTransform.Rotate(90);` is called before assigning to `brush.Transform`. |
| Τα χρώματα φαίνονται ξεθωριασμένα | Ροή εξόδου χαμηλής ανάλυσης | Use a higher‑resolution `PsSaveOptions` or increase the document size. |
| Το αρχείο εξόδου είναι κενό | Η ροή δεν εκκενώθηκε | Verify that `document.Save();` is called outside the `using` block. |

## Συχνές Ερωτήσεις

**Q1: Μπορώ να εφαρμόσω πολλαπλές διαβαθμίσεις σε διαφορετικές περιοχές του ίδιου εγγράφου;**  
A: Ναι, μπορείτε. Απλώς επαναλάβετε τα βήματα για κάθε περιοχή με τις συγκεκριμένες διαστάσεις και το χρωματικό σχήμα της.

**Q2: Πώς μπορώ να ενσωματώσω αυτόν τον κώδικα στο υπάρχον .NET project μου;**  
A: Αντιγράψτε και επικολλήστε τον κώδικα στο αρχείο του project σας και βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Page είναι αναφορά.

**Q3: Υπάρχουν άλλοι τύποι διαβαθμίσεων διαθέσιμοι στο Aspose.Page για .NET;**  
A: Το Aspose.Page υποστηρίζει διάφορους τύπους διαβαθμίσεων, συμπεριλαμβανομένων των radial και path gradients. Ανατρέξτε στην τεκμηρίωση για περισσότερες λεπτομέρειες.

**Q4: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;**  
A: Ναι, μπορείτε. Επισκεφθείτε [εδώ](https://purchase.aspose.com/buy) για να εξερευνήσετε τις επιλογές αδειοδότησης.

**Q5: Υπάρχει κοινότητα ή φόρουμ για το Aspose.Page όπου μπορώ να ζητήσω βοήθεια;**  
A: Φυσικά! Μεταβείτε στο [Aspose.Page forum](https://forum.aspose.com/c/page/39) για να συνδεθείτε με άλλους προγραμματιστές και να λάβετε υποστήριξη.

**Τελευταία ενημέρωση:** 2026-02-25  
**Δοκιμή με:** Aspose.Page 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}