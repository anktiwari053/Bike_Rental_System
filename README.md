# 🏍️ Bike Rental System

Lightweight bike rental web application built with Node.js, Express, MongoDB and EJS. Users can browse and book bikes; admins can manage bikes, users and bookings. This README explains setup, environment variables, available scripts and key routes.

---

**Quick status**

- Local server: `server.js` (Express)
- DB: MongoDB (mongoose)
- Views: EJS templates in `views/`

---

**Prerequisites**

- Node.js v16+ or newer
- MongoDB running locally or a MongoDB Atlas connection string
- (Optional) Cloudinary account for image uploads

---

## Setup

1. Install dependencies

```bash
npm install
```

2. Create a `.env` file at the project root (see example below) and set environment variables.

Example `.env`:

```
MONGO_URI=mongodb://127.0.0.1:27017/bike_rental
PORT=5000
# Optional Cloudinary vars used by `config/cloudinary.js`
CLOUD_NAME=your_cloud_name
CLOUD_API_KEY=your_api_key
CLOUD_API_SECRET=your_api_secret
```

3. Start the app (development)

```bash
npm run dev   # or use: nodemon server.js
```

Start (production)

```bash
npm start
```

---

## Environment variables

- `MONGO_URI` — MongoDB connection string (required)
- `PORT` — Server port (default `5000`)
- `CLOUD_NAME`, `CLOUD_API_KEY`, `CLOUD_API_SECRET` — Cloudinary credentials (optional)

The project expects `MONGO_URI` (see `config/db.js`) — ensure your `.env` uses that key.

---

## Project structure

- `server.js` — App entry
- `config/` — DB and Cloudinary config
- `controllers/` — Request handlers
- `models/` — Mongoose models: `Bike`, `User`, `Booking`
- `routes/` — Express routes
- `views/` — EJS templates
- `public/` — Static assets (CSS)

---

## Useful scripts

- `npm run dev` — Run with `nodemon` for development
- `npm start` — Start the server with `node server.js`

Check `package.json` for exact script names.

---

## Important routes (overview)

- `/` — Home page (browse bikes)
- `/auth/*` — Signup / Login routes
- `/bikes/*` — Bike listing, details, booking
- `/admin/*` — Admin dashboard and bike management

See the route files in `routes/` for full details.

---

## Troubleshooting

- If you see: `The \`uri\` parameter to \`openUri()\` must be a string, got "undefined"` — ensure `MONGO_URI` is set in your `.env` and `config/db.js` uses `process.env.MONGO_URI`.
- If port `5000` is already in use, stop the process using that port or change `PORT` in `.env`.

---

## Contributing

1. Fork the repo
2. Create a feature branch
3. Open a PR with a clear description

---

## License

This project is open-source. Add a license if desired.

---

If you'd like, I can also add a short `CONTRIBUTING.md` or expand the routes list with exact endpoints from the `routes/` files.
