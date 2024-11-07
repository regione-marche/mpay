# MPAY

Strumento della Regione Marche (c) per la gestione dei pagamenti in favore di tutti gli enti.

MPay è la piattaforma della Regione Marche (c) che permette di pagare online imposte, tributi, oneri e sanzioni e di tenere facilmente sotto controllo la propria posizione amministrativa.
Con MPay si possono pagare i servizi di trasporto e mensa scolastica, multe e verbali di contravvenzione, COSAP, TOSAP, Canone Unico e bollo auto, ticket e prestazioni del servizio sanitario regionale.

## SERVIZI

- **Pagamenti con bollettini**: basta indicare l'Ente verso il quale fare il pagamento e inserire gli estremi del bollettino o del IUV (Identificativo Univoco di Versamento).
- **Versamenti spontanei**: basta inserire le informazioni richieste dal sistema: importo, data, codice fiscale e causale del versamento.
- **Estratto Conto**: basta registrarsi con SPID o sistema di autentificazione riconosciuto dalla Regione Marche e ogni cittadino potrà  accedere alla propria posizione debitoria e verificare il dovuto nei confronti degl'Enti aderenti al servizio.

URL = https://mpay.regione.marche.it/mpay/default/homepage.do


## Link documentazione aggiuntiva non inclusa nel presente repository

https://www.regione.marche.it/Portals/0/Paesaggio_Territorio_Urbanistica/GenioCivile/CONCESSIONI%20AREE%20DEMANIALI/2020/istruzioni_pagamento_MyPAY_per_il_cittadino.pdf


## Spiegazione struttura del repository anche a beneficio dei potenziali contributori

Il software si compone di 

* frontend
* procedure batch
* librerie 
* jar client 
* WebServices

Di seguito l'elenco dei repository di riferimento:

