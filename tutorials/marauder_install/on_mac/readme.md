## Flashing Marauder on Dev Board with Mac
#### Preparazione:
1. Prepara il Mac (salta questo passaggio se hai già qualcosa/tutto installato):
    - Installa HomeBrew seguendo i passi riportati sul sito di riferimento: [HomeBrew](https://brew.sh/index_it)
    - Installa i driver utili al riconoscimento della ESP32S2: [CP210X Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads)
    - I driver `CH340X Drivers` di cui avrebbe bisogno Windows sono già installati
    - Se hai installato qualsiasi driver o homebrew fai un reboot che non si sa mai ;)
2. Scarica l'ultimo .zip qui presente e scomprimilo: [FZ_Marauder_Flasher](https://github.com/UberGuidoZ/Flipper/tree/main/Wifi_DevBoard/FZ_Marauder_Flasher)
3. Apri il Terminale e dirigiti con i soliti comandi `ls` e `cd` nella cartella appena unzippata
4. Installa `esptool` lanciando la seguente riga di comando: `brew install esptool`
5. Attacca la tua Flipper Zero Dev Board al Mac tenendo premuto il tasto fisico BOOT; una volta connessa rilascia il pulsante
6. Con il comando `ls /dev/tty.*` individua la porta utilizzata dalla tua Dev Board 
7. Copia la porta
    - per esempio il nome della porta potrebbe essere: `/dev/tty.usbmodem01`
8. Copia il nome del firmware scaricato che trovi nella cartella `<zip_scaricato_in_precedenza>/Marauder/esp32_marauder_*_flipper.bin`
    - per esempio il nome del firmware scaricato potrebbe essere: `esp32_marauder_v0_9_14_20220930_flipper.bin`
---
#### Flashing (queste operazioni sono da svolgersi senza interruzioni):
9. Eliminiamo completamente il contenuto della tua Dev Board con la seguente riga di codice (sostituisci `[PORTA]` con la porta copiata nel passo 7): `esptool.py -p [PORTA] -b 921600 -c esp32s2 --before default_reset -a no_reset erase_region 0x9000 0x6000`
    - ESEMPIO: `esptool.py -p /dev/tty.usbmodem01 -b 921600 -c esp32s2 --before default_reset -a no_reset erase_region 0x9000 0x6000`
10. Installiamo il firmware Marauder sulla devboard (sostituisci `[PORTA]` con la porta copiata nel passo 7 e sostituisci `[_FLIPPER.BIN]` con il nome del firmware copiato nel passo 8): `esptool.py -p [PORTA] -b 921600 -c esp32s2 --before default_reset -a no_reset write_flash --flash_mode dio --flash_freq 80m --flash_size 4MB 0x1000 Marauder/bootloader.bin 0x8000 Marauder/partitions.bin 0x10000 Marauder/[_FLIPPER.BIN]`
    - ESEMPIO: `esptool.py -p /dev/tty.usbmodem01 -b 921600 -c esp32s2 --before default_reset -a no_reset write_flash --flash_mode dio --flash_freq 80m --flash_size 4MB 0x1000 Marauder/bootloader.bin 0x8000 Marauder/partitions.bin 0x10000 Marauder/esp32_marauder_v0_9_14_20220930_flipper.bin` 
---
#### Finito
11. Premere il tasto RESET fisico sulla board e scollegarla dal Mac
