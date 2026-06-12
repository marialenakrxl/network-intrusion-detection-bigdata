# Network Intrusion Detection - Big Data & Data Mining Project

Η παρούσα εργασία πραγματοποιήθηκε στο πλαίσιο του μαθήματος **Διαχείριση Δεδομένων Μεγάλης Κλίμακας** και έχει ως θέμα την **ανίχνευση εισβολών σε δίκτυα υπολογιστών**.

Στόχος της εργασίας είναι η ανάλυση δεδομένων δικτυακής κίνησης και η εφαρμογή τεχνικών **Data Mining**, **Machine Learning** και **Big Data Processing**, ώστε να γίνει διάκριση ανάμεσα σε φυσιολογική και κακόβουλη δραστηριότητα.

## Dataset

Χρησιμοποιήθηκε το dataset **Network Intrusion Detection** από την πλατφόρμα Kaggle.

Το dataset περιλαμβάνει δύο αρχεία:

* `Train_data.csv`
* `Test_data.csv`

Το `Train_data.csv` χρησιμοποιήθηκε για την ανάλυση, την προεπεξεργασία, την εκπαίδευση και την αξιολόγηση των μοντέλων.
Το `Test_data.csv` δεν περιλαμβάνει τη στήλη `class`, επομένως η αξιολόγηση έγινε με διαχωρισμό του training dataset σε 80% training και 20% testing.

## Περιεχόμενα Repository

```text
network-intrusion-detection-bigdata/
│
├── bigData.ipynb
├── data/
│   ├── Train_data.csv
│   └── Test_data.csv
├── .gitignore
└── README.md
```

## Βήματα Υλοποίησης

Η εργασία ακολουθεί τα βασικά στάδια μιας διαδικασίας Data Mining:

1. Data Understanding & Preprocessing
2. Exploratory Data Analysis (EDA)
3. Εφαρμογή αλγορίθμων
4. Model Evaluation
5. Σύγκριση μοντέλων
6. Συμπεράσματα

## Preprocessing

Στο στάδιο της προεπεξεργασίας έγινε:

* έλεγχος των διαστάσεων του dataset
* έλεγχος για missing values
* εξέταση βασικών στατιστικών χαρακτηριστικών
* μετατροπή κατηγορικών μεταβλητών με one-hot encoding
* διαχωρισμός του dataset σε training και testing set

Μετά την κωδικοποίηση, το dataset περιλάμβανε 118 χαρακτηριστικά.

## Αλγόριθμοι που χρησιμοποιήθηκαν

Στην εργασία εφαρμόστηκαν:

* **Naive Bayes**
* **Decision Tree**
* **K-Means Clustering**
* **PySpark**

Τα μοντέλα Naive Bayes και Decision Tree χρησιμοποιήθηκαν για ταξινόμηση, ενώ το K-Means εφαρμόστηκε ως προηγμένη τεχνική ομαδοποίησης. Το PySpark χρησιμοποιήθηκε για βασική Big Data επεξεργασία του dataset.

## Model Evaluation

Τα μοντέλα αξιολογήθηκαν με τις εξής μετρικές:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC Curve

Ιδιαίτερη σημασία δόθηκε στο **recall**, επειδή στην ανίχνευση εισβολών είναι σημαντικό να εντοπίζονται όσο το δυνατόν περισσότερες πραγματικές επιθέσεις ή ανωμαλίες.

## Συμπέρασμα

Από τη σύγκριση των μοντέλων προέκυψε ότι το **Decision Tree** είχε την καλύτερη συνολική απόδοση στο συγκεκριμένο dataset.

Το **Naive Bayes** παρουσίασε υψηλό precision, αλλά χαμηλό recall, με αποτέλεσμα να χάνει αρκετές πραγματικές anomaly εγγραφές. Αντίθετα, το **Decision Tree** πέτυχε υψηλό accuracy, precision, recall και F1-score, εντοπίζοντας σχεδόν όλες τις μη φυσιολογικές εγγραφές.

Συνεπώς, για τη συγκεκριμένη πειραματική διαδικασία, το Decision Tree θεωρείται το καταλληλότερο μοντέλο.
