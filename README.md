[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)

# Seguridad en redes corporativas
### Equipo:
- Luis Fernando Zúñiga Vigil
- Brayan Via Orellana
  
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

En este sprint, se trabajará en la configuración de seguridad del servidor Apache ya instalado, con el objetivo de hacerlo más seguro. Las tareas se basan en la guía de hardening básica de Apache ofrecida por el INCIBE.

## Objetivo
Fortalecer la configuración del servidor Apache mediante prácticas de hardening para minimizar vulnerabilidades y mejorar su seguridad.

## Tareas a Realizar
A continuación, se enumeran las configuraciones y actividades necesarias:

- **Instalación de Apache:** 
- **Configuraciones Globales:** Aplicar configuraciones generales recomendadas por la guía de hardening.
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
    - Investigar y activar `mod_security`.
    - Descargar e implementar las reglas OWASP recomendadas.
    - Configurar reglas para detectar SQL Injection.
- **Pruebas de Seguridad:**
    - Descargar Kali Linux y ejecutar un ataque DoS con Metasploit (Slowloris) para comprobar la vulnerabilidad inicial.
    - Activar `mod_security` y repetir el ataque para confirmar que el servidor sigue accesible tras la protección.


## Resultado Esperado
Un servidor Apache más seguro, resistente a ataques comunes como DoS y SQL Injection, con configuraciones optimizadas para minimizar vulnerabilidades.

