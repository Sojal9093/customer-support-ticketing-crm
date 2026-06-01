# Support CRM 

A fully functional **customer support ticketing system** built with **FastAPI + SQLite + Vanilla JS**.

## Live Demo

🔗 https://customer-support-ticketing-crm-system-ceal.onrender.com/

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Python 3.11 + FastAPI |
| Database | SQLite (Local) |
| Frontend | HTML + CSS + Vanilla JS |
| Deployment | Render |

## Features

- ✅ Create tickets with customer info, subject, and description
- ✅ Auto-generated ticket IDs (TKT-001, TKT-002...)
- ✅ List all tickets with clean table view
- ✅ Search across name, email, subject, description, ticket ID
- ✅ Filter by status (Open / In Progress / Closed)
- ✅ View full ticket details
- ✅ Update ticket status
- ✅ Add internal notes to tickets
- ✅ Responsive design (mobile friendly)
- ✅ Loading skeletons for better UX

## Project Structure

```
support-crm/
├── main.py              # FastAPI app entry point
├── database.py          # SQLite connection setup
├── models.py            # Database table definitions
├── schemas.py           # Request/Response validation
├── routers/
│   └── tickets.py       # All API endpoints
├── static/
│   ├── index.html       # Home — ticket list
│   ├── create.html      # Create new ticket
│   └── ticket.html      # Ticket detail & update
├── crm.db               # SQLite database (auto-created)
├── requirements.txt     # Python dependencies
├── Procfile             # Render deployment config
└── README.md
```

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/customer-support-crm.git
cd customer-support-crm
```

### 2. Create virtual environment

```bash
python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate   # Mac/Linux
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the app

```bash
uvicorn main:app --reload
```

Visit **http://localhost:8000** in your browser.

The database (`crm.db`) is automatically created on first run.

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/tickets/` | Create a new ticket |
| GET | `/api/tickets/` | List all tickets (supports `?status=` and `?search=`) |
| GET | `/api/tickets/{ticket_id}` | Get full ticket details |
| PUT | `/api/tickets/{ticket_id}` | Update status or add note |
| GET | `/health` | Health check |

## Deploy on Render

1. Push your code to **GitHub**
2. Go to **https://render.com**
3. Create a new **Web Service**
4. Connect your GitHub repository
5. Set these values:
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `uvicorn main:app --host 0.0.0.0 --port 8000`
6. Click **Deploy**

Your app will be live in 2-3 minutes!

## Tech Details

- **FastAPI** - Modern Python web framework with automatic API documentation
- **SQLAlchemy** - ORM for database operations
- **SQLite** - Lightweight, file-based database (perfect for small to medium apps)
- **Vanilla JS** - No frameworks, pure JavaScript for frontend interactivity

## Future Enhancements

- User authentication & roles
- Email notifications for ticket updates
- Ticket attachments
- Customer portal
- Analytics dashboard
