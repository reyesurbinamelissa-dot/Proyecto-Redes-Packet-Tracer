# Proyecto-Redes-Packet-Tracer


---

# 📋 INSTRUCTIVO DEL PROYECTO POR PERSONA Y ORDEN

---

## 🔗 ENLACES IMPORTANTES (PARA TODOS)

| Recurso | Enlace |
|---------|--------|
| **Google Drive (archivos .pkt)** | https://drive.google.com/drive/folders/1PaEpVzmUqNdhtyv2Y-qw4PbaLgGknbxP?usp=sharing |
| **GitHub (instrucciones)** | (https://github.com/reyesurbinamelissa-dot/Proyecto-Redes-Packet-Tracer/blob/main/README.md) |

> **Nota:** No necesitan cuenta de Google para entrar a la carpeta de Drive. Solo hagan clic en el enlace.

---

# 🥇 SELENA (PRIMERO)

## Lo que debe hacer Selena:

---

### 📥 Paso 1: Descargar el archivo base

1. **Entra al enlace de Google Drive** que está arriba.
2. Busca el archivo **`Proyecto_Base.pkt`**.
3. Haz clic derecho sobre él → selecciona **"Descargar"**.
4. Guárdalo en tu computadora (por ejemplo, en el Escritorio).

---

### 🖥️ Paso 2: Trabajar en Packet Tracer

1. **Abre** el archivo `Proyecto_Base.pkt` en Packet Tracer.
2. **Agrega 3 routers modelo 1841**:
   - Abajo a la izquierda → ícono de router → "1841".
   - Arrástralos 3 veces al área de trabajo.
3. **Renómbralos** (haz clic en cada router → pestaña "Config" → "Display Name"):
   - Router0 → **Panamá**
   - Router1 → **Honduras**
   - Router2 → **Belice**
4. **Agrega 3 PCs**:
   - Abajo a la izquierda → "End Devices" → "PC".
   - Arrástralas 3 veces.
5. **Conecta las PCs con cable naranja "Copper Straight-Through"**:
   - PC Panamá → FastEthernet0 → Router Panamá → FastEthernet0/0
   - PC Honduras → FastEthernet0 → Router Honduras → FastEthernet0/0
   - PC Belice → FastEthernet0 → Router Belice → FastEthernet0/0
6. **Agrega módulos seriales "WIC-2T"**:
   - Apaga cada router (pestaña "Physical" → botón de encendido).
   - Arrastra "WIC-2T" al Slot 0.
   - Enciende el router.
   - **Importante:** Honduras necesita **2 módulos WIC-2T** (uno en Slot 0 y otro en Slot 1).

---

### ⌨️ Paso 3: Configurar IPs en los routers

**Copia y pega esto en la pestaña "CLI" de cada router:**

**Panamá:**
```
enable
configure terminal
hostname Panamá
interface fastEthernet 0/0
ip address 192.168.4.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.18 255.255.255.252
no shutdown
exit
```

**Honduras:**
```
enable
configure terminal
hostname Honduras
interface fastEthernet 0/0
ip address 192.168.5.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.14 255.255.255.252
no shutdown
exit
interface serial 0/0/1
ip address 10.0.0.17 255.255.255.252
no shutdown
exit
interface serial 0/1/0
ip address 10.0.0.21 255.255.255.252
no shutdown
exit
```

**Belice:**
```
enable
configure terminal
hostname Belice
interface fastEthernet 0/0
ip address 192.168.6.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.22 255.255.255.252
no shutdown
exit
```

---

### 💻 Paso 4: Configurar IPs en las PCs

**En cada PC:**
- Clic en la PC → pestaña "Desktop" → "IP Configuration".

| PC | IP | Máscara | Gateway |
|----|----|---------|---------|
| PC Panamá | 192.168.4.10 | 255.255.255.0 | 192.168.4.1 |
| PC Honduras | 192.168.5.10 | 255.255.255.0 | 192.168.5.1 |
| PC Belice | 192.168.6.10 | 255.255.255.0 | 192.168.6.1 |

---

### 📤 Paso 5: Guardar y subir

1. **File** → **Save As** → escribe: **`Proyecto_Base_Selena.pkt`**.
2. Entra al enlace de Google Drive.
3. Haz clic en **"Nuevo"** → **"Subir archivo"** y selecciona el archivo que guardaste.
4. **Avisa a Yoselin** por WhatsApp/Teams que ya subiste tu parte.

✅ **SELENA HA TERMINADO.**

---

# 🥈 YOSELIN (SEGUNDO)

## Lo que debe hacer Yoselin:

---

### 📥 Paso 1: Descargar el archivo de Selena

1. **Entra al enlace de Google Drive.**
2. Busca el archivo **`Proyecto_Base_Selena.pkt`** (el que subió Selena).
3. Haz clic derecho → **"Descargar"**.
4. Guárdalo en tu computadora.

---

### 🖥️ Paso 2: Trabajar en Packet Tracer

1. **Abre** el archivo `Proyecto_Base_Selena.pkt` en Packet Tracer.
2. **Agrega 3 routers 1841** y renómbralos:
   - Router0 → **Costa Rica**
   - Router1 → **Nicaragua**
   - Router2 → **El Salvador**
3. **Agrega 3 PCs** y conéctalas con cable naranja:
   - PC Costa Rica → FastEthernet0 → Router Costa Rica → FastEthernet0/0
   - PC Nicaragua → FastEthernet0 → Router Nicaragua → FastEthernet0/0
   - PC El Salvador → FastEthernet0 → Router El Salvador → FastEthernet0/0
4. **Agrega módulos WIC-2T:**
   - Costa Rica: 1 módulo.
   - Nicaragua: 2 módulos.
   - El Salvador: 1 módulo.

---

### ⌨️ Paso 3: Configurar IPs en los routers

**Costa Rica:**
```
enable
configure terminal
hostname CostaRica
interface fastEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.1 255.255.255.252
no shutdown
exit
```

**Nicaragua:**
```
enable
configure terminal
hostname Nicaragua
interface fastEthernet 0/0
ip address 192.168.2.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.2 255.255.255.252
no shutdown
exit
interface serial 0/0/1
ip address 10.0.0.5 255.255.255.252
no shutdown
exit
interface serial 0/1/0
ip address 10.0.0.9 255.255.255.252
no shutdown
exit
```

**El Salvador:**
```
enable
configure terminal
hostname ElSalvador
interface fastEthernet 0/0
ip address 192.168.3.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.6 255.255.255.252
no shutdown
exit
```

---

### 💻 Paso 4: Configurar IPs en las PCs

| PC | IP | Máscara | Gateway |
|----|----|---------|---------|
| PC Costa Rica | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |
| PC Nicaragua | 192.168.2.10 | 255.255.255.0 | 192.168.2.1 |
| PC El Salvador | 192.168.3.10 | 255.255.255.0 | 192.168.3.1 |

---

### 📤 Paso 5: Guardar y subir

1. **File** → **Save As** → escribe: **`Proyecto_Base_Yoselin.pkt`**.
2. Sube el archivo a Google Drive.
3. **Avisa a Emmanuel** que ya subiste tu parte.

✅ **YOSELIN HA TERMINADO.**

---

# 🥉 EMMANUEL (TERCERO - ÚLTIMO)

## Lo que debe hacer Emmanuel:

---

### 📥 Paso 1: Descargar el archivo de Yoselin

1. **Entra al enlace de Google Drive.**
2. Busca el archivo **`Proyecto_Base_Yoselin.pkt`** (el que subió Yoselin).
3. Haz clic derecho → **"Descargar"**.
4. Guárdalo en tu computadora.

---

### 🖥️ Paso 2: Trabajar en Packet Tracer

1. **Abre** el archivo `Proyecto_Base_Yoselin.pkt` en Packet Tracer.
2. **Agrega 1 router 1841** y renómbralo a **Canadá**.
3. **Agrega 1 PC** y conéctala con cable naranja:
   - PC Canadá → FastEthernet0 → Router Canadá → FastEthernet0/0.
4. **Agrega 2 módulos WIC-2T** a Canadá (uno en Slot 0 y otro en Slot 1).

---

### ⌨️ Paso 3: Configurar IPs en Canadá

```
enable
configure terminal
hostname Canadá
interface fastEthernet 0/0
ip address 192.168.7.1 255.255.255.0
no shutdown
exit
interface serial 0/0/0
ip address 10.0.0.10 255.255.255.252
no shutdown
exit
interface serial 0/0/1
ip address 10.0.0.13 255.255.255.252
no shutdown
exit
```

---

### 💻 Paso 4: Configurar IP en PC Canadá

| PC | IP | Máscara | Gateway |
|----|----|---------|---------|
| PC Canadá | 192.168.7.10 | 255.255.255.0 | 192.168.7.1 |

---

### 🔌 Paso 5: Conectar todos los routers con cable gris "Serial DTE"

**Usa el cable "Serial DTE" (gris con puntas azules):**

| Conexión | Puerto A | → | Puerto B |
|----------|----------|---|----------|
| Costa Rica → Nicaragua | Serial 0/0/0 (CR) | → | Serial 0/0/0 (NIC) |
| Nicaragua → El Salvador | Serial 0/0/1 (NIC) | → | Serial 0/0/0 (SAL) |
| Nicaragua → Canadá | Serial 0/1/0 (NIC) | → | Serial 0/0/0 (CAN) |
| Canadá → Honduras | Serial 0/0/1 (CAN) | → | Serial 0/0/0 (HON) |
| Honduras → Panamá | Serial 0/0/1 (HON) | → | Serial 0/0/0 (PAN) |
| Honduras → Belice | Serial 0/1/0 (HON) | → | Serial 0/0/0 (BEL) |

---

### 🛤️ Paso 6: Configurar rutas estáticas

**Copia y pega esto en CADA router (en la pestaña CLI):**

**Costa Rica:**
```
ip route 192.168.2.0 255.255.255.0 10.0.0.2
ip route 192.168.3.0 255.255.255.0 10.0.0.2
ip route 192.168.4.0 255.255.255.0 10.0.0.2
ip route 192.168.5.0 255.255.255.0 10.0.0.2
ip route 192.168.6.0 255.255.255.0 10.0.0.2
ip route 192.168.7.0 255.255.255.0 10.0.0.2
```

**Nicaragua:**
```
ip route 192.168.1.0 255.255.255.0 10.0.0.1
ip route 192.168.3.0 255.255.255.0 10.0.0.6
ip route 192.168.4.0 255.255.255.0 10.0.0.10
ip route 192.168.5.0 255.255.255.0 10.0.0.10
ip route 192.168.6.0 255.255.255.0 10.0.0.10
ip route 192.168.7.0 255.255.255.0 10.0.0.10
```

**El Salvador:**
```
ip route 192.168.1.0 255.255.255.0 10.0.0.5
ip route 192.168.2.0 255.255.255.0 10.0.0.5
ip route 192.168.4.0 255.255.255.0 10.0.0.5
ip route 192.168.5.0 255.255.255.0 10.0.0.5
ip route 192.168.6.0 255.255.255.0 10.0.0.5
ip route 192.168.7.0 255.255.255.0 10.0.0.5
```

**Panamá:**
```
ip route 192.168.1.0 255.255.255.0 10.0.0.17
ip route 192.168.2.0 255.255.255.0 10.0.0.17
ip route 192.168.3.0 255.255.255.0 10.0.0.17
ip route 192.168.5.0 255.255.255.0 10.0.0.17
ip route 192.168.6.0 255.255.255.0 10.0.0.17
ip route 192.168.7.0 255.255.255.0 10.0.0.17
```

**Honduras:**
```
ip route 192.168.1.0 255.255.255.0 10.0.0.13
ip route 192.168.2.0 255.255.255.0 10.0.0.13
ip route 192.168.3.0 255.255.255.0 10.0.0.13
ip route 192.168.4.0 255.255.255.0 10.0.0.18
ip route 192.168.6.0 255.255.255.0 10.0.0.22
ip route 192.168.7.0 255.255.255.0 10.0.0.13
```

**Belice:**
```
ip route 192.168.1.0 255.255.255.0 10.0.0.21
ip route 192.168.2.0 255.255.255.0 10.0.0.21
ip route 192.168.3.0 255.255.255.0 10.0.0.21
ip route 192.168.4.0 255.255.255.0 10.0.0.21
ip route 192.168.5.0 255.255.255.0 10.0.0.21
ip route 192.168.7.0 255.255.255.0 10.0.0.21
```

**Canadá:**
```
ip route 192.168.1.0 255.255.255.0 10.0.0.9
ip route 192.168.2.0 255.255.255.0 10.0.0.9
ip route 192.168.3.0 255.255.255.0 10.0.0.9
ip route 192.168.4.0 255.255.255.0 10.0.0.13
ip route 192.168.5.0 255.255.255.0 10.0.0.13
ip route 192.168.6.0 255.255.255.0 10.0.0.13
```

---

### 📡 Paso 7: Probar los pings

**En cada PC:**
1. Clic en la PC → "Desktop" → "Command Prompt".
2. Escribe: `ping 192.168.1.10` (para probar Costa Rica).
3. Si sale `! ! ! ! !` es que funciona.

**Pruebas obligatorias:**

| Desde PC | Hacer ping a |
|----------|--------------|
| Costa Rica | 192.168.7.10 (Canadá) |
| Costa Rica | 192.168.6.10 (Belice) |
| Nicaragua | 192.168.4.10 (Panamá) |
| El Salvador | 192.168.5.10 (Honduras) |
| Panamá | 192.168.1.10 (Costa Rica) |
| Honduras | 192.168.3.10 (El Salvador) |
| Belice | 192.168.2.10 (Nicaragua) |
| Canadá | 192.168.4.10 (Panamá) |

---

### 📤 Paso 8: Guardar y subir

1. **File** → **Save As** → escribe: **`Proyecto_FINAL_Emmanuel.pkt`**.
2. Sube el archivo a Google Drive.
3. **Avisa a Selena y Yoselin** que el proyecto está listo.

✅ **EMMANUEL HA TERMINADO. ¡PROYECTO COMPLETADO!**

---

# 📋 RESUMEN DEL FLUJO DE TRABAJO

```
Yoselin sube: Proyecto_Base.pkt
         ↓
Selena descarga: Proyecto_Base.pkt → trabaja → sube: Proyecto_Base_Selena.pkt
         ↓
Yoselin descarga: Proyecto_Base_Selena.pkt → trabaja → sube: Proyecto_Base_Yoselin.pkt
         ↓
Emmanuel descarga: Proyecto_Base_Yoselin.pkt → trabaja → sube: Proyecto_FINAL_Emmanuel.pkt
         ↓
✅ PROYECTO COMPLETADO ✅
```

---

# 🎤 GUÍA PARA LA EXPOSICIÓN

| Persona | Tema a exponer |
|---------|----------------|
| **Selena** | Explica Panamá, Honduras y Belice: cómo los configuró, qué IPs les puso y cómo los conectó. |
| **Yoselin** | Explica Costa Rica, Nicaragua y El Salvador: cómo los configuró, qué IPs les puso y cómo los conectó. |
| **Emmanuel** | Explica Canadá, cómo conectó todos los routers con el cable gris "Serial DTE", cómo configuró las rutas estáticas y demuestra los pings. |

---

**¡LISTO! Con esto cada uno sabe exactamente qué hacer y cuándo. ¡Éxito! 🚀**
