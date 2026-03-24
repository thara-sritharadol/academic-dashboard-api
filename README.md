# Academic Collaboration Network & Analytics Dashboard

**Live Demo:** [https://academic-dashboard-tau.vercel.app/](https://academic-dashboard-tau.vercel.app/)

A full-stack web application designed to analyze, visualize, and explore academic publications and researcher collaboration networks. This project processes over 4,600 research papers, utilizing Natural Language Processing (NLP) and Topic Modeling to cluster academic domains and discover collaboration trends.

## Key Features

* **Analytics Dashboard:** Provides a high-level overview of publication statistics, domain trends over time (Dynamic Line Charts), and overall expertise distribution (Doughnut Charts). Includes a leaderboard of top researchers by topic.
* **Interactive Author Network:** A visually engaging 2D force-directed graph (using `react-force-graph-2d`) mapping the collaboration network between university authors and external co-authors. Features zoom, pan, and dynamic topic filtering.
* **Paper Repository Search:** A highly optimized search interface for exploring thousands of papers. Includes title/abstract search, topic-based filtering, and server-side pagination for fast loading times.

## System Architecture & Separation of Concerns

To ensure high performance and seamless deployments on cloud infrastructure, the system is architected with strict separation of concerns:

1.  **Data Pipeline & ML (Separate Context):** An offline pipeline handles data extraction, NLP processing (SpaCy), and topic modeling (BERTopic). The processed and clustered data is securely pushed to the production database.
2.  **Lightweight Web API:** The production backend is stripped of heavy machine learning dependencies, acting purely as a fast, reliable REST API to serve pre-calculated data to the client.
3.  **Modern Client:** A responsive, interactive React frontend handles complex data visualizations directly in the browser.

## Tech Stack

**Frontend:**
* React (Vite) + TypeScript
* Tailwind CSS (Styling)
* Recharts (Data Visualization)
* React-Force-Graph-2D (Network Visualization)
* Deployed on **Vercel**

**Backend:**
* Python 3.10
* Django & Django REST Framework (DRF)
* Gunicorn (WSGI Server)
* Docker (Containerization)
* Deployed on **Back4App (CaaS)**

**Database:**
* PostgreSQL
* Hosted on **Neon.tech**

## Getting Started (Local Development)

### Frontend Setup
1. Clone the repository
2. Install dependencies: `npm install`
3. Create a `.env` file and add the API URL:
   ```env
   VITE_API_URL=http://localhost:8000/api
   ```
4. Run the development server: `npm run dev`

### Backend Setup
1. Navigate to the backend directory
2. Create a virtual environment: python -m venv venv and activate it
3. Install dependencies: `pip install -r requirements.txt`
4. Create a .env file with the following variables:
    ```bash
    DEBUG=True
    SECRET_KEY=your_secret_key
    DATABASE_URL=your_neon_postgres_connection_string
    ALLOWED_HOSTS=localhost,127.0.0.1
    CORS_ALLOWED_ORIGINS=http://localhost:5173
    ```
5. Run migrations: `python manage.py migrate`
6. Start the server: `python manage.py runserver`

### Author
Developed as a Senior Project to showcase Full-Stack Development, Data Engineering, and UI/UX implementation.

## Scrennshot
<img width="1920" height="1080" alt="Screenshot (394)" src="https://github.com/user-attachments/assets/9063f109-b1fe-4f6d-9636-49002455ae0e" />
<img width="1920" height="1080" alt="Screenshot (395)" src="https://github.com/user-attachments/assets/005715d3-44be-4409-a263-3f65655a8820" />
<img width="1920" height="1080" alt="Screenshot (397)" src="https://github.com/user-attachments/assets/ec71b883-2dfc-42a6-a016-fa0b948e7da0" />
<img width="1920" height="1080" alt="Screenshot (398)" src="https://github.com/user-attachments/assets/82cf46ed-f31d-43e0-b5ea-e3fcf1641781" />
<img width="1920" height="1080" alt="Screenshot (399)" src="https://github.com/user-attachments/assets/208433f2-db63-41a8-9c73-8cac66d49b16" />

