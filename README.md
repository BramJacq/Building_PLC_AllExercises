# 🏭 Building_PLC_AllExercises

---

## 📂 Projectstructuur

📂 Open hoofdmap  
[`Building_Excercises_Oefeningen1`](./Building_Excercises_Oefeningen1)

---

## 📁 Oefeningen 1 — POUs  
📂 Map:  
[`Building_Excercises_Oefeningen1/Oefeningen1/POUs`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs)

| Oefening | Programma (.TcPOU) |
|--------|------------------|
| Main (alle programma’s oproepen) | [`MAIN.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/MAIN.TcPOU) |
| Ja-functie | [`prg_jafunctie.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_jafunctie.TcPOU) |
| Twee signalen | [`prg_TweeSignalen.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_TweeSignalen.TcPOU) |
| Reactorvat | [`prg_Reactorvat.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_Reactorvat.TcPOU) |
| Opslagvat | [`prg_Opslagvat.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_Opslagvat.TcPOU) |
| Opslagvat foutdetectie | [`PRG_OpslagFoutDetectie.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/PRG_OpslagFoutDetectie.TcPOU) |
| Alarmbewaking | [`prg_Alarmbewaking.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_Alarmbewaking.TcPOU) |
| Teleruptorschakeling | [`prg_Teleruptorschakeling.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_Teleruptorschakeling.TcPOU) |
| Motor met 1 drukknop | [`prg_MotorMetDrukknop.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_MotorMetDrukknop.TcPOU) |
| Twee pompen | [`prg_TweePompen.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_TweePompen.TcPOU) |
| Drie pompen | [`prg_DriePompen.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen1/POUs/prg_DriePompen.TcPOU) |

---

## 📝 Oefeningen 1 — Opgaves

### Ja-functie
- Programmeer een JA-functie
- De uitgang volgt de ingang:
  - ingang = 1 → uitgang = 1
  - ingang = 0 → uitgang = 0

---

### Twee signalen (2 regels code)
- Vergelijk signalen **S01** en **S02**
- Uitgangen:
  - S01 = 1 en S02 = 0 → Q01 brandt
  - S01 = 0 en S02 = 1 → Q02 brandt
  - S01 = 0 en S02 = 0 → Q01 en Q02 branden
  - S01 = 1 en S02 = 1 → Q01 en Q02 branden niet
- Maximaal **2 regels code**

---

### Reactorvat (3 regels code)
- Installatie werkt enkel als hoofdschakelaar **S05 AAN** staat
- Detectoren:
  - S01 → niveau te hoog
  - S02 → temperatuur te hoog
  - S03 → druk te hoog
- Acties:
  - 1 detector actief → oranje lamp **Q01**
  - 2 detectoren actief → rode lamp **Q02**
  - 3 detectoren actief → **Q01**, **Q02** en bel **Q05**
- Bel blijft rinkelen tot stopdrukknop **S04** wordt ingedrukt

---

### Opslagvat (4 regels code)
- Twee niveausensoren: laag en hoog
- Klep **K1**:
  - opent automatisch als vat leeg is
  - sluit automatisch als vat vol is
- Pomp **P1**:
  - start/stop via drukknoppen
  - stopt automatisch als vat leeg is
- Pomp kan niet starten zolang de tank gevuld wordt

---

### Opslagvat met foutdetectie (0 extra regels)
- Onmogelijke situatie:
  - onderste sensor = FALSE
  - bovenste sensor = TRUE
- In dit geval:
  - klep **K1** mag niet actief zijn
  - pomp **P1** mag niet actief zijn

---

### Alarmbewaking (6 regels code)
- Sensoren:
  - Sensor1 → druk (TRUE = te hoog)
  - Sensor2 → temperatuur (TRUE = te hoog)
  - Sensor3 → niveau (FALSE = te laag)
- Lampen:
  - Lamp1 → druk te hoog
  - Lamp2 → temperatuur te hoog
  - Lamp3 → niveau te laag
  - Lamp4 → exact twee alarmen actief
  - Lamp5 → drie alarmen actief (blijft aan tot resetknop)

---

### Teleruptorschakeling (2 regels)
- Verlichting schakelen met meerdere parallelle drukknoppen
- Elke druk verandert de toestand van de lamp (aan ↔ uit)
- Gebruik flankdetectie (**R_TRIG**)

---

### Motor starten met één drukknop (5 regels code)
- Installatie werkt enkel met hoofdschakelaar AAN
- Eén drukknop stuurt:
  1. Start links
  2. Stop
  3. Start rechts
  4. Stop
- Relais MotorLinks en MotorRechts nooit tegelijk actief

---

### Twee pompen  
(2 regels code + 4 regels voor inversie)
- Tank wordt gevuld met twee pompen
- Pompen werken om beurten
- Start:
  - manueel via startdrukknop
  - automatisch via niveauschakelaar onderin
- Stop:
  - manueel via stopdrukknop
  - automatisch via niveauschakelaar bovenaan
- Installatie werkt enkel met hoofdschakelaar AAN

---

### Drie pompen (5 regels code)
- Tank wordt gevuld met drie pompen
- Installatie werkt enkel met hoofdschakelaar AAN
- Eén drukknop schakelt:
  - 1 pomp → 2 pompen → 3 pompen
- Tweede drukknop schakelt alle pompen uit

---

## 📁 Oefeningen 2 — POUs  
📂 Map:  
[`Building_Excercises_Oefeningen1/Oefeningen2/POUs`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs)

| Oefening | Programma (.TcPOU) |
|--------|------------------|
| Main | [`MAIN.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs/MAIN.TcPOU) |
| Potentiometer | [`prg_PotentioMeter.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs/prg_PotentioMeter.TcPOU) |
| Dynamisch verschalen | [`prg_DynamischVerschalen.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs/prg_DynamischVerschalen.TcPOU) |
| Analoge waarden visualiseren | [`Visualization_DynamischVerschalen.TcVIS`](./Building_Excercises_Oefeningen1/Oefeningen2/VISUs/Visualization_DynamischVerschalen.TcVIS) |
| Toleranties en Hysteresis | [`prg_TolerantiesEnHysteresis.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs/prg_TolerantiesEnHysteresis.TcPOU) |
| Display | [`prg_VerschalenDisplay.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs/prg_VerschalenDisplay.TcPOU) |
| Processbewaking 3 vaten | [`prg_Processbewaking3Vaten.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen2/POUs/prg_Processbewaking3Vaten.TcPOU) |
---

## 📝 Oefeningen 2 — Opgaves

### Potentiometer inlezen en verschalen (%)
- Lees de potentiometer in
- Verschaal naar een waarde tussen **0 en 100**
- Voeding via EL4002 (channel 2 = initial value 32767)

---

### Dynamisch verschalen
- Declareer **nScaledMax (INT, initial value = 10)**
- Verschaal de potentiometer naar **0 – nScaledMax**

---

### Analoge waarden visualiseren
- Maak een visualisatie met:
  - instelbare maximumwaarde (**nScaledMax**)
  - actuele verschaalde waarde
- Gebruik twee rectangles in VISU

---

### Analoge waarde met toleranties en hysteresis
- Lees potentiometer in en schaal naar **0–250°C** (nGemeten)
- Stel via visualisatie **nGevraagd** in (180–230°C)
- Gedrag:
  - >10% onder gevraagd → rode LED
  - >10% boven gevraagd → groene LED
  - binnen 10% → vorige toestand behouden
- Visualiseer beide waarden en LED-status

---

### Verschalen en weergave op display
- Toon spanning van de potentiometer op het display
- Bereik: 0–10 V → 0–1000 (per 0.01 V)
- Displaybereik: –100 tot +2000

---

### Procesbewaking van 3 vaten
- Inhoud vaten:
  - Vat 1: max. 2000 L
  - Vat 2: max. 3000 L
  - Vat 3: max. 5000 L
- Simuleer ingangen
- Visualiseer:
  - inhoud per vat
  - totale som
- Gebruik 3 sliders en 1 bar display

---

## 📁 Oefeningen 3 — POUs  
📂 Map:  
[`Building_Excercises_Oefeningen1/Oefeningen3/POUs`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs)

| Oefening | Programma (.TcPOU) |
|--------|------------------|
| Main | [`MAIN.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/MAIN.TcPOU) |
| Teleruptor | [`prg_Teleruptor.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Teleruptor.TcPOU) |
| Startveiligheid | [`prg_Startveiligheid.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Startveiligheid.TcPOU) |
| Trappenhuisautomaat verlenging | [`prg_TrappenhuisautomaatVerlenging.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_TrappenhuisautomaatVerlenging.TcPOU) |
| Trappenhuisautomaat tijdsinstelling | [`prg_TrappenhuisautomaatTijdsinstelling.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_TrappenhuisautomaatTijdsinstelling.TcPOU) |
| Knipperlicht | [`prg_Knipperlicht.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Knipperlicht.TcPOU) |
| Millis | [`prg_Millis.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Millis.TcPOU) |
| Openbaar toilet | [`prg_OpenbaarToilet.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_OpenbaarToilet.TcPOU) |
| Automatische deur | [`prg_AutomatischeDeur.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_AutomatischeDeur.TcPOU) |
| Setpointsturing | [`prg_Setpointsturing.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Setpointsturing.TcPOU) |
| Draairichting motor | [`prg_DraaiRichtingMotor.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_DraaiRichtingMotor.TcPOU) |
| Belsignaal | [`prg_Belsignaal.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Belsignaal.TcPOU) |
| Parking | [`prg_Parking.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_Parking.TcPOU) |
| Producten tellen | [`prg_ProductenTellen.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3/POUs/prg_ProductenTellen.TcPOU) |
---

## 📝 Oefeningen 3 — Opgaves

---
### Oefeningen (Timers)
---

#### Teleruptor bediening
Een teleruptor, ook wel bekend als een impulsrelais, is een relais die ontworpen is om een elektrische belasting, zoals verlichting, aan/uit te schakelen met één enkele impuls. Wanneer een impuls wordt toegepast (bijvoorbeeld door een drukknop in te drukken), schakelt de teleruptor de belasting in. Als er opnieuw een impuls wordt toegepast, schakelt de teleruptor de belasting uit.

De A9C30112 teleruptor van Schneider heeft bijvoorbeeld een impulsduur van 50 ms... 1 s. Dit wil zeggen dat een puls minder dan 50ms de teleruptor niet doet schakelen en bij 1001ms zelf een tweede maal doet schakelen.

Schrijf in één enkele regel code een programma dat een 60ms puls genereert voor bKeuken (= de keukenlamp) bij het indrukken van één van de drukknoppen bDrukKeuken1, bDrukLiving2 en bDrukGang2. Dit moet ongeacht hoelang deze drukknoppen ingedrukt worden slechts eenmaal gebeuren. Geef je timer de naam fbKeuken.

---

#### Startveiligheid
Om er zeker van te zijn dat de machine niet ondoordacht wordt gestart, moet de drukknop 5s ingedrukt worden vooraleer de machine effectief start. Gebruik hiervoor een bStart, fbStart en bMachine. Schrijf dit in één enkele regel code.

---

#### Trappenhuisautomaat met extra verlenging (1 regel)
In een appartementsgebouw staan in de traphal op de verschillende verdiepingen in totaal 6 drukknoppen. Als men één van de drukknoppen bedient gaat de verlichting branden. De verlichting blijft 3min. branden - tijdens de test gebruikt men 3s - vooraleer deze vanzelf uitschakelt.

Bij iedere bediening van een drukknop zal de tijd terug beginnen te lopen vanaf 0 en blijven de lampen branden tot de ingestelde tijd is afgelopen.

---

#### Trappenhuisautomaat met tijdsinstelling (4 regels)
In een appartementsgebouw staan in de traphal op de verschillende verdiepingen in totaal 6 drukknoppen. Als men één van de drukknoppen bedient gaat de verlichting branden. De verlichting blijft 3min. branden - tijdens de test gebruikt men 3s - vooraleer deze vanzelf uitschakelt.

Bij iedere bediening van een drukknop zullen de lampen manueel kunnen gedoofd worden.

---

#### Knipperlicht (2 regels)
Schrijf een programma waarbij een lampje knippert aan een frequentie van 1 Hz – 50% Duty Cycle.

Uitbreiding: zorg dat de frequentie instelbaar is via de potentiometer met 500ms als minimum en 10s als maximum waarde.  
Maak ook hier gebruik van de conversion operators.

Uitbreiding: Ontwerp een knipperlamp met 4 verschillende knipperfrequenties. De frequentie stijgt naarmate het analoge ingangsspanning vanuit de potentiometer stijgt. Bij een ingangsspanning lager dan 2V knippert het lampje met een frequentie van 0.5Hz, tussen 2 en 4V 1 Hz, tussen 4 en 6V 2HZ en boven de 6V moeten er 2 lampjes om beurten knipperen met een frequentie van 5Hz.

---

#### Millis (1 regel code)
Maak met slechts één FB een programma dat iedere x milliseconden één enkele puls geeft.

---

#### Openbaar toilet (4 regel code)
Er zijn drie toiletten met elk een lamp voor de verlichting (L01, L02 en L03) en elk een bistabiele schakelaar (S01, S02 en S03) om deze lampen respectievelijk aan te steken. Wanneer iemand een toilet binnengaat en de schakelaar bedient gebeuren twee zaken:

- enkel in het betreffende toilet zal de lamp gaan branden  
- er is ook één gemeenschappelijke ventilator voor het verluchten van de toiletten

Als de bezoeker terug buitengaat en de verlichting uitschakelt gebeuren twee zaken:

- in het betreffende toilet zal de lamp uitgeschakeld worden  
- de gemeenschappelijke ventilator zal nog 2 minuten (simuleer 5 seconden) blijven werken en daarna automatisch uitschakelen (op voorwaarde dat intussen niemand anders de toiletten bezoekt)

---

#### Automatische deur (1 regel code)
Aan een supermarkt wordt de ingangsdeur geopend en gesloten d.m.v. twee pneumatische cilinders. Aan de ingang buiten staat een fotocel die de deur zal openen bij een naderende klant. Ook aan de kassa kan men de deur openen door gebruik te maken van een drukknop.

De deur wordt automatisch gesloten 1 seconde nadat het detectiesignaal is weggevallen. De automatische werking functioneert enkel als een hoofdschakelaar in het bureau AAN staat.

---

#### Setpointsturing met korte en lange drukknoppen (11 regels)
Stel een setpoint van 0 tot 1.000 in door middel van twee druktoetsen (+ en –) die op het display getoond worden. Met één enkele klik (< 1 s) verhoogt of verlaagt men de waarde telkens met 1 (display)punt, en bij een lange druk (> 1 s) verandert de waarde continu met 100 (display)punten per seconde in de richting van de ingedrukte knop. De waarde mag nooit onder 0 of boven 1000 komen. Het uiteindelijke setpoint wordt lineair omgerekend naar een uitgangsspanning tussen 0 en 10 V voor aansturing via de EL4002.


---
### Oefeningen (Flankdetectie)
---

#### Draairichting van een motor (2 regel code)
Op de as van een motor worden twee sensoren gemonteerd bv reflex fotocellen. Bepaal de draairichting met flankdetectie.

Uitbreiding: Om een verplaatsbare pomp niet te beschadigen mag een elektrische motor enkel links draaien. Daarom wordt de draairichting gedetecteerd door middel van vorige oefening. Wanneer de motor links aanloopt is er normale werking. Als de motor rechts aanloopt zal hij onmiddellijk stilvallen en een rood alarmlicht zal branden.

---

#### Belsignaal aan winkeldeur (3 regel code +1 + 1)
Aan de ingangsdeur van een winkel staan twee fotocellen S01 en S02 opgesteld.  
Wanneer een klant binnenkomt wordt eerst S01 onderbroken, daarna S02, een bel of zoemer zal in werking treden zolang de lichtstralen van de fotocellen onderbroken zijn.  
Wanneer een klant buitengaat wordt eerst S02 onderbroken, daarna S01, hier mag de bel of zoemer niet werken.

Uitbreiding: Tel het aantal binnenkomende klanten met een counter FB.

Uitbreiding: Om te vermijden dat de bel blijft rinkelen als een klant aan de deur blijft stilstaan zal de bel of zoemer slechts 0,5 seconde werken.


---
### Oefeningen (Counters)
---

#### Parking
Maak een visualisatie die de in- en uitgang van een parking voor personenwagens simuleert.

De toegang tot de parking wordt aangegeven door de verkeerslichten aan de ingang. Als het maximum aantal parkeerplaatsen is bezet (zie tellerstand) moet het groene licht doven en het rode licht branden.

Bij het binnenrijden onderbreekt de wagen eerst sensor 1, de slagboom opent en daarna wordt sensor 2 onderbroken. Als de wagen verder naar binnenrijd wordt eerst sensor 1 terug vrijgegeven, daarna wordt sensor 2 vrijgegeven. Op dit moment wordt een wagen bij de tellerstand opgeteld en de slagboom wordt terug gesloten.

Bij het buiten rijden krijgen we de omgekeerde beweging. De wagen onderbreekt eerst sensor 2. De slagboom opent. Daarna wordt sensor 1 onderbroken. Als de wagen naar buiten rijd wordt eerst sensor 2 terug vrijgegeven, daarna wordt sensor 1 vrijgegeven. Op dit moment wordt een wagen van de tellerstand afgetrokken en de slagboom wordt terug gesloten.

---

#### Producten tellen en verdelen
In onderstaand voorbeeld komen de producten vanaf de linkerzijde. Op deze aanvoerband bevindt zich een sensor die de producten detecteert. In het midden bevindt zich een klep die twee standen kan aannemen zodat de producten rechtdoor gaan of afgebogen worden op een tweede transportband. Er dienen 10 producten rechtdoor te gaan en vervolgens worden 20 producten afgebogen waarna er terug 10 rechtdoor gaan, enz.

---

## 📁 Oefeningen 3++ — POUs  
📂 Map:  
[`Building_Excercises_Oefeningen1/Oefeningen3++/POUs`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs)

| Oefening | Programma (.TcPOU) |
|--------|------------------|
| Main | [`MAIN.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/MAIN.TcPOU) |
| Checker function1 | [`CheckBounds.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/CheckBounds.TcPOU) |
| Checker function2 | [`CheckRangeInt.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/CheckRangeInt.TcPOU) |
| PWM | [`prg_PWM.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/prg_PWM.TcPOU) |
| FB_PWM | [`FB_PWM.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/FB_PWM.TcPOU) |
| Click Log | [`prg_Click_Log.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/prg_Click_Log.TcPOU) |
| FB Click Log | [`FB_Click_Log.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/FB_Click_Log.TcPOU) |
| GetMinimum | [`prg_GetMinimum.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/prg_GetMinimum.TcPOU) |
| FB GetMinimum | [`FB_GetMinimum.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/FB_GetMinimum.TcPOU) |
| FUNCTION GetMinimum | [`FGetMinimum.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/FGetMinimum.TcPOU) |
| Personeelsdata | [`prg_Personeelsdata.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/prg_Personeelsdata.TcPOU) |
| Structure Personeelsdata | [`Pers_data.TcDUT`](./Building_Excercises_Oefeningen1/Oefeningen3++/DUTs/Pers_data.TcDUT) |
| SearchString | [`prg_SearchString.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/prg_SearchString.TcPOU) |
| FB SearchString | [`FB_SearchString.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/FB_SearchString.TcPOU) |
| Druktoets functies | [`prg_Druktoets_Functies.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/prg_Druktoets_Functies.TcPOU) |
| FB Druktoets functies | [`FB_DrukknopSpecial.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen3++/POUs/FB_DrukknopSpecial.TcPOU) |

