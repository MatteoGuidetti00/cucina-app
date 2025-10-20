# 🔥 Guida Sincronizzazione Firebase

## Cosa fa Firebase?
Salva tutti i dati (ricette, inventario, spesa, tracking) sul cloud Google.
Quando modifichi da PC, si sincronizza automaticamente sul telefono e viceversa!

---

## Setup Firebase (5 minuti)

### 1. Crea progetto Firebase

1. Vai su https://console.firebase.google.com
2. Clicca "Aggiungi progetto"
3. Nome: `cucina-app` (o quello che vuoi)
4. Disabilita Google Analytics (non serve)
5. Clicca "Crea progetto"

### 2. Aggiungi app web

1. Nel progetto, clicca l'icona `</>` (Add web app)
2. Nome: "Gestionale Cucina"
3. NON spuntare Firebase Hosting
4. Clicca "Registra app"
5. **COPIA** il codice di configurazione che appare (firebaseConfig)

Esempio di cosa copiare:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSy...",
  authDomain: "cucina-app-xxxxx.firebaseapp.com",
  projectId: "cucina-app-xxxxx",
  storageBucket: "...",
  messagingSenderId: "...",
  appId: "..."
};
```

### 3. Attiva Firestore Database

1. Nel menu laterale → "Firestore Database"
2. Clicca "Crea database"
3. Modalità: **"Test mode"** (per ora, poi cambi le regole)
4. Location: `europe-west1` (Europa)
5. Clicca "Attiva"

### 4. Configura regole di sicurezza (IMPORTANTE!)

Nel pannello Firestore → scheda "Regole":

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Richiedi autenticazione per leggere/scrivere
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

### 5. Attiva Autenticazione

1. Menu laterale → "Authentication"
2. Clicca "Inizia"
3. Scheda "Sign-in method"
4. Abilita "Email/Password"
5. Clicca "Salva"

---

## Dimmi quando hai completato questi passi!

Quando hai:
- ✅ Creato il progetto Firebase
- ✅ Copiato le credenziali firebaseConfig
- ✅ Attivato Firestore
- ✅ Attivato Authentication

Dimmi "Ho finito il setup Firebase" e ti creo la versione aggiornata dell'app con sincronizzazione! 🚀

Ti servirà solo incollare le tue credenziali Firebase nel codice.

---

## Alternative a Firebase (se preferisci)

### Supabase (simile a Firebase, ma open source)
- Setup più complesso
- Più controllo sui dati
- Database SQL invece di NoSQL

### Backend proprio (avanzato)
- Node.js + MongoDB/PostgreSQL
- Hosting su Heroku/Railway/Render
- Più lavoro ma totale controllo

**Consiglio:** Inizia con Firebase, è la soluzione più semplice e affidabile!
