Schemi di tipo:$$t::=K|X|t_{1}\rightarrow t_{2}$$
$$\sigma::=t|\forall X.\sigma$$
$terms$:$$
M,N::==k|X|fn\;x\implies M|MN|let\;x=M\text{ in }N
$$
#### Regole di inferenza

- Regola della generalizzazione
![[Pasted image 20231204124423.png]]

- Regola della specializzazione
![[Pasted image 20231204124703.png]]
quindi dove $\sigma'$ è un <u>sottotipo</u> di $\sigma$

#definizione <font color="#00b050">sottotipo in sml</font>
  Sta a significare "istanza generica" quindi una sorta di specificazione qualunque

e otteniamo che:$$
\sigma'\forall Y_{1},Y_{2},\dots,Y_{n}\times t' \text{ è istanza generica di}
$$
$$
\sigma=X_{1},X_{2}\dots X_{n}\times t(\text{ scritto } \sigma>\sigma')sse
$$
- t'=$[\frac{t_{i}}{x_{i}}]t$ 
- 