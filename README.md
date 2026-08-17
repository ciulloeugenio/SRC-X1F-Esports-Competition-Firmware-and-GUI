# SRC X1F-ESPORTS — Firmware USB HID & GUI

> **Versione Firmware Competition Mode**  
> **Designed and Engineered by Eugenio Ciullo**

Pacchetto pronto all'uso contenente il firmware precompilato a 16-bit (`0 .. 32767`) e l'applicazione desktop di calibrazione per la pedaliera professionale **SRC X1F-ESPORTS** (basata su Arduino Leonardo / ATmega32U4 e ADC ADS1115).

La periferica viene riconosciuta nativamente da Windows (`joy.cpl`) e da tutti i simulatori (*Assetto Corsa, iRacing, ACC, rFactor 2, Automobilista 2, Le Mans Ultimate, F1, ecc.*) come **periferica di gioco DirectInput a 16-bit** con il nome ufficiale **`SRC X1F-ESPORTS`**.

---

## 📁 Contenuto del Pacchetto

```text
SRC-X1F-Esports-Competition-Firmware-and-GUI/
│
├── Firmware/
│   ├── SRC_Pedaliera.ino.hex   (Firmware ufficiale pronto per il caricamento)
│   └── EEPROM_Clear.ino.hex    (Utility opzionale per il reset totale della EEPROM)
│
└── GUI/
    ├── SRC_X1F_ESPORTS_GUI.exe (Applicazione standalone per taratura e telemetria)
    └── src.ico                 (Icona applicazione)
```

---

## ⚡ 1. Come caricare il Firmware con SimHub (Flash Rapido)

1. Collega la pedaliera alla porta USB del PC.
2. Apri **SimHub**.
3. Nel menu laterale seleziona **Arduino** -> **My Hardware**.
4. Clicca su **Upload Custom Hex** (o *Flash hex file*).
5. Seleziona il file `Firmware/SRC_Pedaliera.ino.hex`.
6. Seleziona come tipo di scheda **Arduino Leonardo** e la porta **COM** corrispondente.
7. Clicca su **Start upload** e attendi qualche secondo fino al messaggio di conferma.

> **Nota di Ripristino:** In caso di parametri corrotti o se desideri cancellare completamente la memoria, carica prima `Firmware/EEPROM_Clear.ino.hex` e successivamente ricarica `Firmware/SRC_Pedaliera.ino.hex`.

---

## 🖥️ 2. Come utilizzare la GUI di Calibrazione

1. **Chiudi SimHub** (in modo da lasciare libera la porta COM per la calibrazione).
2. Esegui il file `GUI/SRC_X1F_ESPORTS_GUI.exe` *(non richiede installazione)*.
3. Il software troverà automaticamente la pedaliera e si connetterà all'istante.
4. **Calibrazione dei 3 pedali (Frizione, Freno, Acceleratore):**
   * Lascia il pedale a riposo e clicca su **`SET MIN`**.
   * Premi il pedale a fondo corsa e clicca su **`SET MAX`**.
   * Se il sensore è montato al contrario (es. l'Acceleratore diminuisce il valore quando premi), attiva la casella **`Inverti Direzione Asse`**.
5. I parametri vengono salvati immediatamente nella memoria EEPROM della scheda.
6. **Chiudi la GUI** e apri il tuo simulatore di guida preferito: la pedaliera è pronta per scendere in pista con zero latenza!
