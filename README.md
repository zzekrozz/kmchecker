# KM CHECKER PRO

**Vehicle Mileage Verification System**

![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-2.0-green)
![Status](https://img.shields.io/badge/status-Beta-yellow)

---

## 🎯 ¿Qué es KM Checker?

Herramienta profesional de diagnóstico para verificar la **coherencia de kilómetros** en vehículos leyendo múltiples módulos a través del estándar OBD2.

**NO es un detector de fraude mágico.** Es un analizador técnico que compara datos entre módulos del vehículo para detectar inconsistencias sospechosas.

---

## ✨ Características

- ✅ **100% Lectura segura** - Nunca modifica datos
- ✅ **Multi-módulo** - Lee ECU, Tablero, Caja, ABS, Gateway, etc
- ✅ **Análisis coherencia** - Compara km entre módulos
- ✅ **Interfaz profesional** - Diseño tipo Tesla Service / Bosch
- ✅ **WebSerial** - Funciona con USB ELM327 en Chrome/Edge
- ✅ **Simulación** - Testing sin hardware
- ✅ **Multiidioma** - Español, English, Français, Deutsch, Italiano, Português
- ✅ **Gratuito** - Open source
- ✅ **Sin dependencias** - Vanilla JavaScript, funciona offline (excepto conexión OBD2)

---

## 🚀 Quick Start

### **Opción 1: Abrir directamente**
```bash
# Solo necesitas un navegador
# Abre el archivo HTML en Chrome/Edge
open index.html
```

### **Opción 2: Local server**
```bash
# Python 3
python -m http.server 8000

# O Node.js
npx http-server

# Abre: http://localhost:8000
```

### **Opción 3: Deploy en Vercel (Recomendado)**
```bash
# Instala Vercel CLI
npm i -g vercel

# Deploy
vercel
```

**Link resultante:** https://km-checker.vercel.app

---

## 🛠️ Requisitos

### **Hardware:**
- **Adaptador OBD2:** ELM327 USB (€15-30 en Amazon)
  - Modelos recomendados:
    - Vgate iCar Pro 2S
    - ELM327 v2.1+
    - OBDeleven (opcional, más avanzado)

### **Software:**
- **Navegador:** Chrome, Edge, Brave (soportan WebSerial)
- **SO:** Windows, macOS, Linux (donde funcione navegador)

### **Vehículo:**
- Cualquier coche 1996+ con puerto OBD2 (está bajo el volante)
- Algunos vehículos modernos (post-2020) pueden tener acceso restringido

---

## 📖 Cómo Usar

### **Paso 1: Conectar Hardware**
1. Compra adaptador ELM327 USB (€20 Amazon)
2. Conecta al puerto OBD2 del coche (bajo volante, a la izquierda)
3. Enchufa USB a tu PC/laptop

### **Paso 2: Abrir Aplicación**
1. Abre navegador Chrome/Edge
2. Ve a https://km-checker.vercel.app (o archivo HTML local)
3. Selecciona "Puerto Serial (USB)"

### **Paso 3: Seleccionar Puerto**
1. Click "Conectar"
2. Navegador te pide puerto
3. Selecciona COM3, COM5, /dev/ttyUSB0, etc
4. Click "Aceptar"

### **Paso 4: Escanear**
1. Click "Iniciar Escaneo Completo"
2. App muestra: "Escaneando módulos..."
3. Ver progreso visual
4. Tabla con resultados

### **Paso 5: Interpretar Resultados**
```
✅ Accesible = Módulo responde, datos leídos
⚠️ Protegido = Módulo no permite acceso (normal en algunos vehículos)
❌ Sin respuesta = Módulo no responde (puede ser protocolo no soportado)
```

---

## 🎮 Modo Simulación (Sin Hardware)

Para probar sin dispositivo OBD2:

1. Selecciona "Simulación (Demo)"
2. Click "Conectar"
3. Click "Iniciar Escaneo Completo"
4. Ver flujo realista con datos ficticios

**Perfecto para aprender cómo funciona.**

---

## 📊 Interpretar Resultados

### **Coherencia ALTA** ✅
- Todos los módulos accesibles coinciden en km
- ≤ 100 km de diferencia (normal por sincronización)
- **Conclusión:** Vehículo probablemente honesto

### **Coherencia MEDIA** ⚠️
- Pequeñas diferencias entre módulos (100-1.000 km)
- Normal en algunos vehículos (no sincronización perfecta)
- **Conclusión:** Requiere investigación adicional

### **Coherencia BAJA** ❌
- Grandes discrepancias (>1.000 km)
- Módulos no coinciden significativamente
- **Conclusión:** Posible manipulación, requiere pericia profesional

---

## ⚖️ Disclaimer Legal

**IMPORTANTE:**

KM Checker es una herramienta educativa de análisis técnico. 

**NO es:**
- Prueba legal de fraude
- Diagnosis profesional certificada
- Reemplazo de peritaje oficial

**Es:**
- Herramienta informativa
- Análisis técnico educativo
- Complemento a verificación profesional

**Úsalo solo en:**
- Vehículos propios
- Vehículos con autorización del propietario
- Para propósitos educativos

**Para transacciones legales:** Consulta peritos certificados

---

## 🔒 Seguridad & Privacidad

- ✅ **100% offline** - Ningún dato se envía a servidores
- ✅ **Lectura únicamente** - Nunca escribe en el vehículo
- ✅ **Sin login** - No recopila información personal
- ✅ **Sin tracking** - Sin Google Analytics, sin cookies
- ✅ **Open source** - Audita el código

---

## 🛣️ Roadmap

### **v2.0 (Actual)**
- [x] UI profesional
- [x] WebSerial (USB)
- [x] Flujo progresivo
- [x] Simulación realista
- [x] Multiidioma
- [x] Tabla de módulos

### **v2.1 (Próximo)**
- [ ] WebBluetooth (Bluetooth ELM327)
- [ ] Historial de análisis (localStorage)
- [ ] Exportar PDF
- [ ] Detección automática de vehículo por VIN
- [ ] Base de datos de compatibilidad

### **v3.0 (Futuro)**
- [ ] Backend para cloud storage
- [ ] Suscripción PRO
- [ ] Mobile app nativa
- [ ] Soporte para protocolos avanzados (UDS, KWP)
- [ ] IA para análisis de patrones

---

## 🐛 Troubleshooting

### **Problema: "No se detectan puertos seriales"**
```
Soluciones:
1. Verifica ELM327 esté enchufado
2. Instala drivers USB (busca marca de adaptador)
3. Recarga navegador
4. Intenta con otro puerto USB
```

### **Problema: "Conectado pero no detecta módulos"**
```
Soluciones:
1. Enciende el coche (sin arrancar, accesorios ON)
2. Verifica puerto OBD2 esté bien conectado
3. Algunos vehículos necesitan arrancar el motor
4. ELM327 puede ser clone/fallido (compra nuevo)
```

### **Problema: "Algunos módulos sin respuesta"**
```
NORMAL:
- No todos los módulos responden en todos los vehículos
- Depende del modelo, año, protocolo
- Esto NO significa que la app falle
- Es limitación técnica del vehículo
```

### **Problema: "Error: 'navigator.serial is undefined'"**
```
Soluciones:
1. Usa Chrome, Edge o Brave (no Firefox, Safari)
2. Debe ser HTTPS (excepto localhost)
3. Versión navegador actualizada
4. WebSerial es relativamente nuevo
```

---

## 👥 Contribuir

¿Encontraste bug? ¿Tienes mejora?

1. Fork el repo
2. Crea rama: `git checkout -b feature/mejora`
3. Commit: `git commit -m 'Agregué X'`
4. Push: `git push origin feature/mejora`
5. Pull Request

---

## 📧 Soporte

**¿Preguntas?**
- Issues en GitHub
- Discussions en GitHub
- Email: [tu-email]

---

## 📜 License

MIT License - Usa libremente, cita la fuente

---

## 🙏 Agradecimientos

- ELM327 community
- OBD2 protocol documentation
- Todos que reportan bugs y sugieren mejoras

---

## 📈 Estadísticas

- **Vehículos diagnosticados:** [en desarrollo]
- **Usuarios activos:** [en desarrollo]
- **Módulos analizados:** [en desarrollo]

---

## 🎬 Videos & Tutoriales

**Coming soon:**
- Video: "Cómo usar KM Checker"
- Blog: "¿Cómo detectar fraude de odómetro?"
- Tutorial: "Parsear datos OBD2"

---

## 🚀 Status

**Version:** 2.0 Beta  
**Last Update:** 2026-05-19  
**Stability:** Estable para testing

⭐ Si te resultó útil, **star el repo!**

---

## 💡 Pro Tips

1. **Documenta tu coche:** Guarda resultados para comparar después
2. **Múltiples módulos:** Cuantos más módulos, mejor análisis
3. **Vehículos viejos:** Funcionan mejor (menos protección)
4. **Antes de comprar:** Scannea antes de tomar decisión
5. **Con profesional:** Lleva laptop a mecánico para análisis

---

**Hecho con ❤️ para automotive enthusiasts**