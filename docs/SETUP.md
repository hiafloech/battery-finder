# Setup Guide

## Quick Start

### 1. Prerequisites
- Node.js v16+
- PostgreSQL
- Git
- npm or yarn

### 2. Clone the Repository
```bash
git clone https://github.com/hiafloech/battery-finder.git
cd battery-finder
```

### 3. Set Up Backend

```bash
cd backend
npm install
cp .env.example .env
```

Edit `.env` with your PostgreSQL credentials:
```
PORT=5000
DB_HOST=localhost
DB_PORT=5432
DB_NAME=battery_finder
DB_USER=your_db_user
DB_PASSWORD=your_db_password
NODE_ENV=development
```

Create the database:
```bash
createdb battery_finder
psql battery_finder < ../database/schema.sql
```

Start the backend:
```bash
npm run dev
```

Backend should be running on `http://localhost:5000`

### 4. Set Up Frontend

In a new terminal:
```bash
cd frontend
npm install
npm start
```

Frontend should open in your browser at `http://localhost:3000`

## Verify Installation

### Check Backend
```bash
curl http://localhost:5000/api/health
```

You should see:
```json
{"status": "Backend is running!"}
```

### Check Frontend
Visit `http://localhost:3000` in your browser. You should see the Battery Finder welcome page.

## Troubleshooting

### PostgreSQL Connection Error
- Ensure PostgreSQL is running
- Check your `.env` credentials match your PostgreSQL setup
- Verify the database was created: `psql -l | grep battery_finder`

### Port Already in Use
If port 5000 or 3000 is already in use:
- Backend: Change `PORT` in `.env`
- Frontend: Set environment variable: `PORT=3001 npm start`

### Dependencies Installation Failed
Try clearing npm cache:
```bash
npm cache clean --force
rm -rf node_modules package-lock.json
npm install
```

## Next Steps

1. Review the [API Documentation](./API.md)
2. Check the [Database Documentation](./DATABASE.md)
3. Start building features!
4. Read the main [README.md](../README.md) for project overview

## Development Workflow

1. Create a feature branch: `git checkout -b feature/your-feature`
2. Make your changes
3. Test your changes
4. Commit: `git commit -m 'Add your feature'`
5. Push: `git push origin feature/your-feature`
6. Open a Pull Request

Happy coding! 🚗🔋
