---
date: 2026-09-04
description: Μάθετε πώς να μειώσετε το μέγεθος αρχείου EPS περικόπτοντας αρχεία EPS
  σε Java χρησιμοποιώντας το Aspose.Page – ένας οδηγός βήμα‑βήμα που δείχνει πώς να
  περικόψετε eps, να περικόψετε εικόνα eps και να trim αρχείο eps.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Περικοπή αρχείου EPS σε Java
og_description: Μάθετε πώς να μειώσετε το μέγεθος αρχείου EPS περικόπτοντας αρχεία
  EPS σε Java χρησιμοποιώντας το Aspose.Page – ένας γρήγορος οδηγός με κώδικα και
  συμβουλές.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Πώς να περικόψετε αρχεία EPS σε Java για να μειώσετε το μέγεθος αρχείου
  EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Πώς να περικόψετε αρχεία EPS σε Java για να μειώσετε το μέγεθος αρχείου EPS
url: /el/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να περικόψετε αρχεία EPS σε Java για να μειώσετε το μέγεθος αρχείου EPS

## Εισαγωγή
Αν χρειάζεστε να **περικόψετε αρχεία EPS** προγραμματιστικά σε μια εφαρμογή Java και θέλετε να **μειώσετε το μέγεθος αρχείου EPS**, βρίσκεστε στο σωστό μέρος. Σε αυτό το μάθημα θα περάσουμε από όλη τη διαδικασία περικοπής μιας εικόνας EPS χρησιμοποιώντας τη δυνατή βιβλιοθήκη Aspose.Page for Java. Στο τέλος του οδηγού θα κατανοήσετε γιατί η περικοπή EPS είναι σημαντική, θα δείτε τον ακριβή κώδικα που χρειάζεστε και θα είστε έτοιμοι να ενσωματώσετε τη λύση στα δικά σας έργα.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται την περικοπή EPS σε Java;** Aspose.Page for Java.  
- **Πόσο χρόνο χρειάζεται η υλοποίηση μιας βασικής περικοπής;** Περίπου 5‑10 λεπτά.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποιες εκδόσεις της Java υποστηρίζονται;** Java 8 και νεότερες.  
- **Μπορώ να ορίσω προσαρμοσμένο πλαίσιο περιγράμματος;** Ναι – παρέχετε τις συντεταγμένες που χρειάζεστε.

## Τι είναι η περικοπή EPS και γιατί να τη χρησιμοποιήσετε;
**Η περικοπή EPS δημιουργεί ένα νέο πλαίσιο περιγράμματος που ορίζει την ορατή περιοχή ενός αρχείου EPS.**  
Η περικοπή ενός αρχείου EPS αφαιρεί ανεπιθύμητο κενό χώρο και περικόπτει το γραφικό στο τμήμα που πραγματικά χρειάζεστε, κάτι που άμεσα **μειώνει το μέγεθος αρχείου EPS** και βελτιώνει τη συνοχή διάταξης σε επόμενα έγγραφα όπως PDF ή αναφορές.

## Γιατί να περικόψετε αρχεία EPS;
Η περικοπή αρχείων EPS σας επιτρέπει να **σμικρύνετε το μέγεθος του αρχείου έως και 30 %**, να αφαιρέσετε περιττά περιθώρια και να τυποποιήσετε τα γραφικά για αγωγούς μαζικής επεξεργασίας. Είναι ιδιαίτερα χρήσιμη όταν χρειάζεται να ενσωματώσετε πολλά στοιχεία EPS σε ένα μόνο PDF ή όταν θέλετε να επιταχύνετε την απόδοση σε συσκευές χαμηλής ισχύος.

