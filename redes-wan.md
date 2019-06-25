1. Conectar router mediante serial DCE en ISP
2. Configurar ip, clock rate (solo en DCE) y bandwith
  - (if-config)#clock rate 
  - (if-config)#bandwith
3. Configurar ppp en ambos enlaces
  - (if-config)#encapsulation ppp
4. Metodos de autentificacion PPP
    - PAP: No seguro,  texto plano
    - CHAP: encriptado
i. Configurar PAP
    - configurar nombre de R1 (config)#hostname R1
    - En R1 agregar user y pass de R2
      - (config)#username R2 password R1pass
    - Activar PAP
      - (config-if)ppp authentication pap
      - ppp pap sent-username R1 password R1pass
    - Repetir en R2 
ii. Configurar CHAP
    - configurar nombre de R1 (config)#hostname R1
    - En R1 agregar user y pass de R2
          - (config)#username R2 password R1pass
    - Activar CHAP
          - (config-if)ppp authentication chap
