
## Che limitazione ha la funzione di threshold nella regressione lineare?

**![](https://lh7-us.googleusercontent.com/oyxSUHFjva4JzXCuwKJklwOLdgv-CjPjpI4LAsoygJXPDQKINBH9WHNB53tLqTjUJGzjC0DI1VAUZyqqBP5zCYSGvGdxTSxQ87MROylCs8B5Tx8lSBCsp8C13yWPYBkl7kNPYEDuwDzdkPXbHGaGRMOcMQ=s2048)**

<font color="#00b050">IMPOSSIBILE, far passare una retta tra i punti</font>(non è comodo far passare una retta orizzontale)

## E come faccio?

Con la regressione logistica 

#definizione Logistic Function
	 $w\times x$ si chiamano logics (logaritmic digits)

e cosa vediamo ora?

![[Pasted image 20240312084912.png]]

Osserviamo che l'intervallo è molto breve
La proprietà importante che $\sigma$ funziona da etichetta, ovvero osservandola capiremo la probabilità del valore che verrà assunto

<font color="#ff0000">Possiamo usare una loss di tipo L2 ma non è ottimale</font> 

## Binary Cross Entropy Loss


Utilizzare regressione logistica per valutare obesità del paziente, le features devono essere numeriche

Usare regola del gradiente binary cross entropy loss
# Implementare nell'homework
- [x] Fino a overweight 0 e obesity 1 
- [x] Regressione lineare formula chiusa su weight 
- [x] Regressione lineare da implementare con gradient descent weight 
- [ ] Regressione logistica
- [ ] Usare regola del gradiente binary cross entropy loss
- [ ] Implementare albero decisionale (slide 01-253)
- [ ] Nearest Neighbor solo classificazione da implementare (slide 03-55) k = 1 va bene
- [ ] Distanza euclidea 

## Piecewise linear model

#definizione <font color="#00b050">Piecewise linear model</font>

Consiste in un modello memory-based( si memorizzano tutti i punti e si capisce la classificazione da assegnare al nuovo oggetto). 

es. Se io ho n punti ho bisogno di n punti di memoria per memorizzare tutti  i punti, quindi se ho tanti punti diventa ingestibile 

## Table lookup

#definizione Table lookup

Metodo stupido basato non sulla memoria, consiste nel mettere in una tabella di lookup e controllo se il valore di x è stato già messo, se esiste ritorno il valore della y associata. Se il valore non è presente non funzionerà il ritorno, overfitterà con certezza

Possiamo migliorare il modello tramite l'approccio <font color="#ff0000">Nearest-Neighbor </font>

## Nearest Neighbor

#definizione Nearest Neighbor

 Come table lookup ma ritorno l' etichetta del più vicino valore che trovo se non presente

#definizione Nearest-Neighbor Classification


#definizione Nearest-Neighbor Regression


#definizione Locality-Sensitive Hashing


#definizione K-Nearest-Neighbors


#definizione K-Nearest-Neighbor Linear Regression
