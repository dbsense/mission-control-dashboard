# 🍄 Mission Control Dashboard

**Psychedelic dark dashboard for OpenClaw Mission Control**

A modern, responsive dashboard designed for ADHD brains - featuring neon accents, dark mode, and real-time data visualization.

![Dashboard Preview](https://raw.githubusercontent.com/dbsense/mission-control-dashboard/main/preview.png)

---

## ✨ Features

- **🎨 Psychedelic Dark Theme** - Neon purples, pinks, cyans, oranges on dark background
- **🍄 Shroom Aesthetic** - Animated glows, mycelium patterns, fungal vibes
- **📊 Six Pillars Visualization** - Your mission control at a glance
- **📱 Responsive Design** - Works on desktop, tablet, mobile
- **⚡ Real-time Updates** - Live data from your OpenClaw instance
- **🎯 ADHD-Optimized** - Low cognitive load, high contrast, clear hierarchy

---

## 🚀 Quick Deploy (Zeabur)

### Option 1: One-Click Deploy

[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/XXXXX)

### Option 2: Manual Deploy

1. **Fork this repo** or use as template
2. **Connect to Zeabur:**
   - Go to [Zeabur Dashboard](https://dash.zeabur.com)
   - Create new project
   - Deploy from GitHub → Select this repo
3. **Add Domain:**
   - Go to service settings → Domains
   - Add your domain or use auto-generated
4. **Done!** Dashboard live in 2 minutes

---

## 🏠 Self-Host (Anywhere)

### Static Hosting (Recommended)
Just serve the `index.html` file:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .

# PHP
php -S localhost:8080
```

### Docker
```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

### Zeabur/Docker Compose
```yaml
version: '3'
services:
  dashboard:
    image: nginx:alpine
    volumes:
      - ./:/usr/share/nginx/html:ro
    ports:
      - "8080:80"
```

---

## ⚙️ Configuration

### Connect to Your OpenClaw Data

Edit the JavaScript in `index.html` to fetch real data:

```javascript
// Example: Fetch from your OpenClaw API
async function loadDashboardData() {
  const response = await fetch('https://your-openclaw-instance/api/dashboard');
  const data = await response.json();
  
  // Update Six Pillars
  document.querySelector('.pillar-finance .stat-value').textContent = data.finance.progress;
  
  // Update charts
  updateCharts(data.activity);
}
```

### Environment Variables

For dynamic configuration, create `config.js`:

```javascript
window.DASHBOARD_CONFIG = {
  apiEndpoint: 'https://your-api.com',
  refreshInterval: 30000, // 30 seconds
  theme: 'dark',
  accentColor: 'purple'
};
```

---

## 🎨 Customization

### Change Colors

Edit CSS variables in `index.html`:

```css
:root {
  --neon-purple: #b829dd;
  --neon-pink: #ff2a6d;
  --neon-cyan: #05d9e8;
  --neon-orange: #ff6b35;
  --neon-green: #39ff14;
}
```

### Add New Widgets

Copy existing card structure:

```html
<div class="data-card">
  <h3>Your Widget Title</h3>
  <!-- Your content -->
</div>
```

---

## 🔌 Integration

### OpenClaw Integration

This dashboard is designed to work with [OpenClaw](https://openclaw.ai) but can display any data source.

**Data Sources:**
- SQLite databases (finance, trades, flows)
- REST APIs
- WebSocket streams
- Static JSON files

### Example: Connect to Your Data

```javascript
// Fetch from your databases
const financeDB = '/path/to/unified_banking.db';
const tradesDB = '/path/to/trades.db';

// Use sql.js or API to query
// Update dashboard elements
```

---

## 📱 Mobile App

Install as PWA (Progressive Web App):

1. Open dashboard on mobile browser
2. Tap "Add to Home Screen"
3. Works like native app

---

## 🛠️ Development

### Local Development

```bash
git clone https://github.com/dbsense/mission-control-dashboard.git
cd mission-control-dashboard
python3 -m http.server 8080
# Open http://localhost:8080
```

### Structure

```
.
├── index.html          # Main dashboard (single file!)
├── README.md           # This file
└── .github/
    └── workflows/      # CI/CD (optional)
```

---

## 🤝 Contributing

1. Fork the repo
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request

---

## 📜 License

MIT - Feel free to use, modify, distribute.

---

## 🍄 Credits

**Designed for:** db & Shroom  
**Style:** Psychedelic dark with neon accents  
**Inspiration:** Freepik dashboard designs + fungal aesthetics

**Built with:** HTML5, CSS3, Vanilla JS (no frameworks!)

---

## 🔗 Links

- **Live Demo:** [demo.mission-control.sh](https://demo.mission-control.sh)
- **Main Project:** [shroom-memory](https://github.com/dbsense/shroom-memory)
- **OpenClaw:** [openclaw.ai](https://openclaw.ai)
- **Zeabur:** [zeabur.com](https://zeabur.com)

---

**The mycelium spreads. 🍄**
