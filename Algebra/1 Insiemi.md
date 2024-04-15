#definizione <font color="#00b050">Insieme</font>
	Un insieme è una collezione di elementi

#es :
$$
\{ 0,1 \} 
$$
oppure:
$$
(0,1), \{ rosso,nero \}
$$
ecc..

Possiamo anche avere un insieme vuoto che si indica con il seguente simbolo:
$$
\emptyset
$$
Possiamo gestire gli insiemi in vari modi, ad esempio possiamo indicare la loro <mark style="background: #FFB8EBA6;">Inclusione</mark>:
$$
\{ 0 \} \not\subset \{ 1 \}
$$
Qui stiamo indicando che **{0}** non è incluso in **{1}**.

Ora definiamo gli **<mark style="background: #FF5582A6;">insiemi dei numeri principali</mark>**:
$$
\mathbb{N \subset Z \subset Q \subset R \subset C}
$$
Ovvero, <mark style="background: #FF5582A6;">Naturali, Relativi, Razionali, Reali e Complessi</mark>.
Questi insiemi sono caratterizzati a loro volta da altri sottoinsiemi i cui elementi soddisfano certe proprietà.

#es :
$$
\{ x\in \mathbb{R}: |x-2| < 1 \} = ]1,3[
$$
ovvero il sottoinsieme di R che va da 1 a 3.

E' possibile anche realizzare [[1.2 Operazioni sugli insiemi]]

#definizione  <font color="#00b050">Partizione</font>
	
  Consideriamo un insieme $\rho$ di sottoinsiemi $X$ gli elementi di $\rho$ (parti) sono dei sottoinsiemi di $X$  (se $P\in \rho$ allora $P\subset X$).
  Si dice che $\rho$ è una <u>partizione</u> di $X$ se:
  1. $\forall P\in\rho\quad P\neq\emptyset$
  2. $\forall P,Q \in\rho\;,\quad P\neq  Q\rightarrow P\cap Q=\emptyset$
  3. $\forall x \in X \quad \exists \;p\in\rho |x\in P$

#proposizione 2 

 $R=(X,\Gamma)$ è una relazione di equivalenza([[2 Relazioni]])
 $\rho = \{ Cl(x):x \in X \}$ è una partizione di X
 (pg 22 dimostrazione)

#definizione  <font color="#00b050">sistema completo di rappresentanti</font>
	
  Un <u>sistema completo di rappresentanti</u> di $R$ è un sottoinsieme $X'\subset X$ tale che:
  1. $\forall x'_{1},x'_{2}\in X'$ , se $x'_{1}\neq x'_{2}\rightarrow Cl(x'_{1})\cap Cl(x'_{2})=\emptyset$
  2. $\forall x\in X\quad \exists\; x'\in X' \;|\; x\in Cl(x')$
  nel caso (2) verificare se x' è unico.
	  #osservazione 
         In generale non c'è unicità per un sistema completo di rappresentanti. Per esempio possiamo scegliere $P\in R^2$ e il fascio di rette per P : $X_{p}$ è un sistema completo di rappresentanti.
         
  