---

## 📝 Oefeningen 3++ — Opgaves

---

### Oefeningen op creëren van FB en FC

---

### Checker functions
Maak de checker functions aan die gezien werden tijdens de les:

- CheckBounds aan die de waarde tussen 15 en 24 regelt  
- CheckRangeInt met TYPES voor waarden van 0 t.e.m. 32.767

---

### PWM
Maak een FB aan die PWM signaal uitstuurt met een instelbare periode en duty cycle.

---

### Click Log
Maak een FB aan die gedurende 5s. iedere druk registreert, gevolgd met 2s. pauze.  
De output van de FB is een array met de tijdswaarden tussen twee opeenvolgende drukken in.  
De tijd start automatisch bij de eerste druk.

---

### GetMinimum
Maak een FB aan die de kleinste tijdswaarde uit een ARRAY kan halen.  
Controleer via bovenstaande oefening.  
Kan dit ook met een functie?

---

### Personeelsdata
Maak een structure ‘Pers_data’ aan met Name, Firstname, Age, Adress.

Beperk de namen tot 25 en het adres tot 55 karakters.  
Maak een array van onderstaande structures aan.

<img width="1136" height="701" alt="image" src="https://github.com/user-attachments/assets/75e88c19-e668-4477-9195-baa33dd48f8d" />

