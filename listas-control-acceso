# Listas de control de acceso ACL

  Parametros:
    - Numero de puertos
      - Origen
      - Destino
    - Direccion IP
      - Origen
      - Destino
    - Protocolo
      - Ej: IP, ICMP, TCP, UDP
  - Se aplican a una interfaz de un router (Para la entrada *o* salida) 
  
  *Lista ACL:
    - Sentencia 1 (Permitir o denegar)
    - Sentencia 2 (Permitir o denegar)
    - Sentencia n (Permitir o denegar)
    - Sentencia por defecto (Denegar)
  
  
  * Pueden ser de dos tipos
      - ACL Estandar (1-99)
        - Se aplica lo mas cerca del destino
        - Sintaxis: access-list [N°lista] [permit-deny] [ip-origen] [wildcar-mask]
        - Ejemplo:´access-list 10 permit 192.168.30.0 0.0.0.255´
      - ACL EXtendida (100-199)
        - Sintaxis: acces-list [N°lista] [permit-deny] [protocolo] [ip-origen] [wildcard-mask] [ip-destino] eq [puerto]
        - Ejemplo: ´acces-list 103 permit tcp 192.168.30.0 0.0.0.255 any eq 80
        
  * ACL estandar en el router:
      - (config)#access-list [N°lista] [permit-deny] [ip-origen] [wildcar-mask]
      - (config-if)#ip access-group [N°lista] [in-out]
