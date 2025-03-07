---
title: Εφαρμογή Metered License με το Aspose.Page για .NET
linktitle: Εφαρμογή Metered License
second_title: Aspose.Page .NET API
description: Εξερευνήστε την απρόσκοπτη ενσωμάτωση του Aspose.Page για .NET με αυτόν τον αναλυτικό οδηγό για την εφαρμογή μιας μετρημένης άδειας χρήσης. Βελτιστοποιήστε την επεξεργασία εγγράφων χωρίς κόπο.
weight: 10
url: /el/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Εφαρμογή Metered License με το Aspose.Page για .NET

## Εισαγωγή

Ξεκλειδώστε πλήρως τις δυνατότητες του Aspose.Page για .NET εφαρμόζοντας μια μετρημένη άδεια. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία ρύθμισης και εφαρμογής της μετρημένης άδειας, διασφαλίζοντας την ομαλή και βελτιστοποιημένη χρήση αυτής της ισχυρής βιβλιοθήκης .NET.

## Προαπαιτούμενα

Πριν βουτήξετε στα βήματα, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

-  Μια έγκυρη άδεια χρήσης Aspose.Page για .NET: Μπορείτε να την αποκτήσετε από[buy.aspose.com](https://purchase.aspose.com/buy).
-  Εγκαταστάθηκε η βιβλιοθήκη Aspose.Page: Ανατρέξτε στο[τεκμηρίωση](https://reference.aspose.com/page/net/) για οδηγίες εγκατάστασης.
- Περιβάλλον ανάπτυξης .NET: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα λειτουργικό περιβάλλον .NET στον υπολογιστή σας.

## Εισαγωγή χώρων ονομάτων

Στο έργο σας .NET, εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση στις λειτουργίες Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Βήμα 1: Ορίστε τα μετρημένα δημόσια και ιδιωτικά κλειδιά

 Αρχικοποιήστε το`Aspose.Page.Metered` τάξη και ορίστε τα μετρημένα δημόσια και ιδιωτικά κλειδιά. Αντικαθιστώ`<type public key here>` και`<type private key here>` με τα πραγματικά κλειδιά σας.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Βήμα 2: Φορτώστε το αρχείο EPS και δημιουργήστε έγγραφο

 Καθορίστε τη διαδρομή προς το αρχείο EPS και δημιουργήστε μια ροή για να διαβάσετε το περιεχόμενό του. Στη συνέχεια, δημιουργήστε ένα παράδειγμα του`PsDocument` τάξη από το ρεύμα.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Βήμα 3: Μετατροπή EPS σε εικόνα PNG

 Δημιουργήστε ένα`ImageDevice` για τη μετατροπή του αρχείου EPS σε εικόνα PNG. Αποθηκεύστε το αρχείο EPS ως εικόνα χρησιμοποιώντας το`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Βήμα 4: Ανάκτηση byte εικόνας

Λάβετε τα byte της εικόνας, όπου κάθε πίνακας byte αντιπροσωπεύει μία σελίδα. Σε αυτή την περίπτωση, έχουμε μία σελίδα.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Βήμα 5: Αποθήκευση Byte εικόνας στο αρχείο

Αποθηκεύστε τα byte της εικόνας σε ένα αρχείο, διασφαλίζοντας την επιτυχή μετατροπή από EPS σε PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Βήμα 6: Επαλήθευση της μετρημένης άδειας

Ελέγξτε οπτικά εάν η μετρούμενη άδεια εφαρμόζεται με επιτυχία. Εάν η εικόνα που προκύπτει δεν περιέχει το κόκκινο μήνυμα αξιολόγησης, υποδηλώνει ότι η μετρημένη άδεια εφαρμόζεται χωρίς προβλήματα.

Τώρα είστε έτοιμοι να αξιοποιήσετε τις πλήρεις δυνατότητες του Aspose.Page για .NET με μετρημένη άδεια!

## συμπέρασμα

Αυτός ο οδηγός βήμα προς βήμα σάς έχει εξοπλίσει με τις γνώσεις για την απρόσκοπτη εφαρμογή μιας μετρημένης άδειας χρήσης χρησιμοποιώντας το Aspose.Page για .NET. Βελτιώστε τις δυνατότητες επεξεργασίας εγγράφων σας και εξερευνήστε τις τεράστιες δυνατότητες που προσφέρει αυτή η ισχυρή βιβλιοθήκη.

## Συχνές ερωτήσεις

### Ε1: Πώς μπορώ να αποκτήσω μια μετρημένη άδεια για το Aspose.Page για .NET;

 Α1: Επίσκεψη[buy.aspose.com](https://purchase.aspose.com/buy) να αποκτήσει έγκυρη άδεια.

### Ε2: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Page για .NET;

 A2: Ανατρέξτε στο[Aspose.Page .NET](https://reference.aspose.com/page/net/) για πλήρη τεκμηρίωση.

### Ε3: Υπάρχει φόρουμ για συζητήσεις και υποστήριξη Aspose.Page;

 Α3: Ναι, επισκεφθείτε[δικαστήριο](https://forum.aspose.com/c/page/39) να συνεργαστεί με την κοινότητα και να αναζητήσει βοήθεια.

### Ε4: Μπορώ να δοκιμάσω το Aspose.Page για .NET πριν από την αγορά;

 Α4: Απολύτως! Αποκτήστε πρόσβαση στη δωρεάν δοκιμή στη διεύθυνση[εδώ](https://releases.aspose.com/).

### Ε5: Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Page για .NET;

 Α5: Επίσκεψη[προσωρινή άδεια/](https://purchase.aspose.com/temporary-license/) για την απόκτηση προσωρινής άδειας.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
