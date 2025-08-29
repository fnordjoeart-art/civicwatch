Civic Watch – Pacchetto Admin (Decap CMS / Netlify CMS)
=====================================================

CONTENUTO
- /admin/index.html        → Pannello amministrazione raggiungibile su /admin
- /admin/config.yml        → Configurazione CMS (collezioni pagine, news, impostazioni)
- /content/pages/*.md      → Pagine gestite dal CMS
- /content/news/*.md       → News/Avvisi gestiti dal CMS
- /src/site.json           → Impostazioni base della home (hero e CTA)
- /public/uploads/         → Cartella dove finiscono le immagini caricate dal CMS

COME ATTIVARLO (senza usare GitHub Desktop)
1) Su Netlify: Site → Identity → Enable Identity (Registration: Invite only)
2) Identity → Settings → Services → Enable Git Gateway
3) Identity → Users → Invite → inserisci la tua email → accetta l'invito
4) Fai un nuovo deploy caricando TUTTO questo pacchetto dentro al progetto esistente
   - Netlify → Deploys → "Upload deploy" → trascina la cartella *intera* del sito con dentro anche la cartella /admin
   - Oppure fai "Drag & drop" del pacchetto sul tuo sito (verrà creato un deploy con i nuovi file).
5) Vai su https://TUO-DOMINIO/admin → login con la mail invitata → gestisci contenuti.

NOTE
- Se il tuo progetto usa Astro, assicurati che il tuo template legga:
  - /content/pages e /content/news (Markdown) nei componenti/rotte, oppure adatta le path in config.yml.
  - /src/site.json per la hero (o aggiorna il tuo codice per farlo).
- Modifica `site_url` e `logo_url` in config.yml se necessario.
- Se il ramo principale NON è `main`, cambia `branch` in config.yml.

Assistenza rapida
- Se /admin mostra "Errore autenticazione": verifica Identity + Git Gateway + invito utente.
- Se non vedi le raccolte: conferma che le cartelle esistano nel deploy (content/pages, content/news).
- Se le immagini non compaiono online: controlla che `public_folder` sia `/uploads` e che il deploy includa /public/uploads.
