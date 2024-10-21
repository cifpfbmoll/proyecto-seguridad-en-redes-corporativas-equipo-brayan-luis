[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)

# Sprint 1 - Hardening de Ubuntu

### Alumnos:
- Luis Fernando Zúñiga Vigil
- Brayan Via Orellana

## Introducción

Este documento resume las actividades y configuraciones realizadas para asegurar un servidor Ubuntu 24.04 LTS, que se virtualiza mediante VirtualBox. El objetivo es aplicar las medidas de seguridad recomendadas por CIS (Center for Internet Security) y otras configuraciones relevantes para proteger el sistema.

## Actividades Previas

1. **Lectura del Artículo**: Se realizó la lectura de un artículo relevante sobre la seguridad en sistemas Ubuntu para comprender mejor las medidas a implementar.

2. **Auditoría Inicial**: Utilizando la guía proporcionada, se realizó una auditoría del sistema con las medidas de seguridad `cis_level2_server`, registrando los resultados obtenidos.

### Resultados de la Auditoría Inicial

- Se registraron las vulnerabilidades y áreas de mejora identificadas en el sistema.
- Los resultados se documentaron para comparar con la auditoría final tras aplicar las configuraciones de seguridad.

## Configuraciones Aplicadas

1. **Deshabilitar el Cortafuegos**: Antes de aplicar las configuraciones de seguridad, se deshabilitó el cortafuegos del sistema. Esto se realizó mediante la customización del fichero `tailor.xml`.

2. **Aplicación de Reglas `cis_level2_server`**: Se aplicaron las reglas de seguridad del nivel 2 recomendadas por CIS.

3. **Configuraciones de Seguridad Adicionales**:
   - **Configuraciones Globales**: Se aseguraron configuraciones generales del sistema.
   - **Configuración del Arranque GRUB**: Se aplicaron configuraciones para asegurar el gestor de arranque GRUB.
   - **Establecimiento de Contraseña de Arranque**: Se configuró una contraseña para el arranque del sistema.
   - **Permisos del Fichero de Configuración de Arranque**: Se ajustaron los permisos para el fichero de configuración de arranque.
   - **Uso Obligatorio de Contraseña en Modo “Single User”**: Se configuró el sistema para requerir una contraseña al iniciar en modo de usuario único.

4. **Configuración de Usuarios y Grupos**: Se creó un usuario administrador con las iniciales del nombre y apellido (por ejemplo, `rgion`) y se añadió al grupo `sudoers`.

5. **Actualizaciones de Software**: Se verificó que el sistema cumple con las recomendaciones sobre actualizaciones de software.

## Auditoría Final

Se realizó una auditoría final del sistema después de aplicar todas las configuraciones y se compararon los resultados con la auditoría inicial.

### Conclusiones

- **Mejoras en la Seguridad**: La comparación de auditorías mostró mejoras significativas en la seguridad del sistema tras aplicar las configuraciones recomendadas.
- **Áreas de Mejora**: Se identificaron algunas áreas que aún pueden necesitar atención en futuras revisiones de seguridad.

## Referencias

- [Guía de CIS Level 2 Server](https://www.cisecurity.org/benchmark/ubuntu/)
- [Videotutorial sobre Seguridad en Ubuntu](https://www.example.com)

