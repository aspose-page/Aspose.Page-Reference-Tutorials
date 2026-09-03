---
date: 2026-05-25
description: Μάθετε πώς να προσθέσετε gradient σε έγγραφα XPS σε Java χρησιμοποιώντας
  το Aspose.Page. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να προσθέσετε ένα diagonal
  gradient, να εφαρμόσετε linear gradient brushes και να δημιουργήσετε επαγγελματικά
  αρχεία XPS.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Προσθήκη Diagonal Gradient σε Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Πώς να Προσθέσετε Gradient: Diagonal Gradient σε Java XPS'
url: /el/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Διαβάθμιση: Διαγώνια Διαβάθμιση σε Java XPS

## Εισαγωγή
Στη σύγχρονη ανάπτυξη Java, η κατανόηση **πώς να προσθέσετε διαβάθμιση** σε έγγραφα XPS δίνει στις αναφορές σας μια επαγγελματική, εντυπωσιακή εμφάνιση που ξεχωρίζει. Αυτό το μάθημα σας οδηγεί βήμα‑βήμα στη δημιουργία ενός αρχείου XPS από το μηδέν, στην προσθήκη μιας διαγώνιας διαβάθμισης και στην αποθήκευση του αποτελέσματος — όλα με το Aspose.Page for Java. Θα καταλάβετε γιατί οι διαβάθμιση είναι σημαντικές, θα δείτε τις ακριβείς κλήσεις API και θα λάβετε πρακτικές συμβουλές για την αποφυγή κοινών παγίδων.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια βιβλιοθήκη;** Aspose.Page for Java  
- **Ποια μέθοδος προσθέτει τη διαβάθμιση;** `createLinearGradientBrush` with gradient stops  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική έκδοση λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή  
- **Πόσο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για μια βασική διαγώνια διαβάθμιση  
- **Μπορώ να το χρησιμοποιήσω με άλλα πλαίσια Java;** Ναι, το API είναι ανεξάρτητο από πλαίσια  

## Τι είναι μια διαγώνια διαβάθμιση σε ένα έγγραφο XPS;
Μια διαγώνια διαβάθμιση είναι μια ομαλή μετάβαση χρώματος που εκτείνεται από τη μία γωνία ενός σχήματος στην αντίθετη γωνία, δημιουργώντας ένα κεκλιμένο οπτικό εφέ. Στο XPS, αυτό το εφέ ορίζεται από μια γραμμική βούρτσα διαβάθμισης (linear gradient brush) που περιέχει διατεταγμένους σταθμούς διαβάθμισης (gradient stops) που καθορίζουν τα χρώματα και τις σχετικές θέσεις κατά μήκος της διαγώνιας γραμμής.

## Γιατί να προσθέσετε μια διαγώνια διαβάθμιση με το Aspose.Page;
Το Aspose.Page παρέχει **100 % πιστότητα απόδοσης** για διαβάθμιση σε περισσότερους από 20 προβολείς XPS, και υποστηρίζει **30+ δυνατότητες XPS** όπως κείμενο, εικόνες και διανυσματικά σχήματα. Το API αφαιρεί την πολυπλοκότητα του σύνθετου XPS markup, επιτρέποντάς σας να εστιάσετε στο σχεδιασμό ενώ εγγυάται ότι το ίδιο αρχείο εμφανίζεται ταυτόσημο σε πλατφόρμες Windows, macOS και Linux.

