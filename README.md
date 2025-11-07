# lab-ciber1
Laboratorio-ciberseguridad-1


# 🧱 Laboratorio de Ciberseguridad – DVWA + Servicios en Docker

Este laboratorio forma parte de la cátedra **Seguridad Ofensiva Avanzada** (UTN FRM – Malbec Defense).  
Permite practicar reconocimiento, explotación y enumeración de servicios vulnerables en un entorno aislado.

---

## 🚀 Despliegue rápido

1. Clonar este repositorio dentro de tu máquina virtual Linux (Ubuntu/Debian):

   ```bash
   git clone https://github.com/davidroco99/lab-ciber1.git
   cd lab-ciber1


   docker compose up -d
   docker ps



   🌐 Acceso al laboratorio

Como la máquina virtual está configurada en modo puente (bridged), su IP pertenece a la red local del aula.

Para conocerla, ejecutá dentro de la VM:

ip a show
o
ifconfig


#📍 Anotá la dirección IPv4 que aparezca (por ejemplo 192.168.10.50).

Luego abrí en tu navegador:

http://<IP_VM>:8080


#Ejemplo:
👉 http://192.168.10.50:8080

#🔒 Servicios activos
Servicio	Puerto	Descripción	Credenciales
DVWA (Web App)	8080	Aplicación vulnerable para pruebas web	admin / password (por defecto DVWA)
MariaDB	interno	Base de datos DVWA	dvwa / dvwa_password
FTP	2121	Servidor FTP para pruebas	conexión anónima o alumno
Samba	4455	Recurso compartido de red	usuario alumno, pass Insegura123
DNS	5353	Servidor DNS simple (corp.local)	—
#🧪 Pruebas básicas

# Desde la VM o desde otra máquina de la red del aula
curl -I http://<IP_VM>:8080
dig @<IP_VM> lab.corp.local
nmap -p 21,80,445,5353 <IP_VM>

#⚠️ Seguridad

Este entorno es intencionalmente vulnerable.
No debe conectarse a Internet ni a redes productivas.
Solo usar dentro de la red de laboratorio o en una máquina virtual aislada.

#👨‍🏫 Autor

Ing. Ricardo David Roco
Cátedra: Seguridad Ofensiva Avanzada – UTN FRM
Proyecto educativo Malbec Defense
🔗 https://github.com/davidroco99
