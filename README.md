# Adminka — Vue 2 Admin Dashboard Template

A simple and lightweight **admin dashboard** built using **Vue 2**, **Element UI**, **Vue Router**, and **V-Calendar**.  
It provides a clean sidebar layout, multiple routed pages, and base styling for building admin interfaces or internal tools.

---

## 🧭 Quick Start

```bash
# 1. Install dependencies
npm install

# 2. Start development server
npm run serve

# 3. Build for production
npm run build

# 4. Lint & fix files
npm run lint
```

**Recommended Environment**
- Node.js 14–18  
- npm 6+

---

## 📦 Technologies Used

- **Vue 2.6** — reactive front-end framework  
- **Vue Router 3.5** — page routing system  
- **Element UI 2.15** — UI component library  
- **V-Calendar 2.3** — date and calendar UI  
- **core-js** — JavaScript polyfills  

---

## 🗂 Project Structure

```plaintext
template-adminka-master/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── App.vue
│   ├── main.js
│   ├── rourter.js
│   ├── assets/
│   │   ├── logo.png
│   │   └── title.png
│   ├── styles/
│   │   ├── base.css
│   │   ├── index.css
│   │   └── reset.css
│   └── views/
│       ├── AUTHORIZATION.vue
│       ├── Fingerprints.vue
│       ├── all_users.vue
│       ├── cards.vue
│       ├── chart.vue
│       ├── guest.vue
│       ├── real_time.vue
│       ├── report.vue
│       ├── statistics.vue
│       └── vacation.vue
├── package.json
├── package-lock.json
├── babel.config.js
└── README.md
```

---

## 🔗 Routing

The routes are defined inside **src/rourter.js** (typo intended in original template).  
You can rename it to **router.js** if you want, and update imports accordingly.

### Example Main Route Structure

- `/` — Main layout with sidebar  
- `/statistics` — Dashboard view (default page)  
- `/realtime` — Real-time monitoring  
- `/report` — Reports section  
- `/cards` — Cards management  
- `/chart` — Charts and graphs  
- `/guest` — Guest management  
- `/All_users` — All users list  
- `/vacation` — Vacations  
- `/Fingerprints` — Fingerprint data  
- `/authorization` — Login page  

**Default redirect** happens inside `App.vue`:

```js
mounted() {
  this.$router.push('/statistics')
}
```

---

## 🧩 Views & Layout

- **statistics.vue** — Main layout with sidebar menu  
- **AUTHORIZATION.vue** — Login/authorization screen  
- **real_time.vue** — Real-time data page  
- **report.vue** — Report generation view  
- **cards.vue** — Card overview section  
- **chart.vue** — Chart and analytics view  
- **guest.vue** — Guest management interface  
- **all_users.vue** — List of all users  
- **vacation.vue** — Vacation management  
- **Fingerprints.vue** — Fingerprint management  

---

## 🎨 Styling

All global CSS is located inside **src/styles/**.

### Files

- `reset.css` — resets browser defaults  
- `base.css` — base theme, spacing, and utility classes  
- `index.css` — main file importing both base and reset  

To customize the look, modify `index.css` or add new component styles.

**Example (from App.vue):**

```css
body {
  background-color: #16181C;
  color: #fff;
  font-family: "Poppins", sans-serif;
}
```

**Element UI Theme:**

```js
import 'element-ui/lib/theme-chalk/index.css';
```

You can override these in your custom CSS or build a theme via Element CLI.

---

## ➕ Adding a New Page

1. **Create** a new `.vue` file inside `src/views/`, for example:  
   `src/views/settings.vue`

2. **Register** the route in `src/rourter.js`:

   ```js
   import settings from './views/settings.vue';
   { path: '/settings', component: settings }
   ```

3. **Add** it to the sidebar inside `statistics.vue`:

   ```html
   <router-link to="/settings">
     <div class="category-cont">
       <i class="ri-settings-3-line"></i>
       <span>Settings</span>
     </div>
   </router-link>
   ```

---

## 🔧 Scripts

| Command | Description |
|----------|-------------|
| `npm run serve` | Starts development server |
| `npm run build` | Builds production bundle in `/dist` |
| `npm run lint` | Runs ESLint to fix formatting issues |

---

## 🚀 Deployment

1. Build the app:

   ```bash
   npm run build
   ```

2. Deploy the `/dist` folder to your hosting (Netlify, Vercel, Nginx, etc.)

3. For history mode, make sure your server redirects all unknown routes to `index.html`.

**Example (Nginx config):**

```nginx
location / {
  try_files $uri $uri/ /index.html;
}
```

---

## 🧰 Common Pitfalls

- Rename `rourter.js` to `router.js` for a cleaner structure.  
- If you see **404 errors** after deployment — check your history mode redirect.  
- You can **localize Element UI** by adding locale configuration.  
- V-Calendar components use `<vc-calendar>` and `<vc-date-picker>` tags.

---

## 📚 Useful Links

- [Vue.js Docs](https://v2.vuejs.org/)  
- [Vue Router](https://router.vuejs.org/)  
- [Element UI](https://element.eleme.io/)  
- [V-Calendar](https://vcalendar.io/)

---

## 📝 Changelog

**v0.1.0**
- Initial release of Adminka template  
- Added base routes, sidebar, Element UI integration  
- Includes sample pages and styles
