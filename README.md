# 🧮 Calculadora — Vanilla JS

Calculadora web construida con HTML, CSS y JavaScript puro — sin frameworks, sin librerías, sin dependencias. Lista para abrir en el navegador.

## ✨ Características

- **Operaciones básicas** — suma, resta, multiplicación y división
- **Funciones extra** — porcentaje (`%`) y cambio de signo (`+/−`)
- **Encadenamiento de operaciones** — calcula sin necesidad de presionar `=` entre cada paso
- **Historial** — muestra las últimas 5 operaciones realizadas
- **Soporte de teclado** — completamente operable sin mouse
- **Animaciones** — micro-interacciones en botones y resultado
- **Guard de división por cero** — manejo de error amigable
- **Sin ruido flotante** — `0.1 + 0.2` da `0.3`, no `0.30000000000000004`

## ⌨️ Atajos de teclado

| Tecla | Acción |
|---|---|
| `0 – 9` | Ingresar dígito |
| `.` | Punto decimal |
| `+ - * /` | Operador |
| `Enter` o `=` | Calcular resultado |
| `Escape` | Limpiar todo (AC) |
| `Backspace` | Borrar último dígito |

## 🚀 Cómo usar

No requiere instalación ni servidor. Solo clona y abre:

```bash
git clone https://github.com/TU_USUARIO/calculadora.git
cd calculadora
open calculator.html       # macOS
start calculator.html      # Windows
xdg-open calculator.html   # Linux
```

## 📁 Estructura del proyecto

```
calculadora/
├── calculator.html   # Todo en un solo archivo (HTML + CSS + JS)
└── README.md
```

## 🛠️ Stack tecnológico

| Capa | Tecnología |
|---|---|
| Estructura | HTML5 semántico |
| Estilos | CSS3 (variables, Grid, animaciones) |
| Lógica | JavaScript ES6+ |
| Tipografía | Google Fonts — DM Mono + Syne |

## 🧠 Cómo funciona

La calculadora usa una máquina de estados simple con tres variables:

```js
let curr  = '0';    // valor visible en pantalla
let prev  = null;   // operando guardado antes del operador
let op    = null;   // operación pendiente (+, −, ×, ÷)
let fresh = false;  // si el próximo dígito reemplaza el display
```

**Flujo de una operación:**

```
input('3') → curr = '3'
setOp('+') → prev = '3', op = '+'
input('5') → curr = '5'
calculate() → res = 3 + 5 = 8 → curr = '8'
```

**Encadenamiento:** si se presiona un operador mientras hay uno pendiente, se calcula primero el resultado antes de guardar el nuevo operador.

**Precisión flotante:** se usa `.toPrecision(10)` y `parseFloat()` para eliminar el ruido de la aritmética de punto flotante en JavaScript.

## 📄 Licencia

MIT — libre para usar, modificar y distribuir.

---

*Hecho con HTML, CSS y JS puro · Sin dependencias · Open Source*
