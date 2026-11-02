# Schede

App di flashcards per iPhone. Open source (licenza MIT).
L'app è una web app installabile (PWA): funziona offline, non usa server, non usa account.
Le schede restano solo sul dispositivo.

## Funzioni

- Importa uno o più file `.md` (Markdown). Un file = un argomento.
- Ripetizione dilazionata (algoritmo SM-2 semplificato): l'app mostra ogni scheda al momento giusto.
- Ripasso libero di tutte le schede, senza modificare i progressi.
- Nuova importazione dello stesso file: l'app aggiorna il testo e conserva i progressi.
- Backup ed esportazione in un file `.json`.
- Tema chiaro e scuro automatico.

## Formato dei file

```markdown
# Nome dell'argomento

## Domanda lunga?
Risposta su più righe.
- Elenchi puntati, **grassetto**, *corsivo*, `codice`.

---

Domanda breve :: Risposta breve
Una frase con un ==termine chiave== diventa una scheda a completamento.
```

Regole:

1. `# Titolo` è il nome dell'argomento. Se manca, l'app usa il nome del file.
2. `## Testo` è il fronte della scheda. Il retro è il testo sotto, fino al prossimo `##` o a `---`.
3. `Domanda :: Risposta` su una riga è una scheda. Metti uno spazio prima e dopo `::`.
4. `==testo==` in una riga fuori dai blocchi `##` crea una scheda a completamento.
5. Il front matter YAML con `argomento:` (o `title:`) è valido come titolo.

Vedi `esempio.md`.

## Installazione su iPhone (GitHub Pages, gratis)

1. Crea un account su github.com.
2. Crea un repository pubblico con nome `schede`.
3. Carica tutti i file di questa cartella (anche la cartella `icons`).
4. Apri Settings → Pages. In "Branch" seleziona `main` e `/ (root)`. Salva.
5. Attendi 1–2 minuti. L'indirizzo è `https://NOMEUTENTE.github.io/schede/`.
6. Su iPhone apri l'indirizzo con Safari.
7. Tocca Condividi → "Aggiungi alla schermata Home".

## Aggiornare l'app

1. Carica su GitHub il file modificato.
2. In `sw.js` cambia `schede-v1` in `schede-v2` (poi v3, ecc.).
3. Su iPhone apri l'app con la rete attiva, chiudila e aprila di nuovo.

## Sicurezza dei dati

- Le schede sono salvate nella memoria locale dell'app sull'iPhone. Non vanno su GitHub.
- Se elimini l'icona dalla schermata Home, iOS elimina anche le schede. Prima esporta un backup.
- Esporta un backup dal menu `•••` con regolarità.
