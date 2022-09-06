# **Flipper Zero firmware differences**

> Adattato dai messaggi originali di Nano ([Messagio 1](discord.com/users/597435984925294620), [Messaggio 2](https://discord.com/channels/937479784148115456/937489970007003166/970666146804170792), [Messaggio 3](https://discord.com/channels/937479784148115456/937489970007003166/970666162247581806)) nel discord del firmware [Unleashed](#unleashed).  
Tradotto e riaddattato dalla comparazione originale su [Awesome Flipper Zero](https://github.com/djsime1/awesome-flipperzero/blob/main/Firmwares.md)

Questo documento contiene una lista di differenze tra i vari fork di [Flipper Zero firmware](#official).  
Se avessi un dollaro ogni volta che ho visto fare questa domanda, avrei già colmato il mio debito scolastico. ¯\\*(ツ)*/¯  
Prendi in considerazione di guardare [Awesome Flipper Zero list](https://github.com/djsime1/awesome-flipperzero), e la mia [sfuriata contro i due tipi di utenti Flipper](https://gist.github.com/djsime1/73adaaf24f20b8bb70c4d4854431b0f1).

| |Official |Unleashed |RogueMaster |v1nc |Wetox |MuddleBox |
|-|-|-|-|-|-|-|
|Repository |[Official](https://github.com/flipperdevices/flipperzero-firmware) |[Unleashed](https://github.com/Eng1n33r/flipperzero-firmware) |[RogueMaster](https://github.com/RogueMaster/flipperzero-firmware-wPlugins) |[v1nc](https://github.com/v1nc/flipperzero-firmware) |[Wetox](https://github.com/wetox-team/flipperzero-firmware) |[MuddleBox](https://github.com/MuddledBox/flipperzero-firmware) |

## Sommario

- [Official](#official)
- [Unleashed](#unleashed)
- [RogueMaster](#roguemaster)
- [v1nc](#v1nc)
- [Wetox](#wetox)
- [MuddledBox](#muddledbox)
- [Riepilogo](#riepilogo)

### **Official**

> [flipperdevices/flipperzero-firmware](https://github.com/flipperdevices/flipperzero-firmware)

- Sono presenti restrizioni Sub-Ghz per paese dovute a limitazioni legali.
- Non ha la possibilità di salvare o mandare rolling codes(criptati dinamicamente), permette solo di visualizzarli sulla lista dei pacchetti catturati.
- Nome del dispositivo impostato di fabbrica, mostrato dovunque (Bluetooth broadcast, connessione USB, etc) che non può essere modificato.
- Il team del flipper possiede una lista di nomi dei dispositivi che corrispondono alle loro informazioni di produzione [(Nessun indirizzo di informazione)](https://discord.com/channels/740930220399525928/765282833744265246/971881286543224852) che usano per assisterti più facilmente nel caso di problematiche.

### **Unleashed**

#### *(AKA Code Grabber firmware)*

> [Eng1n33r/flipperzero-firmware](https://github.com/Eng1n33r/flipperzero-firmware)

- Sviluppo e communità Discord molto attiva.
- Rimosse restrizioni SubGhz per paese di base.
- Permette di aggiungere frequenze Sub-Ghz estese (esempio Restaurant pagers) attraverso il file *dangerous_settings*.
- Aggiunte frequenze Sub-Ghz estese di default attraverso il file ufficiale *setting_user*.
- Aggiunte chiavi NFC Mifare Classic extra.
- Può essere usato per catturare e mandare protocolli criptati dinamici/rolling code.
- Segnali Sub-Ghz criptati e codici possono essere aggiunti manualmente.
- Aggiunte liste di protocolli Sub-Ghz, può trovarli al seguente [link](https://github.com/Eng1n33r/flipperzero-firmware#current-modified-and-new-subghz-protocols-list).
- Sono presenti plugin e applicazioni extra creati dalla community
- Puoi trovare altri dettagli e la lista completa delle modifiche nel seguente [README](https://github.com/Eng1n33r/flipperzero-firmware#readme).

### **RogueMaster**

> [RogueMaster/flipperzero-firmware-wPlugins](https://github.com/RogueMaster/flipperzero-firmware-wPlugins)

- Basato sul firmware [Unleashed](#unleashed)(Anche se il fork è del firmware [originale](#official).)
- Rimuove le restrizioni Sub-Ghz per paese modificando il file *extend_range.txt*.
- Permette di aggiungere frequenze Sub-Ghz estese (esempio Restaurant pagers) attraverso il file *extend_range.txt*.
- Include protocolli Sub-Ghz e molte altre modifiche prese dal firmware [Unleashed](#unleashed).
- Aggiunge risorse extra create dalla commmunity *(Mifare classic dict, example files, etc)*.
- Include molte pull request dal firmware originale che non sono state mergiate nel firmware originale *(bleeding edge)*.
- Include un buon numero di giochi, molti solo sperimentali, e anche una modalità "Games Only Mode" (aka Dumb Mode).
- Include un potenziato, ma sperimentale, sistem di nuovi "Dolphin Level".
- Hanno aggiunto molte ritocchi della community, plugin e giochi (molti sono instabili o incompleti).
- Include anche un gran numero di piccoli ritocchi e modifiche.
- Puoi trovare altri dettagli e la lista completa delle modifiche nel seguente [README](https://github.com/RogueMaster/flipperzero-firmware-wPlugins#readme).

### **v1nc**

> [v1nc/flipperzero-firmware](https://github.com/v1nc/flipperzero-firmware)

- Supporta differente layout di tastiera per DuckyScript tramite la keyword `DUCKY_LANG`
- Up to date fork of the Unleashed firmware
- Includes community plugins & games

### **Wetox**

> [wetox-team/flipperzero-firmware](https://github.com/wetox-team/flipperzero-firmware)

- Il branch di dev è destinato all'uso pubblico, mentre altri sono sia di test o archiviati contributi hackathon
- Può crackare le password del T5577 RFID passwords tramite dictionary attack.
- Testata del desktop brandizzata [WTX].
- Frequentemente aggiornata con interessanti modifiche sperimentali in diversi [branches](https://github.com/wetox-team/flipperzero-firmware/branches).

### **MuddledBox**

> [MuddledBox/flipperzero-firmware](https://github.com/MuddledBox/flipperzero-firmware)

- **Abbandonato. Nessun aggiornamento da oltre 2 mesi.**
- Rimosse restrizioni Sub-Ghz per paese.
- Aggiunte immagini promozionali nella pagina About delle impostazioni.
- Aggiunte Sub-Ghzfrequenze comuni per catturarle.

### **Riepilogo**

- Rimanere aggiornato con gli aggiornamenti (ufficiali) è importante.
- Rimuovere le restrizioni per paese è inlegale in molte circostanza, usalo a tuo rischio e pericolo.
- Muddlebox è il primo fork popolare ma non è più aggiornato.
- Unleashed è più focalizzato sulle funzionalità, sulla stabilità e sui protocolli Sub-Ghz.
- RogueMaster ha più plugin della community, modifiche grafiche, giochi e modifiche (molte sperimentali).
