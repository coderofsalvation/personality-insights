---

copyright:
  years: 2019
lastupdated: "2019-03-19"

subcollection: personality-insights

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Alta disponibilità e ripristino di emergenza
{: #ha-dr}

Il servizio {{site.data.keyword.personalityinsightsfull}} è altamente disponibile all'interno di qualsiasi ubicazione {{site.data.keyword.cloud_notm}}. Non ha requisiti di backup e ripristino per il ripristino di emergenza.
{: shortdesc}

## Alta disponibilità
{: #high-availability}

Il servizio {{site.data.keyword.personalityinsightsshort}} è altamente disponibile senza singoli punti di malfunzionamento all'interno di qualsiasi ubicazione {{site.data.keyword.cloud_notm}} (Ad esempio, Dallas o Washington, DC). Il servizio raggiunge automaticamente e in modo trasparente l'alta disponibilità tramite la funzione regione multizona (o MZR, Multi-Zone Region) fornita da {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} consente più zone che non condividono un singolo punto di malfunzionamento all'interno di una singola ubicazione. Fornisce anche un bilanciamento del carico automatico tra le zone all'interno di una regione. 

## Ripristino di emergenza
{: #disaster-recovery}

Il servizio {{site.data.keyword.personalityinsightsshort}} è senza stato. Non memorizza dati utente in {{site.data.keyword.cloud_notm}}. In caso di errore catastrofico in una regione, completa la seguente procedura: 

1.  Crea una nuova istanza del servizio {{site.data.keyword.personalityinsightsshort}} in una regione diversa. 
1.  Modifica la tua applicazione per utilizzare l'URL e le credenziali della nuova istanza del servizio. 
