### Switch de Distribucion (Paso 1)

	
	*Configurar el nombre del switch

		#conf t
		#hostname <nombre de switch>

	*Colocar todas las interfaces en modo troncal

		#int <interfaz o puerto>
		#switchport trunk encapsulation dot1q
		#switchport mode trunk



### Switch de acceso (Paso 2)
	

	*Configurar el nombre del switch

		#conf t
		#hostname <nombre de switch>

	*Colocar las interfaces conectadas a los switch de distribucion en modo troncal

		#int <interfaz o puerto>
		#switchport mode trunk

	*Colocar las interfaces conectadas a los equipos en modo acceso

		#int <intefaz o puerto>
		#switchport mode access



### Switch de Distribucion (Paso 3)

	*Configurar VTP en solo 1 switch de distribución, 
	
		#vtp domain CISCO
		#vtp version 2

	*Configurar el modo VTP en servidor, en ambos, aunque por defecto los switches están en mode server

		#vtp mode server



### Switch de acceso (Paso 4) 
	

	*Configurar el modo VTP en cliente

		#conf t
		#vtp mode client



### Switch de distribucion (Paso 5)


	*Crear las VLAN en solo uno de los servidores en modo servidor (al configurar el vtp antes se comparten a todos ls switches)

		#conf t
		#vlan <numero de vlan> //Por si las dudas, despues de cada vlan creada: ejecutar #exit

		//REVISAR VLAN si se las come el otro switch, si es el caso: crearlas de nuevo. (Esto no debería pasar si se configuro el vtp)


	*Configurar Spanning-tree en cada switch

		#conf t
		#spanning-tree mode rapid-pvst



### Switch de acceso (Paso 6)


	*Configurar Spanning-tree en cada switch

		#conf t
		#spanning-tree mode rapid-pvst



### Switch de distribucion (Paso 7)


	*Configurar las raices de spaning-tree en cada switch

		#conf t
		#spanning-tree vlan <numero> root <prioridad: primary/secondary>

		//la prioridad dependera de la VLAN a la que corresponda cada switch. Si la VLAN corresponde al switch, es primary.



### Switch de acceso (Paso 8)


	*Asignar las VLAN a los puertos de cada switch

		#conf t
		#int <interfaz o puerto>
		#switchport access vlan <numero>

	*(Opcional) Activar el port-fasten las interfaces que van a los PC
		#conf t
		#int <interfaz o puerto>
		#spanning-tree portfast		




### Switch de distribucion (Paso 10)


	*Configurar el IP routing en cada switch de distribución

		#conf t
		#ip routing

	*Excluir los rangos de todas las redes IP en cada switch

		#conf t
		#ip dhcp excluded-address <IP inicio - IP termino>

	*Crear y configurar el DHCP pool de todas las VLAN

		#ip dhcp pool <VLAN#>
		#network <IP de la red> <mascara>
		#default-router <Gateway>
		#dns-server 8.8.8.8//ATENCION: El ejercicio puede ofrecer una IP servidor diferente. Especialmente si es que hay un servidor DNS en la red, en ese caso usar su ip.

	*Configurar la IP en cada interfaz VLAN en los dos switch

		#ip address <numero de ip> <mascara>	//La terminación de la IP debe ser diferente: .2 en un switch y .3 en el otro.
		#standby <numero VLAN> ip <gateway> //.1 para ambos
		#standby <numero VLAN> priority <valor: Si VLAN correponde a switch; debe ser mayor (110)sino (100)>
		#standby <numero VLAN> preempt //Se pone preempt en todas las int vlan 





	
