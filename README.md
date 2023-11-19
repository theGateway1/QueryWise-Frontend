# Natural Language to SQL Query Generator

This application allows users to generate SQL queries using natural language input. It connects to a database (or uses a mock database) and provides an interface for users to ask questions in plain English, which are then converted into SQL queries and executed against the database.

![Screenshot](https://github.com/theGateway1/QueryWise-Frontend/blob/master/public/easysql-landing.png)

![Screenshot](https://github.com/theGateway1/QueryWise-Frontend/blob/master/public/easysql-chat.png)

## Features

- Natural language to SQL query conversion
- Database connection management
- Mock database option for testing
- Real-time query results display

## Architecture

- Frontend:

  - Next.js for server-side rendering and API routes
  - Tailwind CSS for styling
  - Shadcn/UI for components

- Backend:
  - FastAPI for handling database connections and text-to-SQL conversion
  - Python for backend logic
  - OpenAI for text-to-SQL conversion
- API Routes:
  - `db-structure/route.ts`: Next.js API route for fetching database structure
  - `proxy/route.ts`: Next.js API route for communicating with FastAPI backend
  - FastAPI backend: Handles database connections and text-to-SQL conversion

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/theGateway1/QueryWise-Frontend.git
   cd QueryWise-Frontend
   ```

2. Install frontend dependencies:

   ```bash
   npm install
   ```

3. Set up frontend environment variables:
   Create a `.env.local` file in the root directory and add:

   ```bash
   API_URL=http://localhost:8000  # FastAPI backend URL
   ```

4. Install backend dependencies:

- Clone the backend repository:
  ```bash
  git clone https://github.com/theGateway1/QueryWise-Backend.git
  cd QueryWise-Backend
  ```

2. Install backend dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Set up backend environment variables:
   Create a `.env` file in the `QueryWise-Backend` directory and add necessary variables.
   ```bash
   OPENAI_API_KEY=<your-openai-api-key>
   ```

## Usage

1. Start the FastAPI backend:

   ```bash
   cd QueryWise-Backend
   uvicorn main:app --reload
   ```

2. In a new terminal, start the Next.js frontend:

   ```bash
   npm run dev
   ```

3. Open [http://localhost:3000](http://localhost:3000) in your browser.

4. Choose to use a mock database or connect to your own database.

5. If using your own database, enter the connection details.

6. Click "Connect" to establish a database connection.

7. Enter a natural language query in the text area.

8. Click "Generate SQL" to convert your query to SQL and execute it.

9. View the results displayed below the query input.
