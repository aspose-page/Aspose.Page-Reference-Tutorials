---
title: Προσθήκη ονομαστικής τιμής με το Aspose.Page
linktitle: Προσθήκη ονομαστικής τιμής
second_title: Aspose.Page .NET API
description: Μάθετε πώς να προσθέτετε επώνυμες τιμές σε αρχεία EPS στο .NET χρησιμοποιώντας το Aspose.Page. Αυτό το περιεκτικό σεμινάριο σας καθοδηγεί στη διαδικασία βήμα προς βήμα.
weight: 12
url: /el/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη ονομαστικής τιμής με το Aspose.Page

## Εισαγωγή

Στον τομέα της επεξεργασίας εγγράφων με .NET, το Aspose.Page ξεχωρίζει ως ένα ισχυρό εργαλείο για το χειρισμό αρχείων EPS. Το Aspose.Page εξουσιοδοτεί τους προγραμματιστές να χειρίζονται μεταδεδομένα XMP, διευκολύνοντας εργασίες όπως η προσθήκη επώνυμων τιμών. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία προσθήκης ονομαστικών τιμών σε ένα αρχείο EPS χρησιμοποιώντας το Aspose.Page με τρόπο βήμα προς βήμα.

## Προαπαιτούμενα

Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Βασικές γνώσεις γλώσσας προγραμματισμού C#.
- Έχει εγκατασταθεί ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE), όπως το Visual Studio.
-  Aspose.Page για τη βιβλιοθήκη .NET. Εάν δεν είναι εγκατεστημένο, μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/page/net/).

## Εισαγωγή χώρων ονομάτων

Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων στον κώδικα C#. Αυτοί οι χώροι ονομάτων είναι ζωτικής σημασίας για την πρόσβαση στις λειτουργίες που παρέχονται από το Aspose.Page:

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

 Το αρχικό βήμα περιλαμβάνει την προετοιμασία της ροής εισόδου για το αρχείο EPS. Αντικαθιστώ`"Your Document Directory"` με τη διαδρομή προς τον κατάλογο εγγράφων σας:

```csharp
// ExStart: 1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Βήμα 2: Λήψη μεταδεδομένων XMP

Ανάκτηση μεταδεδομένων XMP από το αρχείο EPS. Εάν το αρχείο EPS δεν διαθέτει μεταδεδομένα XMP, θα δημιουργηθεί ένα νέο, γεμάτο με τιμές από σχόλια μεταδεδομένων PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Βήμα 3: Αλλάξτε τις τιμές μεταδεδομένων XMP

Τώρα, ας κάνουμε αλλαγές στα μεταδεδομένα XMP. Σε αυτό το παράδειγμα, θα προσθέσουμε μια ονομαστική τιμή στη δομή "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Βήμα 4: Αποθήκευση αρχείου EPS με Αλλαγμένα μεταδεδομένα XMP

Αποθηκεύστε το αρχείο EPS με τα ενημερωμένα μεταδεδομένα XMP. Δημιουργήστε μια ροή εξόδου και αποθηκεύστε το τροποποιημένο αρχείο EPS:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## συμπέρασμα

Συγχαρητήρια! Προσθέσατε με επιτυχία μια ονομαστική τιμή σε ένα αρχείο EPS χρησιμοποιώντας το Aspose.Page στο .NET. Αυτό το σεμινάριο σας καθοδήγησε στα βασικά βήματα, παρουσιάζοντας την απλότητα και την αποτελεσματικότητα του Aspose.Page στη διαχείριση εγγράφων.

## Συχνές ερωτήσεις

### Ε1: Είναι το Aspose.Page συμβατό με διαφορετικές εκδόσεις αρχείων EPS;

A1: Το Aspose.Page υποστηρίζει διάφορες εκδόσεις αρχείων EPS, διασφαλίζοντας τη συμβατότητα με ένα ευρύ φάσμα εγγράφων.

### Ε2: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;

 A2: Ναι, το Aspose.Page συνοδεύεται από εμπορική άδεια και μπορείτε να το αγοράσετε[εδώ](https://purchase.aspose.com/buy).

### Ε3: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Page;

 A3: Ναι, μπορείτε να εξερευνήσετε το Aspose.Page με διαθέσιμη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).

### Ε4: Πώς μπορώ να λάβω υποστήριξη ή να συνδεθώ με την κοινότητα του Aspose;

 A4: Επισκεφθείτε το[Aspose.Page φόρουμ](https://forum.aspose.com/c/page/39) για να λάβετε υποστήριξη και να συνδεθείτε με την κοινότητα.

### Ε5: Τι είναι η προσωρινή άδεια και πώς μπορώ να αποκτήσω;

 A5: Εάν χρειάζεστε μια προσωρινή άδεια για σκοπούς δοκιμής ή αξιολόγησης, μπορείτε να αποκτήσετε μία[εδώ](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