Creëer of overschrijf personeelsdata vanuit de visualisatie in de arrays.  
Pas hierbij de checker functions toe om de leeftijd de beperken van 0 tot 100 jaar.  
Gender doe je via een enum.

---

### SearchString
Maak een Functie block aan die de string waardes uit de bovenstaande structure controleert op een bepaalde string zonder hoofdlettergevoeligheid bv de string ‘stijn’.  
Zou dit ook in een function geplaatst kunnen worden?

Opm. functies vanuit andere libraries kunnen toegevoegd worden via References (zie afb. links) en vervolgens te zoeken naar de desbetreffende functie (blok) (zie afb. rechts).

<img width="1132" height="463" alt="image" src="https://github.com/user-attachments/assets/1bd29de5-2e7d-4e48-a24c-527ec6cb17b4" />

---

### Druktoets functies
Maak een FB DrukknopSpecial aan die een drukknop speciale functies geeft zoals:

- Één enkele klik  
- Dubbele klik  
- Lang klikken ( > 1s )

Dit zijn natuurlijk drie aparte uitgangen en slechts één ingang.

---

## 📁 Oefeningen 4 — POUs  
📂 Map:  
[`Building_Excercises_Oefeningen1/Oefeningen4/POUs`](./Building_Excercises_Oefeningen1/Oefeningen4/POUs)

