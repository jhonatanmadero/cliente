# client

Interfaz web de un chat en vivo, construida con React + Vite. Se conecta al servidor WebSocket de Spring Boot (`ws-server`) para mandar y recibir mensajes en tiempo real.

## Stack

- React 18
- Vite
- WebSocket nativo del navegador (sin librerías externas)

## Funcionalidad

- Pantalla de entrada donde el usuario elige un nombre antes de chatear.
- Mensajes en tiempo real entre todas las pestañas/usuarios conectados.
- Contador de usuarios conectados y estado de conexión (online/offline).
- Indicador de "usuario escribiendo...".
- Animaciones distintas para cada mensaje entrante y fondo animado.

## Requisitos

- Node.js 18 o superior
- El servidor `ws-server` corriendo en `ws://localhost:8080/chat`

## Cómo correrlo

```bash
npm run dev
```

Abre `http://localhost:5173` en el navegador. Prueba abriendo varias pestañas con nombres distintos para ver el chat en tiempo real.

## Estructura

```
src/
├── App.jsx            # Pantalla de username + entrada al chat
├── Chat.jsx            # Interfaz principal del chat
├── Chat.css             # Estilos del chat
└── useWebSocket.js       # Hook que maneja la conexión WebSocket
```

## Configuración

La URL del servidor WebSocket está fija en `useWebSocket.js`:

```js
const WS_URL = 'ws://localhost:8080/chat';
```

Cámbiala si el backend corre en otra dirección o puerto (por ejemplo, en producción).

## Proyecto relacionado

El backend (Spring Boot) que atiende las conexiones WebSocket vive en un repositorio separado: `ws-server/`.