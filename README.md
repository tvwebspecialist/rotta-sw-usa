# Rotta Sud-Ovest USA

Compagno di viaggio interattivo (mobile-first, offline-capable) per il tour
on-the-road **Venezia → San Francisco → canyon → Los Angeles**, 16 maggio – 1 giugno 2027.
Dati dal piano Listrop rif. 61964459.

## Cosa contiene

- **Oggi** — conto alla rovescia / giorno di viaggio, prossimo spostamento, stato valigia
- **Viaggio** — 13 tappe con hotel, meteo, cose da vedere, note condivise, tratte fra le tappe
- **Mappa** — percorso su CA / NV / UT / AZ con pin numerati
- **Valigia** — checklist condivisa + voci personalizzate
- **Info** — voli, noleggio auto, transfer, budget con divisione spese, assicurazioni, contatti

## Sincronizzazione dati

Sito statico, nessun backend. Valigia / note / spese sono salvate nel browser
(`localStorage`, condivise tra le schede dello stesso dispositivo). Aperto dentro
un artifact di Claude usano invece il database condiviso tra tutti i viaggiatori.

## Sviluppo

Nessuna build. È un unico `index.html` + service worker.

```bash
python3 -m http.server 8000   # poi apri http://localhost:8000
```

## Deploy

Serve qualunque host statico. Su GitHub Pages: Settings → Pages → Deploy from branch → `main` / root.
Dopo un cambio a `index.html`, alza `CACHE` in `sw.js` per aggiornare i dispositivi installati.
