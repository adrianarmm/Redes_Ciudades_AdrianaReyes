# Redes_Ciudades_AdrianaReyes

# 🏛️ Ejercicio 1: La Ruta Perdida entre Dos Reinos

## ✨ Narrativa
Siguiendo el mapa milenario encontrado en la Cripta del Ping Infinito, descubriste que dos ciudades hermanas —**Ciudad A** (TorreA) y **Ciudad B** (TorreB)— alguna vez compartieron un canal sagrado de comunicación llamado la **Ruta Sagrada de Datos**.  
Has reconstruido su infraestructura con routers, switches, PCs y un servidor ancestral para compartir reliquias digitales vía FTP.  
Tras superar tormentas de paquetes y pérdidas de señal, has devuelto la vida a la red que alguna vez unió a estas civilizaciones.

---

## 🗺️ Topología (descripción textual)


![image](https://github.com/user-attachments/assets/f05cba3a-35b6-44c6-b8a9-f7eeb4ec16bd)
---

## 📐 Direccionamiento IP

### 🌆 Ciudad A

| Dispositivo        | IP              | Máscara           | Gateway         |
|--------------------|----------------|-------------------|-----------------|
| Torre A G0/0       | 192.168.10.1   | 255.255.255.0     | —               |
| Habitante A1       | 192.168.10.2   | 255.255.255.0     | 192.168.10.1    |
| Habitante A2       | 192.168.10.3   | 255.255.255.0     | 192.168.10.1    |
| Servidor FTP       | 192.168.40.100 | 255.255.255.0     | 192.168.40.1    |
| Torre A G0/1       | 192.168.40.1   | 255.255.255.0     | —               |

### 🌉 Enlace entre Torres (WAN)

| Dispositivo  | Interfaz     | IP              | Máscara           |
|--------------|--------------|------------------|-------------------|
| Torre A      | Serial0/0/0  | 192.168.30.1     | 255.255.255.252   |
| Torre B      | Serial0/0/1  | 192.168.30.2     | 255.255.255.252   |

### 🌆 Ciudad B

| Dispositivo        | IP              | Máscara           | Gateway         |
|--------------------|----------------|-------------------|-----------------|
| Torre B G0/0       | 192.168.20.1   | 255.255.255.0     | —               |
| Habitante B1       | 192.168.20.2   | 255.255.255.0     | 192.168.20.1    |
| Habitante B2       | 192.168.20.3   | 255.255.255.0     | 192.168.20.1    |
| Habitante C        | 192.168.60.2   | 255.255.255.0     | 192.168.60.1    |
| Torre B G0/1       | 192.168.60.1   | 255.255.255.0     | —               |

---

## ⚙️ Configuración de Routers

### 🌐 Torre A

```bash
interface GigabitEthernet0/0
 ip address 192.168.10.1 255.255.255.0
 no shutdown
!
interface GigabitEthernet0/1
 ip address 192.168.40.1 255.255.255.0
 no shutdown
!
interface Serial0/0/0
 ip address 192.168.30.1 255.255.255.252
 clock rate 64000
 no shutdown
!
ip route 192.168.20.0 255.255.255.0 192.168.30.2
ip route 192.168.60.0 255.255.255.0 192.168.30.2

🌐 Torre B
interface GigabitEthernet0/0
 ip address 192.168.20.1 255.255.255.0
 no shutdown
!
interface GigabitEthernet0/1
 ip address 192.168.60.1 255.255.255.0
 no shutdown
!
interface Serial0/0/1
 ip address 192.168.30.2 255.255.255.252
 no shutdown
!
ip route 192.168.10.0 255.255.255.0 192.168.30.1
ip route 192.168.40.0 255.255.255.0 192.168.30.1
```


🔐 Extra: Servidor FTP para Reliquias Digitales

IP	Servicio	Resultado desde Browser
192.168.40.100	FTP	✅ Se muestran archivos en el navegador
💡 Puedes acceder al servidor FTP con éxito ingresando ftp://192.168.40.100 desde la aplicación Web Browser en cualquier PC.

📶 Comprobación de Pings

Desde	Hacia	Resultado
Habitante A1	Habitante B1	✅
Habitante B2	Servidor FTP	✅
Habitante C	Habitante A2	✅
A1	192.168.30.2	✅
🏷️ Etiquetas Narrativas

Dispositivo	Etiqueta Narrativa
TorreA	Gran Torre de la Sabiduría
TorreB	Bastión de los Mensajeros del Sur
Servidor FTP	Archivo Sagrado de Reliquias Digitales
Enlace WAN	Ruta Sagrada de Datos
Habitante C	Viajero de Territorios Olvidados
🔧 Extras implementados: Reliquias restauradas más allá del mandato

✅ Servidor FTP operativo con Web Browser
✅ Cliente remoto (Habitante C) desde red adicional
✅ Enlace WAN probado y funcional con subred /30
✅ Etiquetas narrativas visibles en el mapa de Packet Tracer
✅ Ping exitoso entre todas las subredes
✅ Accesos a servidor FTP desde cualquier host
✅ Direcciones estáticas en routers para todo el tráfico
✅ (Opcional configurado en pruebas): ACL simulando control de acceso ancestral
✅ Conclusión

La misión ha sido completada con éxito.
La red perdida entre los dos reinos ha sido restaurada, y el conocimiento digital puede fluir nuevamente entre las ciudades a través de la Ruta Sagrada.
Los habitantes ya pueden intercambiar reliquias y mensajes gracias al FTP ancestral, y la civilización tecnológica ha despertado de su letargo.