| Oefening | Programma (.TcPOU) |
|--------|------------------|
| Main | [`MAIN.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen4/POUs/MAIN.TcPOU) |
| Kantoorverlichting | [`prg_KantoorVerlichting.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen4/POUs/prg_KantoorVerlichting.TcPOU) |
| Thermostaatregeling | [`prg_Thermostaatregeling.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen4/POUs/prg_Thermostaatregeling.TcPOU) |
| Thermostaatregeling tijdsturing | [`prg_ThermostaatregelingTijdsturing.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen4/POUs/prg_ThermostaatregelingTijdsturing.TcPOU) |
| Finale | [`prg_Finale.TcPOU`](./Building_Excercises_Oefeningen1/Oefeningen4/POUs/prg_Finale.TcPOU) |

---

## 📝 Oefeningen 4 — Opgaves

---

### 1. Kantoorverlichting
Wanneer de eerste persoon op kantoor aankomt, kan deze via schakelaar_1 de verlichting inschakelen (alsook nadien uitschakelen). Na een bepaalde instelbare tijd zullen de lichten 3x knipperen om aan te geven dat deze over 30seconden zullen uitschakelen. Men kan het automatisch uitschakelen van de verlichting stoppen (opnieuw verlengen met de ingestelde tijd) door schakelaar_1 lang in te drukken (2 seconden).

