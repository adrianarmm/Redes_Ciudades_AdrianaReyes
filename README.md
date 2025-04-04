# Redes_Ciudades_AdrianaReyes
# 🧠 Parte I: Conceptos y Teoría

## 🏺 1. El Mural de las Siete Capas

### 🗿 Inscripción
En la cámara principal del templo se alza un gran mural compuesto por siete franjas horizontales. Los antiguos sabios grabaron símbolos que representan las etapas del viaje que realiza un mensaje digital. Comprendían que toda comunicación debía atravesar una secuencia ritual de transformaciones para alcanzar su destino.

### 🔍 Interpretación moderna: El Modelo OSI
El mural hace referencia al **Modelo OSI** (Open Systems Interconnection), un modelo de referencia de siete capas que define cómo se comunican los dispositivos en una red.

| Capa Nº | Nombre                      | Descripción técnica                                                                 |
|--------|------------------------------|--------------------------------------------------------------------------------------|
| 7      | Capa de Aplicación           | Interfaz directa con el usuario y las aplicaciones. Ej: HTTP, FTP, SMTP.            |
| 6      | Capa de Presentación         | Traduce y codifica los datos: cifrado, compresión, conversión de formato.           |
| 5      | Capa de Sesión               | Controla sesiones entre aplicaciones: apertura, gestión y cierre.                   |
| 4      | Capa de Transporte           | Asegura la entrega confiable y ordenada de los datos. Ej: TCP, UDP.                 |
| 3      | Capa de Red                  | Encargada del direccionamiento lógico y el enrutamiento. Ej: IP.                    |
| 2      | Capa de Enlace de Datos      | Forma tramas, controla errores y direcciona mediante direcciones MAC.               |
| 1      | Capa Física                  | Transmite bits por medios físicos: señales eléctricas, ópticas o inalámbricas.      |

📘 **Importancia**: Este modelo permite entender y diseñar redes de forma modular, facilitando la interoperabilidad entre sistemas distintos.

---

## 📜 2. Los Dos Pergaminos del Mensajero

### 🗿 Inscripción
Dos rituales quedaron registrados en la piedra:
- El **Mensajero Confiable**: realiza una triple señal con el receptor, entrega el mensaje, y espera confirmación.
- El **Mensajero Veloz**: no espera, lanza su mensaje sin confirmar la recepción.

### 🔍 Interpretación moderna: TCP vs UDP

| Característica              | TCP (Mensajero Confiable)           | UDP (Mensajero Veloz)             |
|----------------------------|-------------------------------------|-----------------------------------|
| Conexión previa            | Sí                                  | No                                |
| Control de errores         | Sí                                  | No                                |
| Retransmisión de paquetes  | Sí                                  | No                                |
| Orden garantizado          | Sí                                  | No                                |
| Latencia                   | Mayor                               | Menor                             |
| Uso típico                 | Web, Email, FTP                     | Video en vivo, Juegos online      |

🔍 **Conclusión**: TCP se usa cuando se necesita fiabilidad; UDP, cuando se requiere velocidad. La elección depende del contexto de la aplicación.

---

## 🧱 3. El Enigma de las Subredes

### 🗿 Inscripción
> "Nuestro reino digital tenía la dirección sagrada 192.168.50.0.  
> Los cuatro grandes gremios exigían su propio distrito en la red."

### 🔍 Interpretación moderna: Subnetting (Datos genéricos)

**Objetivo**: Dividir la red 192.168.50.0 en 4 subredes de igual tamaño.

### Cálculo:

1. **Red original**: 192.168.50.0 → Clase C → Máscara por defecto: /24 (255.255.255.0)
2. **Bits adicionales necesarios**: 2 (porque 2² = 4 subredes)
3. **Nueva máscara**: /26 = 255.255.255.192
4. **Direcciones por subred**: 2⁶ = 64 direcciones → 62 válidas para hosts

### Resultado:

| Subred Nº | Rango de hosts utilizables       | Dirección de red | Broadcast         |
|-----------|----------------------------------|------------------|-------------------|
| 1         | 192.168.50.1 – 192.168.50.62     | 192.168.50.0     | 192.168.50.63     |
| 2         | 192.168.50.65 – 192.168.50.126   | 192.168.50.64    | 192.168.50.127    |
| 3         | 192.168.50.129 – 192.168.50.190  | 192.168.50.128   | 192.168.50.191    |
| 4         | 192.168.50.193 – 192.168.50.254  | 192.168.50.192   | 192.168.50.255    |

