# F1Analysis

# F1 Lab

Pagina unica (`index.html`) per studiare telemetria e sessioni F1 di tutti i piloti e per generare previsioni di Qualifica e Gara.

**Dati:** [OpenF1](https://openf1.org) – API gratuita, senza chiave, per le sessioni passate (dal 2023). Tutti i tipi di sessione: Libere, Qualifica, Sprint Qualifying, Sprint, Gara.

## Come si usa
Scegli anno, Gran Premio, sessione → **Carica sessione**.
- **Risultati**: miglior giro, settori, giro ideale, velocità di punta.
- **Giri**: andamento di tutti i piloti, con attiva/disattiva.
- **Gomme**: stint, passo e degrado.
- **Telemetria**: velocità, acceleratore, freno, marcia e delta tra 3 piloti.
- **Meteo**: temperature, umidità, pioggia.
- **Previsioni**: usa le sessioni già disputate del weekend selezionato.

## Come ragionano le previsioni
- **Qualifica**: distacco % dal migliore in ogni sessione (mix giro reale + ideale), media pesata (FP3 pesa di più). I pesi sono modificabili.
- **Gara**: passo sui long run (stint di almeno 5 giri puliti), confrontato gomma per gomma, più effetto della posizione in griglia. Simulazione Monte Carlo (3000 gare) per probabilità di vittoria, podio, top 10.
- **Backtest**: sui weekend già disputati confronta previsione e risultato reale (errore medio e correlazione di Spearman). Prova i pesi su più Gran Premi passati e tieni quelli che sbagliano meno.

## Limiti
OpenF1 limita le richieste (circa 3 al secondo): il caricamento è volutamente lento. Se compare un errore, aspetta un minuto e riprova.
