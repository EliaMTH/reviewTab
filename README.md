# reviewTab

Tabella locale per preparare le risposte ai revisori di un articolo.
Un solo file HTML: niente installazione, niente server, funziona offline. I dati stanno in un file `.json` sul tuo computer.

## Uso

1. Apri `revisione.html` con Chrome o Edge.
2. 🆕 crea un nuovo progetto (chiede nome e cartella del file), oppure 📂 apri un `.json` esistente.
3. Ctrl+S salva sul file. La volta successiva basta ↻ Riprendi.

Il pulsante **?** nella barra elenca tutti i comandi.

## Funzioni

- Una riga per commento: ID, commento del revisore, commenti, da fare, risposta. Tutte le celle sono testo libero.
- 📄 testo originale del revisore, usato nell'export.
- Ordinamento per ID (alfanumerico: R1-2 prima di R1-10) o per gravità; righe trascinabili.
- Colore per riga: rosso, arancio, giallo, verde (Alt+1…4, Alt+C per toglierlo), con riepilogo nella barra.
- ＋ aggiunge righe; ✕ le nasconde senza cancellarle (👁 per vederle, ↺ per ripristinarle). Le righe vuote non vengono salvate.
- ⤓ export `.docx`: per ogni ID, il commento del revisore in corsivo e la risposta, in ordine di ID.
- Modalità notte e dimensione del testo.

## Formato dei dati

```json
{
  "versione": 1,
  "salvato": "2026-10-29T17:03",
  "preferenze": { "notte": false, "fs": 13, "nascoste": false, "originali": true },
  "righe": [
    {
      "id": "R1-1",
      "originale": "testo originale del revisore",
      "revisore": "riassunto",
      "commenti": "",
      "azioni": "",
      "risposta": "",
      "colore": "rosso",
      "visibile": true
    }
  ]
}
```

`colore`: `rosso`, `arancio`, `giallo`, `verde` oppure `null`. `visibile: false` indica una riga rimossa.

`preferenze` (facoltativo): modalità notte, dimensione del testo in px (10–22), righe rimosse visibili, testi originali visibili. Se manca, si usano le ultime preferenze del browser.

## Note

- Il salvataggio diretto sul file usa la File System Access API (Chrome, Edge). Negli altri browser Ctrl+S scarica una copia.
- Ogni modifica viene copiata anche nella memoria del browser, per recuperarla se la pagina si chiude prima del salvataggio.

## Licenza

[MIT](LICENSE)
