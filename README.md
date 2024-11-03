Pregled podatkovne zbirke
Podatki so bili pridobljeni iz javno dostopnih repozitorijev na Kaggle.com in Google Scholar Datasets. Osredotočili smo se na zbirke, ki vsebujejo tako zdrave kot okužene rastline, ter dodatne posamezne zbirke samo zdravih ali samo bolnih primerkov. Vsaka vrsta rastline je organizirana v ločene mape, razdeljene na zdrave in bolne primerke. Na primer, paprike so razdeljene v dve mapi: pepper_healthy in pepper_sick, pri čemer vsaka mapa vsebuje podmape za posamezne bolezni, ki vplivajo na to vrsto rastline.

Augmentacija slik
Za izboljšanje robustnosti in posplošitve modela so bile slike zajete pod različnimi koti in z različnimi svetlobnimi pogoji. Nadaljnje metode augmentacije podatkov so bile uporabljene, vključno z:

Rotacijo (90°, 180° in 270°)
Horizontalnim in vertikalnim zrcaljenjem
S tem zagotavljamo raznolik učni nabor, ki modelu pomaga pri generalizaciji na nove slike.

Predprocesiranje
Slike so bile predprocesirane za zagotavljanje kakovosti in doslednosti:

Čiščenje: Odstranili smo slike slabe kakovosti ali podvojene slike.
Normalizacija: Intenziteta vsakega piksla je bila skalirana v razpon [0, 1].
Standardizacija: Vrednosti pikslov so bile prilagojene tako, da imajo povprečje 0 in standardni odklon 1.
Spreminjanje velikosti: Slike so bile prilagojene na 256x256 pikslov za doslednost vhodov v model.
Organizacija podatkovne zbirke
Healthy_Sick: Slike, kategorizirane v zdrave in bolne rastline (skupaj 11,988 primerkov, 5,994 za Healthy in 5,994 za Sick).
Sick: Slike, kategorizirane po posameznih boleznih za vsako rastlinsko vrsto.
Species: Slike, kategorizirane po vrsti rastlin (skupaj 11,988 primerkov, po 1,998 za vsako vrsto).
test_Healthy_Sick: Testne slike za klasifikacijo zdrave proti bolne (skupaj 128 primerkov, 64 za Healthy in 64 za Sick).
test_SPECIES: Testne slike za klasifikacijo po vrstah rastlin.
test_sick: Testne slike za klasifikacijo specifičnih bolezni.
Razdelitev podatkov
Podatkovna zbirka je razdeljena na učni, validacijski in testni nabor:

Klasifikacija vrst: 11,988 primerkov za učenje in validacijo, enakomerno porazdeljenih med zdrave in bolne primerke za vsako vrsto rastline.
Klasifikacija bolezni: Skupaj 3,000 primerkov na rastlinsko vrsto, kar vključuje tisoč primerkov za zdrave rastline in po tisoč primerkov za vsako bolezen.
Klasifikacija zdravja: Prvotno smo predvideli 360 primerkov za določitev zdravstvenega stanja rastline brez specifikacije bolezni ali vrste, vendar smo kasneje, zaradi opaženih odstopanj, uporabili enakih 11,988 primerkov kot pri klasifikaciji vrst, razdeljenih le na Healthy in Sick.
Vsaka naloga klasifikacije uporablja uravnotežen nabor podatkov, medtem ko so bili validacijski in testni nabori izbrani tako, da ohranjajo originalno strukturo podatkov z manjšim številom primerkov.

Uporaba
Podatkovna zbirka je primerna za treniranje modelov strojnega učenja za:

Klasifikacijo vrst: Identifikacijo vrste rastline na podlagi značilnosti lista.
Klasifikacijo zdravja: Določitev zdravstvenega stanja (zdrav ali bolan).
Klasifikacijo bolezni: Identifikacijo specifičnih bolezni, ki vplivajo na rastline.
Končne podatkovne zbirke so zasnovane tako, da zagotavljajo celovit pokritost različnih vrst rastlin in bolezni ter omogočajo uravnoteženo predstavitev vseh razredov.
