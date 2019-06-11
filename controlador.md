
1. Conectar controlador usando puerto 1 al switch
2. Desconectar el controlador y al reiniciar apretar ESC-> opción 5 para reiniciar luego completar los datos.
- Management int ip dado: 192.168.10.100
- Management int ip mask: 255.255.255.0
- Management    int ip default router: 192.168.10.1
- Management int vlan: 10
- Management interface Port núm: 1
- Management int DHCP server: 192.168.10.1
- AP Manager int ip 192.168.10.101
- NTP Server: 200.27.106.116

3. En el switch:
        -Controlador en modo trunk
        - PC y AP en modo access vlan 10
4. Entrar mediante el navegador web al controlador
        * https://192.168.10.100
5. En el navegador entrar a WLAN->MESÓN2->Security_>none

6.Configurar AP
        - Revisar que este en versión k9w8 usando `sh version`
- Montar servidor tftp y configurar ap en la misma red
- archive download-sw /overwrite /reload tftp://ip-pc/ruta-archivo
-
~                                                                                         
~                                                                                         
~                                                                                         
~                                       
