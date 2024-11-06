# MPAY

Strumento della Regione Marche per la gestione dei pagamenti in favore di tutti gli enti.

MPay è la piattaforma regionale della Regione Marche che permette di pagare online imposte, tributi, oneri e sanzioni e di tenere facilmente sotto controllo la propria posizione amministrativa.
Con MPay si possono pagare i servizi di trasporto e mensa scolastica, multe e verbali di contravvenzione, COSAP, TOSAP, Canone Unico e bollo auto, ticket e prestazioni del servizio sanitario regionale.

## SERVIZI
- Pagamenti con bollettini: basta indicare l'Ente verso il quale fare il pagamento e inserire gli estremi del bollettino o del IUV (Identificativo Univoco di Versamento).
- Versamenti spontanei: basta inserire le informazioni richieste dal sistema: importo, data, codice fiscale e causale del versamento.
- Estratto Conto: basta registrarsi con SPID o sistema di autentificazione riconosciuto dalla Regione Marche e ogni cittadino potrà  accedere alla propria posizione debitoria e verificare il dovuto nei confronti degl'Enti aderenti al servizio.

URL = https://mpay.regione.marche.it/mpay/default/homepage.do


## Link documentazione aggiuntiva non inclusa nel presente repository;
https://www.regione.marche.it/Portals/0/Paesaggio_Territorio_Urbanistica/GenioCivile/CONCESSIONI%20AREE%20DEMANIALI/2020/istruzioni_pagamento_MyPAY_per_il_cittadino.pdf


## Spiegazione struttura del repository anche a beneficio dei potenziali contributori (struttura delle directory e dei branch);

Librerie per poter permettere a repo webservice e front-end di essere compilati correttamente:
com.esed.easybridge.core: libreria usata dal WS Easybridge per primitive modello 1 con pagopa.
com.esed.pagopa.pdf: componente per la creazione degli avvisi di pagamento.
com.esed.log.req: componente per la scritura dei log su tabella di alcuni metodi MPAY
com.seda.payer.ext: componente per il colloquio con il portale esterno.
com.seda.payer.pro.rendicontazione: componente per la rendicontazione dei pagamenti
com.seda.payer.rtbatch.base: componente per la conserazione
pagonet-base: pom.xml base per le librerie generali necessarie ai vari repo.
com.seda.payer.core: componente busines MPAY per l'interrogazione delle Stored procedure ed il colloquio con il database.

Jar Client da compilare necessari sia per i front-end che per i WS:
Sono client predisposti per i relativi Webservice e la spiegazione sarà  eseguita al lato dei WebServices se REPO proprietari.

com.esed.payer.monitoraggio.webservice.client
com.esed.easybridge.webservice.client
com.esed.payer.archiviocarichi.webservice.client
com.seda.payer.notifiche.webservice.client
com.seda.payer.ottico.webservice.client
com.seda.smssender.webservices.client
com.esed.payer.stampaavvisopagopa.webservice.client
com.seda.payer.integraottico.webservice.client
com.seda.payer.mercati.webservices.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
com.seda.payer.gateways.webservice.client
org.esed.myPayPagonet.webservice.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
com.seda.payer.integrazioneente.webservice.client
com.seda.payer.bancadati.webservice.client
com.seda.cart.webservices.client
com.seda.pagamenti.lottomatica.webservice.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
org.e_sed.payer.attestatiPagamento.webservice.client
com.seda.emailsender.webservices.client
com.esed.nodospc.wisp2.webservice.client
com.seda.payer.agenda.webservice.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
com.seda.payer.nodospc.webservices.client
com.esed.authservice.webservice.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
it.seda.risconet.WS_PROVVEDIMENTI_EXT: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
com.seda.payer.impostasoggiorno.webservice.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
com.seda.payer.cup.webservices.client
com.seda.security.webservice.client
it.seda.risconet.ws_provvedimenti_ext.client: WS esterno non utilizzato da MPAY ma necessario per la compilazione del front-end
com.seda.payer.integraente.webservice.client
it.maggioli.pagopa.jppa.client
com.seda.payer.pgec.webservice.client

Repo WebServices da compilare successivamente ai componenti precedenti.
com.seda.payer.integraottico.webservice; WS per estrarre i PDF di estratto conto se avvisi gestiti da Enti e non da MPAY
com.esed.easybridge.webservice; WS per il colloquio con PagoPA modello 1
com.seda.payer.pgec.webservice; WS per il colloquio con il Database per la parte di configurazione  e pagamento.
com.seda.payer.notifiche.webservice: WS per la notifica di pagamento ai contribuenti.
org.e_sed.payer.attestatiPagamento.webservice: Ws interrogato dagli Enti per avere informazioni su una transazione
com.seda.payer.bancadati.webservice: Ws interno per colloquio di alcune funzionalità  del repo /manager
com.seda.payer.ottico.webservice: Ws di integrazione per gestione download Avvisi dentro MPAY
com.seda.smssender.webservices: WS invio SMS se integrazione presente
org.e_sed.payer.recupera.iuv.webservice: WS per ricercare Avvisi dentro BlackBox o Estratto Conto MPAY
com.esed.log.req.webservice: Ws gestione LOG 
com.seda.emailsender.webservices: WS per invio mail
com.esed.payer.stampaavvisopagopa.webservice: Ws richiamato da Enti per la stampa degli avvisi.
com.esed.pagopa.pdf.webservice: Ws richiamato dai Batch per la generazione degli avvisi
com.esed.payer.monitoraggio.webservice: WS interrogato dagli Enti per chiedere informazioni su una transazione
com.esed.payer.archiviocarichi.webservice: WS per la gestione dell'Archivio Carichi In Attesa di MPAY (estratto conto interno)
com.seda.payer.integraente.webservice: WS per interrogare Bollettin e Estratto Conto.
com.seda.cart.webservices: Ws per gestione Carrello
com.seda.payer.gateways.webservice: Ws per la gestione dei gateway di pagamento
com.seda.security.webservice: Ws per la sicurezza (login)
com.seda.payer.nodospc.webservice: Ws per la gestione dei modelli 3.


