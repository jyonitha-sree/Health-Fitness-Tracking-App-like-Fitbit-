# Health & Fitness Tracking Application

A full-stack application for tracking health and fitness activities, managing tasks with Agile methodology, and viewing comprehensive analytics.

## Project Overview

This application combines health tracking with Agile project management, providing:

- **Activity Tracking**: Log steps, calories, heart rate, sleep, and hydration
- **Task Management**: Kanban-style board with story points and sprints
- **Analytics**: Comprehensive charts and insights
- **Agile Metrics**: Velocity reports, burndown charts, and cumulative flow diagrams

## Tech Stack

### Backend
- **FastAPI** - Modern Python web framework
- **SQLModel** - SQL database ORM with Pydantic integration
- **SQLite** - Development database (PostgreSQL for production)
- **Pydantic** - Data validation

### Frontend
- **React 18** - UI library
- **Vite** - Build tool
- **React Router** - Navigation
- **Axios** - HTTP client
- **Chart.js** - Data visualization
- **Tailwind CSS** - Styling

## Project Structure

```
Health Fit/
├── backend/
│   ├── app/
│   │   ├── main.py              # FastAPI application
│   │   ├── models.py            # Database models
│   │   ├── schemas.py           # Pydantic schemas
│   │   ├── database.py          # Database connection
│   │   ├── routers/             # API endpoints
│   │   │   ├── users.py
│   │   │   ├── activities.py
│   │   │   ├── tasks.py
│   │   │   ├── worklogs.py
│   │   │   ├── sprint.py
│   │   │   ├── analytics.py
│   │   │   └── admin.py
│   │   ├── services/            # Business logic
│   │   │   ├── insights.py
│   │   │   ├── velocity.py
│   │   │   ├── burndown.py
│   │   │   └── cfd.py
│   │   ├── utils/               # Utilities
│   │   └── tests/               # Unit tests
│   ├── requirements.txt
│   └── README.md
│
└── frontend/
    ├── src/
    │   ├── components/          # Reusable components
    │   ├── pages/               # Page components
    │   ├── api.js               # API service layer
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── index.css
    ├── package.json
    ├── vite.config.js
    ├── tailwind.config.js
    └── README.md
```

## Getting Started

### Prerequisites

- Python 3.9+
- Node.js 16+
- npm or yarn

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Start the server:
   ```bash
   uvicorn app.main:app --reload
   ```

5. Access the API documentation:
   - Swagger UI: http://localhost:8000/docs
   - ReDoc: http://localhost:8000/redoc

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create `.env` file:
   ```
   VITE_API_BASE=http://localhost:8000
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```

5. Open your browser to http://localhost:3000

## API Endpoints

### Users
- `POST /users/` - Create user
- `GET /users/` - List users
- `GET /users/{id}` - Get user by ID

### Activities
- `POST /activities/` - Log activity
- `GET /activities/?user_id=` - Get activities
- `GET /activities/summary?user_id=&days=` - Get summary

### Tasks
- `POST /tasks/` - Create task
- `GET /tasks/?story_id=` - Get tasks
- `PUT /tasks/{id}` - Update task
- `POST /tasks/{id}/complete` - Mark task as done

### Worklogs
- `POST /worklogs/` - Log work hours
- `GET /worklogs/?task_id=` - Get worklogs

### Sprints
- `POST /sprints/` - Create sprint
- `GET /sprints/{id}` - Get sprint
- `POST /sprints/{id}/tasks/{task_id}` - Add task to sprint
- `GET /sprints/{id}/summary` - Get sprint summary

### Analytics
- `GET /analytics/summary?user_id=` - Weekly summary
- `GET /analytics/trends?user_id=` - Trend analysis
- `GET /analytics/hr-zones?user_id=` - Heart rate zones
- `GET /analytics/insights?user_id=` - Smart insights
- `GET /analytics/velocity` - Velocity history
- `GET /analytics/burndown?sprint_id=` - Burndown chart
- `GET /analytics/cfd?sprint_id=` - Cumulative flow diagram

### Admin
- `GET /admin/engagement` - User engagement metrics
- `GET /admin/performance` - System performance metrics

## Features

### Activity Tracking
- Log multiple activity types (steps, calories, heart rate, sleep, hydration)
- View activity history
- Visualize trends with charts
- Get weekly summaries

### Task Management
- Create and manage tasks
- Assign story points
- Track task status (To Do, In Progress, Done)
- Set priority levels
- Log work hours

### Sprint Management
- Create sprints with start/end dates
- Assign tasks to sprints
- Track sprint progress
- Generate sprint summaries

### Analytics & Insights
- Weekly activity summaries
- Trend analysis
- Heart rate zone distribution
- Smart insights based on activity data
- Calories in vs out comparison

### Agile Metrics
- Sprint velocity tracking
- Burndown charts
- Cumulative flow diagrams
- Velocity history
- Performance indicators

## Testing

### Backend Tests
```bash
cd backend
pytest
```

### Frontend Tests
```bash
cd frontend
npm run test
```

## Production Deployment

### Backend

1. Update database connection to PostgreSQL in `database.py`
2. Set environment variables for production
3. Deploy to services like:
   - Heroku
   - AWS EC2
   - Google Cloud Run
   - DigitalOcean

### Frontend

1. Build the production bundle:
   ```bash
   npm run build
   ```

2. Deploy to:
   - Netlify
   - Vercel
   - AWS S3 + CloudFront
   - GitHub Pages

3. Update `VITE_API_BASE` to point to production backend

## Environment Variables

### Backend
- `DATABASE_URL` - Database connection string (for production)

### Frontend
- `VITE_API_BASE` - Backend API base URL

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

MIT License

## Support

For issues and questions, please open an issue on GitHub.
