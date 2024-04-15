
#definizione <font color="#00b050">Sistema F2</font>
 Un super-linguaggio di F1


 Viene definito con:
 
 - <font color="#ff0000">Types</font> $A,B::=K|A\rightarrow B|X|\forall X.A$ 
 - <font color="#ff0000">Terms</font> $M,N::=k|\;x\;|fn\; x\implies M|MN|$ $\Lambda X.M$$|MA$ 
     N.B. si può fare astrazione su dei tipi(es. $\Lambda X.(fn\;x:X.x)$ dove osserviamo che tramite il simbolo $\Lambda$ otteniamo che $\forall X.X\rightarrow X$) ma come funziona $\Lambda$?
     Bisogna prima definire $\Lambda$ e successivamente specializzarlo(MA).
     #Es $\Lambda$ (REALIZZARE ESEMPI SPECIALIZZAZIONI)  
     N.B. APPUNTI DISPENSE



%% Eugenio Moggi %%
<span style="background:#ff4d4f">ATTENZIONE</span>, si può generalizzare a patto che $X \notin FV(\Gamma)$ dove $FV$ è (PG 65 Note professore) 

[[ML]]