Front-end:
org.seda.payer.web: app per permettere ai contribuenti di eseguire pagamenti e visualizzare il proprio estratto conto.
org.seda.payer.manager.web: app per la configurazione MPAY e monitoraggio da parte degli Enti
PortaleEsternoTest: applicatione di test che simula della valorizzazione del Carrello su MPAY da parte di un portale esterno.


Batch:
com.seda.payer.mip: batch per allineamento notifica con i portali esterni
com.seda.payer.allineamentogateways: batch per allineamento transazioni di pagamento con il gateway di appartenenza
com.seda.payer.rtbatch.invio: batch per conservazione / invio
com.seda.payer.rtbatch.controllo: batch per conservazione / controllo
com.esed.integrazioneposte.batch: batch per integrazione con Poste
com.seda.payer.rendicontazione: batch per rendicontazione pagamenti
com.esed.payer.caricaTabelleAppIO: batch integrazione appIO
com.esed.payer.notificapagamentiext.batch: batch allineamento notifiche pagamenti tramite chiamata SOAP con sistemi esterni
com.seda.payer.performance.tester: batch controllo risposta webservice.
com.esed.pagonet.checkservices: batch controllo sistema e perfomance chiamate integraEnte e pagopa
com.esed.payer.loadPdfFromGeos: caricament PDF generati da inviaAvvisiForGeos
com.seda.payer.utility: batch di utiliti sulle utenze o caricamenti massivi
com.seda.payer.estrattoconto_csv: batch caricament pendenze su estratto conto MPAY
com.seda.payer.quadratura.nodo: batch di scarico flussi rendicontazione nodo e quadratura degli stessi con le transazioni pagate dai cittadini.
com.esed.payer.inviaAvvisiForGeos: batch per generazione PDF delle pendenze caricate dal processo estratto_conto_csv

## Elenco dettagliato prerequisiti e dipendenze (sistemi operativi, librerie, framework eccetera) con esplicita indicazione di eventuali dipendenze da software commerciali;

Tutti i repo MPAY utilizzano MAVEN come  strumento di automazione della costruzione e di gestione delle dipendenze. 

All'interno di ogni repo MPAY è presente nel proprio pom.xml il richiamo di tutte le dipendenze necessarie.
Esempio:  
   <parent>
      <groupId>it.maggioli.informatica.base.pom</groupId>
      <artifactId>pagonet-base</artifactId>
      <version>1.5.0</version> <!-- LP 20240826 - PGNTEASYBC-1 -->
      <relativePath/>
   </parent>

L'elenco delle librerie quindi è presente nel pom.xml del progetto https://github.com/regione-marche/pagonet-base

## Istruzioni per l'installazione:
procedura di installazione di requisiti e dipendenze;
build system (se previsto dal progetto);
comandi per la compilazione o il deployment, possibilmente automatizzati da uno script/Makefile (se previsto dal progetto);

- compilare con maven tutti i repo.
- installare wildfly 19 o 20.
- configurare in wildfly le connection poll indicate dentro i jboss-web-xml dei repo WebServices
- configurare le variabili d'ambiente richiamate dai repo installati.
- configurare i file properties dei repo.
- installare in wildfly i war prodotti dalle compilazioni.

Fare riferimento al manuale "MANUALE_ISTALLAZIONE_MPAY.docx"

## Status del progetto:
stato di alpha/beta/stabile eccetera;
importanti limitazioni o known issues;

I repo hanno al loro interno la branch "develop" e "master"
develop: branch rilascio sviluppo e collaudo.
master: branch stabile ed installata in ambiente di esercizio

(SHOULD) link ad eventuali sistemi di Continuous Integration (TravisCI, CircleCI), code coverage (copertura del codice) ed altre metriche associati al repository;

(SHOULD) documentazione relativa all'eventuale utilizzo di sistemi per semplificare e accelerare il deployment in ambiente di sviluppo, test e produzione (ad esempio immagini Docker o altri sistemi di virtualizzazione con predisposizione di immagini preconfigurate);

## Nomi dei detentori di copyright, ovvero l'Amministrazione committente;

## Nomi dei soggetti incaricati del mantenimento del progetto open source (è richiesto il nome dell'azienda e facoltativamente si possono aggiungere nomi delle persone incaricate);

## Indirizzo e-mail a cui inviare segnalazioni di sicurezza (specificare che le segnalazioni di sicurezza non vanno inviate attraverso l'issue tracker pubblico ma devono essere inviate confidenzialmente a tale indirizzo e-mail);