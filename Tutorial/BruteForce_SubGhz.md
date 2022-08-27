# **Tutorial Brute Force SubGhz**

### **Funzionamento brute force subghz:**
Quando scaricate i file per fare brute force vi scaricherá un albero di cartelle cosí suddiviso:  
```

PROTOCOLLO
    └── GRANDEZZA FILE
        └── file da lanciare

```
Inizialmente conviene lanciare il file di dimensione maggiore, è quello contenente tutti i segnali salvati. Facendo riferimento alla frequenza interessata, potrebbe volerci un discreto tempo prima di trovare il segnale.
Per poter affinare la ricerca e ridurre il tempo dell'attacco si fa' quanto segue:

Una volta trovato il segnale nel file precedentemente utilizzato si procede lanciando i file nelle cartelle di dimensione inferiore e via così fino a trovare il file più piccolo contenente  la frequenza corrispondente. I file più piccoli non sono altro che suddivisioni di quello/i più grande/i.

**Una rapida considerazione per comprendere meglio come utilizzarle.**

Consideriamo le seguenti suddivisioni delle cartelle:
```
4096
└── 4096.sub (da 0 a 4096)
2048
└── 2048_001.sub (da 0 a 2048)
└── 2048_002.sub (da 2048 a 4096)
1024
└── 1024_001.sub (da 0 a 1024)
└── 1024_002.sub (da 1024 a 2048)
└── 1024_003.sub (da 2048 a 3072)
└── 1024_004.sub (da 3072 a 4096)
...
...
...

```
**Esecuzione:**

-Lanciamo il file 4096, troviamo il segnale!
-A questo punto scegliamo di lanciare il primo file 2048_001.sub
-Troviamo nuovamente il segnale, questo significa che il prossimo passaggio andremo a provare i primi due della successiva divisione: 1024_001.sub e 1024_002.sub
-Se invece avessimo avuto corrispondenza lanciando il file 2048_002.sub avremmo dovuto cercare la divisione della seconda metà quindi: 1024_001.sub e 1024_002.sub e via così man mano che vogliamo aumentare la precisione del segnale cercato.