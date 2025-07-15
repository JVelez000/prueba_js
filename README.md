# Event SPA

A Single Page Application (SPA) for event management where administrators can create, edit, and delete events, and users can browse and purchase tickets. The application uses `Bulma` for UI, `JSON Server` as a fake REST API, and `npx serve` to host the static frontend.

## 📁 Project Structure

```
├── public/
│   ├── index.html
│   └── ...
├── views/
│   ├── login.js
│   ├── register.js
│   ├── home.js
│   └── create_event.js
├── components/
│   ├── aside_bar.js
│   └── event_cards.js
├── api/
│   └── api.js
└── db.json
```

## ⚙️ Features

- Admin login with session persistence
- Admin dashboard with event creation, editing, and deletion
- Users can view available events and purchase tickets
- Sidebar navigation
- Route handling with `window.location.hash`
- Role-based access control (admin/user)
- Responsive UI using Bulma CSS

### Prerequisites

- Node.js installed
- `json-server` and `serve` installed globally or via `npx`

### Setup

1. Clone this repo or download the source files.
2. Open a terminal in the project root.

### Start JSON Server

```bash
npx json-server --watch db.json --port 3000
```

This will run a RESTful API server on `http://localhost:3000`.

### Start Static Server

```bash
npx serve public -l 5500
```

This will serve the frontend from the `public/` directory on `http://localhost:5500`.

## 🔐 Protected Routes

- `#login` & `#register`: Public
- `#home`: Drotected
- `#create_event`: Protected (available only for admin)

The router redirects reaading the information of the
 `localStorage`.
---

## ✅ Extras

- Buttons edit & delete only visible for Admin.
- Events `out of stock` can't be bought.
- Basic validation of visual errors and forms

---

## 🧪 Example API (`db.json`)
```json
{
  "users": [],
  "events": []
}
```

## 🧠 Notes

- SPA uses hash routing (`#home`, `#login`, etc.)
- Session data is stored in `localStorage`
- Only admins can access `#create_event`
- All events are fetched from `/events` endpoint

## 👨‍💻 Author

**Jeims Emmanuel Vélez Echavarría**
