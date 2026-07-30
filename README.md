# ☕ Sistema de Puntos de Lealtad

## 📌 Descripción

Este módulo implementa un **Sistema de Puntos de Lealtad** para el bot de la cafetería. Cada vez que un usuario realiza un pedido, acumula puntos según el monto total de su compra. Los puntos se almacenan en la hoja **USUARIOS** y pueden consultarse desde el menú principal del bot.

---

## 🎯 Objetivo

Incentivar el uso del bot recompensando a los clientes con puntos de lealtad por cada compra realizada.

---

## ⚙️ Funcionalidades

- Cálculo automático de puntos por cada pedido.
- Actualización del saldo de puntos del usuario.
- Consulta de puntos acumulados desde el menú principal.
- Persistencia de la información en la hoja **USUARIOS**.

---

## 📐 Regla de Negocio

El sistema asigna:

- **1 punto por cada $5.00 gastados.**


## 💾 Persistencia de Datos

Después de confirmar el pedido, el flujo realiza los siguientes pasos:

1. Buscar al usuario mediante su **telegram_id**.
2. Obtener los puntos actuales.
3. Sumar los puntos ganados en la compra.
4. Actualizar el registro en la hoja **USUARIOS**.



## 📂 Estructura de la hoja USUARIOS

| Campo | Descripción |
|--------|-------------|
| telegram_id | Identificador único del usuario en Telegram |
| nombre | Nombre del usuario |
| puntos | Puntos acumulados |

---

## 📱 Menú Principal

Se agregó una nueva opción al menú:

```
1. /menu
2. /pedir
3. /estado
4. /puntos
```

---

## 🏆 Consulta de Puntos

Cuando el usuario selecciona la opción **"/puntos"**, el sistema busca su información en la hoja **USUARIOS** utilizando el **telegram_id** y responde con el siguiente mensaje:

```
Hola [Nombre], actualmente tienes 🏆 [Puntos] puntos acumulados.

¡Sigue comprando para canjear premios!
```

Ejemplo:

```
Hola Vane, actualmente tienes 🏆 100 puntos acumulados.

¡Sigue comprando para canjear premios!
```

---

## 🔄 Flujo del Sistema

```
Pedido confirmado
        │
        ▼
Calcular total de compra
        │
        ▼
Calcular puntos
(total / 5)
        │
        ▼
Buscar usuario por telegram_id
        │
        ▼
Obtener puntos actuales
        │
        ▼
Sumar nuevos puntos
        │
        ▼
Actualizar hoja USUARIOS
        │
        ▼
Confirmar pedido
```

### Consulta de puntos

```
Menú Principal
        │
        ▼
Ver mis Puntos
        │
        ▼
Buscar usuario por telegram_id
        │
        ▼
Obtener puntos
        │
        ▼
Mostrar mensaje al usuario
```

---

## ✅ Tecnologías utilizadas

- Telegram Bot
- n8n
- Google Sheets
- Expresiones JavaScript
- Nodo Set / Edit Fields

---

## 📌 Resultado

Con esta implementación el bot:

- Calcula automáticamente los puntos de cada compra.
- Mantiene actualizado el historial de puntos del usuario.
- Permite consultar los puntos acumulados en cualquier momento.
- Incentiva la fidelización de los clientes mediante un sistema de recompensas.


## IMAGENES
![alt text](image-2.png)

![alt text](image-1.png)

![alt text](image.png)
