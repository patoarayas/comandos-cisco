1. Router

	1.1 asignar ip gi0/1 (Pared)

		int gi0/1
		ip address 172.30.2.201 255.255.255.0
		no shut
	1.2 Configurar subinterfaces en Gi0/0 (al Switch)

		- int gi0/0
		no shut
		- int gi0/0.10
			encapsulation dot1q 10
			ip add 192.168.10.1 255.255.255.0

		- int gi0/0.20
			encapsulation dot1q 20
			ip add 192.168.20.1 255.255.255.0

	1.3 configurar dhcp en el router
	1.4 configurar NAT
		int gi0/1
			ip nat outside
		int gi0/0.10
			ip nat inside

		int gi0/0.20
			ip nat inside
	
		access-list 1 permit 192.168.10.0 0.0.0.255
		ip nat inside source list 1 int gi0/1 overload



2. Switch
	2.1 Configurar troncales
		trunk int fa0/1 (al AP), fa0/48 (al Router)

	2.2 crear vlans 10 y 20
	
	!! Si el AP esta en una boquilla con vlan el pc para acceder debe estar en
	   una boquilla con vlan.
	!! Si el AP esta en una boqilla en modo trunk el PC para acceder debe estar en una 
	   boquilla sin VLAN (es decir sin nada) o en modo trunk. 



3. Access point (BVI1 -> 10.0.0.1)
	
	3.1 Configuar BVI1 (en la CLI del AP)
		(config)#int bvi1
			(config-if)#ip address 10.0.0.1 255.255.255.0

	3.2 Configurar interfaces dotRadio (En la GUI)
		* Para ambas interfaces.
		express setup 
			mode: acces point
			optimize radio network for: throughput
			air: enable
		Tambien se puede hacer desde el home->click en la interface radioX->settings. Ademas se puede configurar aca el canal para transmitir

3.3 Configurar VLAN en AP
	Entrar en Security->SSID Manager->Define VLan
	Poner numero y interfaz que va a usar (G es 2.4G / A es 5G) y guardar
3.4 Configurar SSID
	Entrar en Security->SSID Manager
	Con el cursor en NEW 
		Asignar nombre al SSID
		Asignar VLAN
		Asignar Interface
		Guardar (el primer apply que sale)
3.5 Configurar el beacon

	En Security SSID Manager
	Ir al final y a la SSID que queramos que se despliegue en su interface asignada 
	configurar Set Single Guest Mode SSID con el nombre de la red.	
	
	
