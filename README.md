# Interview AI

Interview AI is a full-stack web app that generates personalized interview preparation reports from a target job description and a candidate resume/profile. It uses a React frontend, an Express/MongoDB backend, and Google Gemini to create technical questions, behavioral questions, skill-gap analysis, a day-wise preparation roadmap, and a tailored resume PDF.

## Features

- User registration, login, logout, and cookie-based authentication
- AI-generated interview reports based on resume, self-description, and job description
- Match score for the target role
- Technical and behavioral interview questions with answer guidance
- Skill-gap analysis with severity levels
- Day-wise preparation roadmap
- Recent interview report history
- AI-generated tailored resume PDF download

## Tech Stack

**Frontend**

- React
- Vite
- React Router
- Axios
- Sass

**Backend**

- Node.js
- Express
- MongoDB with Mongoose
- JWT authentication
- Multer file uploads
- Google GenAI SDK
- Puppeteer for PDF generation

## Project Structure

```text
.
+-- Backend
|   +-- server.js
|   +-- package.json
|   +-- src
|       +-- app.js
|       +-- config
|       +-- controllers
|       +-- middlewares
|       +-- models
|       +-- routes
|       +-- services
+-- Frontend
    +-- package.json
    +-- index.html
    +-- src
        +-- App.jsx
        +-- app.routes.jsx
        +-- features
        +-- style.scss
```

## Prerequisites

- Node.js
- MongoDB database connection string
- Google GenAI API key

## Environment Variables

Create a `.env` file inside the `Backend` folder:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_GENAI_API_KEY=your_google_genai_api_key
```

## Installation

Install backend dependencies:

```bash
cd Backend
npm install
```

Install frontend dependencies:

```bash
cd ../Frontend
npm install
```

## Running Locally

Start the backend server:

```bash
cd Backend
npm run dev
```

The backend runs on:

```text
http://localhost:3000
```

Start the frontend development server:

```bash
cd Frontend
npm run dev
```

The frontend runs on:

```text
http://localhost:5173
```

## Usage

1. Register or log in.
2. Paste the target job description.
3. Upload a resume PDF and/or enter a short self-description.
4. Generate the interview strategy.
5. Review the match score, interview questions, skill gaps, and preparation roadmap.
6. Download a tailored resume PDF for the selected interview report.

## API Routes

### Auth

```text
POST /api/auth/register
POST /api/auth/login
GET  /api/auth/logout
GET  /api/auth/get-me
```

### Interview Reports

```text
POST /api/interview/
GET  /api/interview/
GET  /api/interview/report/:interviewId
POST /api/interview/resume/pdf/:interviewReportId
```

## Notes

- The frontend expects the backend to be available at `http://localhost:3000`.
- The backend CORS config allows requests from `http://localhost:5173`.
- Resume parsing currently uses PDF parsing on the backend, so PDF uploads are the safest supported format.

## License

This project is licensed under the ISC License.
