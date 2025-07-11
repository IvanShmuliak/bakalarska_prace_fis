# Dobývání znalostí z databází na datech z trhu ojetých a skladových automobilů značky BMW

Tento repozitář obsahuje kompletní projekt bakalářské práce zaměřené na analýzu trhu s ojetými a skladovými vozy značky BMW v ČR pomocí metod datového dolování a strojového učení.

Bakalářská práce se zabývá aplikací metodiky CRISP-DM na data z českého trhu ojetých a skladových vozidel značky BMW s cílem identifikovat faktory ovlivňující cenotvorbu. Data byla získána pomocí nástroje Scrapy z portálu TipCars a následně podrobena procesu čištění, transformace a analýzy. Explorační analýza přinesla přehled o nabízených modelech, technických vlastnostech vozidel a jejich geografickém rozložení. V analytické fázi byl aplikován regresní model náhodného lesa, který dosáhl přijatelné predikční přesnosti a vyzdvihl jako klíčové prediktory rok registrace, výkon a objem motoru. Metoda shlukování DBSCAN odhalila přirozené skupiny vozidel podle technických parametrů, přičemž některé odpovídaly sportovním verzím, jiné běžným modelům či elektromobilům. Výsledky práce lze využít pro podporu rozhodování v oblasti sekundárního trhu s automobily. Mezi omezení výzkumu patří subjektivní hodnocení technického stavu, absence údajů o výbavě a nerovnoměrné zastoupení kategorií.

## Zdrojový kód pro sběr dat

Ve složce `scraper/spiders` se nachází crawler napsaný pomocí Scrapy:

- `__main__.py` – hlavní skript pro spuštění spiderů
- `car_details.py` – scrapuje data z jednotlivých inzerátů
- `tipcar_urls.py` – scrapuje URL jednotlivých inzerátů

## Analýza v Jupyter Noteboocích

Složka `notebook` obsahuje jednotlivé kroky datové analýzy:

1. `1_data_clearing.ipynb` – předzpracování a čištění dat  
2. `2_exploratory_data_analysis.ipynb` – vizualizace a průzkum dat  
3. `3_random_forest.ipynb` – model predikce cen pomocí Random Forest  
4. `4_cluster_analysis.ipynb` – shlukování pomocí DBSCAN

## Použitá data

Ve složce `data`:

- `raw_data/car_urls.csv` – seznam URL inzerátů  
- `raw_data/cars.csv` – původní surová data po scrapování  
- `raw_data/zv_cobce_psc.csv` – pomocná data s PSČ a obcemi  
- `processed_data/1_data_clearing/1_clearing_cars.csv` – data po čištění

## Struktura projektu
```
├── data
│   ├── processed_data/1_data_clear...
│   │   └── 1_clearing_cars.csv           # Předzpracovaná data po čištění
│   ├── raw_data
│   │   ├── car_urls.csv                 # URL inzerátů
│   │   ├── cars.csv                     # Surová data po scrapování
│   │   └── zv_cobce_psc.csv             # Pomocná data s PSČ a obcemi
├── figures                              # Obrázky a grafy použité v práci
├── notebook
│   ├── 1_data_clearing.ipynb            # Čištění dat
│   ├── 2_exploratory_data_analysis.ipynb# Explorační analýza dat
│   ├── 3_random_forest.ipynb            # Model náhodného lesa (regrese)
│   └── 4_cluster_analysis.ipynb         # Shlukování (DBSCAN)
├── scraper
│   ├── spiders
│   │   ├── car_details.py               # Scrapování detailů inzerátů
│   │   ├── tipcar_urls.py               # Scrapování URL inzerátů
│   │   └── __main__.py                  # Spouštěcí skript pro spider
├── .gitignore
```
## Poznámka

Práce byla úspěšně obhájená na Vysoké škole ekonomické v Praze (2025).  
