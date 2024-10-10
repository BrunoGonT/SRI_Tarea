# Practica 2: Instalación y configuración de DHCP en Debian
`por Bruno González Tresgallo - ASIR2`

En esta actividad vamos a crear una conexión entre maquinas con DHCP, para esto usaremos a PfSense como router, Debian 12.1 como servidor, Windows 10 y Debian 12 como clientes.
![imagen](./IMG/16.png)

## Ejercicio 1. Configuración del servidor DHCP. 
a) Instala el servidor DHCP en la máquina correspondiente.
![imagen](./IMG/1.png)

b) Realiza las configuraciones adicionales necesarias para que funcione el servidor DHCP.
![imagen](./IMG/3.png)

c) Realiza las configuraciones necesarias para cumplir los siguientes requisitos: 
    a. El servidor repartirá direcciones IP en el rango 10.0.XX.1 - 10.0.ΧΧ. 100. 

    b. Utilizará la máscara por defecto correspondiente a esa subred.

    c. Deberá utilizar como puerta de enlace la que corresponda según el diagrama de red.

    d. Como servidor DNS preferido se utilizará el del instituto (deberás averiguarlo) y como alternativo el de google.

    e. Además, se enviará a los clientes el sufijo DNS sriXX.local.

    f. Para el cliente Ubuntu se le reservará la dirección 10.0.XX.60. 

    g. Respecto a los tiempos de alquiler:

    i. El tiempo de alquiler por defecto será de 15 días para todos los equipos. 

    ii. Nunca será superior a 30 días. 

    iii. Nunca será inferior a 1 semana.

![imagen](./IMG/6.png)


d) Reinicia el servicio y verifica que tras el reinicio está activo y en ejecución.

![imagen](./IMG/8.png)

Esta activo y en ejecucion

![imagen](./IMG/6.png)

![imagen](./IMG/9.png)




## Ejercicio 2. Configuración de los clientes DHCP. 
a) Configura los equipos Windows y Linux como clientes DHCP.

Windows

![imagen](./IMG/13.png)

Linux

![imagen](./IMG/14.png)



b) Observa dentro del archivo adecuado del servidor si las IPs han sido asignadas.

Windows

![imagen](./IMG/17.png)

Linux

![imagen](./IMG/14.png)



c) Observa dentro de ambos clientes que son correctos todos los parámetros enviados por el servidor, es decir: 

    i. IP 

    ii. Máscara 

    iii. Puerta de enlace 

    iv. DNS primario 

    v. DNS alternativo 

    i. Nombre de dominio 

    vii. La MAC del equipo que tiene la reserva. 

Linux

 ![imagen](./IMG/14.png)

Windows

![imagen](./IMG/17.png)
d) Verifica que existe conectividad entre los equipos y que además ambos equipos se conectan a Internet.

Windows

 ![imagen](./IMG/18.png)

 Ping a linux

![imagen](./IMG/19.png)

Linux

![imagen](./IMG/20.png)

Ping a windows

![imagen](./IMG/21.png)



## Ejercicio 3. Funcionamiento del servicio. 

Para terminar, deberás explicar la actividad generada por el servidor isc-dhcp-server que has instalado y configurado y que se ha registrado en los logs del sistema por la herramienta Journalctl.

![imagen](./IMG/22.png)

DHCPOFFER:
El servidor DHCP responde al mensaje DHCPDISCOVER ofreciendo una dirección IP al cliente a través de este mensaje.

DHCPREQUEST:
Una vez que el cliente recibe la oferta de IP, envía este mensaje para confirmar su interés en esa dirección IP.

DHCPACK:
El servidor DHCP responde con este mensaje para confirmar que la dirección IP ha sido asignada al cliente y que está lista para ser utilizada.
