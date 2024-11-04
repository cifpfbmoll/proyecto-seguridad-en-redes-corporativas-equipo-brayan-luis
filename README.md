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
- Es imprescindible comprobar la recuperación de los datos. 
- Se solicita realizar una batería de pruebas para verificar que el programa funciona correctamente.
