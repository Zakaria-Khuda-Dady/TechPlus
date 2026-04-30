# TechPulse — Developer Blog Platform

A full-stack blog platform built for developers, featuring article management, an admin panel, and a clean cyberpunk-inspired UI.

## Live Demo

> http://54.81.137.86:5000

---

## Preview

### Home Page
The landing page displays the latest developer articles with titles and publish dates. Articles are loaded dynamically from MongoDB.

![Home Page](screenshots/Home.png)

---

### Article Feed
Articles are listed with a **Load More** button for pagination, keeping the page clean and fast without loading everything at once.

![Article Feed](screenshots/Article.png)

---

### About Page
Describes the mission of TechPulse and the topics covered — Node.js, MongoDB, REST APIs, frontend frameworks, and DevOps/CI-CD.

![About Page](screenshots/About.png)

---

### Contact Page
A contact form allowing visitors to send messages directly from the site.

![Contact Page](screenshots/ContactUs.png)

---

### Admin Panel
A secure admin panel protected by JWT authentication. Admins can sign in or register to manage articles — create, edit, and delete posts.

![Admin Panel](screenshots/SignIn.png)

---

## Features

- Browse and read developer articles
- Search articles by keyword
- Load more articles with pagination
- Admin panel with secure login and registration
- Create, edit, and delete articles (admin only)
- Contact form
- Session-based authentication with JWT
- MongoDB session persistence

---

## Tech Stack

| Layer | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express.js |
| Templating | EJS + Express EJS Layouts |
| Database | MongoDB + Mongoose |
| Authentication | JWT + Bcrypt |
| Session Storage | connect-mongo |
| Styling | Custom CSS |
| Containerization | Docker |
| CI/CD | Jenkins |
| Hosting | AWS EC2 |

---

## Getting Started

### Prerequisites

- Node.js v18+
- MongoDB (local or MongoDB Atlas)

### Installation

```bash
git clone https://github.com/Zakaria-Khuda-Dady/TechPlus.git
cd TechPlus
npm install
```

Create a `.env` file in the root:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

```bash
npm run dev
```

Visit `http://localhost:5000`

---

## Project Structure

```
TechPlus/
├── server/
│   ├── config/        # Database connection
│   ├── helpers/       # Utility functions
│   ├── models/        # Mongoose schemas
│   └── routes/        # Express routes (main + admin)
├── views/
│   ├── layouts/       # EJS layout templates
│   └── admin/         # Admin panel views
├── public/            # Static assets (CSS, JS, images)
├── screenshots/       # App preview images
├── app.js             # Entry point
└── .env               # Environment variables
```

---

## Deployment

This project is deployed using a full CI/CD pipeline:

- **Docker** — containerized for consistent environments
- **Jenkins** — automated build, test, and deploy on every git push
- **AWS EC2** — hosted on a Linux server

Every `git push` to `main` automatically builds and deploys the latest version.

---

## Author

**Zakaria Khudadady** — Full Stack Developer

---

## License

MIT
