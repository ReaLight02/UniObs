#### <font color="#8064a2">Algebre induttive</font>

#definizione **<font color="#00b050">Assiomi di Peano</font>**
	L'insieme dei numeri naturali N è definito secondo i seguenti assiomi:
	1.$$ 0 \in \mathbb{N} $$
	2.$$ n \in \mathbb{N} \rightarrow succ(n) \in \mathbb{N}| succ:\mathbb{N}\rightarrow\mathbb{N}:f(next)$$
	3.$$\forall n,m \in\mathbb{N},succ(n)=succ(m)\rightarrow n=m, succ= iniettiva$$
	4.$$\not\exists n\in \mathbb{N}| succ(n)= 0 $$
	5.$$\forall S \subseteq \mathbb{N}|(0\in S\land(n\in S \rightarrow succ(n)\in S)) \rightarrow S= \mathbb{N}   $$

#proposizione **<font color="#245bdb">Numeri naturali di Von Neumann</font>**
   indicati come:
	
	$$0n:=\{ \}$$
	$$1n:= \{  \{  \}\}$$
	$$2n:=\{ \{\},\{ \{  \} \} \}$$
	$$3n:=\{ \{  \},\{ \{  \} \} ,\{ \{  \},\{ \{  \} \} \}\}$$

#principio **<font color="#de7802">Induzione</font>**
	Sia P una proprietà che vale per n=0. Dato $n \in \mathbb{N}$, se si verifica che la veridicità di P per n implica che P sua vera anche per n+1, allora P vale per tutto $\mathbb{N}$. In simboli, abbiamo che:
	$$\forall P ((P(0)\land(P(n)\rightarrow P(n+1)))) \rightarrow \forall m \in \mathbb{N} \;P(m)$$

#definizione **<font color="#00b050">Insieme unità</font>**
	 Definiamo come insieme unità l'insieme $\mathbb{1}=\{ () \}$, ossia l'insieme composto da una zerupla

#definizione **<font color="#00b050">funzione nullaria</font>**
	Definiamo una funzione $f(y):\mathbb{1}\rightarrow S$, dunque avente $\mathbb{1}$ come dominio, come funzione nullaria (o funzione costante). Inoltre, per comodità indichiamo $f(x)$ direttamente con $f$, dato che x = ()

#definizione **<font color="#00b050">Segnatura di una funzione</font>**
	Data una funzione $f$ definiamo $f : D\rightarrow C$ come segnatura di $f$ dove D è il dominio di $f$ e C è il codominio di $f$

#definizione **<font color="#00b050">Algebra</font>
	Definiamo come Algebra (o struttura algebrica) una n-upla (A, y1,....,yn) dove A è un insieme non vuoto, detto dominio, e y1,...,yn sono delle operazioni definite su A stesso.

#definizione <font color="#00b050">Segnatura di un'algebra</font>
	Data un'algebra(A,$y_{1},\dots,y_{n}$), definiamo come segnatura dell'algebra l'insieme delle segnature delle operazioni definite su essa

#definizione <font color="#00b050">Segnature equivalenti</font> 
	Date due algebre (A,$y_{1},\dots,y_{n}$) e (B,$k_{1},\dots,k_{n}$), definiamo le segnature di tali algebre come equivalenti se per ogni operazione y definita su A esiste un'operazione k definita su B per cui invertendo B con A all'interno della segnatura di k si ottiene la segnatura di y

#definizione <font color="#00b050">Algebra induttiva e costruttori</font>
	Definiamo l' algebra (A,y1,...,yn) come induttiva(o iniziale) se:
	 - y1,...,yn sono iniettive
	 - $\forall i\not= \mathrm{Im}\cap\mathrm{Im}=\varnothing$, ossia le immagini delle operazioni sono due a due disgiunte
	 - $\forall S \subseteq A(\forall i \in [1,n],a_{1},\dots,a_{k} \in S \; y_{i}(a_{1},\dots,a_{k})\in S)\rightarrow S=A$ , ossia è soddisfatto il principio di induzione per ogni operazione
	Inoltre definiamo $y_{1},\dots,y_{n}$ come <font color="#ff0000">costruttori</font> di A.

#definizione <font color="#00b050">Omomorfismo</font>
	Date due strutture algebriche(A,$y_{1},\dots,y_{n}$) e (B,$k_{1},\dots,k_{n}$) dello stesso tipo definiamo $f: A\rightarrow B$ come omomorfismo se
	$$\forall a_{1},\dots,a_{n} \in A, i\in[1,k]\quad f(y_{1}(a_{1},\dots,a_{k}))=k_{i}(f(a_{1}),\dots,f(a_{k}))$$
#definizione <font color="#00b050">Isomorfismo</font>
	Definiamo come isomorfismo un omomorfismo biettivo, inoltre, definiamo due algebre (A,$y_{1},\dots,y_{n}$),(B,$k_{1},\dots,k_{n}$)come isomorfe indicato con $A \cong B$, se esiste un isomorfo tra loro


