# Guía de Contribución - KM CHECKER PRO

¡Gracias por tu interés en contribuir! Aquí está cómo hacerlo.

---

## 🤝 Tipos de Contribución

### **1. Reportar Bugs**
Si encuentras un error:

1. Abre un issue con título claro
2. Describe:
   - ¿Qué pasó? (comportamiento actual)
   - ¿Qué debería pasar? (comportamiento esperado)
   - Pasos para reproducir
   - Screenshots/videos si es posible
   - Tu setup (SO, navegador, ELM327, vehículo)

**Ejemplo:**
```
Título: WebSerial timeout en vehículos con protocolo KWP2000

Descripción:
- Coche: BMW 318 2012
- OS: Windows 10
- Navegador: Chrome 120
- ELM327: Vgate iCar Pro

Pasos:
1. Conectar adaptador
2. Seleccionar puerto COM3
3. Click "Iniciar Escaneo"

Resultado: Timeout después de 5 segundos en ECU Motor

Esperado: Debería reintentar o saltarse el módulo
```

### **2. Sugerir Mejoras**
¿Una idea? Abre issue con etiqueta "enhancement":

```
Título: Agregar soporte WebBluetooth

Descripción:
Muchos usuarios tienen ELM327 Bluetooth y no pueden usar 
porque solo soportamos USB. Propongo:

1. Agregar WebBluetooth API
2. Mostrar dispositivos detectados
3. Conectar automáticamente

Esto aumentaría userbase en ~50%
```

### **3. Contribuir Código**

#### **Setup Local**
```bash
# Fork y clonar
git clone https://github.com/TU_USERNAME/km-checker-pro.git
cd km-checker-pro

# Crear rama
git checkout -b feature/mi-mejora

# Hacer cambios
# ... edita archivos ...

# Commit
git commit -m "Agregué X: descripción clara"

# Push
git push origin feature/mi-mejora

# Abrir Pull Request en GitHub
```

#### **Standards de Código**

**JavaScript:**
```javascript
// ✅ BIEN: Nombres claros, comentarios
async function connectToUSB() {
    // Detectar puertos disponibles
    const ports = await navigator.serial.getPorts();
    
    if (ports.length === 0) {
        console.warn('No serial ports found');
        return null;
    }
    
    return ports;
}

// ❌ MAL: Nombres vagos, sin comentarios
async function f1() {
    let x = await navigator.serial.getPorts();
    return x;
}
```

**CSS:**
```css
/* ✅ BIEN: Clases descriptivas, organized */
.module-status {
    display: flex;
    align-items: center;
    gap: 8px;
}

/* ❌ MAL: nombres genéricos, mixed concerns */
.m1 { display: flex; }
```

**HTML:**
```html
<!-- ✅ BIEN: Semántico, ids descriptivos -->
<div id="progressSection" class="progress-section">
    <div id="progressItems"></div>
</div>

<!-- ❌ MAL: divs genéricos, ids vagos -->
<div id="x1">
    <div id="x2"></div>
</div>
```

#### **Commit Messages**
```bash
# ✅ BIEN
git commit -m "feat: Add WebBluetooth support for ELM327"
git commit -m "fix: Prevent timeout loop in slow modules"
git commit -m "docs: Update README with Bluetooth instructions"

# ❌ MAL
git commit -m "fix stuff"
git commit -m "updated"
git commit -m "WIP"
```

---

## 📝 Proceso de Pull Request

1. **Crear fork** del repo
2. **Crear rama** con nombre descriptivo
   - `feature/nombre-feature`
   - `fix/nombre-bug`
   - `docs/nombre-doc`
3. **Hacer cambios** con commits claros
4. **Testear** localmente
5. **Abrir PR** con descripción:
   ```
   ## Descripción
   Qué cambió y por qué
   
   ## Testing
   Cómo testear este cambio
   
   ## Checklist
   - [ ] Código testeado localmente
   - [ ] Sin errores de console
   - [ ] Documentación actualizada
   - [ ] Funciona en Chrome/Edge
   ```
6. **Responder feedback** de mantenedores
7. **Merge** cuando esté aprobado

---

## 🧪 Testing

### **Antes de submitir PR, testea:**

```
[ ] Funciona en Chrome
[ ] Funciona en Edge
[ ] Funciona en localhost
[ ] Sin errores en console (F12)
[ ] UI responsive (mobile)
[ ] Simulación funciona
[ ] WebSerial funciona (si lo tocaste)
[ ] Compatibilidad con navegadores viejos
```

### **Testing Real:**
Si tienes hardware:
```
[ ] Conectar ELM327 USB real
[ ] Testear con 2+ vehículos distintos
[ ] Documentar resultados
```

---

## 📚 Documentación

Si cambias funcionalidad:

1. **Actualiza README.md** si es user-facing
2. **Comenta código complejo:**
   ```javascript
   // Reintentar 3 veces si timeout
   // (algunos módulos responden lentamente)
   for (let retry = 0; retry < 3; retry++) {
       try {
           return await sendCommandWithTimeout(cmd, 2000);
       } catch (e) {
           if (retry === 2) throw e;
       }
   }
   ```
3. **Actualiza CHANGELOG** (si existe)

---

## 🎯 Áreas Donde Se Necesita Ayuda

- [ ] **WebBluetooth** - Soporte para ELM327 Bluetooth
- [ ] **Compatibilidad de vehículos** - Documentar qué funciona donde
- [ ] **Traducción** - Agregar idiomas
- [ ] **Testing** - QA en distintos navegadores
- [ ] **Documentación** - Tutoriales, guides
- [ ] **UX** - Mejoras visuales
- [ ] **Performance** - Optimizaciones
- [ ] **Seguridad** - Audits de código

---

## ❓ Preguntas?

- Abre un issue con tag "question"
- Responderemos ASAP

---

## 📋 Checklist Final

Antes de hacer PR:

- [ ] Lei esta guía
- [ ] Mi código sigue los standards
- [ ] Hice testing local
- [ ] Actualicé documentación
- [ ] No hay cambios sin sentido
- [ ] Commit messages son claros

---

**¡Gracias por contribuir! 🚀**