# Vaizdų ir vaizdo įrašų analizės sistema

### Naudoti Metodai ir Bibliotekos:

Projektas naudoja šias pagrindines technologijas:

YOLOv8 – objektų atpažinimui iš vaizdų ir vaizdo įrašų.

OpenCV – vaizdų apdorojimui ir transformacijoms (triukšmo pridėjimas, rezoliucijos mažinimas, JPEG artefaktai).

NumPy – matricų ir skaičiavimų operacijoms.

Matplotlib – rezultatų vizualizavimui.

scikit-learn (KMeans) – kadrų klasterizavimui pagal aptikimo kokybę.

Google Colab – failų įkėlimui ir rezultatų saugojimui (naudojamas Google Drive).

### Sistemos Veikimas:

Projektas sudarytas iš dviejų pagrindinių modulių:

#### Vaizdų analizė

Naudojami degradacijos metodai: Gauso suliejimas, triukšmo pridėjimas, rezoliucijos mažinimas, JPEG suspaudimas.

Kiekvienam apdorotam vaizdui atliekama objektų atpažinimo analizė naudojant YOLOv8 modelį.

Rezultatai pateikiami su aptiktais objektais ir jų pasitikėjimo lygiais.

#### Vaizdo įrašų analizė

Vaizdo įrašas suskaidomas į atskirus kadrus.

Kiekviename kadre atliekamas objektų atpažinimas.

Kadrai grupuojami naudojant KMeans klasterizaciją pagal atpažinimo pasitikėjimą.

Identifikuojami mažo pasitikėjimo kadrai.

### Iškilusios Problemos ir Sprendimai

Triukšmingų duomenų įtaka: Aptikimo modelis kartais negalėjo atpažinti objektų dėl per didelio triukšmo.

Sprendimas: Optimizuoti degradacijos metodų parametrus, kad išlaikytume realistiškus iškraipymus.

Aukštas skaičiavimo našumo poreikis: Vaizdo įrašų analizė užima daug laiko.

Sprendimas: Analizuoti tik kas n-tą kadrą arba naudoti efektyvesnius vaizdų apdorojimo metodus.

Mažo pasitikėjimo rezultatai: Kai kurie vaizdai generavo labai mažo pasitikėjimo aptikimus.

Sprendimas: Klasterizavimo metodu išryškinti mažo pasitikėjimo kadrus, kad būtų galima juos iš naujo analizuoti.

### Sistemos Paleidimo Instrukcijos

Google Colab aplinka:

Įkelkite reikiamus failus („test.jpg“ arba „path_to_video.mp4“).

Paleiskite atitinkamą skriptą:

Vaizdams: analyze_image("test.jpg")

Vaizdo įrašams: extract_frames("path_to_video.mp4", output_folder) ir analyze_frames(output_folder).

Reikalingos bibliotekos (jei naudojate lokaliai):

pip install ultralytics opencv-python numpy matplotlib scikit-learn

### Rezultatų peržiūra:

Sugeneruoti vaizdai su aptiktais objektais bus atvaizduojami „Matplotlib“ lange.

Analizės rezultatai saugomi Google Drive (/content/drive/My Drive/Image_ND/frames).

### 3ND

3 namų darbas yra patalpintas:

#### https://huggingface.co/spaces/ItsMantax/3ND
