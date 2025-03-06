---
title: Προσθήκη απλών ιδιοτήτων με το Aspose.Page για .NET
linktitle: Προσθήκη απλών ιδιοτήτων
second_title: Aspose.Page .NET API
description: Βελτιώστε τα αρχεία EPS με το Aspose.Page για .NET. Προσθέστε απλές ιδιότητες χωρίς κόπο για προσαρμοσμένα μεταδεδομένα εγγράφων.
weight: 14
url: /el/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη απλών ιδιοτήτων με το Aspose.Page για .NET

## Εισαγωγή

Στον τομέα του χειρισμού και της βελτίωσης εγγράφων, το Aspose.Page για .NET αναδεικνύεται ως ένα ισχυρό εργαλείο, παρέχοντας στους προγραμματιστές τη δυνατότητα να προσθέτουν και να τροποποιούν μεταδεδομένα XMP σε αρχεία EPS απρόσκοπτα. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία προσθήκης απλών ιδιοτήτων σε ένα αρχείο EPS χρησιμοποιώντας το Aspose.Page για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Page για .NET: Βεβαιωθείτε ότι έχετε εγκατεστημένο το Aspose.Page για .NET στο περιβάλλον ανάπτυξης σας. Εάν όχι, μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/page/net/).

2.  Κατάλογος εγγράφων: Ρυθμίστε έναν κατάλογο για να αποθηκεύσετε τα αρχεία EPS σας. Ενημερώστε το`dataDir` μεταβλητή στο παρεχόμενο απόσπασμα κώδικα με τη διαδρομή προς τον κατάλογο εγγράφων σας.

## Εισαγωγή χώρων ονομάτων

Για να ξεκινήσετε, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να ενεργοποιήσετε την επικοινωνία με το Aspose.Page για .NET. Προσθέστε τις ακόλουθες γραμμές στην αρχή του αρχείου κώδικα:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Βήμα 1: Αρχικοποιήστε τη ροή εισόδου αρχείου EPS

```csharp
// ExStart: 1
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
// Αρχικοποίηση ροής εισόδου αρχείου EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Δημιουργία παρουσίας PsDocument από τη ροή
PsDocument document = new PsDocument(psStream);
```

## Βήμα 2: Λήψη μεταδεδομένων XMP

```csharp
// Λάβετε μεταδεδομένα XMP. Εάν το αρχείο EPS δεν περιέχει μεταδεδομένα XMP, λαμβάνουμε ένα νέο γεμάτο με τιμές από σχόλια μεταδεδομένων PS (%%Creator, %%CreateDate, %%Title, κ.λπ.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Βήμα 3: Αλλάξτε τις τιμές μεταδεδομένων XMP

```csharp
// Αλλάξτε τις τιμές μεταδεδομένων XMP
DateTime now = DateTime.UtcNow;

// Προσθήκη ιδιότητας ακέραιου αριθμού
xmp.Add("xmp:Intg1", new XmpValue(111));

// Προσθήκη ιδιότητας DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Προσθήκη Διπλής ιδιοκτησίας
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Προσθήκη ιδιότητας συμβολοσειράς
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Βήμα 4: Αποθήκευση αρχείου EPS με Αλλαγμένα μεταδεδομένα XMP

```csharp
// Αποθήκευση αρχείου EPS με αλλαγμένα μεταδεδομένα XMP

// Δημιουργία ροής εξόδου
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Αποθήκευση αρχείου EPS
    document.Save(outPsStream);
}
```

## Βήμα 5: Κλείστε το FileStream

```csharp
finally
{
    psStream.Close();
}
```

Ακολουθώντας αυτά τα βήματα, μπορείτε να ενσωματώσετε αβίαστα απλές ιδιότητες στα αρχεία EPS σας χρησιμοποιώντας το Aspose.Page για .NET.

## συμπέρασμα

Εν κατακλείδι, το Aspose.Page για .NET αποδεικνύεται ότι είναι ένα ανεκτίμητο πλεονέκτημα για προγραμματιστές που επιδιώκουν να βελτιώσουν τα αρχεία EPS με προσαρμοσμένα μεταδεδομένα XMP. Προσθέτοντας απλές ιδιότητες, μπορείτε να προσαρμόσετε και να εμπλουτίσετε τα έγγραφά σας ώστε να ανταποκρίνονται σε συγκεκριμένες απαιτήσεις, ανοίγοντας έναν κόσμο δυνατοτήτων για χειρισμό εγγράφων.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Page για .NET συμβατό με όλα τα αρχεία EPS;

A1: Το Aspose.Page για .NET υποστηρίζει ένα ευρύ φάσμα αρχείων EPS. Ωστόσο, η συμβατότητα μπορεί να διαφέρει ανάλογα με την πολυπλοκότητα και τη δομή των μεμονωμένων αρχείων.

### Ε2: Μπορώ να τροποποιήσω τα υπάρχοντα μεταδεδομένα XMP με το Aspose.Page για .NET;

Α2: Απολύτως! Όπως αποδεικνύεται σε αυτό το σεμινάριο, μπορείτε εύκολα να αλλάξετε τις υπάρχουσες τιμές μεταδεδομένων XMP ή να προσθέσετε νέες που ταιριάζουν στις ανάγκες σας.

### Ε3: Υπάρχουν περιορισμοί στους τύπους ιδιοτήτων που μπορώ να προσθέσω;

A3: Το Aspose.Page για .NET υποστηρίζει διάφορους τύπους δεδομένων για ιδιότητες, συμπεριλαμβανομένων ακεραίων, ημερομηνιών, διπλών και συμβολοσειρών. Έχετε ευελιξία στην επιλογή του κατάλληλου τύπου για τα μεταδεδομένα σας.

### Ε4: Πώς μπορώ να αποκτήσω τεχνική υποστήριξη για το Aspose.Page για .NET;

 A4: Για τεχνική βοήθεια, επισκεφθείτε το[Aspose.Page Forum](https://forum.aspose.com/c/page/39) ή εξερευνήστε το[τεκμηρίωση](https://reference.aspose.com/page/net/) για ολοκληρωμένη καθοδήγηση.

### Ε5: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Page για .NET;

 A5: Ναι, μπορείτε να έχετε πρόσβαση σε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
