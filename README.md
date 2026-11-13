# Weekly To-Do

MERN to-do app: tasks grouped by week (Mon–Sun) with open/completed counts, plus create, edit, delete and search.

React + Tailwind frontend (`client`), Express + Mongoose API (`server`). On Netlify the API runs as a function, so one site serves both.

## Run locally

```bash
npm install
cp server/.env.example server/.env   # point MONGODB_URI at your MongoDB
npm run dev                          # API on :5000 and app on :5173 together
```

The app proxies `/api` to the API, so open http://localhost:5173.

## API

| Method | Path | Notes |
| --- | --- | --- |
| GET | `/api/tasks` | all tasks, sorted by date |
| POST | `/api/tasks` | `title` and `dueAt` required |
| PUT | `/api/tasks/:id` | partial update, also used for status |
| DELETE | `/api/tasks/:id` | |

## Deploy (Netlify)

1. Create a free MongoDB Atlas cluster and copy its connection string (add `/todo` as the database name).
2. Push this repo to GitHub, then on Netlify choose Add new site, Import from Git.
3. Build settings come from `netlify.toml`, nothing to fill in.
4. Add the environment variable `MONGODB_URI` with the Atlas string, then deploy.
