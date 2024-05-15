# Configuración de Servidor DHCP en Ubuntu
Este README detalla los pasos para configurar un servidor DHCP en Ubuntu, una tarea fundamental en la administración de redes informáticas. El servidor DHCP permite asignar direcciones IP automáticamente a dispositivos en una red, simplificando la administración de direcciones IP.
## Paso 1: Instalación del paquete 'isc-dhcp-server'
Para comenzar, es necesario instalar el paquete 'isc-dhcp-server', que proporciona el software para configurar y ejecutar un servidor DHCP en Ubuntu.

![instalacion isc-dhcp-server](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/4889a25bd2dd092c1cd3b5a09d5d0c38c8fcd812/instalarDHCP.png)

## Paso 2: Configuración básica del archivo 'dhcpd.conf'
El archivo 'dhcpd.conf' es el corazón de la configuración del servidor DHCP. En este paso, definiremos parámetros clave como la subnet, el rango de direcciones IP disponibles y las opciones de red.

![abrir el archivo dhcpd.conf desde el editor de texto](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/0c851ff6e9b355d0e6eea79e7c77a1960d6ad055/configuracion.png)
![configuracion del archivo dhcpd.conf](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/0c851ff6e9b355d0e6eea79e7c77a1960d6ad055/configuracionbasica.png)

## Paso 3: Configuración de la interfaz de red
Es esencial configurar la interfaz de red que utilizará el servidor DHCP para escuchar las solicitudes de asignación de direcciones IP. Esto se realiza mediante el archivo '/etc/default/isc-dhcp-server'.

![abrir el archivo de configuracion de la interfaz de red desde el editor de texto](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/af6b310c2452792e04887027a75ee2db39ec38f4/red.png)
![configuracion de la interfaz de red](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/af6b310c2452792e04887027a75ee2db39ec38f4/configuracionred.png)