* **Librerie** per poter permettere a repo webservice e front-end di essere compilati correttamente:
  * [com.esed.easybridge.core](https://github.com/regione-marche/com.esed.easybridge.core): libreria usata dal WS Easybridge per primitive modello 1 con pagopa.
  * [com.esed.pagopa.pdf](https://github.com/regione-marche/com.esed.pagopa.pdf): componente per la creazione degli avvisi di pagamento.
  * [com.esed.log.req](https://github.com/regione-marche/com.esed.log.req): componente per la scritura dei log su tabella di alcuni metodi MPAY
  * [com.seda.payer.ext](https://github.com/regione-marche/com.seda.payer.ext): componente per il colloquio con il portale esterno.
  * [com.seda.payer.pro.rendicontazione](https://github.com/regione-marche/com.seda.payer.pro.rendicontazione): componente per la rendicontazione dei pagamenti
  * [com.seda.payer.rtbatch.base](https://github.com/regione-marche/com.seda.payer.rtbatch.base): componente per la conserazione
  * [pagonet-base](https://github.com/regione-marche/pagonet-base): pom.xml base per le librerie generali necessarie ai vari repo.
  * [com.seda.payer.core](https://github.com/regione-marche/com.seda.payer.core): componente busines MPAY per l'interrogazione delle Stored procedure ed il colloquio con il database.

* **Jar Client** da compilare necessari sia per i front-end che per i WS:
Sono client predisposti per i relativi Webservice e la spiegazione sarà  eseguita al lato dei WebServices se REPO proprietari.
  * [com.esed.payer.monitoraggio.webservice.client](https://github.com/regione-marche/com.esed.payer.monitoraggio.webservice.client)
  * [com.esed.easybridge.webservice.client](https://github.com/regione-marche/com.esed.easybridge.webservice.client)
  * [com.esed.payer.archiviocarichi.webservice.client](https://github.com/regione-marche/com.esed.payer.archiviocarichi.webservice.client)
  * [com.seda.payer.notifiche.webservice.client](https://github.com/regione-marche/com.seda.payer.notifiche.webservice.client)
  * [com.seda.payer.ottico.webservice.client](https://github.com/regione-marche/com.seda.payer.ottico.webservice.client)
  * [com.seda.smssender.webservices.client](https://github.com/regione-marche/com.seda.smssender.webservices.client)
  * [com.esed.payer.stampaavvisopagopa.webservice.client](https://github.com/regione-marche/com.esed.payer.stampaavvisopagopa.webservice.client)
  * [com.seda.payer.integraottico.webservice.client](https://github.com/regione-marche/com.seda.payer.integraottico.webservice.client)
  * [com.seda.payer.mercati.webservices.client](https://github.com/regione-marche/com.seda.payer.mercati.webservices.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [com.seda.payer.gateways.webservice.client](https://github.com/regione-marche/com.seda.payer.gateways.webservice.client)
  * [org.esed.myPayPagonet.webservice.client](https://github.com/regione-marche/org.esed.myPayPagonet.webservice.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [com.seda.payer.integrazioneente.webservice.client](https://github.com/regione-marche/com.seda.payer.integrazioneente.webservice.client)
  * [com.seda.payer.bancadati.webservice.client](https://github.com/regione-marche/com.seda.payer.bancadati.webservice.client)
  * [com.seda.cart.webservices.client](https://github.com/regione-marche/com.seda.cart.webservices.client)
  * [com.seda.pagamenti.lottomatica.webservice.client](https://github.com/regione-marche/com.seda.pagamenti.lottomatica.webservice.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [org.e_sed.payer.attestatiPagamento.webservice.client](https://github.com/regione-marche/org.e_sed.payer.attestatiPagamento.webservice.client)
  * [com.seda.emailsender.webservices.client](https://github.com/regione-marche/com.seda.emailsender.webservices.client)
  * [com.esed.nodospc.wisp2.webservice.client](https://github.com/regione-marche/com.esed.nodospc.wisp2.webservice.client)
  * [com.seda.payer.agenda.webservice.client](https://github.com/regione-marche/com.seda.payer.agenda.webservice.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [com.seda.payer.nodospc.webservices.client](https://github.com/regione-marche/com.seda.payer.nodospc.webservices.client)
  * [com.esed.authservice.webservice.client](https://github.com/regione-marche/com.esed.authservice.webservice.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [it.seda.risconet.WS_PROVVEDIMENTI_EXT](https://github.com/regione-marche/it.seda.risconet.WS_PROVVEDIMENTI_EXT): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [com.seda.payer.impostasoggiorno.webservice.client](https://github.com/regione-marche/com.seda.payer.impostasoggiorno.webservice.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [com.seda.payer.cup.webservices.client](https://github.com/regione-marche/com.seda.payer.cup.webservices.client)
  * [com.seda.security.webservice.client](https://github.com/regione-marche/com.seda.security.webservice.client)
  * [it.seda.risconet.ws_provvedimenti_ext.client](https://github.com/regione-marche/it.seda.risconet.ws_provvedimenti_ext.client): WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
  * [com.seda.payer.integraente.webservice.client](https://github.com/regione-marche/com.seda.payer.integraente.webservice.client)
  * [it.maggioli.pagopa.jppa.client](https://github.com/regione-marche/it.maggioli.pagopa.jppa.client)
  * [com.seda.payer.pgec.webservice.client](https://github.com/regione-marche/com.seda.payer.pgec.webservice.client)

* Repo **WebServices** da compilare successivamente ai componenti precedenti.

  * [com.seda.payer.integraottico.webservice](https://github.com/regione-marche/com.seda.payer.integraottico.webservice): WS per estrarre i PDF di estratto conto se avvisi gestiti da Enti e non da MPAY
  * [com.esed.easybridge.webservice](https://github.com/regione-marche/com.esed.easybridge.webservice): WS per il colloquio con PagoPA modello 1
  * [com.seda.payer.pgec.webservice](https://github.com/regione-marche/com.seda.payer.pgec.webservice): WS per il colloquio con il Database per la parte di configurazione  e pagamento.
  * [com.seda.payer.notifiche.webservice](https://github.com/regione-marche/com.seda.payer.notifiche.webservice): WS per la notifica di pagamento ai contribuenti.
  * [org.e_sed.payer.attestatiPagamento.webservice](https://github.com/regione-marche/org.e_sed.payer.attestatiPagamento.webservice): Ws interrogato dagli Enti per avere informazioni su una transazione
  * [com.seda.payer.bancadati.webservice](https://github.com/regione-marche/com.seda.payer.bancadati.webservice): Ws interno per colloquio di alcune funzionalità  del repo /manager
  * [com.seda.payer.ottico.webservice](https://github.com/regione-marche/com.seda.payer.ottico.webservice): Ws di integrazione per gestione download Avvisi dentro MPAY
  * [com.seda.smssender.webservices](https://github.com/regione-marche/com.seda.smssender.webservices): WS invio SMS se integrazione presente
  * [org.e_sed.payer.recupera.iuv.webservice](https://github.com/regione-marche/org.e_sed.payer.recupera.iuv.webservice): WS per ricercare Avvisi dentro BlackBox o Estratto Conto MPAY
  * [com.esed.log.req.webservice](https://github.com/regione-marche/com.esed.log.req.webservice): Ws gestione LOG 
  * [com.seda.emailsender.webservices](https://github.com/regione-marche/com.seda.emailsender.webservices): WS per invio mail
  * [com.esed.payer.stampaavvisopagopa.webservice](https://github.com/regione-marche/com.esed.payer.stampaavvisopagopa.webservice): Ws richiamato da Enti per la stampa degli avvisi.
  * [com.esed.pagopa.pdf.webservice](https://github.com/regione-marche/com.esed.pagopa.pdf.webservice): Ws richiamato dai Batch per la generazione degli avvisi
  * [com.esed.payer.monitoraggio.webservice](https://github.com/regione-marche/com.esed.payer.monitoraggio.webservice): WS interrogato dagli Enti per chiedere informazioni su una transazione
  * [com.esed.payer.archiviocarichi.webservice](https://github.com/regione-marche/com.esed.payer.archiviocarichi.webservice): WS per la gestione dell'Archivio Carichi In Attesa di MPAY (estratto conto interno)
  * [com.seda.payer.integraente.webservice](https://github.com/regione-marche/com.seda.payer.integraente.webservice): WS per interrogare Bollettin e Estratto Conto.
  * [com.seda.cart.webservices](https://github.com/regione-marche/com.seda.cart.webservices): Ws per gestione Carrello
  * [com.seda.payer.gateways.webservice](https://github.com/regione-marche/com.seda.payer.gateways.webservice): Ws per la gestione dei gateway di pagamento
  * [com.seda.security.webservice](https://github.com/regione-marche/com.seda.security.webservice): Ws per la sicurezza (login)
  * [com.seda.payer.nodospc.webservice](https://github.com/regione-marche/com.seda.payer.nodospc.webservice): Ws per la gestione dei modelli 3.

* **Front-end**

  * [org.seda.payer.web](https://github.com/regione-marche/org.seda.payer.web): app per permettere ai contribuenti di eseguire pagamenti e visualizzare il proprio estratto conto.
  * [org.seda.payer.manager.web](https://github.com/regione-marche/org.seda.payer.manager.web): app per la configurazione MPAY e monitoraggio da parte degli Enti
  * [PortaleEsternoTest](https://github.com/regione-marche/PortaleEsternoTest): applicatione di test che simula della valorizzazione del Carrello su MPAY da parte di un portale esterno.

* **Batch**:

  * [com.seda.payer.mip](https://github.com/regione-marche/com.seda.payer.mip): batch per allineamento notifica con i portali esterni
  * [com.seda.payer.allineamentogateways](https://github.com/regione-marche/com.seda.payer.allineamentogateways): batch per allineamento transazioni di pagamento con il gateway di appartenenza
  * [com.seda.payer.rtbatch.invio](https://github.com/regione-marche/com.seda.payer.rtbatch.invio): batch per conservazione / invio
  * [com.seda.payer.rtbatch.controllo](https://github.com/regione-marche/com.seda.payer.rtbatch.controllo): batch per conservazione / controllo
  * [com.esed.integrazioneposte.batch](https://github.com/regione-marche/com.esed.integrazioneposte.batch): batch per integrazione con Poste
  * [com.seda.payer.rendicontazione](https://github.com/regione-marche/com.seda.payer.rendicontazione): batch per rendicontazione pagamenti
  * [com.esed.payer.caricaTabelleAppIO](https://github.com/regione-marche/com.esed.payer.caricaTabelleAppIO): batch integrazione appIO
  * [com.esed.payer.notificapagamentiext.batch](https://github.com/regione-marche/com.esed.payer.notificapagamentiext.batch): batch allineamento notifiche pagamenti tramite chiamata SOAP con sistemi esterni
  * [com.seda.payer.performance.tester](https://github.com/regione-marche/com.seda.payer.performance.tester): batch controllo risposta webservice.
  * [com.esed.pagonet.checkservices](https://github.com/regione-marche/com.esed.pagonet.checkservices): batch controllo sistema e perfomance chiamate integraEnte e pagopa
  * [com.esed.payer.loadPdfFromGeos](https://github.com/regione-marche/com.esed.payer.loadPdfFromGeos): caricament PDF generati da inviaAvvisiForGeos
  * [com.seda.payer.utility](https://github.com/regione-marche/com.seda.payer.utility): batch di utiliti sulle utenze o caricamenti massivi
  * [com.seda.payer.estrattoconto_csv](https://github.com/regione-marche/com.seda.payer.estrattoconto_csv): batch caricament pendenze su estratto conto MPAY
  * [com.seda.payer.quadratura.nodo](https://github.com/regione-marche/com.seda.payer.quadratura.nodo): batch di scarico flussi rendicontazione nodo e quadratura degli stessi con le transazioni pagate dai cittadini.
  * [com.esed.payer.inviaAvvisiForGeos](https://github.com/regione-marche/com.esed.payer.inviaAvvisiForGeos): batch per generazione PDF delle pendenze caricate dal processo estratto_conto_csv

## Elenco dettagliato prerequisiti e dipendenze

Tutti i repo MPAY utilizzano MAVEN come  strumento di automazione della costruzione e di gestione delle dipendenze. 

All'interno di ogni repo MPAY è presente nel proprio pom.xml il richiamo di tutte le dipendenze necessarie.
Esempio:  

```xml
   <parent>
      <groupId>it.maggioli.informatica.base.pom</groupId>
      <artifactId>pagonet-base</artifactId>
      <version>1.5.0</version> <!-- LP 20240826 - PGNTEASYBC-1 -->
      <relativePath/>
   </parent>
```

L'elenco delle librerie quindi è presente nel pom.xml del progetto https://github.com/regione-marche/pagonet-base

## Istruzioni per l'installazione:

- compilare con maven tutti i repo.
- installare wildfly 19 o 20.
- configurare in wildfly le connection poll indicate dentro i jboss-web-xml dei repo WebServices
- configurare le variabili d'ambiente richiamate dai repo installati.
- configurare i file properties dei repo.
- installare in wildfly i war prodotti dalle compilazioni.

Fare riferimento al manuale [MANUALE_ISTALLAZIONE_MPAY](https://github.com/regione-marche/mpay/blob/main/MANUALE_ISTALLAZIONE_MPAY.docx)

## Status del progetto:

I repo hanno al loro interno la branch "develop" e "master":

* **develop**: branch rilascio sviluppo e collaudo.
* **master**: branch stabile ed **installata in ambiente di esercizio**

## Nomi dei detentori di copyright

Copyright (c) **Regione Marche Giunta Regionale**, Via Gentile da Fabriano, 9 - 60125 Ancona

La [licenza AGPL](https://github.com/regione-marche/mpay/blob/main/LICENSE.md) si intende applicata ad ogni componente del servizio.
Ogni repository indicato nel seguente file è soggetto alla stessa licenza e tutti gli autori sono ricavabili dai repository di ciascun componente, come indicato nel file [AUTHORS.md](https://github.com/regione-marche/mpay/blob/main/AUTHORS.md).


## Nomi dei soggetti incaricati del mantenimento del progetto open source

* Fabrizio Quaresima
* Andrea Polenta
* Michele Russo

Ditta: **Maggioli spa**, con sede in Via del Carpino, 8, 47822 Santarcangelo di Romagna (RN) - Cod.Fisc. 06188330150 e P.IVA 02066400405




## Indirizzo e-mail a cui inviare segnalazioni di sicurezza

Tutte le segnalazioni di sicurezza vanno inviate **esclusivamente** all'indirizzo **pagamenti.mpay@regione.marche.it**
evitando l'uso dell'issue tracker pubblico di github.com