## Προαπαιτούμενα
- **Aspose.Page for Java** βιβλιοθήκη εγκατεστημένη – κατεβάστε την από την επίσημη σελίδα [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 ή νεότερο εγκατεστημένο στον υπολογιστή σας.  
- **Ένας φάκελος** για να αποθηκεύσετε το εισερχόμενο EPS (`input.eps`) και το προκύπτον αρχείο περικοπής (`output_crop.eps`).

## Εισαγωγή πακέτων
Πρώτα, εισάγετε τις απαραίτητες κλάσεις Java. Αυτό το απόσπασμα παραμένει ακριβώς το ίδιο όπως στο αρχικό μάθημα:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Πώς να περικόψετε εικόνα EPS σε Java
Φορτώστε το πηγαίο EPS, ορίστε ένα νέο πλαίσιο περιγράμματος και καλέστε το API περικοπής – ολόκληρη η λειτουργία ολοκληρώνεται σε πέντε σύντομα βήματα.

### Βήμα 1: ορίστε τον φάκελο εγγράφου και τη ροή εισόδου
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Εδώ κατευθύνουμε τον κώδικα στον φάκελο που περιέχει το πηγαίο αρχείο EPS και ανοίγουμε μια ροή για την ανάγνωσή του.

### Βήμα 2: αρχικοποιήστε το αντικείμενο PsDocument
Η κλάση `PsDocument` αντιπροσωπεύει ένα αρχείο EPS στη μνήμη, επιτρέποντάς σας να διαβάζετε και να τροποποιείτε τις ιδιότητές του.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
Το αντικείμενο σας δίνει πρόσβαση στο αρχικό πλαίσιο περιγράμματος και σε άλλα μεταδεδομένα.

### Βήμα 3: εξαγάγετε το αρχικό πλαίσιο περιγράμματος
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Η εξαγωγή του αρχικού πλαισίου περιγράμματος σας παρέχει τις συντεταγμένες της τρέχουσας ορατής περιοχής – χρήσιμο για να αποφασίσετε πόσο πρέπει να περικόψετε.

### Βήμα 4: δημιουργήστε τη ροή εξόδου
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Ανοίγουμε μια ροή όπου θα γραφτεί το περικομμένο EPS.

### Βήμα 5: ορίστε νέο πλαίσιο περιγράμματος και περικόψτε
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Παρέχετε τις τέσσερις συντεταγμένες (κάτω‑αριστερό x, κάτω‑αριστερό y, πάνω‑δεξιό x, πάνω‑δεξιό y) που ορίζουν την περιοχή που θέλετε να διατηρήσετε. Η μέθοδος εκτελεί την περικοπή και γράφει το αποτέλεσμα στο `output_crop.eps`.

## Κοινά προβλήματα και λύσεις
- **Λανθασμένες συντεταγμένες:** Το EPS χρησιμοποιεί μονάδες σημείων (1/72 ίντσα). Αν η περικοπή φαίνεται λανθασμένη, ελέγξτε ξανά τη μετατροπή μονάδων.  
- **Σφάλματα αρχείου δεν βρέθηκε:** Βεβαιωθείτε ότι το `dataDir` τελειώνει με το κατάλληλο διαχωριστικό διαδρομής (`/` ή `\`).  
- **Εξαιρέσεις άδειας:** Η εκτέλεση του κώδικα χωρίς έγκυρη άδεια μπορεί να προσθέσει υδατογράφημα στο αποτέλεσμα. Εφαρμόστε την προσωρινή ή μόνιμη άδειά σας πριν τη χρήση σε παραγωγή.

## Συχνές ερωτήσεις

**Ε: Είναι το Aspose.Page συμβατό με Java 8;**  
Α: Ναι, το Aspose.Page λειτουργεί με Java 8 και οποιαδήποτε μεταγενέστερη έκδοση.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Page για εμπορικά έργα;**  
Α: Απόλυτα. Απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις. Μπορείτε να αποκτήσετε μία από τη [Aspose purchase page](https://purchase.aspose.com/buy).

**Ε: Πού μπορώ να βρω πρόσθετους πόρους και υποστήριξη κοινότητας;**  
Α: Επισκεφθείτε το επίσημο [Aspose.Page forum](https://forum.aspose.com/c/page/39) για συζητήσεις, παραδείγματα κώδικα και συμβουλές αντιμετώπισης προβλημάτων.

**Ε: Υπάρχει δωρεάν δοκιμή διαθέσιμη για δοκιμή;**  
Α: Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμή του Aspose.Page από τη σελίδα εκδόσεων [Aspose.Page releases page](https://releases.aspose.com/).

**Ε: Πώς μπορώ να αποκτήσω προσωρινή άδεια για βραχυπρόθεσμη αξιολόγηση;**  
Α: Μπορείτε να ζητήσετε προσωρινή άδεια από την πύλη αδειών [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να περικόψετε αρχεία EPS** σε Java χρησιμοποιώντας το Aspose.Page για **μείωση του μεγέθους αρχείου EPS**. Ορίζοντας ένα προσαρμοσμένο πλαίσιο περιγράμματος και καλώντας το `cropEps`, μπορείτε να αφαιρέσετε ανεπιθύμητα περιθώρια ή να απομονώσετε συγκεκριμένα τμήματα ενός γραφικού EPS με λίγες μόνο γραμμές κώδικα. Ενσωματώστε αυτό το απόσπασμα στις μεγαλύτερες αλυσίδες επεξεργασίας εγγράφων σας για να αυτοματοποιήσετε τη διαχείριση EPS, **περικόψτε εικόνες EPS**, και **κόψετε περιεχόμενο αρχείου EPS** αποδοτικά.

---

**Τελευταία ενημέρωση:** 2026-09-04  
**Δοκιμάστηκε με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να αλλάξετε το μέγεθος αρχείων EPS σε Java με Aspose.Page](/page/java/manipulation-eps/resize/)
- [Μετατροπή EPS σε PNG με Aspose.Page Java (Άδεια με μέτρηση)](/page/java/license-management/set-metered-license/)
- [Μάθημα Aspose Page Java – Προσθήκη μεταδεδομένων XMP σε αρχεία EPS](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}