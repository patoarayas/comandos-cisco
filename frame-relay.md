1. Configurar nube
  Agregar a cada int serial de la nube el dlci
    Para el hub crear un dlci por cada conexion tipo 10x donde x es el router destino
    Para los demas usar el numero del router ej x00
    como nombre ponerle Rorigen-Rdestino
  Realizar las conexiones en la nube->Frame Relay 
2. configurar router
  p2mp punto multi punto
  1. Cambiar nombre
  2. (config-if)#encapsulation frame-relay
  3. (config-if)#ip address (para 3 router usar maskara 29 .248)
  
  4. Crear mapas (es automatico para las conectadas directamente) revisar en  #sh frame-relay map
     sino pra crearlas, expecialmente para los router no conectados directamente
      (config-if)#frame-relay map ip (ip-destino) (dlci) broadcast cisco
      
   p2p punto a punto
   1. Cambiar nombre
   2. (config-if)#encapsulation frame-relay y no shut
   
   3. para el router HUB (R1) usar subinterfaces para asignar ip
    (config)#int s0/0/0.10x point-to-point
    (config)#ip addr
    (config)#frame-relay interface-dlci 10x 
   3. para los otros router
      (config-if)#ip address (mascara 30)
      (config)#frame-relay interface-dlci x00 
      
   4. crear rutas estaticas entre los router no conectados directamente  
