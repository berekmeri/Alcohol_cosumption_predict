# US Alcohol Consumption Time Series Analysis (1977–2023)

## Projekt áttekintés

Ez a projekt az Egyesült Államok alkoholfogyasztásának alakulását vizsgálja idősorelemzési módszerek segítségével a 1977–2023 közötti időszakban.

A cél:

* a hosszú távú trendek feltárása,
* a fogyasztási szerkezet (sör, bor, tömény italok) elemzése,
* valamint előrejelző modellek építése és összehasonlítása.

A projekt teljes egészében egy Jupyter Notebookban (R nyelven) valósul meg.

---

## Adathalmaz

Az elemzés a következő nyilvános adatkészletre épül:

* Forrás: https://www.kaggle.com/datasets/sanaijlalshahrukh/us-alcohol-consumption-by-state-19772023

### Időtáv

1977 – 2023

### Megfigyelések

* USA összes állama
* éves bontás

### Főbb változók

* `state_name` – állam neve
* `year` – év
* `ethanol_beer_gallons_per_capita` – sörből származó fogyasztás
* `ethanol_wine_gallons_per_capita` – borfogyasztás
* `ethanol_spirit_gallons_per_capita` – tömény italok fogyasztása
* `ethanol_all_drinks_gallons_per_capita` – teljes alkoholfogyasztás

---

## Feltáró adatelemzés (EDA)

A notebook több vizualizációt tartalmaz:

* államonkénti fogyasztási trendek
* top államok kiemelése
* országos átlag alakulása időben
* fogyasztási szerkezet (sör–bor–tömény)
* eloszlások (hisztogramok)

### Fő megállapítások

* a tömény italok fogyasztása nagyobb volatilitást mutat
* a sör és bor fogyasztása stabilabb
* a magas fogyasztású államokban a tömény italok aránya jellemzően magasabb

---

## Idősorelemzés

Az országos átlagos alkoholfogyasztás idősorán történt modellezés.

---

## Alkalmazott modellek

### 1. ARIMA

* automatikusan választott modell: **ARIMA(1,0,2)**
* erős perzisztencia (AR komponens ~0.94)
* jó illeszkedés reziduális vizsgálat alapján

### 2. ETS (Error–Trend–Seasonality)

* magas súly a friss megfigyeléseken
* csillapított trend
* reziduálisok: fehér zaj jellegűek

### 3. TSLM (Time Series Linear Model)

* egyszerű lineáris trend modell
* enyhén csökkenő trend
* alacsony magyarázóerő (R² ≈ 0.15)

---

## Modellek összehasonlítása

A modellek teljesítményének összehasonlítása:

* `accuracy()` metrikák alapján
* több modell párhuzamos értékelése

---

## Előrejelzés

Mindhárom modell esetében készült:

* **10 éves előrejelzés**
* vizualizált forecast görbék

---

## Használt technológiák

* R
* Jupyter Notebook
* tidyverse
* tsibble
* fable / fabletools
* feasts
* tseries

---

## Futtatás

1. Repository klónozása:

```bash
git clone https://github.com/felhasznalonev/projektnev.git
cd projektnev
```

2. Notebook megnyitása Jupyter Lab-ben:

```bash
jupyter lab
```

3. Nyisd meg:

```
alcohol_cosumption_predict.ipynb
```

---

## Megjegyzések

* A projekt R alapú, nem Python
* A notebook futtatásához szükséges az adathalmaz (`.csv`)
* A vizualizációk nagy méretűek (plot beállítás miatt)

---

## Jövőbeli fejlesztések

* szezonális modellek mélyebb vizsgálata
* többváltozós idősorelemzés
* külső tényezők bevonása (pl. gazdasági mutatók)

---

## Szerző

Berekméri Barna
