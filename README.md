# Utilizzo del Suolo della Regione Campania (2008–2014)
## Descrizione del progetto

Questo progetto analizza l’evoluzione dell’**utilizzo del suolo nella Regione Campania** negli anni **2008** e **2014**, con particolare attenzione ai seguenti tematismi:
* Urbanizzazione
* Aree boschive e vegetazione
* Corpi idrici
* Aree agricole

L’analisi è stata condotta utilizzando sia i **dati vettoriali del Geoportale della Regione Campania**, sia dati satellitari ottenuti tramite **Google Earth Engine (dataset MODIS)**.
Il progetto include inoltre la creazione del **Modello Digitale del Terreno (DEM)**, ombreggiature, curve di livello e mappe 3D.

## Software utilizzati
### QGIS (v. 3.28 e 3.32)

Utilizzato per:
* Visualizzazione e modifica di dati geospaziali
* Elaborazione dei tematismi 2008/2014
* Creazione ed estrazione del DEM
* Calcolo delle aree tematiche e analisi delle differenze
  
### Google Earth Engine
Utilizzato per:
* Estrazione dei tematismi MODIS 2008 e 2014
* Estrazione delle province
* Analisi basata sulle bande LC-Type1 e LW

## Selezione dell’area di interesse

L’area di studio corrisponde alla **Regione Campania**.
Sono stati utilizzati:
* Tematismi regionali del 2008 come base
* Tematismi con dettaglio comunale

## Modello Digitale del Terreno (DEM)
* Acquisito tramite **INGV** con risoluzione 10m
* Mosaicatura dei blocchi tramite funzione "Fondi" di QGIS
* Ritaglio sull’area della Campania tramite maschera raster
* Creazione di:
  * Ombreggiatura
  * Curve di livello (intervallo: 100m)
  * Visualizzazioni 3D
    
## Tematismi – anno 2008

Estratti dal Geoportale della Regione Campania:
* Urbanizzazione (Figura 15)
Aree boschive e vegetazione (Figura 16)
Corpi idrici (Figura 17)
Aree agricole (Figura 18)

## Tematismi – anno 2014

Poiché non erano disponibili tematismi completi per il 2014, si è proceduto tramite il confronto con il 2008 usando il comando "**Differenza**" di QGIS.

Tematismi generati:
* Urbanizzazione 2014 
* Aree boschive e vegetazione
* Corpi idrici
* Aree agricole
  
## Analisi con Google Earth Engine

Dataset utilizzati:

* **MODIS MCD12Q1**
  Bande:
    * **LC-Type1** → copertura del suolo (classi 1–17)
    * **LW** → acqua/suolo (1/2)
* **FAO GAUL – Province**

Tematismi estratti:
* **MODIS 2008**
  * Suolo
  * Acqua
  * Boschi
  * Terreni coltivati
  * Urbanizzazione
* **MODIS 2014**
  * Suolo
  * Acqua
  * Boschi
  * Terreni coltivati
  * Urbanizzazione

## Analisi e Confronti
### Confronto Geoportale Campania (2008 vs 2014)
Risultati principali:
* **Aree agricole**: -10,69%
* **Aree boschive / verdi**: -4,33%
* **Corpi idrici**: -10,86%
* **Urbanizzazione**: +16,68%
  (aumento influenzato dalla presenza dell'area dei centri abitati nel dataset 2014)

### Confronto MODIS (2008 vs 2014)

Risultati principali:
* **Urbanizzazione**: +0,65%
* **Acqua**: invariata (~1%)
* **Boschi**: -12,9%
* **Terreni coltivati**: -18,3%
* **Aree non utilizzate/naturali**: +33,38%

## Confronto tra Geoportale Campania e MODIS
Sono state riscontrate differenze rilevanti dovute a:
* diversa risoluzione dei dati
* natura dei dataset
* inclusione di categorie distinte nei tematismi regionali

Differenze principali:
* Le aree agricole sono molto maggiori nei dati del Geoportale rispetto a MODIS.
* MODIS rileva ampie “aree naturali” non classificate nei tematismi regionali.
* Urbanizzazione simile nei due dataset, con differenze legate al dettaglio cartografico.
