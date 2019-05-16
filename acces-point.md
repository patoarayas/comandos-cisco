# Configuración Access Point
- ### Interfaces:
  * Dot11Radio0 (2.4GHz)
  * Dot11Radio1 (5 GHz)
  * FastEthernet
  * BVI1 (Bridge Virtual interface) Interface de administración del AP
  
  ### Configuración:
    1. Asignar IP a int BVI1
    2. Con un PC en la misma red entrar a la ip de la interface BVI1 desde un explorador web.
    3. Express setup.
    4. Configurar Dot11Radio0  Home->Radio802.11g
        - Enable radio
        - Role Access Point
        - Configurar Data Rates
        - Seleccionar canal
    5. Express Security
        - Nombrar SSID
        - Seleccionar broadcast
    6. En el Switch configurar DHCP para la pool de la SSID
    7. Configurar int vlan para el gateway
    8. (Opcional) Neetwork Interfaces->FastEthernet->Settings->Enable Ethernet
    9. Para dar conexion a internet se debe hacer desde el router
      - Configurar ruta por defecto en el router hacia Internet
      - Configurar ruta por defecto en el Switch hacia el Router
      (config)#ip route 0.0.0.0 0.0.0.0 /<direccion-proximo-salto>
        
