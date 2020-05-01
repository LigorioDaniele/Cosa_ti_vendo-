# Cosa_ti_vendo?

### Frequent-Pattern
Association Rule Mining è utile quando si desidera trovare un'associazione tra diversi elementi, trovare pattern frequenti in un data warehouse, datalake o qualsiasi altro repository che contiene le informazioni che ci servono.

Di seguito alcuni concetti chiave mediante l'utilizzo prodotti comuni per una più semplice interpretazione:

**1.** Support: è la popolarità di un prodotto/servizio. Il supporto dell'articolo A non è altro che il rapporto tra le transazioni che coinvolgono A rispetto al numero totale di transazioni.

    Support (Uva) = (Transazioni che coinvolgono l'uva) / (Transazione totale)

    Support (uva) = 0,666

**2.** Confidence: probabilità che il cliente abbia acquistato sia A che B. Divide il numero di transazioni che coinvolgono sia A che B per il numero di transazioni che coinvolgono B.

    Confidence(A => B) = (Transazioni che coinvolgono sia A che B) / (Transazioni che coinvolgono solo A)
    Confidence({Uva, Mela} => {Mango}) = Supporto (Uva, Mela, Mango) / Supporto (Uva, Mela)

    = 2/6 / 3/6 
    = 0.667

**3.** Lift: aumento della vendita di A quando vendi B.

    Lift (A => B) = Confidence (A, B) / Support (B)
    Lift ({Uva, Mela} => {Mango}) = 1

Il valore determinato dal Lift indica il grado di correlazione tra i prodotti.

**-Lift (A => B) = 1** significa che non c'è correlazione all'interno del set di elementi.

**-Lift (A => B)> 1** significa che esiste una correlazione positiva all'interno del set di articoli, vale a dire che i prodotti nel set di articoli, A e B hanno maggiori probabilità di essere acquistati insieme.

**-Lift (A => B) <1** significa che esiste una correlazione negativa all'interno del set di articoli, vale a dire che è improbabile che vengano acquistati insieme prodotti nel set di articoli, A e B.

La libreria di utilizzata è FP-growth algorithm 
[Spark FP-growth](https://spark.apache.org/docs/2.2.0/ml-frequent-pattern-mining.html)

Per sfruttare un cluster di nodi, consultare parallel fp-growth
[Spark PFP-growth](https://dl.acm.org/doi/10.1145/1454008.1454027)


