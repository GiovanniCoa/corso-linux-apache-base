# Rotazione dei log

La gestione efficace dei file di log è un aspetto critico per garantire il corretto funzionamento di un sistema informatico e per facilitare il troubleshooting in caso di problemi. Tra le varie pratiche utilizzate per gestire i log in maniera efficiente, la rotazione dei log risulta essere una delle più importanti.

## Cos'è la rotazione dei log

La rotazione dei log è il processo mediante il quale i file di log vengono rinominati o spostati in modo da evitare che diventino troppo grandi e ingestibili. Questo processo permette di mantenere i log in modo ordinato e di evitare che occupino troppa memoria sul sistema.

## Utilizzo di logrotate

Logrotate è uno strumento ampiamente utilizzato per gestire la rotazione dei log su sistemi Unix e Linux. Esso permette di definire regole per la rotazione dei log, specificando ad esempio la dimensione massima dei file di log, il numero di file da mantenere e la frequenza con cui eseguire la rotazione.

## Come configurare logrotate

Per configurare logrotate è necessario creare un file di configurazione all'interno della directory `/etc/logrotate.d/`. In questo file è possibile specificare le regole di rotazione per ciascun file di log da gestire.

Ad esempio, il seguente file di configurazione definisce le regole per la rotazione del file di log `/var/log/syslog`:

```
/var/log/syslog {
    rotate 7
    weekly
    missingok
    notifempty
    compress
}
```

In questo caso, logrotate manterrà fino a 7 file di log rotati, eseguirà la rotazione settimanalmente, comprimerà i file vecchi e non genererà errori nel caso in cui il file di log non esista.

## Esecuzione di logrotate

Per eseguire manualmente la rotazione dei log utilizzando logrotate è possibile lanciare il comando `logrotate -f /etc/logrotate.conf`. Questo comando forzerà logrotate ad eseguire la rotazione dei log basandosi sulle regole definite nel file di configurazione.

## Conclusioni

La rotazione dei log è una pratica fondamentale per mantenere i file di log in ordine e per evitare che diventino ingestibili. Logrotate è uno strumento potente e flessibile che permette di gestire la rotazione dei log in maniera efficiente e automatizzata. Configurare correttamente logrotate è quindi un passo importante per garantire la corretta gestione dei log su un sistema informatico.