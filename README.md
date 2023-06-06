# BD-P3-CASO-5
1*) A= (π cuil ρ cuil ← Cuil1 CCTES) ∪ (π cuil ρ cuil ← Cuil2 CCTES)
    B= (π cuil ρ cuil ← Cuil1 CAHORRO) ∪ (π cuil ρ cuil ← Cuil2 CAHORRO)
    π nombre,cuil (PERS ⨝ (A ∪ B))
2*) A= (π cuil ρ cuil ← Cuil1 CCTES) ∪ (π cuil ρ cuil ← Cuil2 CCTES)
    B= (π cuil ρ cuil ← Cuil1 CAHORRO) ∪ (π cuil ρ cuil ← Cuil2 CAHORRO)
    π nombre (PERS ⨝ (A ∪ B))
3*) A= π Nro σ Saldo < 0 ρ Nro ← NroCuenta TRANSAC
    π Nro CCTES - A
4*) A= π Cuil1,Cuil2 σ SaldoActual > 0 CCTES
    B= π Cuil1,Cuil2 σ SaldoActual > 0 CAHORRO
    C = (ρ cuil ← Cuil1 (π Cuil1 A ∪ π Cuil2 A)) ∪ (ρ cuil ← Cuil1 (π Cuil1 B ∪ π Cuil2 B))
    π cuil, nombre (PERS ⨝ C)
5*) A= π TipoTransaccion ρ TipoTransaccion ← Descripcion TIPO_TRANS
    π Nro,SaldoActual (CCTES ⨝ (π Nro ρ Nro ← NroCuenta (π NroCuenta,TipoTransaccion TRANSAC ÷ A)))
6*) ES LO MISMO QUE EL 3*) A= π Nro σ Saldo < 0 ρ Nro ← NroCuenta TRANSAC
                           π Nro CCTES - A
7*) A= π NC,NT σ Saldo < 0 ρ NC ← NroCuenta,NT ← NroTrans TRANSAC
    B= π NroCuenta,NroTrans σ Saldo < 0 TRANSAC
    C= A ⨯ B
    D= CCTES ⨝ (π Nro ρ Nro ← NroCuenta (σ NC = NroCuenta ∧ NT ≠ NroTrans C))
    PERS ⨝ ((π cuil ρ cuil ← Cuil1 D) ∪ (π cuil ρ cuil ← Cuil2 D))                           
