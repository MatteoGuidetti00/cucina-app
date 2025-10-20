# 🍳 Gestionale Cucina & Dieta

App web completa per gestire ricette, inventario, lista spesa e tracking pasti.

## ✅ Hai già l'app pronta!

Il file `index.html` è un'app standalone che funziona subito. Apri il file con un browser e sei già operativo!

---

## 📱 OPZIONE 1: Uso Locale (più semplice)

### Su PC:
1. Apri `index.html` con Chrome/Firefox/Edge
2. I dati vengono salvati automaticamente nel browser (localStorage)
3. Aggiungi ai preferiti per accesso rapido

### Su Mobile:
1. Copia `index.html` sul telefono (via email, WhatsApp, Drive...)
2. Apri con un browser mobile
3. Su iPhone: tocca "Condividi" → "Aggiungi a Home" per un'icona app
4. Su Android: menù → "Aggiungi a schermata Home"

### ⚠️ Limitazioni:
- I dati sono salvati solo sul dispositivo dove apri l'app
- PC e telefono hanno dati separati
- Se cancelli i dati del browser, perdi tutto (fai backup con Export!)

---

## 🌐 OPZIONE 2: Hosting Online con GitHub Pages (CONSIGLIATO)

Con questa opzione avrai un URL tipo `https://tuousername.github.io/cucina-app` accessibile da qualsiasi dispositivo!

### Passi con Claude Code:

1. **Apri il terminale nella cartella del progetto:**
   ```bash
   cd C:\Users\matte\WebstormProjects\cucina-app
   ```

2. **Inizializza Git:**
   ```bash
   git init
   git add .
   git commit -m "Prima versione app cucina"
   ```

3. **Crea repository su GitHub:**
   - Vai su https://github.com/new
   - Nome: `cucina-app`
   - Pubblico o Privato (entrambi funzionano)
   - NON aggiungere README, .gitignore o licenza
   - Clicca "Create repository"

4. **Collega e pusha:**
   ```bash
   git remote add origin https://github.com/TUO_USERNAME/cucina-app.git
   git branch -M main
   git push -u origin main
   ```

5. **Attiva GitHub Pages:**
   - Vai nelle Settings del repository
   - Sezione "Pages" (nel menu laterale)
   - Source: "Deploy from a branch"
   - Branch: `main` → cartella `/ (root)`
   - Clicca "Save"

6. **Aspetta 1-2 minuti** e l'app sarà online su:
   ```
   https://TUO_USERNAME.github.io/cucina-app
   ```

### 📲 Usa su tutti i dispositivi:
- Apri l'URL su PC, telefono, tablet
- Aggiungi ai preferiti o alla home screen
- **I dati sono ancora locali** (ogni dispositivo ha la sua copia)

---

## 🔄 OPZIONE 3: Sincronizzazione Cloud (la migliore!)

Per avere i dati sincronizzati automaticamente tra tutti i dispositivi, posso aggiungere Firebase (gratuito).

### Cosa serve:
1. Account Google (ce l'hai già)
2. 5 minuti per configurare Firebase

### Vantaggi:
- ✅ Dati sincronizzati in tempo reale
- ✅ Accesso da PC, telefono, tablet
- ✅ Backup automatico sul cloud
- ✅ Gratuito fino a 1GB di dati (più che sufficiente)

**Vuoi che ti guidi per aggiungere Firebase?** Ti basta dirmi "Sì, aggiungi Firebase" e ti do i passi.

---

## 🔧 Come Aggiornare l'App

### Se usi in locale:
- Sostituisci `index.html` con la nuova versione
- I tuoi dati non vengono persi (sono salvati nel browser)

### Se usi GitHub Pages:
```bash
# Dopo aver modificato index.html
git add .
git commit -m "Aggiornamento app"
git push
```
In 1-2 minuti l'app online si aggiorna automaticamente!

---

## 💾 Backup dei Dati

**IMPORTANTE:** Fai backup regolari!

1. Clicca "Esporta" nell'app
2. Salva il file JSON in un posto sicuro (Drive, OneDrive...)
3. Per ripristinare: clicca "Importa" e seleziona il file

**Suggerimento:** Fai un export ogni settimana e salvalo nel cloud!

---

## 🆘 Risoluzione Problemi

**L'app non si apre:**
- Verifica di usare un browser moderno (Chrome, Firefox, Safari, Edge)
- Prova a disabilitare estensioni che bloccano JavaScript

**Ho perso i dati:**
- Se hai un backup JSON, usa "Importa"
- Altrimenti, controlla se il browser ha ancora i dati: F12 → Application → Local Storage → cerca "cucinaAppData"

**Su GitHub Pages non funziona:**
- Aspetta 5 minuti dopo il primo push
- Controlla che il file si chiami esattamente `index.html` (minuscolo)
- Verifica nelle Settings → Pages che sia attivo

---

## 🎯 Prossimi Passi

**Decidi quale opzione vuoi:**

1. **Uso locale** → Hai già tutto pronto! Apri `index.html`

2. **Hosting online** → Segui i passi GitHub Pages sopra

3. **Con sincronizzazione** → Dimmi "Aggiungi Firebase" e ti guido

**Con Claude Code è tutto più veloce!** Posso aiutarti anche con i comandi Git se serve 😊