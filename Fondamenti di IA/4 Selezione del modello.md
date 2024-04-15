
Il nostro obiettivo nel machine learning è quello di selezionare un "<font color="#ff0000">optimal fit</font>" i nostri "<font color="#ff0000">future examples</font>".

#definizione <font color="#00b050">Optimal fit</font>
	 Si intende l'ipotesi che minimizza l'<font color="#ff0000">error rate</font>: la proporzione delle volte in cui si presenta $h(x)\neq y$ per un $(x,y)$.  

#definizione <font color="#00b050">Future example</font>
	Un esempio futuro deve rappresentare una situazione simile al passato, dobbiamo avere presente che si sta parlando di valori <font color="#ff0000">I.I.D.</font> (**Independent and Identically Distributed**), quindi:
	$\quad$
	 - Identicamente distribuiti:$$P(E_{j})=P(E_{j+1})=P(E_{j+2})=\dots$$
	 - Indipendenti:$$P(E_{j})=P(E_{j}|E_{j-1},E_{j-2},\dots)$$

## <font color="#ffff00">Come facciamo a stimare l'error rate?</font> 

Tramite un test set è possibile misurare la <font color="#ff0000">performance</font>, questo processo si divide in:

- <font color="#ff0000">Training set</font>, per creare l'ipotesi 
- <font color="#ff0000">Test set</font>, per confermarla

## <font color="#ffff00">Ma basta una sola ipotesi?</font>

Il più delle volte <font color="#ff0000">NO</font>, avremo bisogno di creare varie ipotesi basate su:

- testare diversi <font color="#ff0000">modelli di machine learning</font>
- aggiustare gli <font color="#ff0000">hyperparameters</font>
- provare diversi <font color="#ff0000">threasholds</font>, diversi gradi polinomiali, ecc...

## <font color="#ffff00">Cosa sono gli Hyperparameter?</font>

#definizione <font color="#00b050">Hyperparameter</font>
	Parametri di una classe del modello, non del modello individuale.
	Supponendo che un ricercatore generi un ipotesi per una sezione di dati, potrebbe misurare l'error rate con il test set e poi provare con altri hyperparametri

## <font color="#ffff00">Quindi come si divide il processo di valutazione dei dati?</font> 

Bisogna avere <font color="#ff0000">TRE</font> data sets:

- un <font color="#ff0000">training set</font>, che allena i modelli candidati
- un <font color="#ff0000">validation set</font>,  conosciuto anche come il set di sviluppo, per valutare il candidato
- un <font color="#ff0000">test set</font>, per fare una <font color="#ff0000">valutazione finale unbiased</font> del miglior modello

## <font color="#ffff00">Cosa facciamo se non abbiamo abbastanza dati per fare questi tre data sets?</font>

Possiamo ottenerne di più tramite la tecnica <font color="#ff0000">K-fold cross-validation</font>. 

#definizione <font color="#00b050">K-fold cross-validation</font>
	Consiste nel definire i dati con un doppio scopo, quello di training data e quello di validation data, <font color="#ff0000">MA</font> non allo stesso tempo.

Quindi come sviluppiamo questa tecnica?

1. Dividiamo i dati in <font color="#ff0000">k</font> subset di uguale dimensione
2. Attuiamo <font color="#ff0000">k</font> cicli di learning
	- ogni ciclo 1/k di dati è tenuto per il validation set e il restante k-1/k viene utilizzato per il training set
	- Il la media del risultato generale dei test sui <font color="#ff0000">k</font> cicli vale più del singolo risultato in 1/k
	- di solito <font color="#ff0000">k</font> deve essere tra 5 e 10
3. Anche se abbiamo la cross-validation abbiamo comunque bisogno di test set separati

