# ⚽ Pitchside | Football Analytics Platform

**Pitchside** is a modern, full-stack web application designed for managing local football leagues and tournaments. It provides a comprehensive dashboard for tracking key statistics, managing teams and players, and leveraging advanced analytics like Expected Goals (xG) to gain deeper insights into team performance.

This project was built from the ground up using the MENN stack (MongoDB, Express.js, Next.js, Node.js) and is fully containerized with Docker for easy setup and deployment.

---

## ✨ Features

-   **Interactive Dashboard:** Get a quick overview of all league activities, including the number of active tournaments, registered teams, and players.
-   **Tournament Management:** Easily create, view, update, and delete tournaments (both League and Cup formats).
-   **Team Management:** Register new teams and link them to existing tournaments.
-   **Player Management:** Add players to teams and track their core statistics.
-   **Advanced Analytics:** Visualize player performance with metrics like Goals vs. Expected Goals (xG).
-   **Responsive Design:** A clean, modern UI built with Tailwind CSS that works beautifully on all devices.
-   **Dark Mode:** The UI automatically adapts to your system's preferred color scheme.

---

## 🛠️ Tech Stack

This project utilizes a modern, robust technology stack:

-   **Frontend:** [Next.js](https://nextjs.org/) (React Framework) & [Tailwind CSS](https://tailwindcss.com/)
-   **Backend:** [Node.js](https://nodejs.org/) & [Express.js](https://expressjs.com/)
-   **Database:** [MongoDB](https://www.mongodb.com/) (NoSQL Database) with [Mongoose](https://mongoosejs.com/) ODM
-   **Containerization:** [Docker](https://www.docker.com/) & [Docker Compose](https://docs.docker.com/compose/)

---

## 🚀 Getting Started

Follow these instructions to get the project up and running on your local machine.

### Prerequisites

Ensure you have the following software installed on your system:

-   **Node.js** (v18 or newer): We recommend using [NVM](https://github.com/nvm-sh/nvm) (Node Version Manager) to manage Node.js versions.
-   **Docker** and **Docker Compose**: For running the application and database in containers.

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd pitchside
    ```

2.  **Backend Configuration:**
    Navigate to the `backend` directory and create an environment file.
    ```bash
    cd backend
    touch .env
    ```
    Add the following line to your new `.env` file. This is the connection string for our Dockerized MongoDB instance.
    ```
    MONGO_URI=mongodb://mongo-db:27017/pitchside
    ```

3.  **Run the Application with Docker Compose:**
    Navigate back to the project's root directory (`pitchside`) and start the application.
    ```bash
    cd ..
    docker-compose up --build
    ```
    The `--build` flag tells Docker to build the images from your Dockerfiles the first time you run it.

4.  **Access the Application:**
    -   The **Frontend** will be running at: [http://localhost:3000](http://localhost:3000)
    -   The **Backend API** will be running at: [http://localhost:5001](http://localhost:5001)

---

## 📁 Project Structure

The project is organized into two main directories:


pitchside/
├── backend/
│   ├── controllers/        # Contains the business logic for API routes
│   ├── models/             # Mongoose database schemas
│   ├── routes/             # API route definitions
│   ├── Dockerfile          # Instructions to build the backend image
│   ├── package.json        # Backend dependencies and scripts
│   └── server.js           # The main Express server entry point
│
├── frontend/
│   ├── app/                # Next.js App Router directory
│   │   ├── components/     # Reusable React components
│   │   └── ...             # Page routes and layouts
│   ├── lib/                # Data fetching logic
│   ├── tailwind.config.ts  # Tailwind CSS configuration
│   └── package.json        # Frontend dependencies and scripts
│
├── docker-compose.yml      # Defines and orchestrates all services
└── README.md               # You're here!



---

## 📖 API Endpoints

The backend provides the following RESTful API endpoints.

| Method   | Endpoint                  | Description                     |
| :------- | :------------------------ | :------------------------------ |
| `POST`   | `/api/tournaments`        | Create a new tournament         |
| `GET`    | `/api/tournaments`        | Get all tournaments             |
| `GET`    | `/api/tournaments/:id`    | Get a single tournament by ID   |
| `PUT`    | `/api/tournaments/:id`    | Update a tournament             |
| `DELETE` | `/api/tournaments/:id`    | Delete a tournament             |
| `POST`   | `/api/teams`              | Create a new team               |
| `GET`    | `/api/teams`              | Get all teams                   |
| `POST`   | `/api/players`            | Create a new player             |
| `GET`    | `/api/players`            | Get all players                 |

---

## 🔮 Future Improvements

Based on the original architecture diagram, future enhancements could include:

-   **Real-time Updates:** Integrate `Socket.io` for live match updates and notifications.
-   **Caching Layer:** Implement a `Redis` cache to improve API response times for frequently requested data.
-   **Dedicated Analytics Service:** Build a separate Python service for more complex data analysis and machine learning models.
-   **User Authentication:** Add user accounts and authentication to secure the platform.

---

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.
