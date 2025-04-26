# DeskBuddy

## Table of Contents
- [Project Description](#project-description)
- [Tech Stack](#tech-stack)
- [Getting Started Locally](#getting-started-locally)
- [Available Scripts](#available-scripts)
- [Project Scope](#project-scope)
- [Project Status](#project-status)
- [License](#license)

## Project Description
DeskBuddy is a web-based desk booking system designed to eliminate conflicts in office seating. It provides a simple and user-friendly interface for employees to book, cancel, and review their desk reservations. The application supports up to 200 users and 50 desks, ensuring a streamlined process for daily desk management along with a dedicated admin panel for overseeing reservations and user accounts.

## Tech Stack
- **Frontend:** Astro 5, React 19, TypeScript 5, Tailwind 4, Shadcn/ui
- **Backend:** Supabase (PostgreSQL) for authentication and data management
- **CI/CD:** GitHub Actions pipeline with DigitalOcean hosting via Docker
- **Other Tools:** Node.js (version 22.14.0 as specified by `.nvmrc`)

## Getting Started Locally
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/DeskBuddy.git
   cd DeskBuddy
   ```
2. **Install dependencies:**
   ```bash
   npm install
   ```
3. **Ensure you are using Node.js version 22.14.0:**
   ```bash
   nvm use
   ```
4. **Start the development server:**
   ```bash
   npm run dev
   ```

## Available Scripts
- **dev:** Starts the Astro development server.
- **build:** Builds the project for production.
- **preview:** Serves the production build for preview.
- **astro:** Runs Astro commands.
- **lint:** Checks the code with ESLint.
- **lint:fix:** Automatically fixes linting issues.
- **format:** Formats the code using Prettier.

## Project Scope
The MVP version of DeskBuddy includes:
- User registration, login, and profile management.
- A weekly calendar view to display desk availability.
- Full-day desk booking and cancellation functionality.
- Reservation history for users.
- An admin panel to manage desks and user reservations.

DeskBuddy aims to resolve common issues such as uncertainty over desk availability and booking conflicts through a centralized reservation system.

## Project Status
This project is currently in the MVP stage, with core functionalities implemented. Continuous improvements and additional features are planned based on user feedback and iterative development.

## License
This project is licensed under the MIT License. 
