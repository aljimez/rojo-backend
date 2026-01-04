Este proyecto es el backend para una aplicación de reservas de menús en un restaurante a través de un bot de Telegram. El backend está desarrollado en Node.js y utiliza MongoDB como base de datos.

He reorganizado y mejorado la documentación para ofrecer una guía clara de instalación, configuración y ejecución.

## Requisitos ⚙️

- Node.js v14 o superior
- MongoDB (local o en la nube)
- Token del bot de Telegram

## Instalación y configuración 🚀

1. Clona el repositorio:

```bash
git clone <URL_del_repositorio>
cd rojo-backend
```

2. Instala dependencias:

```bash
npm install
```

3. Crea y configura un archivo `.env` en la raíz del proyecto (nunca subas este archivo al repositorio):

```env
TELEGRAM_BOT_TOKEN="<TU_TOKEN_AQUI>"
MONGODB_URI="mongodb://localhost:27017/tu_basedatos"
PORT=3000
```

> **Importante:** sustituye `<TU_TOKEN_AQUI>` por el token real de tu bot y añade `.env` a `.gitignore`.

## Conexión con MongoDB

Ejemplo de conexión con Mongoose (ya presente en el código):

```javascript
const mongoose = require("mongoose");
require("dotenv").config();

mongoose
  .connect(process.env.MONGODB_URI, {
    useNewUrlParser: true,
    useUnifiedTopology: true,
  })
  .then(() => console.log("Conexión exitosa a MongoDB"))
  .catch((err) => console.error("Error conectando a MongoDB:", err));
```

## Ejecución ▶️

- Desarrollo (con recarga automática):

```bash
npm run dev
```

- Producción:

```bash
node index.js
```

> Si prefieres, añade un script `start` en `package.json` con `"start": "node index.js"`.

## Funcionalidades principales

- Recepción y manejo de comandos y mensajes desde Telegram.
- Gestión de reservas de menús por usuario.
- Persistencia de usuarios y reservas en MongoDB.

## Contribuir 🤝

Abre un issue para discutir cambios o envía un PR con mejoras claras y pruebas cuando sea posible.

## Licencia 📄

Licencia: **ISC** (ver `package.json`).

---
