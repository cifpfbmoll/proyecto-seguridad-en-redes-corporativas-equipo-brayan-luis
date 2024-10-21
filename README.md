[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)

# Seguridad en redes corporativas
### Alumnos:
- Luis Fernando Zúñiga Vigil
- Brayan Via Orellana
  
## Sprint 1 - Hardening de Ubuntu
Este documento resume las configuraciones realizadas para asegurar un servidor Ubuntu 22.04 LTS, aplicando medidas de seguridad recomendadas por CIS (Center for Internet Security).

## Actividades Previas

1. **Leer el Artículo**: Comprensión de las medidas de seguridad en sistemas Ubuntu.
2. **Primera Auditoría**: Se realizó una auditoría con las medidas de seguridad `cis_level2_server` y se comentaran los resultados.

## Configuraciones Aplicadas

1. **Deshabilitar Cortafuegos**: Se deshabilitó el cortafuegos mediante el fichero `tailor.xml`.
2. **Aplicación de Reglas `cis_level2_server`**: Se implementaron las configuraciones recomendadas.
3. **Configuraciones de Seguridad**:
   - Seguridad global y del gestor de arranque GRUB.
   - Establecimiento de contraseña de arranque.
   - Ajustes de permisos en el fichero de configuración de arranque.
   - Requerir contraseña en modo “single user”.
4. **Configuración de Usuarios**: Creación de un usuario administrador (ej. `rgion`) y adición al grupo `sudoers`.
5. **Actualizaciones de Software**: Verificación del cumplimiento de las recomendaciones de actualizaciones
## Auditoría Final

Se realizó una auditoría final, comparando los resultados con la auditoría inicial.

### Conclusiones

- **Mejoras en Seguridad**: Se ven mejoras significativas tras aplicar las configuraciones.
- **Áreas de Mejora**: Se identificaron aspectos que necesitan atención en futuras revisiones.

## Referencias

- [Guía de CIS Level 2 Server](https://www.cisecurity.org/benchmark/ubuntu/)
- [Videotutorial sobre Seguridad en Ubuntu](https://www.example.com)
