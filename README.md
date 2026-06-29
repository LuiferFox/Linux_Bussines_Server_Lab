# Linux Enterprise Server Lab

Implementación de un servidor Linux empresarial utilizando Ubuntu 24.04 LTS en VirtualBox. Este laboratorio documenta la instalación y configuración de servicios esenciales como OpenSSH y Apache, además de la administración de usuarios, grupos y permisos siguiendo buenas prácticas de administración de sistemas.

---

## Objetivo

Desarrollar un entorno de laboratorio que simule la implementación inicial de un servidor empresarial, fortaleciendo conocimientos en:

- Administración básica de Linux.
- Gestión de servicios mediante `systemctl`.
- Administración remota mediante SSH.
- Implementación de un servidor web Apache.
- Gestión de usuarios, grupos y permisos.
- Validación de servicios y conectividad.

---

## Tecnologías utilizadas

| Tecnología | Descripción |
|------------|-------------|
| Ubuntu 24.04 LTS | Sistema Operativo |
| VirtualBox | Virtualización |
| OpenSSH Server | Administración remota |
| Apache2 | Servidor Web |
| Bash | Administración del sistema |
| Windows 11 | Cliente para pruebas SSH y HTTP |

---

## Arquitectura del laboratorio

```text
                 Windows 11
            (Cliente de administración)
                  │
        ┌─────────┴─────────┐
        │                   │
      SSH (22)          HTTP (80)
        │                   │
        ▼                   ▼
      Ubuntu 24.04 LTS (VirtualBox)
               srv-web-fox
        ├── OpenSSH Server
        ├── Apache2
        ├── Usuarios
        └── Permisos
```

---

## Funcionalidades implementadas

- Configuración del hostname del servidor.
- Actualización del sistema operativo.
- Instalación y configuración de OpenSSH Server.
- Administración remota mediante SSH.
- Instalación y validación del servicio Apache.
- Publicación de una página web personalizada.
- Creación de usuarios y grupos.
- Configuración de permisos sobre recursos compartidos.
- Verificación del estado de los servicios.
- Validación de conectividad desde un cliente Windows.

---

## Evidencias

| Captura | Descripción |
|----------|-------------|
| 01 | Información inicial del sistema |
| 02 | Cambio de hostname |
| 03 | Actualización del sistema (`apt update`) |
| 04 | Actualización de paquetes (`apt upgrade`) |
| 05 | Verificación de privilegios sudo |
| 06 | Estado del servicio SSH |
| 07 | Dirección IP del servidor |
| 08 | Conexión SSH desde Windows |
| 09 | Estado del servicio Apache |
| 10 | Página web por defecto de Apache |
| 11 | Página web personalizada |
| 12 | Creación de usuarios |
| 13 | Configuración de grupos |
| 14 | Configuración de permisos |
| 15 | Validación de permisos |

Las evidencias se encuentran en la carpeta **screenshots/**.

---

## Estructura del proyecto

```text
linux-empresa-server/

├── README.md
├── screenshots/
├── comandos/
│   ├── apache.txt
│   ├── ssh.txt
│   ├── usuarios.txt
│   └── permisos.txt
├── LICENSE
└── .gitignore
```

---

## Comandos principales

### Actualización del sistema

```bash
sudo apt update
sudo apt upgrade -y
```

### OpenSSH

```bash
sudo apt install openssh-server -y
systemctl status ssh
```

### Apache

```bash
sudo apt install apache2 -y
systemctl status apache2
```

### Usuarios

```bash
sudo adduser administrador
sudo adduser soporte
sudo groupadd ti
```

### Permisos

```bash
sudo mkdir /empresa
sudo chown :ti /empresa
sudo chmod 770 /empresa
```

Los comandos completos utilizados durante el laboratorio se encuentran en la carpeta **comandos/**.

---

## Validaciones realizadas

Durante el laboratorio se verificó que:

- El servidor obtuvo conectividad a la red.
- El servicio OpenSSH quedó activo y operativo.
- Fue posible administrar el servidor remotamente desde Windows mediante SSH.
- Apache respondió correctamente a solicitudes HTTP.
- La página web personalizada fue accesible desde otro equipo de la red.
- Los usuarios y grupos fueron creados correctamente.
- Los permisos asignados protegieron el acceso al recurso compartido.

---

## Competencias desarrolladas

- Administración básica de servidores Linux.
- Gestión de servicios con `systemctl`.
- Configuración de acceso remoto mediante SSH.
- Implementación de servidores web Apache.
- Administración de usuarios y grupos.
- Gestión de permisos en Linux.
- Resolución básica de problemas.
- Documentación técnica de laboratorios.

---

## Mejoras futuras

- Configuración de firewall mediante UFW.
- Autenticación SSH mediante llaves públicas.
- Implementación de HTTPS.
- Automatización mediante Bash.
- Configuración de copias de seguridad.
- Monitoreo básico del servidor.

---

## Autor

**Luis Fernando Sánchez Mariño**

Proyecto desarrollado como parte de mi portafolio de Administración de Sistemas, Linux y Redes.
