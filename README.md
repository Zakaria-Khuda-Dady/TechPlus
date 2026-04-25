# TechPulse — Developer Blog Platform

A full-stack blog platform built for developers, featuring article management, 
an admin panel, and a clean cyberpunk-inspired UI.

## Live Demo

> [Coming soon — deploying to AWS EC2]

---

## Preview

### Home Page
The landing page displays the latest developer articles with titles and publish 
dates. Articles are loaded dynamically from MongoDB.

![Home Page](screenshots/home.png)

---

### Article Feed
Articles are listed with a **Load More** button for pagination, keeping the 
page clean and fast without loading everything at once.

![Article Feed](screenshots/articles.png)

---

### About Page
Describes the mission of TechPulse and the topics covered — Node.js, MongoDB, 
REST APIs, frontend frameworks, and DevOps/CI-CD.

![About Page](screenshots/about.png)

---

### Contact Page
A contact form allowing visitors to send messages directly from the site.

![Contact Page](screenshots/contact.png)

---

### Admin Panel
A secure admin panel protected by JWT authentication. Admins can sign in or 
register to manage articles — create, edit, and delete posts.

![Admin Panel](screenshots/admin.png)

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

---

## Getting Started

### Prerequisites

- Node.js v18+
- MongoDB (local or MongoDB Atlas)

### Installation

```bash
# Clone the repo
git clone https://github.com/yourusername/techpulse.git
cd techpulse

# Install dependencies
npm install

# Create environment file
cp .env.example .env
