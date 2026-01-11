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
| Analoge waarden visualiseren | [`Visualization_DynamischVerschalen.TcVIS`](./Building_Excercises_Oefeningen1/Oefeningen2/VISUsVisualization_DynamischVerschalen.TcVIS) |
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

### Waardeschaling met een libraryfunctie
- Voeg library toe via **References**
- Gebruik **F_Scale** om analoge waarden te verschalen

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
