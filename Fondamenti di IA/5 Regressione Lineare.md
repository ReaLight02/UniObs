
L'argomento si incentra sullo studio delle funzioni lineari basate sul continuo inserimento di valori.

## <font color="#ffff00">Funzione Lineare Invariata</font>

#definizione <font color="#00b050">Funzione Lineare invariata</font>
	Si definisce funzione lineare invariata una funzione lineare che appunto non subisce variazioni, ha degli input <font color="#ff0000">x</font> e degli output <font color="#ffc000">y</font> che interagiscono secondo la seguente formula:$$ y=h(x)=w_{1}x+w_{0}$$
	dove $w_{0}$ e $w_{1}$ sono coefficienti reali.
	 **![](https://lh7-us.googleusercontent.com/atw8flSOIcC67dpS_30QOpm4Urf6NwwJnwQb2XtTzqg3y59AFXY5dbgGdTY3xC1KFMpF_QLU1lALb29quhZKFtEhS2fYmuCaitdOUk_0IxhaZnHdwfuaxs8RQODi2-69c5BGILZTIrjWaJGmWc4UuFKWuQ=s2048)**
	 $\quad$
	 Utilizziamo la lettera $w$ perché stiamo parlando di weights (pesi), i valori di <font color="#ffc000">y</font> cambiano a seconda dei pesi di $w_{1}$ e $w_{0}$ 

In <font color="#ff0000">forma vettoriale</font> definiamo $w$  come un vettore $<w_{0},w_{1}\rangle$ , e possiamo definire la <font color="#ff0000">funzione lineare</font> tramite questi pesi:$$h_{w}(x)=w_{1}x+w_{0}=w\;\times<x,1>$$
Il nostro obiettivo è quindi quello di trovare la $h_{w}$ che calzi a pennello(<font color="#ff0000">best fit</font>) i dati, arriviamo quindi a parlare di <span style="background:#ff4d4f">REGRESSIONE LINEARE</span>, ma cosa si intende per "calzare a pennello"?

Dobbiamo trovare una linea per i dati, tutto ciò che dobbiamo fare è trovare i pesi $\langle w_{0},w_{1}\rangle$ che minimizzano la perdita empirica. 

-------


-------


-----
## <font color="#ffff00">Optimal</font> $W^*$ 


Soluzione analitica


## <font color="#ffff00">Come funziona l'overfitting nella regressione lineare multivariata?</font>

Quando si parla della regressione lineare invariata non dobbiamo preoccuparci dell'overfitting, ma quando si parla della multivariata in spazi dimensionali grandi si potrebbero avere problemi che risultano nell'overfitting, è di uso comune utilizzare la <font color="#ff0000">regolarizzazione</font>

## <font color="#ffff00">Regolarizzazione nella regression lineare</font>

Con la regolarizzazione minimizziamo i costi totali di un ipotesi
**![](https://lh7-us.googleusercontent.com/8mxPStBdQ4WbfKolWKuQ5qsrWUjVJ6ir33WE4WT_NBYEb02LDDXnawneJtwuuxvGwZRgw4QmR4QOcxl1IQpd9kRFZkarMVyVeM_x7tl8stkb_RigtUt4QlCcdKCoOqN_xf0aOQkS4Y3KPJ74Jf09E9wbwA=s2048)**
Per le funzioni lineari possiamo considerare la complessità come peso 
**![](https://lh7-us.googleusercontent.com/rAOx_r1524rSxrpgqHYe4LWKdzHMVth5BUmiP-ieryWCpD2Wb8uu7xrvO6NyCY5D7KNL3pjgTihZnO2P6vIN_3HcvPGJ3U67qwwc55FQSHM2jhTDPFOKigGwrZIExMpuL8vnhpcbkripw_PVLpUIglQt2w=s2048)**

## <font color="#ffff00">Regolarizzazione L1 vs L2 </font>

**![](https://lh7-us.googleusercontent.com/GsBVyGbaIGbojHO5BG8M2qXWrAZt-L-uVrnwO8o-o_k8oHTrtss_fIvpnQeqDxcbzfcPloHBjhP8BDJGCkf_zRN86BH6ixvoURksLlC30YtB4CEkuT_LuLsvhyRHQZZfCfPKg_iYbq4Am03CCpCLRGALPA=s2048)**

L1 setta i parametri inutili a 0

L2 vincola i parametri a non crescere troppo, blocca i parametri troppo grossi


## <font color="#ffff00">Ridge regression L2 regolarizzazione</font>

#definizione <font color="#00b050">Ridge Regression</font>
	Consiste in un metodo per stimare i coefficienti di un modello di regressione multiplo dove le variabili indipendenti lineari sono <font color="#ff0000">altamente correlate</font>.
	La forma delle ipotesi è $$L(y,ŷ)+\lambda L_{2}(w)$$



## Lasso Regression L1 regolarizzazione

#definizione Lasso Regression
## <font color="#ffff00">Elastic net</font>

#definizione Elastic Net
	Nei casi pratici aumenta la complessità delle computazione, combina L1 e L2 e uno diventa il complemento dell'altro
	



## <font color="#ffff00">Posso usare la regressione lineare per fare classificazione?</font>

<font color="#00b050">SI</font>, si traccia una linea e la funzione che discrimina sarà una funzione di tipo threshold.
Questo metodo ci permette di analizzare i problemi semplificando la forma dei classificatori, imponendo che la funzione sia una <font color="#ff0000">retta</font>
![[Pasted image 20240312083453.png]]

## <font color="#ffff00">Quindi qual è l'ipotesi di classificatore?</font>


## <font color="#ffff00">Funzione threshlod</font>


## <font color="#ffff00">Come minimizziamo la funzione threshlod?</font>

<font color="#00b050">Tramite Gradient Descent</font>, con $(x,y)$


oppure con Perceptron Update rule
![[Pasted image 20240312083738.png]]
Combinazione lineare dei pesi con funzione di attivazione dei threshold, osservare se valore è uguale a 0. In parole povere quando si raggiunge una certa soglia si attiva tale modello.

## <font color="#ffff00">Learning curves</font>




### VEDERE MOLTIPLICATORE DI LAGRANGE