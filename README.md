# dip225-projekta-darbs-hkalnins
# Web Scraping ar Selenium un izvade uz Openpyxl

Šī krātuve satur Python skriptu, kas automatizē procesu produktu meklēšanā iekš salidzini.lv mājaslapas un izdevīgākos piedāvājumus no salidzini.lv izvada izdevīgākos Excel failā, izvadot cenu, preces nosaukumu un preces hipersaiti.

## Saturs

1. `projektdarbs.py` - Šis skripts pieprasa Lietotājam ievadīt produktu un šī produkta minimālo cenu. Pēc kā tas automatizē Lietotāja ievadi iekš salidzini.lv mājaslapas, iekļaujot minimālo cenu, ko Lietotājs būtu gatavs samaksāt par šo produktu. Pēc filtru izmantošanas skripts izvada Excel (.XLSX) formāta failu iekš mapes, kurā tiek atvērts skripts izmantojot MS Visual Studio Code, Excel failā būs norādīta cena, produkta nosaukums un hipersaite. Salidzini.lv ir Latvijas internetveikalu sludinājumu salīdzināšanas mājaslapa, kurā ir pieejami visaktuālākie un vislētākie pakalpojumi un preces.

## Izmantotās Python Bibliotēkas

### `Openpyxl`

- **Description**: `Openpyxl` ir Python bibliotēka lai lasītu un rakstītu Excel failus, tā piedāvā augsta līmeņa saskarsni lai veidotu un rediģetu .xlsx failus.
- **Usage in this Project**: Šajā projektā, `Openpyxl` ir pielietots lai izvadītu izdevīgākos sludinājumus no salidzini.lv mājaslapas un pievienotu tos iekš Excel .xslx faila. Kolonna A iekš faila ir cena. Kolonna B ir produkta nosaukums un Kolonna C ir sludinājuma hipersaite. Excel failā Openpyxl tiek izmantots arī lai iestatītu šūnas izmēru, lai šūna būtu tik plata, cik plata ir garākā simbolu virkne jebkurā no tās kolonnas šūnām.

### `Selenium`

- **Description**: `Selenium` ir spēcīgs rīku kopums, kas ļauj automatizēt Lietotāja darbības interneta pārlūkprogrammā.
- **Usage in this Project**: Šajā projektā, `Selenium` ir pielietots lai automatizētu Lietotāja saskarsmi ar interneta pārlūkprogrammu un izgūtu informāciju, jeb sludinājumus no salidzini.lv mājaslapas. Tā pirmkārt, apstiprina mājaslapas `Cookies`, tad ievada pirmajā skripta palaišanas solī ievadīto tekstu, kas ir šis produkts iekš salidzini.lv meklēšanas funkcijas un tad nospiežot search atrod izdevīgākos sludinājumus, pēc kā tā automatizē un uzliek filtru, tā cenu, kuru ir ievadījis Lietotājs otrajā solī. Pēc šī procesa tiek izgūti pirmās lapas pirmie divdesmit sludinājumi, kas tiek saglabāti iekš rindas.

## Uzstādīšana un izmantošana

### Nepieciešamības

- Python 3.x
- Python izstrādes vide (Visual Studio Code vai IDLE, Anaconda)
- Openpyxl un Selenium bibliotēkas

### Skriptu palaišana

Lai palaistu skriptu ir nepieciešams to atvērt iekš kādas no Python izstrādes vidēm, tas var būt iekš Visual Studio Code, IDLE, Anaconda.

Skripts pieprasa jums ievadīt produktu un tā minimālo cenu. Pēc kā skripts piemeklēs ievadīto produktu iekš salidzini.lv mājaslapas un uzliks arī minimālās cenas filtru un izvadīs pirmos divdesmit izdevīgākos piedāvājumus no mājaslapas salidzini.lv iekš Excel faila un tad saglabās šo Excel failu tajā pašā mapē, kurā ir saglabāts `projektdarbs.py`.

Piezīme: Ja jūs vēlaties nomainīt interneta pārlūku, kuru jūs lietojat lai palaistu skriptu ir nepieciešams iekš skripta izmainīt interneta pārluka nosaukumu.
Nepieciešams izmainīt šīs rindiņas -
    option = webdriver.ChromeOptions()
    driver = webdriver.Chrome(service=service, options=option)
Uz
 option = webdriver.____Options()
 driver = webdriver._____(service=service, options=option)
 a)Apakšsvītru vietā rakstot Firefox, ja tiek izmantots Mozilla Firefox.
 b)Apakšsvītru vietā rakstot Edge, ja tiek izmantots Microsoft Edge
 c)Apakšsvītru vietā rakstot Safari, ja tiek izmantots Apple Safari.

## Izvade

Skripta izvade iekš Excel faila ir nosaukta kā vārdi vai vārds, ko ir ievadījis Lietotājs katru reizi palaižot šo kodu un tas satur no šādām kolonnām

1. Cena: Produkta cena piedāvājumā.
2. Nosaukums: Produkta nosaukums, kas norādīts piedāvājumā.
3. Hipersaite: Produkta hipersaite, lai varētu piekļūt šim produktam.
Excel fails ir saglabāts tajā pašā mapē, kurā saglabāts ir pats skripts.

## Izmantotie resursi
1.https://www.selenium.dev/documentation/webdriver/elements/locators/ Resurss tika izmantots, lai varētu atrast nepieciešamos mājaslapas elementus pēc XPATH, jo pēc ID bija neiespējami atpazīt piedāvājumus.
2.https://www.selenium.dev/documentation/webdriver/browsers/ Resurss tika izmantots lai dokumentācijā uzrakstītu par, ja ir nepieciešams nomainīt interneta pārlūku.
3.https://stackoverflow.com/questions/13197574/openpyxl-adjust-column-width-size Resurss tika izmantots, lai skripts automātiski nomainītu Excel kolonnas platumu, balstoties uz jebkurā rindā esošo garāko simbolu kopu. Iekš Excel manuāli tas ir izdarāms nospiežot dubultklikšķi uz platuma maināmās kolonnas malas.
