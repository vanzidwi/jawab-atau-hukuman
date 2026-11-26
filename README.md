# JAWAB ATAU HUKUMAN!

Multiplayer 3D Party Game berbasis HTML5, Three.js, Express.js, dan Socket.IO.

## Catatan Penting Deploy di Vercel

Vercel menggunakan *Serverless Functions* yang **tidak mendukung koneksi WebSocket persisten (Socket.IO) dan state *in-memory*** antar-request.
Oleh karena itu, arsitektur deployment terbaik dan siap pakai yang sudah dikonfigurasi di repo ini adalah:
1. **Frontend (Vite + Three.js)** → Deploy ke **Vercel** (`vercel.json` sudah tersedia).
2. **Backend (Node.js + Express + Socket.IO)** → Deploy ke **Render**, **Railway**, atau **Fly.io** (`render.yaml` & `Dockerfile` sudah tersedia).

### Langkah Deploy
1. **Deploy Backend (Render/Railway):**
   - Hubungkan repo ke Render (otomatis membaca `render.yaml`) atau Railway (`Dockerfile` / `npm start`).
   - Catat URL backend, misalnya: `https://jawab-atau-hukuman-server.onrender.com`.
2. **Deploy Frontend (Vercel):**
   - Import repo ke Vercel (otomatis membaca `vercel.json`).
   - Tambahkan Environment Variable di Vercel:
     - `VITE_SERVER_URL` = `https://jawab-atau-hukuman-server.onrender.com`
   - Klik **Deploy**.

## Menjalankan Secara Lokal

```bash
npm install
npm run dev
```

Buka `http://localhost:5173`.

## Menjalankan Unit Test Logika Game

```bash
node --test server/tests/game-logic.test.js
```
