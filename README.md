# llaves-torneo-front

Frontend estático del Torneo LLAVES (un solo `index.html`). Habla con el backend
por HTTP + SSE.

## Configuración (importante)

Abre `index.html` y edita **una línea** cerca del inicio del `<script>`:

```js
const API_BASE = "";
```

- **Local** (back en tu máquina): `"http://localhost:3000"`
- **Railway** (deploy separado): la URL pública del back, ej:
  ```js
  const API_BASE = "https://llaves-torneo-back-production.up.railway.app";
  ```
  Sin barra `/` final.

> No hay env vars en el front: es estático. La URL del back se fija en esa línea.

## Deploy en Railway

1. Pon la URL del back en `API_BASE` y commitea.
2. **New Project → Deploy from GitHub repo** → `llaves-torneo-front`.
3. Railway corre `npm start` (`serve` sirve el estático en `$PORT`).
4. Genera dominio público (Settings → Networking). Esa URL va en `ALLOWED_ORIGIN` del back.

## Cómo se usa

- **Organizador**: botón **🔓 Editar** → mete `ADMIN_KEY` → ya puede crear/editar torneos. Sus cambios se guardan en el back y se empujan a todos.
- **Resto**: entran al link y ven **en vivo** (solo lectura). No necesitan clave.

## Local rápido (sin deploy)

```bash
npm install
PORT=8080 npm start   # abre http://localhost:8080
```
Con el back corriendo en `http://localhost:3000` y `API_BASE` apuntando ahí.
