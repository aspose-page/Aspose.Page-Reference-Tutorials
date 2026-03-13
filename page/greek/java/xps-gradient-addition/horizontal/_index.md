---
date: 2026-03-13
description: Μάθετε πώς να προσθέτετε διαβάθμιση σε έγγραφα XPS στη Java χρησιμοποιώντας
  το Aspose.Page και πώς να προσαρμόζετε τα σημεία διαβάθμισης για εντυπωσιακά οριζόντια
  εφέ.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Πώς να προσθέσετε διαβάθμιση – Οριζόντια διαβάθμιση σε Java XPS
url: /el/java/xps-gradient-addition/horizontal/
weight: 11
---

 Greek translations.

Make sure to keep markdown formatting exactly.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε διαβάθμιση – Οριζόντια διαβάθμιση σε Java XPS

## Εισαγωγή
Καλώς ήρθατε σε αυτόν τον οδηγό βήμα‑βήμα για **πώς να προσθέσετε διαβάθμιση** σε ένα έγγραφο XPS χρησιμοποιώντας Java. Σε αυτό το tutorial θα μάθετε πώς να προσθέσετε μια οριζόντια διαβάθμιση, γιατί είναι σημαντική για το οπτικό φινίρισμα, και πώς να **προσαρμόσετε τα σημεία διαβάθμισης** για ακριβή έλεγχο χρωμάτων. Το Aspose.Page for Java κάνει τη δουλειά με έγγραφα XPS (XML Paper Specification) απλή, επιτρέποντάς σας να εστιάσετε στο σχεδιασμό αντί στη χαμηλού επιπέδου διαχείριση αρχείων.

## Γρήγορες Απαντήσεις
- **Τι βιβλιοθήκη χρειάζεται;** Aspose.Page for Java  
- **Ποια έκδοση Java λειτουργεί;** Any Java 8+ runtime  
- **Χρειάζομαι άδεια;** A free trial works for development; a commercial license is required for production  
- **Μπορώ να αλλάξω την κατεύθυνση της διαβάθμισης;** Yes – just modify the start/end points of the linear brush  
- **Είναι δυνατόν να προσθέσετε πολλαπλές διαβάθμιση;** Absolutely – repeat the path creation steps with different brushes  

## Τι είναι η Οριζόντια Διαβάθμιση σε XPS;
Μια οριζόντια διαβάθμιση είναι μια ομαλή μετάβαση χρωμάτων από τα αριστερά προς τα δεξιά μέσα σε ένα σχήμα. Στο XPS αντιπροσωπεύεται από ένα γραμμικό πινέλο διαβάθμισης που παρεμβάλλει μεταξύ των ορισμένων **σημείων διαβάθμισης**. Αυτό το οπτικό εφέ χρησιμοποιείται συχνά για banners, κουμπιά και γεμίσματα φόντου.

## Γιατί να Χρησιμοποιήσετε το Aspose.Page για Java;
- **Πλήρης υποστήριξη XPS** – δημιουργία, επεξεργασία και απόδοση χωρίς εργαλεία τρίτων.  
- **Απλό API** – high‑level objects like `XpsDocument`, `XpsPath`, and `XpsGradientBrush` hide the XML complexity.  
- **Απόδοση** – optimized for large documents and batch processing.  

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

