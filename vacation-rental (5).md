# Playbook: Sito casa vacanze (prenotazioni dirette)

## Obiettivo
Sottrarre prenotazioni alle OTA: il sito deve battere l'annuncio Booking/Airbnb
su fiducia, informazioni e convenienza.

## Fase 0 — Contesto
- [ ] brain/: struttura, zona, punti di forza, prezzi, recensioni esistenti
- [ ] Chiedi: canale di prenotazione (form richiesta? motore con calendario? link WhatsApp?)

## Fase 1 — Struttura pagine
- [ ] Home = landing: hero con foto migliore + "perché prenotare diretto"
      (sconto vs OTA, contatto diretto, flessibilità)
- [ ] Pagina alloggio: galleria, servizi, piantina, regole, dettagli pratici
- [ ] La zona: cosa fare, distanze reali (spiagge, ristoranti), mappa
- [ ] Recensioni: importate dalle OTA con fonte dichiarata
- [ ] Contatti/prenota: form + WhatsApp + telefono (gli host convertono al telefono)

## Fase 2 — Elementi di fiducia (critici: qui si batte l'OTA)
- [ ] Host con nome e volto; "chi vi accoglie"
- [ ] Politiche chiare: cancellazione, check-in, caparra, animali
- [ ] Prezzi trasparenti o "richiedi disponibilità" con risposta in X ore

## Fase 3 — SEO locale
- [ ] JSON-LD VacationRental/LodgingBusiness + geo + amenityFeature + aggregateRating
- [ ] Keyword: "[tipo alloggio] [località]" + pagine zona ("casa vacanze vicino [attrazione]")
- [ ] Google Business Profile menzionato nelle note di consegna

## Fase 4 — Tecnica
- [ ] Astro (statico, velocissimo, foto ottimizzate AVIF)
- [ ] Galleria lightweight, lazy, con preload della prima immagine
- [ ] Form richiesta → email + thank-you page tracciata

## Fase 5 — Self-review
- [ ] Checklist standard + test: "prenoterei qui invece che su Booking?" Perché?
