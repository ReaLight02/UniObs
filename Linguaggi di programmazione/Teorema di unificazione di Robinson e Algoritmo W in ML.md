#controlla
#definizione <font color="#00b050">Tipo abitato</font>
   Quando un <font color="#ff0000">termine</font> ha un <font color="#ff0000">tipo</font> esso si può definire <u>abitato</u> 

#definizione <font color="#00b050">Tipo principale</font>
#completa

#definizione <font color="#00b050">Sostituzione</font>
   Una <u>sostituzione</u> è una funzione $V:TypeVar\rightarrow PrimTypes$ | solo per un numero finito di $X$ si ha che $VX\ne X$

#definizione <font color="#00b050">Unificazione</font>
   Un <u>unificazione</u> di due tipi <u>primitivi</u> $\mathcal{T}_{1}\text{ e }\mathcal{T}_{2}$ è una sostituzione $V \mid V'\mathcal{T}_{1}=V'\mathcal{T}_{2}$
   dove $V'X=VX$ e $V'A\rightarrow V'B$.
   Ad esempio$$(A\rightarrow C)\rightarrow(A\rightarrow(A\rightarrow C))$$
  
   si può osservare come$$A\rightarrow(B\rightarrow A)$$
#teorema  <font color="#00b050">Teorema di unificazione di Robinson</font>
   Esiste un algoritmo $\mathcal{U}$ che, dati $\mathcal{T}_{1}$ e $\mathcal{T}_{2}$ restituisce una sostituzione $V$ o altrimenti fallisce.

  #es Dato $\mathcal{T}_{1}$ e $\mathcal{T}_{2}$ tale che
	  $\mathcal{T}_{1}=A\rightarrow(A\rightarrow A)$ 
	  $\mathcal{T}_{2}=B\rightarrow B$
	Si può vedere a occhio che si verifica una ciclicità infinita

  Inoltre:
  
  1. Se $\mathcal{U}(\mathcal{T}_{1},\mathcal{T}_{2})=V$ allora:
      - $VX\ne X$ solo se X compare in $\mathcal{T}_{1}$ o in $\mathcal{T}_{2}$ 
      - $V$ <u>unifica</u> $\mathcal{T}_{1}$ e $\mathcal{T}_{2}$ 
      #es Dati $\mathcal{T}_{1}$ e $\mathcal{T}_{2}$ tale che 
	      $\mathcal{T}_{1}=X\rightarrow Y$
	      $\mathcal{T}_{2} =X\rightarrow Z$ 
	      allora un unificatore potrebbe essere $Y\mapsto Z$, non è quindi necessario osservare altri elementi

  2. Se $\exists$ un unificatore $W$ di $\mathcal{T}_{1}$ e $\mathcal{T}_{2}$ allora $\mathcal{U}(\mathcal{T}_{1},\mathcal{T}_{2})=V$ e $W=UV$ per qualche sostituzione $Z$ 
      #es Dati $\mathcal{T}_{1}$ e $\mathcal{T}_{2}$ tale che
	      $\mathcal{T}_{1}=X\rightarrow Y$
	      $\mathcal{T}_{2}=Z\rightarrow Y$ 
	      possiamo osservare che dato un unificatore $W$ che ha 
	      $X\mapsto Z$ 
	      $Y\mapsto int\mapsto bool$ 
	      ci è di aiuto alla risoluzione di questa verifica data data la generalizzazione di $W$, potremmo ad esempio applicare un unificatore $V$ 

#definizione <font color="#00b050">Algoritmo</font> $\mathcal{W}$ 
	asada
    #definizione Correttezza (Riosservare sulle dispense del prof)
	Supponiamo di voler tipare il termine $yx$ dove $X:X\text{ e }y:Y$ osserviamo che $Y$ deve essere una funzione, quindi $Y=X\rightarrow Z$
	Osserviamo ora $not(xy)$ mi aspetto che $\mathcal{W}(\Gamma,M)=V,\mathcal{T}$
    <font color="#ff0000">-----</font>
    $\mathcal{W}(\Gamma,M)=(V,\mathcal{T})$
    - se $M=x$ e $\Gamma x=\forall X_{1}\dots Xn.\mathcal{T'}\mid \Gamma x=\sigma$ allora $V=id$ e $\mathcal{T}=\left[ \frac{Yi}{Xi} \right]\mathcal{T'}$ dove le $Yi$ sono "nuove"
    - se $M=M_{1}M_{2}$ e inoltre
        1. $\mathcal{W}(\Gamma,M_{1})=(V_{1},\mathcal{T}_{1})$
        2. $\mathcal{W}(V_{1}\Gamma,M_{2})=(V_{2},\mathcal{T}_{2})$
        3. $\mathcal{U}(V_{2}\mathcal{T}_{1},\mathcal{T}_{2}\rightarrow Y)=W$ dove $Y$ è "nuova"
     allora $\mathcal{T}=WY$ e $V=W(V_{1}V_{2})$ 
     - se $M =$ $Fn\; x\implies N$ e $\mathcal{W}(\Gamma,x:X,N)=(V_{1},\mathcal{T}_{1})$ dove $X=\text{"nuova"}$ allora $$
V=V_{1}\text{ e } \mathcal{T}=V_{1}X\rightarrow\mathcal{T}_{1}
$$
     - se $M=let\;x=M_{1}\text{ in }N\text{ e }$
        $\mathcal{W}(\Gamma,M_{1})=(V_{1},\mathcal{T}_{1})$
        #completa$\mathcal{W}()$(APPLICARE ESEMPIO MOSTRATO CON REGOLA DELLA SEGNATURA, ovvero viene perognizzato ogni elemento tranne quello che appartiene all'elemento segnato)

#definizione <font color="#00b050">Schema principale</font>
   Uno schema $\sigma_{p}$ si dice "principale" per $\Gamma$ e $M$ quando
   - $\Gamma\vdash M:\sigma_{p}$
   - se $\Gamma\vdash M:\sigma$ allora $\sigma<\sigma_{p}$



#appunto Correttezza
    Se $\mathcal{W}(\Gamma,M)=(V,\mathcal{T})$ allora $V\Gamma\vdash M:\mathcal{T}$ è derivabile

#appunto Completezza 
    Se $\Gamma\vdash M:\sigma'$ allora $\mathcal{W}(\Gamma,M)=(V,\mathcal{T})$ dove $\sigma=\overline{V\Gamma}(\mathcal{T})$ è principale per $V\Gamma,M$