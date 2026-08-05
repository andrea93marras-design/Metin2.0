# Pietre Corrotte — Idle Farming RPG

Idle RPG in stile MMORPG oldschool (atmosfera ispirata a Metin2): combatti automaticamente, raccogli
equipaggiamento a rarità crescente, potenzia il tuo eroe e rinasci per bonus permanenti.
Un solo file statico (`index.html`), nessuna build, nessun backend: il salvataggio è nel `localStorage` del browser.

## Come funziona il gioco
- **Combattimento automatico**: il tuo eroe attacca da solo a intervalli regolari; puoi anche cliccare "Colpisci" per danno extra manuale.
- **Zone**: 5 zone da sbloccare salendo di livello, ognuna con mostri e boss (ogni 10 uccisioni) più forti.
- **Bottino**: gli oggetti droppano in 4 rarità (Comune → Raro → Epico → Leggendario) su 4 slot (Arma, Armatura, Elmo, Amuleto).
- **Potenziamenti**: spendi Yang (oro) per aumentare Attacco, Difesa, Velocità, Vita, Bottino e guadagno d'oro.
- **Rinascita**: dal livello 25 puoi rinascere, azzerando i progressi normali in cambio di Gemme permanenti spendibili in bonus che restano per sempre.
- **Progressi offline**: alla riapertura il gioco calcola quanto avresti farmato durante l'assenza (fino a 8 ore).

## Deploy su Vercel

### Opzione A — dashboard Vercel (nessuna riga di comando)
1. Vai su [vercel.com](https://vercel.com) e crea un account/accedi.
2. Clicca **Add New → Project**.
3. Trascina questa cartella (o caricala come repo Git — vedi Opzione C) e importala.
4. Framework Preset: scegli **Other** (sito statico). Non serve alcun build command.
5. Clicca **Deploy**. In pochi secondi ottieni l'URL pubblico.

### Opzione B — Vercel CLI
```bash
npm install -g vercel
cd idle-metin
vercel        # segui il wizard per il deploy di anteprima
vercel --prod # deploy in produzione
```

### Opzione C — da GitHub
1. Crea un repository e carica questi file (`index.html`, `vercel.json`, `README.md`).
2. Su Vercel: **Add New → Project → Import Git Repository**, seleziona il repo.
3. Nessuna configurazione di build necessaria: Vercel serve `index.html` come sito statico.
4. Deploy.

## Struttura del progetto
```
idle-metin/
├── index.html    # tutto il gioco: markup, CSS e JS in un unico file
├── vercel.json    # configurazione minima per l'hosting statico
└── README.md
```

## Personalizzazione rapida
Tutti i valori di bilanciamento (mostri, rarità, costi dei potenziamenti, formula di rinascita) sono
raccolti in cima al blocco `<script>` di `index.html`, negli oggetti `ZONES`, `RARITIES`, `UPGRADE_DEFS`
e `PRESTIGE_UPGRADE_DEFS`: puoi modificarli senza toccare il resto della logica.
