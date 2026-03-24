# 🚀 Real-Time Location Tracker

[![Node.js](https://img.shields.io/badge/Node.js-v20-green)](https://nodejs.org)
[![Express](https://img.shields.io/badge/Express-4.x-blue.svg)](https://expressjs.com/)
[![Socket.IO](https://img.shields.io/badge/Socket.IO-v4-010101.svg)](https://socket.io/)
[![Leaflet](https://img.shields.io/badge/Leaflet-1.9-brightgreen.svg)](https://leafletjs.com/)

## 📄 Description

A real-time collaborative location tracking application built with **Node.js**, **Express**, **Socket.IO**, and **Leaflet.js**. Users can share their live GPS locations in a shared fullscreen map. Perfect for tracking friends, family, or teams in real-time!

Multiple users' positions are displayed as individual markers that update continuously. When a user disconnects, their marker is automatically removed.

## ✨ Features

- 🌍 **Real-time location sharing** via browser Geolocation API (high accuracy)
- 🗺️ **Interactive fullscreen OpenStreetMap** powered by Leaflet.js
- 👥 **Multi-user support** - See everyone’s position with unique markers
- 📡 **WebSocket communication** with Socket.IO for instant updates
- 🎯 **Auto map centering** on location updates
- 🚪 **Automatic cleanup** of disconnected users
- 📱 **Mobile-friendly** responsive design
- ⚡ **No backend storage** - Pure real-time broadcasting

## 📸 Screenshots

<!-- Add screenshots here after running the app -->

```
[Fullscreen map with multiple user markers]
[Real-time marker movement demo GIF]
```

## 🚀 Quick Start

1. **Clone & Install**

   ```bash
   git clone <repo>
   cd Location-Tracker-Nodejs-and-socketio-
   npm install
   ```

2. **Run Development Server**

   ```bash
   npm start
   ```

3. **Open in Browser**

   ```
   http://localhost:8000
   ```

4. **Grant location permission** when prompted
5. **Share the URL** with others to join the map!

## 📱 Usage

1. Open `http://localhost:8000` in multiple browser tabs/devices
2. Allow geolocation access
3. Watch markers appear and move in real-time!
4. Close tab → marker disappears automatically

**Pro Tip:** Test with phone hotspot + mobile browser for real GPS tracking!

## 🛠️ Tech Stack

| Frontend        | Backend          | Real-time | Mapping                    |
| --------------- | ---------------- | --------- | -------------------------- |
| HTML5, EJS      | Node.js, Express | Socket.IO | Leaflet.js + OpenStreetMap |
| JavaScript ES6+ |                  |           | CSS Grid/Flexbox           |

## 🏗️ Architecture

```
Browser (Geolocation API)
    ↓ watchPosition (high accuracy)
Socket.IO Client ───────→ Socket.IO Server (port 8000)
                              ↓ broadcast to all
Leaflet Map ←──── markers ←─ "recive-location" {id, lat, lng}
```

**Socket Events:**

- `send-location`: `{latitude, longitude}`
- `recive-location`: `{id, latitude, longitude}`
- `user-disconnected`: `socket.id`

## 💻 Local Development

```bash
# Install dependencies
npm install

# Development with auto-reload
npm start

# Production
node index.js
```

Server runs on **port 8000**.

## ☁️ Deployment

### Vercel/Heroku

1. Update `package.json` scripts: `"start": "node index.js"`
2. Set `port` to `process.env.PORT || 8000`
3. Deploy!

### Railway/Docker

```
Dockerfile:
FROM node:20-alpine
COPY . .
RUN npm install
EXPOSE 8000
CMD ["node", "index.js"]
```

## 🤝 Contributing

1. Fork the project
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📄 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Socket.IO](https://socket.io) for real-time magic
- [Leaflet](https://leafletjs.com) for amazing maps
- [OpenStreetMap](https://www.openstreetmap.org) for free tiles

---

⭐ **Star this repo if you found it useful!** ⭐
