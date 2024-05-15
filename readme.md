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

## Paso 4: Declaración de la subnet 172.16.0.0/16

Para esto declararemos la subnet creando un netplan y abriendolo desde el editor de texto

![abrir el netplan desde el editor de texto](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/bb09816dc444511cb199bc9360c9de9494f4a6c5/netplan.png)

Con el editor de texto abierto, declararemos la subnet con la siguiente configuración

![configuracion subnet](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/bb09816dc444511cb199bc9360c9de9494f4a6c5/declaracionsubnet.png)

Y finalmente para aplicar la configuración de nuestra subnet, debemos lanzar el siguiente comando

![netplan apply](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/bb09816dc444511cb199bc9360c9de9494f4a6c5/netplanapply.png)

## Paso 5: Arranque del servicio DHCP

Una vez configurado, debemos iniciar el servicio DHCP para que esté disponible para atender las solicitudes de los clientes en la red.

## Paso 6: Comprobación del estado del servicio

Es importante verificar que el servicio DHCP esté en ejecución y funcionando correctamente. Esto se realiza mediante el comando 'systemctl status'.

![arranque y comprobacion del servicio](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/94c1d15022209b92add4813660f694b51c010381/systemctl.png)

## Paso 7: Prueba con un cliente

Para confirmar que el servidor DHCP está asignando direcciones IP correctamente, conectaremos un cliente a la red y verificaremos si recibe una dirección IP dentro del rango especificado en la configuración.

![prueba con cliente](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/3cbcaef7ed1151ebd97be8eb3eea1c75db00231a/cliente.png)

## Paso 8: Asignación por dirección MAC fija

Podemos asignar direcciones IP fijas a dispositivos específicos basados en su dirección MAC. Esto garantiza que ciertos dispositivos siempre reciban la misma dirección IP, lo que puede ser útil para servidores o dispositivos de red críticos.

![asignacion direccion mac fija](https://github.com/CarlosAlvarezDiaz/DHCP_maquina_virtual/blob/14fb1a05d503ecf36de377b93494bef99fd9b339/ipfija.png)