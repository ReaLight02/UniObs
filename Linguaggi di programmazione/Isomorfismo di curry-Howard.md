
Utile per il reverse engineering 




Semantica denotazionale 

Semantica operazionale

#completa Spiega le differenze e in cosa sono utili seguendo le note del professore


Eliminazione dell'implica
$$
\frac{\Gamma\vdash M:A\rightarrow B \quad \Gamma\vdash N:A}{\Gamma\vdash MN:B}
$$

Introduzione dell'implica
$$
\frac{\Gamma ;x:A\vdash M:B}{\Gamma\vdash Fn\;x:A\implies M:A\rightarrow B}
$$

Cut elimination

Esiste 