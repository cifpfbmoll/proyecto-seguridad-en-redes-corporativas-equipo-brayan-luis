[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)

# Seguridad en redes corporativas
### Equipo:
- Luis Fernando Zúñiga Vigil
- Brayan Via Orellana
## Índice
1. [Sprint 1 - Hardening de Ubuntu](#sprint-1---hardening-de-ubuntu)
2. [Sprint 2 - Copias de seguridad](#sprint-2---copias-de-seguridad)
3. [Sprint 3 - Hardening Apache](#sprint-3---hardening-apache)
4. [Sprint 4 -Hardening SSH](#sprint-4---hardening-ssh)
5. [Sprint 5 - Escaneo de vulnerabiliades](#sprint-5---escaneo-de-vulnerabiliades)
6. [Sprint 6 - Seguridad perimetral con pfSense](#sprint-6---seguridad-perimetral-con-pfsense)
7. [Sprint 7 - Seguridad Perimetral y VPN con pfSense](#sprint-7---seguridad-perimetral-y-vpn-con-pfsense)
8. [Sprint 8 - Alta disponibilidad](#sprint-8---alta-disponibilidad)
---
## Sprint 1 - Hardening de Ubuntu
Este documento resume las configuraciones realizadas para asegurar un servidor Ubuntu 22.04 LTS, aplicando medidas de seguridad recomendadas por CIS (Center for Internet Security).

### Configuraciones Aplicadas - Sprint 1

1. **Deshabilitar Cortafuegos**: Poner en "false" en cortafuegos "ufw" mediante el fichero `tailor.xml`.
2. **Aplicación de Reglas `cis_level2_server`**
3. **Configuraciones de Seguridad**:
   - Configuración del arranque GRUB.
   - Establecimiento de contraseña de arranque.
   - Establecer permisos fichero de configuración de arranque.
   - Requerir contraseña en modo “single user”.
4. **Configuración de Usuarios**: Creación de un usuario administrador y añadirlo al grupo `sudoers`.
5. **Actualizaciones de Software**: Verificación del cumplimiento de las recomendaciones de actualizaciones
6. Realizar la auditoría Final y comprobar los resultados.

#### Conclusión Sprint 1
Estas configuraciones mejoran la seguridad del sistema, minimizar vulnerabilidades y asegurar el correcto funcionamiento de la infraestructura. Gracias a la auditorio se ven la mejoras en la seguridad del servidor.

## Sprint 2 - Copias de seguridad

### Respaldo de Seguridad

Realizar dos procesos de copias de seguridad automatizadas hacia Google Drive para proteger los datos de las carpetas **Documentos** e **Imágenes** en el servidor.

### Copia Documentos
- **Origen**: Carpeta `Documentos` del servidor
- **Destino**: Google Drive
- **Cifrado**: Sí
- **RPO (Recovery Point Objective)**: Máximo 1 hora de pérdida de datos permitida
- **Frecuencia**: Lunes a viernes

### Copia Imágenes
- **Origen**: Carpeta `Imágenes` del servidor
- **Destino**: Google Drive
- **Cifrado**: No
- **RPO (Recovery Point Objective)**: Máximo 1 día de pérdida de datos permitida
- **Frecuencia**: Lunes a domingo

**Consideraciones Adicionales:**
- Comprobar la recuperación de los datos. 
- Realizar una batería de pruebas para verificar que el programa funciona correctamente.

## Sprint 3 - Hardening Apache
Fortalecer la configuración del servidor Apache mediante prácticas de hardening para minimizar vulnerabilidades y mejorar su seguridad.

### Tareas a Realizar
- **Instalación de Apache** 
- **Configuraciones Globales:**
  - **Ficheros de Configuración:** Revisar y ajustar configuraciones clave en los archivos principales.
  - **Configuración de Usuarios y Grupos:** Limitar privilegios a usuarios y grupos específicos.
  - **Ocultación de Versiones:** Configurar Apache para que no exponga la versión del servidor.
  - **Exposición Mínima de Módulos:** Deshabilitar módulos innecesarios para reducir la superficie de ataque.
  - **Creación de VirtualHost:** Crear un VirtualHost con tu nombre y apellido.
    - **Directiva `Options`:** Implementar configuraciones múltiples y de contexto.
- **Archivos `.htaccess`:** Comprender su propósito y configurarlos adecuadamente.
- **Evitar el Hotlinking:** Configurar reglas para prevenir el uso indebido de recursos multimedia.
- **Configuración HTTPS:**
  - Generar certificados con OpenSSL.
  - Configurar el VirtualHost para que todos los accesos sean por HTTPS.
- **Módulo `mod_security`:**
    - Investigar sobre `mod_security`.

- **Pruebas de Seguridad:**
  - Descargar Kali Linux y ejecutar un ataque DoS con Metasploit (Slowloris) en nuestro servidor web.
  - Clonar e implementar las reglas OWASP recomendadas.
  - Configurar reglas para detectar SQL Injection.
  - Instalar y activar `mod_security` para repetir el ataque y confirmar que el servidor sigue accesible.


### Conclusión
En este sprint, se mejoró la seguridad del servidor Apache configurando opciones clave como la ocultación de versiones, desactivación de módulos innecesarios y la implementación de HTTPS. Se habilitó el módulo mod_security con reglas OWASP para proteger contra ataques comunes y se realizaron pruebas de seguridad, como un ataque DoS (Slowloris). 

## Sprint 4 - Hardening SSH
Asegurar el servidor SSH mediante configuraciones de hardening.

### Tareas a realizar:

1. **Instalación del servidor SSH**
3. **Configuraciones de Hardening**:
   - **Autenticación SSH por clave pública**: Deshabilitar autenticación por contraseña.
   - **Cambio de puerto**: Cambiar el puerto SSH de 22 a uno no estándar.
   - **Limitar IPs**: Restringir el acceso por IP.
   - **Deshabilitar ROOT**: Evitar acceso SSH con el usuario ROOT.
   - **Limitar usuarios**: Restringir el acceso SSH a usuarios específicos.
   - **Deshabilitar contraseñas**: Deshabilitar inicio de sesión por contraseña.
   - **Contraseñas vacías**: Deshabilitar contraseñas vacías.
   - **Limitar intentos fallidos**: Configurar límite de intentos fallidos de login.
   - **Limitar conexiones simultáneas**: Restringir conexiones SSH no autenticadas.
   - **Banner de advertencia**: Configurar un banner para los usuarios SSH.
   - **Timeout de sesión inactiva**: Configurar cierre de sesión después de inactividad.
   - **Deshabilitar X11 forwarding**: Evitar el uso de aplicaciones gráficas.
   - **Chroot (Bloquear usuarios)**: Limitar a los usuarios a sus directorios de inicio.
4. **Doble Factor de Autenticación (2FA)**:
   - Investigar, habilitar y configurar 2FA en SSH y verificar su funcionamiento.

### Conclusión
El hardening del servidor SSH mejora la seguridad al mitigar riesgos como el acceso no autorizado, ataques de fuerza bruta y el uso de contraseñas débiles. Las configuraciones implementadas, como la autenticación por clave pública, el cambio de puerto y el uso de 2FA, refuerzan la protección del sistema, asegurando un acceso remoto más seguro.


## Sprint 5 - Escaneo de vulnerabiliades
Análisis de vulnerabilidades en entornos empresariales mediante el uso de Nmap

### Tareas a realizar:
1. **Descargar MV metasplotaible2 e impórtala**
2. **Escaneo utilizando la técnica SYN Scan y reconoce los principales servicios en :**
   - MV de metasplotaible2
   - Servidor de Ubuntu
3. **Escaneo de los principales puertos UDP abiertos en Mestasplotaible2**
4. **escaneo lanzando el script vuln en :**
   - MV de metasplotaible2
   - Servidor de Ubuntu
5. **Escaneo agresivo (opción -A) en:**
   - MV de metasplotaible2
   - Servidor de Ubuntu
6. **Escaneo de descubrimiento de equipos en la red de casa**

### Conclusión
Los escaneos realizados con Nmap proporcionaron una visión exhaustiva del estado de seguridad del equipo como: identificar los principales puertos abiertos, servicios, posibles vulnerabilidade y indentificación de equipos de la re local.
Estas actividades son fundamentales para detectar puntos débiles y reforzar la seguridad en entornos empresariales y domésticos.


## Sprint 6 - Seguridad perimetral con pfSense
En este sprint, aprenderemos a instalar y configurar pfSense, y crearemos reglas específicas para cada interfaz de red. Asegurando y gestionando el tráfico entre las diferentes redes, implementando medidas de seguridad para proteger el sistema y la infraestructura de la red.

## Requisitos
- **pfSense 2.7.2** instalado.
- Tres tarjetas de red configuradas:
  - **WAN** (Adaptador puente)
  - **LAN DMZ** (Red interna `10.0.3.0/24`)
  - **LAN Empleados** (Red interna `10.0.2.0/24`)
- **Servidor** en la DMZ con IP fija.
- **Equipo de empleados** en la red interna `10.0.2.0/24` (simulando un Windows).

## Comprobaciones iniciales
- ¿El servidor web y SSH es accesible desde el exterior?
- ¿El servidor tiene acceso a internet?
- ¿El equipo de los empleados tiene internet?
- ¿El servidor web es alcanzable desde el equipo de los empleados? ¿Y viceversa?

## Configuración de reglas en pfSense
1. **El servidor tenga acceso a internet**
2. **Los empleados tengan acceso a internet.**
3. **El servidor web sea accesible únicamente por el puerto 443 y redirija el tráfico del 80 al 443**
4. **El servidor SSH sea accesible únicamente desde el puerto que elegiste en el Sprint de Hardening SSH**
5. **Una regla que no permita el tráfico directo entre el servidor y los empleados, y al revés**
6. **Crear una regla de emergencia para bloquear tráfico del servidor a la red WAN en caso de ciberataque.**
7. **Bloquear una IP específica que haya realizado un ataque DoS al servidor web.**
8. **Crear una regla personalizada**

### Conclusión
Creamos varias reglas en las 3 interfaces de red para bloquear o permitir ciertas acciones, lo que nos ayuda a asegurar la segmentación de tráfico entre redes, proteger el servidor web y SSH, y establecer medidas de emergencia en caso de ciberataques. Esto mejora la seguridad perimetral y la respuesta ante incidentes.


## Sprint 7 - Seguridad Perimetral y VPN con pfSense

El objetivo de este sprint es configurar el cortafuegos pfSense con IDS/IPS Suricata y un servidor VPN, permitiendo a los empleados conectarse de manera segura desde redes públicas.

### Tareas Realizadas:

#### 1. Instalación de IDS/IPS Suricata:
- Instalación y configuración de Suricata en pfSense con las reglas de la comunidad **Snort**.

#### 2. Prueba de Ataque DoS:
- Se realizó un ataque DoS al servidor Web antes de habilitar Suricata.
- Tras habilitar Suricata en modo **IPS**, se repitió el ataque y se verificó la detección y bloqueo en los logs.

#### 3. Configuración del Servidor VPN:
- Configuración de un servidor VPN en pfSense con las siguientes opciones:
  - **OpenVPN** y **WireGuard** para permitir conexiones seguras.

#### 4. Análisis de Tráfico con ntopng:
- Instalación de **ntopng** en pfSense para monitorear el tráfico de red y detectar posibles amenazas.

### Conclusión:
Este sprint mejoró la seguridad perimetral mediante Suricata (IDS/IPS) y un servidor VPN, permitiendo acceso remoto seguro y analizando el tráfico para identificar amenazas.


## Sprint 8 - Alta disponibilidad

Se implementa un sistema de alta disponibilidad con Apache configurado como proxy inverso y balanceador de carga. Además, se explora la configuración de un proxy caché con pfSense.

### **US12 - Proxy Inverso**
- Se configuró Apache como proxy inverso para redirigir peticiones a un servidor final.
- Se utilizó la aplicación `http.server` de Python en Ubuntu como servidor final.
- Se creó una página HTML con el texto: **proxy inverso + [Nombre y Apellido]**.
- Se habilitaron los módulos necesarios:
  ```bash
  sudo a2enmod proxy
  sudo a2enmod proxy_http
  ```
- Se comprobó el funcionamiento del proxy inverso desde un equipo en la WAN.

### **US13 - Apache Balancer**
- Se configuró Apache como balanceador de carga con tres miembros (*workers*).
- Cada *worker* utilizó `http.server` en Ubuntu y sirvió una página HTML con el texto: **miembro balanceador nº __ + [Nombre y Apellido]**.
- Se definió un balanceador en Apache con el apellido del equipo.
- Se implementó el método de balanceo `byrequests`, asignando el triple de carga al primer nodo.
- Se configuró un tercer nodo como **hot-standby**.
- Se activó el módulo de administración `balancer-manager` y se comentó su información.
- Se habilitaron los módulos necesarios:
  ```bash
  sudo a2enmod proxy
  sudo a2enmod proxy_http
  sudo a2enmod proxy_balancer
  sudo a2enmod lbmethod_byrequests
  sudo a2enmod slotmem_shm
  sudo a2enmod proxy_connect
  ```
- Se verificó el correcto funcionamiento del balanceador y la activación del tercer nodo *hot-standby*.

### **US14 - Proxy caché con pfSense (opcional)**
- Se realizó una configuración básica de proxy caché en pfSense para que los equipos de la LAN pasen por él.
- Se verificó que el tráfico pasaba correctamente por el proxy.
- Se investigaron las configuraciones principales y su utilidad.

### **Conclusión Sprint 8**
Se implementó un sistema de alta disponibilidad con Apache, configurando un proxy inverso y un balanceador de carga. Se probaron las configuraciones en distintos escenarios para verificar su funcionamiento y se exploró la configuración de un proxy caché con pfSense para optimizar el tráfico de la LAN.