1. **Περιβάλλον Ανάπτυξης Java** – Install the latest JDK from [java.com](https://www.java.com).  
2. **Βιβλιοθήκη Aspose.Page for Java** – Download the JAR from the [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  

## Εισαγωγή Πακέτων
Ξεκινήστε εισάγοντας τις απαραίτητες κλάσεις. Αυτές οι εισαγωγές σας δίνουν πρόσβαση στη δημιουργία εγγράφου, τη διαχείριση διαβάθμισης και τη βασική γεωμετρία.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Βήμα 1: Αρχικοποίηση του XPS Εγγράφου
Δημιουργήστε μια νέα παρουσία `XpsDocument` και ορίστε το φάκελο όπου θέλετε να αποθηκεύσετε το αποτέλεσμα.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Βήμα 2: Δημιουργία Οριζόντιας Διαβάθμισης
Ορίστε μια λίστα από **σημεία διαβάθμισης** που ελέγχουν το χρώμα και τη θέση κάθε σημείου μετάβασης. Το παρακάτω παράδειγμα δημιουργεί μια ζωντανή διαβάθμιση τύπου ουράνιου τόξου.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Πώς να προσαρμόσετε τα σημεία διαβάθμισης
- **Χρώμα** – Use `doc.createColor(alpha, red, green, blue)` to set any ARGB value.  
- **Θέση** – The second argument (`float` between `0` and `1`) defines where the stop appears along the gradient line. Adjust these values to shift colors left or right.

## Βήμα 3: Προσθήκη Διαδρομής με Διαβάθμιση
Δημιουργήστε μια ορθογώνια διαδρομή, εφαρμόστε μετασχηματισμό αν χρειάζεται, και γεμίστε την με το γραμμικό πινέλο διαβάθμισης. Το πινέλο χρησιμοποιεί δύο σημεία (`(10,0)` έως `(228,0)`) για να παράγει οριζόντιο αποτέλεσμα. Επειδή οι συντεταγμένες Y είναι ίδιες, αυτό το πινέλο λειτουργεί ως **οριζόντιο πινέλο διαβάθμισης**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** Η επαναχρησιμοποίηση της ίδιας λίστας `stops` για πολλαπλές διαδρομές μπορεί να βελτιώσει την απόδοση, αλλά θυμηθείτε να καλέσετε `clear()` πριν προσθέσετε νέα σημεία.

## Βήμα 4: Αποθήκευση του Εγγράφου
Αποθηκεύστε το αρχείο XPS στον δίσκο. Τώρα μπορείτε να το ανοίξετε με οποιονδήποτε προβολέα XPS για να δείτε την οριζόντια διαβάθμιση σε δράση.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Πώς να Εφαρμόσετε Πολλαπλές Διαβάθμιση
Αν θέλετε να **εφαρμόσετε πολλαπλές διαβάθμιση** στο ίδιο έγγραφο XPS, απλώς επαναλάβετε τα βήματα “Δημιουργία Οριζόντιας Διαβάθμισης” και “Προσθήκη Διαδρομής με Διαβάθμιση” για κάθε νέο σχήμα. Χρησιμοποιήστε μια νέα λίστα αντικειμένων `XpsGradientStop` (ή καθαρίστε την υπάρχουσα λίστα) και εκχωρήστε ένα νέο `LinearGradientBrush` με τα δικά του σημεία έναρξης/λήξης. Αυτή η προσέγγιση σας επιτρέπει να στρώσετε διαβάθμιση, να δημιουργήσετε σύνθετα φόντα ή να τονίσετε διαφορετικά UI στοιχεία σε μία σελίδα.

## Γιατί Είναι Σημαντικό – Οφέλη της Οριζόντιας Διαβάθμισης
- **Οπτικό βάθος:** A horizontal gradient brush adds a subtle three‑dimensional feel without extra images.  
- **Αποδοτικότητα μεγέθους αρχείου:** Gradients are stored as vector definitions, keeping the XPS file lightweight.  
- **Κλιμακωσιμότητα:** Because the gradient is vector‑based, it scales cleanly on high‑resolution displays.  

## Συχνά Προβλήματα & Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Η διαβάθμιση εμφανίζεται στερεή | Δεν έχουν προστεθεί σημεία διαβάθμισης ή δεν έχει οριστεί η πινέλο | Βεβαιωθείτε ότι το `path.setFill(...)` χρησιμοποιεί ένα `LinearGradientBrush` και ότι τα σημεία προστίθενται μέσω `getGradientStops().addAll(stops)`. |
| Τα χρώματα φαίνονται αχνά | Λανθασμένη τιμή alpha (πρώτη παράμετρος) | Χρησιμοποιήστε `255` για πλήρως αδιαφανή χρώματα εκτός εάν επιθυμείτε διαφάνεια. |
| Το μέγεθος της διαδρομής είναι λανθασμένο | Οι τιμές του μετασχηματισμού matrix είναι λανθασμένες | Ρυθμίστε τις παραμέτρους του matrix (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Συχνές Ερωτήσεις

**Q: Μπορώ να εφαρμόσω πολλαπλές διαβάθμιση σε ένα μόνο έγγραφο XPS;**  
A: Ναι, μπορείτε να προσθέσετε πολλαπλές διαδρομές, καθεμία με το δικό της πινέλο διαβάθμισης, για να δημιουργήσετε σύνθετα στρωμένα σχέδια.

**Q: Είναι το Aspose.Page συμβατό με τις τελευταίες εκδόσεις Java;**  
A: Το Aspose.Page for Java ενημερώνεται τακτικά και λειτουργεί με Java 8 και νεότερες εκδόσεις.

**Q: Υπάρχουν άλλοι τύποι διαβάθμισης διαθέσιμοι στο Aspose.Page;**  
A: Εκτός από γραμμικές διαβάθμιση, το Aspose.Page υποστηρίζει επίσης radial gradients για κυκλικές μεταβάσεις χρώματος.

**Q: Μπορώ να προσαρμόσω τα χρώματα και τις θέσεις των σημείων διαβάθμισης;**  
A: Απόλυτα! Έχετε πλήρη έλεγχο πάνω σε κάθε ARGB χρώμα σημείου και στη σχετική του θέση (εύρος 0‑1).

**Q: Υπάρχει φόρουμ κοινότητας για το Aspose.Page όπου μπορώ να ζητήσω βοήθεια;**  
A: Ναι, μπορείτε να επισκεφθείτε το [Aspose.Page forum](https://forum.aspose.com/c/page/39) για να συνδεθείτε με την κοινότητα και να λάβετε υποστήριξη.

---

**Τελευταία Ενημέρωση:** 2026-03-13  
**Δοκιμάστηκε Με:** Aspose.Page for Java 24.11  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}