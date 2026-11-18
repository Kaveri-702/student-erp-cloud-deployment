# Frontend – React (Vite)

## 1. Install Node.js and npm
```bash
sudo apt update && sudo apt install nodejs npm -y
node -v
npm -v
```

## 2. Install dependencies
```bash
cd frontend
npm install
```

## 3. Set the backend URL
Create a `.env` file in the `frontend/` folder:
```
VITE_API_URL="http://<BACKEND_PUBLIC_IP>:8080/api"
```
A sample is provided in `.env.example`. Do not commit `.env`.

## 4. Build for production
```bash
npm run build
```
This creates a `dist/` folder with optimized production files.

## 5. Deploy on Apache2
```bash
sudo apt install apache2 -y
sudo systemctl start apache2
sudo cp -rf dist/* /var/www/html/
```
Open `http://<FRONTEND_PUBLIC_IP>` in your browser.

> Alternative: upload the `dist/` files to an AWS S3 bucket with static website hosting.

## Security Group
Allow inbound port **80** (HTTP) from anywhere, and SSH (22) only from your IP.