**![](https://lh7-us.googleusercontent.com/UWil0vkmwyZQgXtsEMj734eJnpt9ahG4zThPHwpJKXzNrW6bF3aZLbG_u2xyoG85nGp-cuArv69EKQECoIPMdTjVi0GdoS8AA2kQvOxt9MNWDqWbsK0m6PwJ6kZr8hHcx5bAFNoXGGkrKYd3jPC1qe_neg=s2048)**

## <font color="#ffff00">Fino a dove può spingersi la cross-validation?</font>

L'estremizzazione della cross-validation arriva a <span style="background:#ff4d4f">k=n</span>, si parla di <font color="#ff0000">LOOCV</font>(**leave-one-out cross-validation**)**![](https://lh7-us.googleusercontent.com/v7GEVL4Nehaf6VKDnaeo1wd-3O_bh9BwqaEDRfmNkxfDO9ACv_Qt1s4RpIP_qDTJqUkgL2Djwh92qfBl00QmIO6EBBzsiEGsXV7fOfiRXD6pYPUV4RbQAV6Ryr17OuAYi-5K6Kgv9yWLqMoner6uB4In-Q=s2048)**

## <font color="#ffff00">Selezione del modello contro Ottimizzazione</font>

Possiamo pensare all' obiettivo di trovare buone ipotesi come due sotto obiettivi:
1. Selezione del modello(<font color="#ff0000">model selection</font>), selezione di un buono spazio per le ipotesi
2. Ottimizzazione(<font color="#ff0000">optimization</font> o <font color="#ff0000">training</font>), trovare la migliore ipotesi nello spazio

Una parte della Selezione del modello è qualitativa e soggettiva, ad esempio selezionare polinomi invece delle decisioni ad albero basate su qualcosa che sappiamo riguardo il problema.

Una parte dell'ottimizzazione è quantitativa ed empirica, ad esempio potremmo scegliere il grado alla seconda perché potrebbe performare meglio nel validation data set.

## <font color="#ffff00">Cos'è la complessità di un modello?</font>

La complessità viene misurata diversamente a seconda della famiglia delle ipotesi.
Per esempio:
- numero delle decisioni nei nodi dell'albero
- numero dei parametri in un polinomiale

Per molte classi del modello, più la complessità aumenta più il training set error raggiunge lo zero.

Esempi:

![[Pasted image 20240310203224.png]]![[Pasted image 20240310203235.png]]

## <font color="#ffff00">Interpolation contro Extrapolation</font>

Un albero decisionale con n foglie può rappresentare esempi perfetti di n osservazioni.

#definizione <font color="#00b050">Interpolation</font>
	un modello adatta perfettamente tutte i training data si dice che ha <font color="#ff0000">Interpolato</font> i dati. I dati diventano meno utili quando si raggiunge il punto di interpolazione.

## <font color="#ffff00">Funzione Loss</font>

#definizione <font color="#00b050">loss function</font>
	la loss function (<font color="#c00000">funzione di perdita</font>) rappresenta una misura della discrepanza tra i valori predetti dal modello e i valori effettivi dei dati di addestramento. La sua finalità è guidare il processo di addestramento del modello, cercando di minimizzare questa discrepanza. In italiano, la "loss function" può essere chiamata anche "funzione di perdita" o "funzione obiettivo".


L'obiettivo del Machine Learning è quello di minimizzare una funzione loss (massimizzare l'utilità).