###### <font color="#ffff00">Lemma di Lambek</font>
#lemma 
	Data un'algebra induttiva(A,$y_{1},\dots,y_{n}$), per ogni algebra(B,$k_{1},\dots,k_{n}$) con la stessa segnatura di A si ha che
	 $$\exists! \; omomorfismo\; f:A\rightarrow B$$

#teorema <font color="#e5b9b7">Lemma di Lambek (versione ridotta)</font>
	Date due algebre induttive (A,$y_{1},\dots,y_{n}$) e (B,$k_{1},\dots,k_{n}$) con la stessa segnatura, si ha che $A\cong B$ 


#### <font color="#c00000">Strutture dati induttive</font>

#definizione <font color="#00b050">Insieme delle liste finite</font>
    
 Definiamo List$<T>$ come l'insieme delle liste finite di elementi 

#proposizione <font color="#245bdb">Algebra induttiva delle liste finite</font>
    
  la tripla $(List<T>,empty,cons)$,dove:

 - empty : $\mathbb{1}\rightarrow List<T>:x \rightarrow [\;]$ è la funzione nullaria che restituisce la lista vuota
 - cons: $List<T> \times \; T \rightarrow List<T>:x,([x_{1}\rightarrow\dots\rightarrow x_{n}]\rightarrow[x\rightarrow x_{1}\rightarrow\dots x_{n}])$ è la funzione di costruzione delle liste
 è un algebra induttiva
#definizione <font color="#00b050">Insieme degli alberi binari finiti</font>
    
  Definiamo <font color="#9bbb59">BinTree</font> come l' insieme degli alberi binari finiti

#proposizione <font color="#245bdb">Algebra induttiva degli alberi binari finiti</font>
    
  La tripla(BinTree, leaf, branch) dove:
  - leaf : $\mathbb{1}\rightarrow$ BinTree : $x\rightarrow o$ è la funzione nullaria che restituisce una foglia
  - branch : BinTree $\times$ BinTree $\rightarrow$ BinTree : ($t_{sx},t_{dx}\rightarrow t$) è la funzione di costruzione dei rami, ossia tale che

![[Pasted image 20231107135340.png]]

è un'algebra induttiva


##### <font color="#ffff00">Induzione Strutturale</font>

 #definizione  <font color="#00b050">Induzione strutturale</font>
    
   Definiamo come induzione strutturale il metodo dimostrativo generalizzante il principio di induzione basato sulle proprietà di un'algebra induttiva.
   In particolare, viene ipotizzato che una proprietà P valga per ogni argomento di ogni costruttore dell'algebra e tramite il terzo assioma viene dimostrata che tale proprietà
   valga per tutti gli elementi dell'algebra stessa

#teorema <font color="#e5b9b7">Relazione tra nodi e foglie</font>
	
  Dato $t\in BinTree$ avente $n$ foglie, il numero di nodi di $t$ è pari a $2n-1$ 

#### <font color="#4f6128">Sintassi astratta</font>

 #definizione <font color="#00b050">Linguaggio</font>
	
  Definiamo come <font color="#00b050">linguaggio</font> un insieme di stringhe

 #definizione <font color="#00b050">Grammatica</font>
	
  Definiamo come <font color="#00b050">grammatica</font> un insieme di regole, detti <u>termini</u> , che definiscono come poter manipolare le stringhe di un linguaggio.
  La <span style="background:#d3f8b6">forma di Backus-Naur</span> è una notazione utilizzata per descrivere grammatiche ed è definita come:
  $$<symbol>::=\_espression\_{}$$
  dove:
  - $<symbol>$ è un simbolo non-terminale espresso dalla grammatica
  
  - l'operatore ::= indica che ciò che si trova alla sua sinistra possa essere sostituito con ciò che si trova alla sua destra
  
  - $<\_espression\_>$  consiste in una o più sequenze di simboli terminali o non-terminali dove ogni sequenza è separata da una barra verticale(quindi  |  ) indicante una scelta possibile per l' operatore ::=

 #definizione <font color="#00b050">Sintassi astratta</font>
	
  La <font color="#00b050">sintassi astratta</font> di un linguaggio è una definizione induttiva di un insieme T di termini che permette di definire strutture algebriche senza dover necessariamente definire concretamente le sue operazioni

 #teorema  <font color="#e5b9b7">Algebra induttiva dei termini</font>
	
  Dato u linguaggio $L$ con una sintassi astratta con termini definiti in $T$ , esiste sempre un'algebra induttiva($T,a$). Di conseguenza, tutte le proprietà di un linguaggio sono dimostrabili tramite l'induzione strutturale sulla sua algebra dei termini


[[2 Paradigma funzionale]]