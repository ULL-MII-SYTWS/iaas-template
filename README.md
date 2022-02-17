# Práctica: IAAS

Esta práctica tiene por objetivo configurar la máquina personal del *IAAS*.

**Asignatura**: [Procesadores de Lenguajes](https://github.com/ULL-ESIT-PL-2122)

**Alumno**: [Andrés Pérez Castellano](https://github.com/AndPerCast)

## Configuración inicial

### Reclamar una máquina virtual

Primero, acceda a la página del servicio [IAAS](https://iaas.ull.es). Encienda la máquina virtual y<br>
obtenga la dirección *ip* desde el panel de administración.

![IAAS](./docs/static/iaas.png)

Dentro de la red universitaria (o usando una *VPN*) conéctese a su máquina remota.
```bash
# Sustituya <ipaddr> por la dirección real
ssh usuario@<ipaddr>
```

### Conexión remota

Para simplificar el mecanismo de conexión, haga lo siguiente.

Genere una clave *ssh* en su máquina local
```bash
ssh-keygen -t rsa
```

Concatene la clave pública `~/.ssh/id_rsa.pub` con aquellas aceptadas en la máquina remota.
```bash
cat .ssh/id_rsa.pub | ssh usuario@<ipaddr> 'cat >> .ssh/authorized_keys'
```

Ahora puede iniciar una sesión remota rápidamente y sin introducir contraseña.

![Contraseña](./docs/static/contraseña.png)

### Actualizar e instalar paquetes

Cambie la contraseña por defecto. Actualice el sistema.
```bash
sudo apt update
sudo apt upgrade
sudo apt autoremove
```

![Update](./docs/static/update.png)
