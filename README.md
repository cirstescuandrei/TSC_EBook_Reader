# TSC_EBook_Reader

### Cîrstescu Andrei-Vlad 331CC

# Tabletă E-Paper ESP32-C6 – Documentație Hardware

## Descriere Generală

Această tabletă cu afișaj E-Paper este proiectată pentru consum redus de energie și uzabilitate extinsă. 
Se bazează pe ESP32-C6 și include funcționalități precum citire din microSD, senzori de mediu, RTC și 
interacțiune cu utilizatorul prin butoane tactile.

![openbook_diagram](https://github.com/user-attachments/assets/57522059-fa07-4814-ab9a-e129ab9cc9b2)

# BOM
| Components                                                                                                                                                                 	| Links                                                                                                                                                                         	|
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| BOOT_BUTTON, RESET_BUTTON, CANGE_BUTTON                                                                                                                                    	| https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k                                                                                 	|
| C1, C1_BAT, C1_BAT1, C1_BAT2, C2, C2_BAT, C4, C4_USB, C5, C6, C7, C8, C9, C10, C_DELAY,  EPD_C1, EPD_C2, EPD_C5, EPD_C6, EPD_C7, EPD_C8, EPD_C9, EPD_C10, EPD_C11, EPD_C12 	| https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO                                                                                                           	|
| C3                                                                                                                                                                         	| https://componentsearchengine.com/part-view/TCJB107M002R0055E/Kyocera%20AVX                                                                                                   	|
| C10_SUPERCAP                                                                                                                                                               	| https://www.snapeda.com/parts/CPH3225A/Seiko+Instruments/view-part/?ref=eda                                                                                                   	|
| CHG_LED                                                                                                                                                                    	| https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/view-part/?ref=search&t=LED%200603                                                                                      	|
| D1                                                                                                                                                                         	| https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda                                                                                              	|
| D2, D7                                                                                                                                                                     	| https://eu.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D                                                                            	|
| D3, D4, D5                                                                                                                                                                 	| https://www.snapeda.com/parts/MBR0530/Onsemi/view-part/?ref=eda                                                                                                               	|
| D6, D8, D9, D10, D11, D12                                                                                                                                                  	| https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda                                                                                                      	|
| IC1                                                                                                                                                                        	| https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor                                                                                                   	|
| IC4                                                                                                                                                                        	| https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex                                                                                                              	|
| J1                                                                                                                                                                         	| https://www.mouser.co.uk/ProductDetail/Hirose-Connector/FH34SRJ-24S-0.5SH99?qs=vcbW%252B4%252BSTIpKBl5ap9J8Fw%3D%3D                                                           	|
| J2                                                                                                                                                                         	| https://componentsearchengine.com/part-view/USB4110-GF-A/GCT%20(GLOBAL%20CONNECTOR%20TECHNOLOGY                                                                               	|
| J3                                                                                                                                                                         	| https://www.mouser.co.uk/ProductDetail/Adafruit/4208?qs=PzGy0jfpSMtbScLbr0L5dw%3D%3D                                                                                          	|
| J4                                                                                                                                                                         	| https://store.comet.srl.ro/Catalogue/Product/43497/                                                                                                                           	|
| L1                                                                                                                                                                         	| https://eu.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D                                                                            	|
| PFMF.050.1                                                                                                                                                                 	| https://www.mouser.co.uk/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D                                                                            	|
| Q1, Q2                                                                                                                                                                     	| https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated                                                                                                 	|
| Q3                                                                                                                                                                         	| https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay_                                                                                                         	|
| R1, R1-PINH, R1-PINH1, R1_BAT, R1_PWRUSB, R2, R2-PINH, R2-PINH1, R2-USB, R2-USB1, R2_BAT, R3, R4, R5, R6, R7, R8, R9, 10, R_BOOT, R_CAPACITOR, R_CHANGE, R_CL1, R_RESET    	| https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO                                                                                 	|
| SENSOR2                                                                                                                                                                    	| https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home                                                                                                            	|
| SJ1                                                                                                                                                                        	| https://grabcad.com/library/solder-jumpers-1                                                                                                                                  	|
| TP                                                                                                                                                                         	| -                                                                                                                                                                             	|
| U1                                                                                                                                                                         	| https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda                                                                                             	|
| U2                                                                                                                                                                         	| https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda                                                                                        	|
| U3                                                                                                                                                                         	| https://www.snapeda.com/parts/DS3231SN%23/Analog+Devices/view-part/?ref=eda                                                                                                   	|
| U4                                                                                                                                                                         	| https://www.snapeda.com/parts/MAX17048G+T10/Analog+Devices/view-part/?ref=eda                                                                                                 	|
| U5                                                                                                                                                                         	| https://www.mouser.co.uk/ProductDetail/Microchip-Technology/MCP73831T-5ACI-OT?qs=hH%252BOa0VZEiAcgAcEkuamXg%3D%3D 	|

---

## Componente Principale

### ESP32-C6-WROOM-1-N8
- Control total: afișaj, senzori, memorie
- Protocoale: SPI, I²C, UART, USB 2.0
- Consum: ~130 mA activ / ~12 µA deep sleep

### Afișaj E-Paper 7.5” (800x480 px)
- SPI + GPIO: BUSY, DC, RST, CS
- Consum 0 mA idle, ~26 mA la refresh
- Perfect pentru afișare statică de lungă durată

### Memorie
- **W25Q512 NOR Flash** (64MB, SPI) – firmware & cărți
- **MicroSD Card** (SPI partajat) – fișiere externe

### RTC – DS3231SN
- I²C + GPIO (INT, RST)
- Timp real precis, funcțional și în sleep
- Suportă trezirea automată

### Senzor Ambiental – BME680
- Temperatură, umiditate, presiune, compuși volatili
- I²C partajat cu RTC
- Consum redus: ~2.1 mA activ

### Alimentare
- **Baterie Li-Po 2500 mAh**
- **Încărcare USB-C** cu MCP73831 (max 1A)
- **LDO XC6220** – 3.3V stabil pentru sistem
- Monitorizare baterie prin MAX17048 (ADC pe IO18)
- LED încărcare controlat de IO4

### USB-C & Protecție
- Protocol: USB 2.0 + VBUS
- Programare + alimentare
- Protecție ESD integrată

### Interfață Utilizator
- 3 butoane tactile: BOOT (IO15), RESET (IO3), CHANGE (IO23)
- LED stare încărcare (IO4)

### Extensii
- **Qwiic/Stemma QT**: senzori I²C plug & play (IO19/IO20)
- GPIO suplimentari disponibili

---

## Pinout ESP32-C6

| Pin ESP32 | Funcție       | Periferic           |
|-----------|---------------|---------------------|
| IO2       | MISO (SPI)    | Flash, SD, E-Paper  |
| IO6       | SCK (SPI)     | Flash, SD, E-Paper  |
| IO7       | MOSI (SPI)    | Flash, SD, E-Paper  |
| IO12      | CS Flash      | Memorie NOR         |
| IO10      | CS E-Paper    | Display             |
| IO4       | CS SD         | microSD             |
| IO5       | DC E-Paper    | Display             |
| IO14      | BUSY E-Paper  | Display             |
| IO21      | RST E-Paper   | Display             |
| IO19/20   | SDA/SCL (I²C) | RTC, BME680, Qwiic  |
| IO0       | INT RTC       | RTC Wake            |
| IO17      | RTC RST       | RTC Reset           |
| IO18      | ADC Battery   | Monitorizare        |
| IO15      | BOOT          | Buton BOOT          |
| IO3       | RESET         | Buton RESET         |
| IO23      | CHANGE        | Buton navigare      |
| IO25/24   | UART TX/RX    | Debug Serial        |

---

## Estimare Consum

| Modul             | Activ           | Idle / Sleep     |
|------------------|------------------|------------------|
| ESP32-C6         | ~130 mA          | ~12 µA           |
| E-Paper          | ~26 mA           | 0 mA             |
| BME680           | ~2.1 mA          | 0.15 mA          |
| microSD          | 30–100 mA        | ~0.1 mA          |
| RTC              | ~1 µA            | -                |
| LED              | max 10 mA        | -                |

### Durată estimată cu baterie 2500 mAh
- Utilizare activă: **8–10 ore**
- Standby / Deep sleep: **până la 300 zile**

---