si possono osservare vari tipi di perdite:
- Absolute-value loss: $$L_{1}(y,ŷ)=|y−ŷ|$$
- Squared-error loss: $$L_{2}(y, ŷ) = (y − ŷ)^2$$
- 0/1 loss: $$L_{0/1}(y,ŷ) = 0 \text{ if }y = ŷ, \text{else } 1$$
## <font color="#ffff00">Loss generalizzata</font>  ![](https://lh7-us.googleusercontent.com/qApqiPO1YDTSNVj1hTE7QoF8m-cHlRsL6X1W6-GddM_zup0GBuXav1bIFqfoyWWCTXWROJrpXAZ_QPY3ScaGPPKqdhEoBdIX-TLPVRPoVfSpH1lUGkaE8NmPcDq3LHJoviI0d-6XHyqKHnAMukiLaT-rAQ=s2048)
Dove P(x, y) è la probabilità distributiva e la migliore ipotesi è il minimo risultato ottenuto da GenLoss:
**![](https://lh7-us.googleusercontent.com/rVS4f8x9gyvcTepbvhbBmOCIgNoSEtG3OIRmjDLeEJWJfVQzigGVnx0HQiYp8yALyc1HL1Yw6rb_1Pz7sL8NP6RVw9CVlhLklW2lEnDQhEInRrp-ELZWrB_PEDrepj_o1yRQOspWfc3OZDsRXBPaugJbBA=s2048)**

<font color="#ffff00">Loss empirica</font>
Si attua quando non si ha conoscenza di P(x, y)
**![](https://lh7-us.googleusercontent.com/p5mmGQdpiVEbRlgoM3shYX1oGkT7u_dkBOcv26jDDSTcuF-Lr9gIJSXSoqyNARTFQxowtU9ejA4Ilvk4grmwAdpqKFSN-tqLyW74SV1XRCEs3q_3YR0oQczQzMpvf_Dx-CgOgZaOGQG6_5Wcyn03hqw_DQ=s2048)**
e di conseguenza
**![](https://lh7-us.googleusercontent.com/9zuaXoy87zboIli2CONIDpXOe3qiDpSwc74UpRnD41j6boHxPFRD6yoPcNK1-Ixm26QjZOqpukK1tBpZHvT_25VuCMsxMQbJI6YTCjYLkb13QbwxZqCHjuyNM8p-_U1zXy-SRIEdZJ_koln5lP0rl-pzPg=s2048)**

Vi sono vari motivi per cui $ĥ^*$ è diversa dalla funzione corretta: 

- <font color="#ff0000">Realizzazione</font>, un learning problem è realizzabile se lo spazio delle ipotesi contiene la funzione corretta che ha generato i dati 

- <font color="#ff0000">Varianza</font>, il learning algorithm genererà un risultato differente dalle ipotesi per diversi esempi dei set. Se il problema è realizzabile allora all'aumentare del numero di training examples decrescerà fino allo zero il numero della varianza 

- <font color="#ff0000">Rumore</font>, la funzione corretta potrebbe essere non deterministica o rumorosa (potrebbe ritornare valori diversi dallo stesso input). Il rumore non può essere predetto.

- <font color="#ff0000">Complessità computazionale</font>, quando la funzione è complessa e in uno spazio delle ipotesi largo potrebbe rivelarsi impossibile il suo studio computazionalmente parlando

## <font color="#ffff00">Piccola scala contro Larga scala</font>

La <font color="#ff0000">piccola scala</font> viene sfruttata nei metodi tradizionali di statistica e agli inizi del machine learning, avvengono errori data l'approssimazione non avendo la corretta funzione nello spazio delle ipotesi, Si hanno anche errori dovuti a stime errate non avendo abbastanza esempi di training per <font color="#ff0000">limitare la varianza</font>.

La <font color="#ff0000">larga scala</font> sta venendo sfruttata in tempi più recenti, il suo limite è la potenza di computazione, ci potrebbero essere confusioni nel trovare la corretta funzione visti i troppi dati, di solito con la larga scala si tende a fare un'<font color="#ff0000">approssimazione</font>.

## <font color="#ffff00">Come scegliere il modello?</font>

E' consigliato evitare di utilizzare modelli troppo complessi, potrebbero facilmente essere overfit.
Di base bisogna selezionare la migliore ipotesi, altrimenti l'alternativa è quella di minimizzare la perdita empirica (empirical loss) e la complessità.

#definizione <font color="#00b050">Total cost</font>
	 Il costo della somma dei pesi di <font color="#ff0000">perdita empirica</font> e <font color="#ff0000">complessità</font>
	 **![](https://lh7-us.googleusercontent.com/bc2fUZ_Kf5dwmXyOdiCAV-Kf4cYm-GIo93ck1t3vOfs4imjK6A8jtPdO7MavhHprOm3oRdgjhchD3A3NYTDea5aJfQqMBJpOzx3gdWfkpSeLgNh-iCH-GDWtjpdYx1ncwWhLvXt7Bxmh_74f213z5dT_Rg=s2048)**
	 dove $\lambda$ è un hyperparametro : un numero positivo che svolge il compito di tasso di conversione tra la perdita e la complessità dell'ipotesi

## <font color="#ffff00">Qual è quindi il metodo che si attua per scegliere il modello?</font>

Si attua una regolarizzazione.

#definizione <font color="#00b050">Regolarizzazione</font>
	Il processo esplicito che penalizza le ipotesi complesse (stiamo cercando funzioni più regolari).
	Mettiamo quindi a rapporto due funzioni di perdita e definiamo quale delle due è la funzione regolarizzata e si sceglie secondo lo spazio delle ipotesi.

Si vanno così a scegliere le features che importano veramente

## <font color="#ffff00">Come si regola l'hyperparametro? </font>

- **<font color="#ff0000">Hand Tuning</font>**, indovinare i parametri secondo le esperienze passate e provare finché non si soddisfa la performance richiesta
- <font color="#ff0000">Grid Search</font>, provare tutte le combinazioni dei valori e vedere quale performa meglio per il validation data
- <font color="#ff0000">Random Search</font>, se ci sono troppe combinazioni di valori allora si attua una ricerca randomica ovviamente si sa quali sono i problemi

## <font color="#ffff00">Ma come funziona in pratica il machine learning?</font>

#schema Pipeline ML
**![](https://lh7-us.googleusercontent.com/QkWkxEcDn-mPYSmJoeD-y-HnWLlbSwN9Xg2f7vrE842mULmgeVmHFlPUUtm8Yv63QUNik7GLtXdKoSijm0hXTjL4VprvqwMPAwrWJZlmzYbgomKrmq0xNK8QxqiIV__B4YO9Elttatcp73U_NNxdrxQy8A=s2048)**

Ci sono varie metriche di valutazione utilizzate in ML che dipendono dall'utilizzo che se ne deve fare. Innanzitutto suddividiamo in due macro gruppi e definiamo le singole metriche:

## 1. <font color="#ff0000">Classification</font>

- #definizione <font color="#00b050">Accuracy</font>
	Ci permette di avere un immagine del tutto su quanto possiamo fidarci delle predizioni del nostro modello. Questa metrica è cieca alla differenza tra le classi e i tipi di errore, quando si parla dell'<font color="#ff0000">accuratezza dei dataset sbilanciati</font> non è abbastanza affidabile.$$Accuracy=\frac{\text{Number of Correct predictions}}{\text{Total number of prediction made}}$$
	**![](https://lh7-us.googleusercontent.com/kD9iHQE2ew090D0TyfUYVbvDV7kPEXYrTlgpexsKUIQJWktQHmmxepIbeb1_htadHBR9acis_SAN7L-8x90f2YObMq61AlnZnqX_GwcIT7NbmV7VS0mLnIdRC8ELAdXHEeM3B_KX5Ey-gYi5Nd7Q-abjHA=s2048)**

- #definizione <font color="#00b050">Confusion Matrix</font>
	Una via per assicurarsi che l'accuratezza sia affidabile è valutare la qualità del modello seguendo ogni classe indipendentemente, un modo consueto per visualizzare questo lavoro è tramite la <font color="#ff0000">Confusion matrix</font>
	**![](https://lh7-us.googleusercontent.com/iTZQZldtaaaUNORBnepDdzMHEMVfWMI2NyeaznmybPVtT-fIylr0AezGEGWvtOYe8PY-OmIb7GkwFZlY_VRsvskawP9IiwWKHOjmvbX3tXaxowGM0c5JhOv75uyn_ARdysimnNjGEviCRNQn5Yro4kXgqQ=s2048)**
	**![](https://lh7-us.googleusercontent.com/JxnfvE_oQsbOdB2hc3zaYvJhy1Qrf4owqdRltTxZLevfoLBPbvgOSnGKSFHHQSDpX-Y0BCnGr0-d8_mIbF5sUG_ZzrJB1qCmgCn3wBjJQsDmUhG2ScVkes4qFFUpNRRgFsB89e52mSHhflP2_Lsd45ElWA=s2048)**

- #definizione <font color="#00b050">False Positives and False Negatives</font>
	Un falso positivo è un errore di classificazione binaria dove il test da il risultato sbagliato.
	Un falso negativo è l'errore opposto.

- #definizione <font color="#00b050">Precision and Recall</font>
	Sono due metriche che contribuiscono a conoscere il tipo di errore che si sta affrontando.
	
	La <font color="#ff0000">Precisione</font> (o positive predictive value) ci da una misura di quanto possiamo fidarci di una predizione positiva del nostro modello.$$Precision=\frac{TP}{TP+FP}$$
	La <font color="#ff0000">Recall</font> (o sensibilità o true positive rate TPR) ci da la misura di quanti valori reali esistono.$$TPR=Recall=\frac{TP}{TP+FN}$$

- #definizione <font color="#00b050">F1 Score</font>
	Di solito c'è uno scambio tra l' avere una alta precisione e un alta recall, si parla di 
	<font color="#ff0000">F1 Score </font>quando si vuole visualizzare un overall score bilanciato$$F1=\frac{2}{\frac{1}{precision}+\frac{1}{recall}}=\frac{2\times precision\times recall}{precision+recall}$$

- #definizione <font color="#00b050">ROC Curve</font>
	Con l'obiettivo di visualizzare lo scambio tra i falsi positivi e i falsi negativi di un modello, possiamo utilizzare la curva <font color="#ff0000">Receiver Operating Characteristic</font>(ROC). 
	**![](https://lh7-us.googleusercontent.com/CUUjUBFTJRVM_sdDNlusPCL_k63uBAImm3zLvNEBref0i9b43oY15BnX3B3253G42WR9yUK1gY32Lpy1dfAv0ZNP_vBhf77fetyQwAQy9H4UbLvlkT-cUWFNfQsjd30oXHGLKETsHRrexFRUqnjBkU3d8g=s2048)**
	**![](https://lh7-us.googleusercontent.com/eJ5M46WAoOwYlwPhJupq6c6sdDzThalCMk0Cn-2GKNHGG4r2HGTOLgGQHNJiTrzdmRnH6UCiut8blxxRRg2qoq7j769kMoW1zwInLodCuMVdfLLDO-Kt5orfL4NP2wDGfyLD8QfuyXepC5hdAHsclTOR8A=s2048)**

- #definizione <font color="#00b050">Precision Recall Curve</font>
	Questa curva ci dà informazioni dirette riguardo valori differenti che possiamo ottenere riguardo la precisione e la recall.
	<font color="#00b0f0">N.B.</font> la precisione non è necessariamente monotona riguardo la predizione dei threshold. Questo grafo può essere difficile da analizzare in alcuni casi.
	**![](https://lh7-us.googleusercontent.com/fh_bZ-tfcrHCycF9olkYHVWhKIZKCCV3AVv5bwSdvHZxRG_FPVx33QzzuDxahS4ThJTiEqlNLdOlQ-opULG3yrSx6ojsNem86IvLfY5yaBLYVtzaDZMu_mPhetQB8fIXxuDf2GFRTpzf8E8hqV-6fW_kXw=s2048)**

- #definizione <font color="#00b050">AUC</font>
	Metrica utilizzata per semplificare i grafi ROC utilizzando valori singoli 
	**![](https://lh7-us.googleusercontent.com/WZkA--Ct4mrZABjolIwU2bdZIIAlhfxFxeoMiIiDTiLoPhCWa4vbDEHYuCTEBC0d0Jt8GUq4pHL6z0mu6R4OsQ8RkQ-Oldl39QTrXSdIO5HCtTzZE7uKz4MTgPMslrNnS6UYLQkT9uDQ_mTqkEkn8covdQ=s2048)**

## 2. <font color="#ff0000">Regression</font>

- #definizione <font color="#00b050">MAE</font>
	Ovvero <font color="#ff0000">Mean Absolute Error</font> è una misura degli errori tra osservazioni congiunte che esprimono lo stesso fenomeno, ad esempio $Y$ contro $X$ include una comparazione di predizioni riguardo uno "scontro" osservato.
	**![](https://lh7-us.googleusercontent.com/xNPDqQdJTHzhDQMNF343v0cJTD7VqpQfNCwp3jnlEvUnF5iw4P63QHlGF4TdCYvbv7Nh9HbzH2-sC0NpT2DTOxg7zL1aIwta04C4b03-Etkt__60Qu3uVPQKWN0aYssEivbZMwgkrGLHpE7l15sxdYowCQ=s2048)**
	**![](https://lh7-us.googleusercontent.com/brasRSowwV3z6xHDJfJQQ0jBOi7JLCNf0elx-pRQ7QONjuIK9fx8uALJCG02L0kkB2muSAXvZBxAv1d0mYnamxQSoidr7iRYK2bRWjuclYELtqa-OXn3g-ia7CL1U_TQHv41joQHlHSbwi_8jivoUnv07Q=s2048)**

- #definizione <font color="#00b050">MSE</font>
	Ovvero <font color="#ff0000">Mean Square Error</font> misura la media degli errori quadratici che è la differenza tra il valore stimato e il valore attuale.
	**![](https://lh7-us.googleusercontent.com/k_2vsDdL21BAeLUXNSai1b0bG2rTkwqIxKydbuQmKXeil8ANT0diMFZe_YYIGWTqyTUqeGfPM6yl2ObeGPpgZcWVF_3DFlM_a0duD7wjzjrcQxYS-XgNlwhDBTzNDQbnkELlfrOiBz-zAcNIfjEQngPBLA=s2048)**
	**![](https://lh7-us.googleusercontent.com/bx8R_rI8wnll0k9KYyZ7SAWkR3TMfmUZWEg21Zjr3z60cy7BsAf01xhr_gJzbEm4MVsqAk4716cxMWJ0jLXkOM_IECpZxwJObvM3mb8BJyJSF4VoIcxsGHhR5TcvqYiNfJcyDjufVpUWW_9XRzbFuUfMpw=s2048)**

- #definizione <font color="#00b050">RMSE</font>
	Ovvero <font color="#ff0000">Root Mean Square Error</font>(o Root Mean Square Deviation) che serve per misurare la qualità di quanto sia adatto il modello
	**![](https://lh7-us.googleusercontent.com/e3zpTsBE3z4JHv3BLsrmM6cRxgZD1WCTEMvJYirO14OA9Cg91xTiLj7Ud2DtQVO364omB0bWjQIctaoDB2ybBAOSHpsFy00CMVjfEadvKOrkUdCedhfwPnV-Xt8UNAhbuChpDJeJBhJIzh3M4MqvGIj79g=s2048)**
	**![](https://lh7-us.googleusercontent.com/-lv3o1Z8J1Xz1_lmMq1VYEtok8AnBt96XATJU-idYbZcVYTcOh4KKb-_rEIkChRXbY94pH2lI8ELtIl3dqJgMMZtOrMdcgV44VZMs_65pglyzueK7Dtp7RYU0cPriVUltGyzJsHda9vBqFNYqtkXy_5xEg=s2048)**

<font color="#00b0f0">N.B. </font> Non fidarti mai di una singola metrica, utilizza sempre tutte le varie metriche per avere una vista totale del lavoro

pg 52
