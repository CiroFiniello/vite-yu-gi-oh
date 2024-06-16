Descrizione:
Create un nuovo progetto utilizzando Vite e Vue 3 e definite i componenti necessari per strutturare il layout come da screenshot allegato.
Al caricamento della pagina, effettuate una chiama ajax all'API di Yu Gi Oh: https://db.ygoprodeck.com/api/v7/cardinfo.php e con i dati restituiti, stampate una card per ogni carta.
ATTENZIONE:
l’api restituisce tutti i risultati in un colpo solo.
Per evitare attese e/o rallentamenti nelle richieste, potete diminuire il numero di risultati sfruttando i parametri num e offset
https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0
Bonus:
Creare un componente loader da visualizzare fintantoché i risultati non sono pronti.
Documentazione:
https://ygoprodeck.com/api-guide/

Iniziamo col decidere i componenti da creare, sicuramente voglio un AppMain.vue , e un AppHeader.vue,
 all'interno di header metterò l'h1 con il titolo
 mentre nel main, creerò due section, una search e l'altra body, dividerò poi i componenti, 
 ma inizierò col creare il componente ListCards che avrà il compito di fare una chiamata get all'indirizzo
 proseguirò analizzando il dato, e inserendo all'interno del foglio i dati previsti,


 ho deciso che per velocizzare il processo importerò anche bootstrap.