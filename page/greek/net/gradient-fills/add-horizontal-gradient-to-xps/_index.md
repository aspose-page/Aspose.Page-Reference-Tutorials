---
date: 2026-02-25
description: Μάθετε πώς να δημιουργήσετε διαβάθμιση XPS με οριζόντια γέμιση χρησιμοποιώντας
  το Aspose.Page για .NET. Αναβαθμίστε την οπτική ελκυστικότητα με ευκολία στα έγγραφά
  σας.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Δημιουργία διαβάθμισης XPS: Οριζόντιο γέμισμα με Aspose.Page για .NET'
url: /el/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Gradient XPS – Προσθήκη Οριζόντιου Gradient σε XPS με Aspose.Page για .NET

## Εισαγωγή

Σε αυτό το σεμινάριο θα **δημιουργήσετε γεμίσματα gradient XPS** που τρέχουν οριζόντια σε όλες τις σελίδες σας. Η προσθήκη ενός οριζόντιου gradient μπορεί αμέσως να κάνει ένα έγγραφο XPS να φαίνεται πιο επαγγελματικό και ελκυστικό, ειδικά για εκθέσεις, φυλλάδια ή οποιαδήποτε οπτικά πλούσια έξοδο. Θα περάσουμε από όλη τη διαδικασία χρησιμοποιώντας το Aspose.Page για .NET, από τη ρύθμιση του περιβάλλοντος μέχρι την αποθήκευση του τελικού αρχείου XPS.

## Γρήγορες Απαντήσεις
- **Τι καλύπτει αυτό το σεμινάριο;** Προσθήκη οριζόντιου gradient σε έγγραφο XPS με Aspose.Page για .NET.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Page για .NET (οποιαδήποτε πρόσφατη έκδοση).  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική έκδοση λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 5–10 λεπτά για ένα βασικό gradient.  
- **Μπορώ να αλλάξω την κατεύθυνση του gradient;** Ναι – τροποποιήστε τα σημεία έναρξης/λήξης του `LinearGradientBrush`.

## Πώς να δημιουργήσετε gradient XPS με Aspose.Page για .NET

Παρακάτω θα βρείτε έναν οδηγό βήμα‑βήμα που εξηγεί **γιατί** υπάρχει κάθε γραμμή κώδικα, όχι μόνο **τι** κάνει. Μπορείτε να το ακολουθήσετε στο Visual Studio ή σε οποιονδήποτε προτιμώμενο επεξεργαστή .NET.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω:

1. **Aspose.Page για .NET Library:** Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Page για .NET στο περιβάλλον ανάπτυξής σας. Μπορείτε να τη κατεβάσετε από την [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. **Περιβάλλον Ανάπτυξης:** Ρυθμίστε ένα κατάλληλο περιβάλλον ανάπτυξης, συμπεριλαμβανομένου ενός επεξεργαστή κώδικα όπως το Visual Studio.

## Εισαγωγή Ονομάτων Χώρων

Ξεκινήστε εισάγοντας τα απαραίτητα namespaces στο έργο σας. Αυτά τα namespaces είναι ουσιώδη για την εργασία με Aspose.Page για .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλαπλά βήματα.

## Βήμα 1: Ορισμός Διαδρομής Φακέλου Εγγράφου

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Βήμα 2: Δημιουργία Νέου Εγγράφου XPS

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Βήμα 3: Αρχικοποίηση Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Βήμα 4: Δημιουργία Νέου Path

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Βήμα 5: Αποθήκευση του Τελικού Εγγράφου XPS

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Τώρα έχετε προσθέσει επιτυχώς ένα οριζόντιο gradient στο έγγραφο XPS χρησιμοποιώντας το Aspose.Page για .NET.

## Κοινά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Το gradient εμφανίζεται ως στερεό χρώμα | Τα gradient stops δεν προστέθηκαν σωστά | Βεβαιωθείτε ότι εκτελείται `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` μετά τον ορισμό του πινέλου. |
| Το αποθηκευμένο αρχείο είναι κενό | Το `dataDir` δείχνει σε μη‑υπάρχον φάκελο | Επαληθεύστε ότι ο φάκελος υπάρχει ή χρησιμοποιήστε απόλυτη διαδρομή. |
| Σφάλμα μεταγλώττισης στο `PointF` | Λείπει η αναφορά στο `System.Drawing` | Προσθέστε αναφορά στο `System.Drawing.Common` (για .NET Core/5+). |

## FAQ's

### Q1: Πού μπορώ να βρω την τεκμηρίωση του Aspose.Page για .NET;

A1: Μπορείτε να βρείτε την τεκμηρίωση [εδώ](https://reference.aspose.com/page/net/).

### Q2: Πώς κατεβάζω το Aspose.Page για .NET;

A2: Μπορείτε να κατεβάσετε τη βιβλιοθήκη από τη [σελίδα λήψης Aspose.Page για .NET](https://releases.aspose.com/page/net/).

### Q3: Πού μπορώ να αγοράσω το Aspose.Page για .NET;

A3: Μπορείτε να αγοράσετε το Aspose.Page για .NET από τη [σελίδα αγοράς](https://purchase.aspose.com/buy).

### Q4: Υπάρχει διαθέσιμη δωρεάν δοκιμή;

A4: Ναι, μπορείτε να λάβετε δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).

### Q5: Πώς λαμβάνω προσωρινή άδεια για το Aspose.Page για .NET;

A5: Μπορείτε να αποκτήσετε προσωρινή άδεια από [αυτόν τον σύνδεσμο](https://purchase.aspose.com/temporary-license/).

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω αυτήν την τεχνική gradient με έγγραφα XPS που ήδη περιέχουν εικόνες;**  
Α: Απολύτως. Το gradient εφαρμόζεται σε ένα επίπεδο path, έτσι οι υπάρχουσες εικόνες παραμένουν αμετάβλητες.

**Ε: Είναι δυνατόν να δημιουργήσω κάθετο gradient αντί για οριζόντιο;**  
Α: Ναι. Αλλάξτε τα σημεία έναρξης και λήξης του `LinearGradientBrush` ώστε να έχουν διαφορετικές συντεταγμένες Y ενώ το X παραμένει σταθερό.

**Ε: Υποστηρίζει το Aspose.Page το .NET Core;**  
Α: Η βιβλιοθήκη είναι πλήρως συμβατή με .NET Core, .NET 5 και μεταγενέστερες εκδόσεις.

**Ε: Πώς μπορώ να επαναχρησιμοποιήσω το ίδιο gradient σε πολλαπλές σελίδες;**  
Α: Δημιουργήστε το `XpsLinearGradientBrush` μία φορά, αποθηκεύστε το σε μεταβλητή και αναθέστε το σε paths σε κάθε σελίδα.

## Συμπέρασμα

Η βελτίωση των εγγράφων XPS με gradients όχι μόνο ενισχύει την οπτική ελκυστικότητα, αλλά προσφέρει και μια πιο ελκυστική εμπειρία χρήστη. Με το Aspose.Page για .NET, μπορείτε **να δημιουργήσετε γεμίσματα gradient XPS** γρήγορα και αξιόπιστα, δίνοντας στις εκθέσεις, τα φυλλάδια ή τα e‑books σας έναν επαγγελματικό λουκ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-02-25  
**Δοκιμάστηκε Με:** Aspose.Page for .NET 24.11  
**Συγγραφέας:** Aspose  

---