📘 Esto permite asignar una subred por gremio, optimizando la asignación IP.

---

## 🔀 4. La Encrucijada de las Rutas

### 🗿 Inscripción
Un tótem sagrado con flechas, algunas talladas en piedra y otras móviles, guiaba a los antiguos datos por los caminos adecuados.

### 🔍 Interpretación moderna: Tabla de enrutamiento

Un **router** mantiene una tabla con rutas a distintas redes. Cada entrada especifica:

- Red de destino
- Máscara de subred
- Next hop (siguiente salto)
- Interfaz de salida

### Tipos de enrutamiento:

| Tipo de Ruta      | Simbolismo         | Descripción                                                |
|-------------------|--------------------|------------------------------------------------------------|
| Estática          | Flechas talladas   | Configuradas manualmente, no cambian sin intervención      |
| Dinámica (RIP/OSPF)| Flechas móviles    | Aprendidas automáticamente, se adaptan a cambios en la red |

🔁 La tabla se consulta por cada paquete. Si no se encuentra ruta específica, se usa una por defecto.

---

## 🛡️ 5. El Guardián de la Máscara Única

### 🗿 Inscripción
> "Cuando un emisario salía, llevaba mi rostro. Nadie vio el suyo.  
> Cuando el mundo respondía, yo le devolvía el mensaje original."

### 🔍 Interpretación moderna: NAT (Network Address Translation)

**NAT** permite que múltiples dispositivos con IPs privadas accedan a Internet usando una **única IP pública**.

### ¿Cómo funciona?

- El router reemplaza la IP privada del host por su propia IP pública al enviar el paquete.
- Mantiene una tabla con cada conexión.
- Al llegar la respuesta, la IP pública se sustituye nuevamente por la del host interno correspondiente.

### Beneficios:

| Ventaja                  | Explicación                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| Conservación de IPs      | Reduce la necesidad de múltiples direcciones IPv4 públicas                 |
| Seguridad                | Oculta las direcciones internas, dificultando ataques directos             |

🔐 NAT actúa como el **guardián de las máscaras**, gestionando las identidades en la frontera entre el mundo interno y externo.

---

## 🏁 Conclusión

Has recorrido las cámaras del templo digital, descifrando los secretos del **Modelo OSI**, los rituales de transporte, los misterios de las subredes, las rutas ocultas del enrutamiento y el poder del guardián NAT.  
Cada enigma resuelto te acerca a restaurar por completo el conocimiento ancestral de las redes.

🧭 ¡Ahora estás listo para adentrarte en la segunda parte: la restauración práctica de la red perdida en Cisco Packet Tracer!

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

## 🔐 Extra: Servidor FTP para Reliquias Digitales

| IP              | Servicio | Resultado desde Browser               |
|-----------------|----------|----------------------------------------|
| 192.168.40.100  | FTP      | ✅ Se muestran archivos en el navegador |

💡 Puedes acceder al servidor FTP con éxito ingresando  
`ftp://192.168.40.100`  
desde la aplicación **Web Browser** en cualquier PC de la red.

---

## 📶 Comprobación de Pings

| Desde         | Hacia           | Resultado |
|---------------|------------------|-----------|
| Habitante A1  | Habitante B1     | ✅        |
| Habitante B2  | Servidor FTP     | ✅        |
| Habitante C   | Habitante A2     | ✅        |
| A1            | 192.168.30.2     | ✅        |

---

## 🏷️ Etiquetas Narrativas

| Dispositivo      | Etiqueta Narrativa                        |
|------------------|-------------------------------------------|
| TorreA           | Gran Torre de la Sabiduría                |
| TorreB           | Bastión de los Mensajeros del Sur         |
| Servidor FTP     | Archivo Sagrado de Reliquias Digitales    |
| Enlace WAN       | Ruta Sagrada de Datos                     |
| Habitante C      | Viajero de Territorios Olvidados          |

---

## 🔧 Extras implementados: Reliquias restauradas más allá del mandato