Om de ingestelde tijd te kunnen bepalen wordt schakelaar_2 gebruikt om deze in waarde te doen verhogen en via schakelaar_3 te verlagen.

TIP: Maak gebruik van FB_Light en CTUD functie blokken.

---

### 2. Thermostaatregeling
Met de kamerthermostaat wordt de temperatuur in de huiskamer geregeld. Is de temperatuur lager dan de ingestelde waarde -1°C dan schakelt de verwarming in en als deze hoger is dan de ingestelde waarde +1°C dan schakelt de verwarming uit.

Potentiometer 1 bepaald de ingestelde temperatuur van 10°C tot 30°C (verschaalt).  
Potentiometer 2 bepaald de huidige temperatuur van -30°C tot 40°C (verschaalt).  

Geef de temperaturen weer via een Bar Display.  
Een LAMP geeft aan wanneer de verwarming ingeschakeld is.

Deze thermostaatregeling mag enkel gebeuren tijdens een bepaalde tijdsperiode, met een begin- en eindtijdstip voor iedere dag van de week. Gebruik hiervoor de FB_WeeklyTimeSwitch uit de TcBABasic.lib en bekijk de structure TIMESTRUCT nader voor de implementatie.

---

### 3. Thermostaatregeling met tijdsturing en logging
Zorg dat de temperatuur van de laatste 20seconden met een sample rate van één seconde weergegeven wordt in de visualisatie. Dit gebeurt via een Table en een alarm kleur indien deze lager is dan 10°C.

