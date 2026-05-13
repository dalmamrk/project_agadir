# Linee Guida per Agenti AI (Modifiche Eseguite)

Questo documento contiene le direttive fondamentali per qualsiasi agente AI che andrà a modificare, aggiornare o estendere questo progetto.

## 📱 Contesto e Destinazione d'Uso
- **Progetto**: Minisito statico e Travel Dashboard per una vacanza ad Agadir (Marocco).
- **Target**: L'unico utente finale sarà il proprietario del progetto.
- **Dispositivo**: L'app sarà usata ESCLUSIVAMENTE su un **iPhone 12** in modalità **verticale (portrait)**. Tutto il design deve ruotare attorno a questo vincolo.
- **Distribuzione**: Il progetto verrà pubblicato su **GitHub Pages**.
- **Uso Offline**: Deve funzionare offline o in condizioni di rete instabile (tramite Service Worker).

## 🛠️ Stack Tecnologico e Architettura
- **Architettura**: Multi-page app statica basata su HTML, CSS e JS nativo. Nessun framework (niente React, Vue, ecc.), nessun bundler.
- **Styling**: Tailwind CSS via CDN (`cdn.tailwindcss.com`).
- **Tema**: Dark mode forzata. La palette è focalizzata su colori scuri (Slate) per gli sfondi e tocchi di calore/colore (Amber, Emerald, Sky) per evidenziare elementi.
- **Font**: Inter (fornito tramite Google Fonts).

## ⚠️ Regole e Vincoli Categorici per le Modifiche

1. **Mobile-First Estremo**: Qualsiasi nuova UI (pagine, modali, componenti) deve essere ottimizzata SOLO per schermi mobile verticali. Non sprecare tempo o codice per layout desktop responsivi.
2. **Nessuna Dipendenza Esterna Aggiuntiva**: Evita l'uso di nuove librerie esterne. Mantieni le risorse locali usando **percorsi relativi** (`./` o nome del file).
3. **Integrità PWA**: Non alterare o rimuovere i meta-tag di iOS (`apple-mobile-web-app-capable`, `safe-area-inset-top/bottom`) o la registrazione del Service Worker (`sw.js`).
4. **Stile Visivo Premium**: 
   - Mantieni un'estetica premium: usa gradienti sottili, bordi traslucidi (`border-slate-700/50`), card con effetti glassmorphism o shadow dedicate.
   - Ogni elemento interattivo deve avere un feedback al tocco (es. `active:scale-[0.97]` o `hover:bg-slate-700/80`).
5. **Consistenza tra le Pagine**: Tutte le nuove pagine create (es. pagine di itinerario come `tamri-timlaline.html`) devono mantenere esattamente lo stesso header di navigazione e stile della `index.html`.
6. **Integrazione Navigatore (Google Maps)**: Qualsiasi link a un luogo o a coordinate DEVE essere formattato come link di navigazione diretta (`https://www.google.com/maps/dir/?api=1&destination=lat,lng` oppure `destination=NomePosto`). Evita i semplici link di ricerca (es. `?q=`). Questo assicura che il link apra istantaneamente l'app nativa di Google Maps su iOS in modalità navigatore (avviando il routing e sfruttando le mappe offline scaricate dall'utente).

## 📝 Storico Task Completati
I task di setup iniziale sono stati tutti eseguiti e verificati. Questi includono:
- Redesign completo dell'Header (aggiunta sottotitolo e gradiente).
- Styling della Mappa e layout della griglia Convertitore Valuta.
- Redesign dei pulsanti di navigazione principale con icone ed effetti attivi.
- Configurazione avanzata di Tailwind, font Inter e safe area per iOS.
- PWA e Service worker settati per funzionare offline.
- Convertiti tutti i link di destinazione/coordinate (inclusi quelli di `tamri-timlaline.html`) per usare l'URL schema "Directions" di Google Maps, integrando l'app in un vero e proprio navigatore GPS locale.

*Puoi usare questo file come riferimento per tutte le sessioni future.*