- ✅ **Servidor FTP operativo con Web Browser**
- ✅ **Cliente remoto (Habitante C) desde red adicional**
- ✅ **Enlace WAN probado y funcional con subred /30**
- ✅ **Etiquetas narrativas visibles en el mapa de Packet Tracer**
- ✅ **Ping exitoso entre todas las subredes**
- ✅ **Accesos a servidor FTP desde cualquier host**
- ✅ **Direcciones estáticas en routers para todo el tráfico**
- ✅ **ACL simulando control de acceso ancestral**


# 🏰 Ejercicio 2: La Ciudad de las Redes Aisladas

## ✨ Narrativa
En lo más profundo de las ruinas de la metrópolis ancestral, descubriste una organización social compuesta por gremios que usaban canales sagrados para comunicarse sin interferencias.  
Gracias a la reactivación del antiguo enrutador del consejo —la Gran Torre Central— y a la reconfiguración del sistema de caminos (Switches y VLANs), estos gremios pueden volver a intercambiar conocimientos.

Has restaurado una arquitectura basada en VLANs y router-on-a-stick, lo que permite que los gremios se comuniquen de manera controlada, manteniendo su autonomía, pero ahora bajo una infraestructura interconectada y eficiente.

---

## 🗺️ Topología (descripción)

![image](https://github.com/user-attachments/assets/3433b272-7bbb-4730-abc5-262a176e87bc)


## 📐 Direccionamiento IP

### VLANs de los Gremios

| Gremio         | VLAN | Red IP           | Gateway         |
|----------------|------|------------------|-----------------|
| Arquitectos    | 10   | 192.168.10.0/24  | 192.168.10.1    |
| Escribas       | 20   | 192.168.20.0/24  | 192.168.20.1    |
| Alquimistas    | 30   | 192.168.30.0/24  | 192.168.30.1    |
| Historiadores  | 40   | 192.168.40.0/24  | 192.168.40.1    |
| Administración | 99   | 192.168.99.0/24  | 192.168.99.1    |

---

## ⚙️ Configuración de la Gran Torre Central (Router)

```bash
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0
!
interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
!
interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0
!
interface GigabitEthernet0/0.40
 encapsulation dot1Q 40
 ip address 192.168.40.1 255.255.255.0
!
interface GigabitEthernet0/0.99
 encapsulation dot1Q 99
 ip address 192.168.99.1 255.255.255.0
!
interface GigabitEthernet0/0
 no shutdown
```
## 📧 Servidor de Correos (mail.ciudadperdida.com)

- **Dirección IP**: `192.168.99.200`  
- **VLAN**: 99 (Administración)  
- **Servicios habilitados**:
  - SMTP
  - POP3
  - DNS (resuelve dominio `ciudadperdida.com`)

### 📥 Cuentas de correo configuradas:

- `arquitecto1@ciudadperdida.com`
- `arquitecto2@ciudadperdida.com`
- `escriba1@ciudadperdida.com`
- `alquimista1@ciudadperdida.com`
- `historiador1@ciudadperdida.com`

💡 **Todos los mensajes se intercambian correctamente** a través del cliente de correo integrado en los PCs de cada gremio.

---

## 📶 Comprobación de Conectividad

| Desde         | Hacia                | Resultado |
|---------------|----------------------|-----------|
| Arquitecto1   | Escriba1             | ✅        |
| Alquimista1   | Historiador1         | ✅        |
| Todos los PCs | Servidor de Correos  | ✅        |

---

## 🏷️ Etiquetas Narrativas en la Topología

| Dispositivo       | Nombre Narrativo                        |
|-------------------|------------------------------------------|
| Router            | Gran Torre Central del Consejo           |
| Switch Central    | Núcleo de Convergencia de Gremios        |
| Server            | Altar del Saber Administrativo           |
| VLANs             | Canales Sagrados                         |

---

## ✅ Extras Añadidos

- ✅ **Router-on-a-stick** con 5 subinterfaces activas para VLANs
- ✅ **Servidor de correo SMTP/POP3 funcional** con dominio ficticio
- ✅ **DNS resuelve correctamente** `mail.ciudadperdida.com`
- ✅ **Etiquetas narrativas personalizadas** en el diseño gráfico de Packet Tracer
- ✅ **Comprobación de conectividad con éxito**: `ping`, `Web Browser`, `Correo electrónico`
- ✅ **Configuración IP estática + gateway correcto en cada gremio**