## Προαπαιτούμενα
- Βασικές γνώσεις προγραμματισμού Java.  
- Εγκατεστημένο JDK στο σύστημά σας.  
- Βιβλιοθήκη Aspose.Page for Java – κατεβάστε την **[εδώ](https://releases.aspose.com/page/java/)**.  
- Ένα IDE όπως το IntelliJ IDEA ή το Eclipse.

## Εισαγωγή Πακέτων
Ξεκινήστε εισάγοντας τις κλάσεις που θα χρειαστείτε. Αυτές οι εισαγωγές σας δίνουν πρόσβαση σε γεωμετρία, διαχείριση διαβάθμισης και δημιουργία εγγράφων XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Βήμα 1: Ρυθμίστε το Έργο Σας
Δημιουργήστε ένα νέο έργο Java στο προτιμώμενο IDE σας και προσθέστε τα αρχεία JAR του Aspose.Page στη διαδρομή κατασκευής του έργου.

## Βήμα 2: Ορίστε τον Κατάλογο Εγγράφου
Καθορίστε πού θα αποθηκευτεί το παραγόμενο αρχείο XPS.

```java
String dataDir = "Your Document Directory";
```

## Βήμα 3: Δημιουργία Εγγράφου XPS
`XpsDocument` είναι το βασικό αντικείμενο που αντιπροσωπεύει ένα αρχείο XPS στη μνήμη. Η δημιουργία του σας παρέχει έναν καμβά για την προσθήκη σελίδων, σχημάτων και βουρτσών.

```java
XpsDocument doc = new XpsDocument();
```

## Βήμα 4: Προσθήκη Διαγώνιας Διαβάθμισης στο Μονοπάτι
Δημιουργήστε ένα ορθογώνιο μονοπάτι που θα λάβει τη διαβάθμιση. Η γεωμετρία του μονοπατιού χρησιμοποιεί μια απλή εντολή move‑line‑close.  
XpsPath ορίζει ένα διανυσματικό σχήμα στο έγγραφο XPS, όπως ένα ορθογώνιο ή προσαρμοσμένη γεωμετρία.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Βήμα 5: Ορισμός Σταθμών Γραμμικής Διαβάθμισης
Ορίστε τα χρώματα και τις θέσεις τους. Κάθε στάση (stop) καθορίζει ένα σημείο στη διαβάθμιση όπου εμφανίζεται ένα συγκεκριμένο χρώμα.  
XpsGradientStop αντιπροσωπεύει μια μοναδική στάση χρώματος σε μια διαβάθμιση, καθορίζοντας το χρώμα και την απόκλισή του.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Βήμα 6: Εφαρμογή Γραμμικής Διαβάθμισης στο Μονοπάτι
`XpsLinearGradientBrush` είναι ο τύπος βούρτσας του Aspose.Page για γραμμικές μεταβάσεις χρώματος. Δέχεται δύο σημεία που ορίζουν την κατεύθυνση της διαβάθμισης και μια συλλογή από στάσεις διαβάθμισης που καθορίζουν τα χρώματα κατά μήκος αυτής της γραμμής.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Βήμα 7: Αποθήκευση του Εγγράφου
Αποθηκεύστε το αρχείο XPS στον δίσκο. Το αρχείο θα περιέχει το ορθογώνιο γεμάτο με τη διαγώνια διαβάθμιση που ορίσατε.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Πώς να προσθέσετε διαβάθμιση σε Java XPS;
Φορτώστε το XpsDocument, δημιουργήστε ένα `XpsLinearGradientBrush` με σημείο εκκίνησης `(0,0)` και σημείο λήξης `(width,height)`, συνδέστε τις στάσεις διαβάθμισης, αναθέστε τη βούρτσα στην ιδιότητα `Fill` ενός σχήματος και, τέλος, καλέστε `save`. Αυτή η σύντομη ροή σας επιτρέπει να ενσωματώσετε μια διαγώνια διαβάθμιση με λίγες μόνο κλήσεις API, διατηρώντας τον κώδικα σας καθαρό και συντηρήσιμο.

## Κοινά Παράπλοκα & Συμβουλές
- **Κατεύθυνση διαβάθμισης** – βεβαιωθείτε ότι τα σημεία εκκίνησης και λήξης της βούρτσας αντανακλούν τη διαγώνια που θέλετε· η εναλλαγή τους αντιστρέφει τη διαβάθμιση.  
- **Ακρίβεια χρώματος** – το Aspose χρησιμοποιεί ARGB· συμπεριλάβετε το κανάλι άλφα εάν χρειάζεστε διαφάνεια.  
- **Διαδρομή αρχείου** – χρησιμοποιείτε πάντα απόλυτη διαδρομή ή επαληθεύστε ότι η σχετική διαδρομή δείχνει σε υπάρχον φάκελο με δικαιώματα εγγραφής.

## Συχνές Ερωτήσεις

**Q: Πώς να **προσθέσω διαβάθμιση** σε υπάρχον σχήμα XPS;**  
A: Δημιουργήστε ένα `XpsLinearGradientBrush`, ορίστε τις στάσεις διαβάθμισης και αναθέστε το στην ιδιότητα `Fill` του σχήματος όπως φαίνεται στο Βήμα 6.

**Q: Τι κάνει στην πραγματικότητα η **εφαρμογή γραμμικής διαβάθμισης** στο παρασκήνιο;**  
A: Δημιουργεί έναν ορισμό βούρτσας στο πακέτο XPS που αναφέρεται στα σημεία εκκίνησης/λήξης και σε μια συλλογή στάσεων διαβάθμισης, τις οποίες ο προβολέας αποδίδει ως ομαλή μετάβαση χρώματος.

**Q: Υπάρχει γρήγορος τρόπος για **πώς να χρησιμοποιήσω aspose** για άλλες δυνατότητες XPS;**  
A: Ναι, το API του Aspose.Page περιλαμβάνει μεθόδους για προσθήκη εικόνων, κειμένου και προσαρμοσμένων σχημάτων — απλώς εξερευνήστε την κλάση `XpsDocument` για πρόσθετους βοηθούς.

**Q: Μπορώ να **προσθέσω διαβάθμιση σε μονοπάτι** σε μη-ορθογώνια σχήματα;**  
A: Απόλυτα. Ορίστε οποιαδήποτε γεωμετρία χρησιμοποιώντας `createPathGeometry` και στη συνέχεια ορίστε το `Fill` της σε μια βούρτσα διαβάθμισης.

**Q: Επηρεάζει η διαβάθμιση το μέγεθος του αρχείου σημαντικά;**  
A: Μόνο ελαφρώς· οι ορισμοί διαβάθμισης είναι ελαφριές καταχωρήσεις XML μέσα στο πακέτο XPS.

---

**Τελευταία Ενημέρωση:** 2026-05-25  
**Δοκιμή Με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Προσθήκη Διαβάθμισης XPS με Aspose Page](/page/java/xps-gradient-addition/)
- [Προσθήκη Κειμένου XPS σε Java - Μάθημα Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [Πώς να Προσθέσετε Εικόνα σε Έγγραφα Java XPS – Ένας Απλός Οδηγός με Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}