---

### 4. Finale versie met alle toeters en bellen
Maak een nieuw project aan met de naam “Building automation” en verwijder de mappen Global Variables, POUs en Visualizations. Maak de mappen gelijkvloers, verdiep en woning aan.

Onder de map gelijkvloers, voeg je nu een program POU (PRG) toe in de taal ST en naam ‘Gelijkvloers’, alsook een visualisation met de naam VISU_GVL. Maak in de visualisatie je woning na, waarbij een klik op een kamer de lichten doet togglen. In iedere kamer wil ik ook de temperatuur kunnen zien. Het zichtbaar maken van deze waarden moeten getoggled kunnen worden doormiddel van een button in de hoek langs het grondplan.

Probeer dit te vervolledigen voor de rest van de woning waarbij onder de map woning je een totaalzicht hebt met de buitenverlichting en status van de woning bv. Ergens staan de lichten nog aan of de chauffage staat nog aan.

Voor de verwarming zal de temperatuur van iedere kamer iedere 10 seconden gemeten worden.

Maak een Moving Average (MA) filter van 10 waardes voor de temperatuur.  
Sla de MA waarden voorafgegaan van een timestamp in een 2D array op. Toon hiervan de laatste 20 MA gelogde waarden in de visualisatie m.b.v. de tabel component.  
Zorg ervoor dat alle MA ook in een CSV file opgeslagen worden.

---
