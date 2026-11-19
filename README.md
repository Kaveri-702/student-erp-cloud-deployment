# Student ERP – Student Registration System
“Application source provided by CloudBlitz training. This repo documents my AWS deployment.”


A full-stack student registration app (add, list and delete students), deployed on a cloud server.

## Tech Stack
| Layer | Technology |
|-------|------------|
| Frontend | React (Vite), served by Apache2 |
| Backend | Spring Boot (Java 17, Maven), REST API on port 8080 |
| Database | MariaDB |
| Cloud | AWS EC2 (Ubuntu) + Security Groups |

## Architecture
```
Browser --> Frontend (Apache2, port 80) --> Backend API (Spring Boot, port 8080) --> MariaDB (port 3306)
```

## Project Structure
```
student-erp/
├── database/   -> MariaDB setup guide + schema.sql
├── backend/    -> Spring Boot REST API
├── frontend/   -> React UI
└── screenshots/
```

## How to Run (follow this order)
1. **Database** – see [database/README.md](database/README.md)
2. **Backend** – see [backend/README.md](backend/README.md)
3. **Frontend** – see [frontend/README.md](frontend/README.md)

## Screenshots
Add images in the `screenshots/` folder and link them here:

![App](screenshots/app.png)
![Database](screenshots/database.png)
![API](screenshots/api.png)
![Security Group](screenshots/security-group.png)

## Security Notes
- Never commit `.env` files or real passwords.
- Do not expose the database port (3306) to the internet. Allow it only from the backend server.
- Restrict SSH (port 22) to your own IP.

## Author
Your Name – [LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/)
