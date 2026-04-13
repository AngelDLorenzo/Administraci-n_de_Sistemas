
## 🔧 Funcionalidades implementadas

### Gestión de usuarios unificada
- Alta/baja automática con una misma contraseña para SSH, webmail, SFTP y login físico.
- Confirmación por correo electrónico (servicio externo como Gmail).
- Cuota de 100 MB por usuario y límite de buzón de correo 5 MB.
- Scripts en Perl que modifican directamente `/etc/passwd`, `/etc/shadow`, `/etc/group` y almacenan en MariaDB.

### Servicios proporcionados
- **Servidor web** (Apache/nginx) con portal de estado que indica si cada servicio está operativo.
- **Correo electrónico** (Postfix/Dovecot) + webmail (Roundcube) y acceso POP3.
- **SFTP** (OpenSSH) con chroot a directorio personal.
- **Espacio web personal** con creación automática de `index.html` y blog (herramienta gratuita).

### Monitorización y copias de seguridad
- Script en Perl que recolecta carga de CPU, uso de memoria, disco y logs. Envía informe diario al administrador.
- Copia de seguridad diaria de los directorios de usuarios y ficheros de configuración (almacenada localmente).

### Seguridad y logs
- Registro de accesos correctos/incorrectos con identificación de la máquina origen.
- Demonio que alerta por correo cada vez que el usuario `root` inicia sesión (solución sugerida por Carlos).
- Recuperación segura de contraseña mediante enlace temporal.

### Funcionalidades adicionales (opcionales)
- **Integración con Moodle:** al dar de alta un usuario, se registra automáticamente en la plataforma (sugerencia del Decanato).

