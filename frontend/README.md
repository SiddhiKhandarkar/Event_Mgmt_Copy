siddhi# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)






Nice 🔥 — since you’re using **AWS EC2**, I’ll give you **exact step-by-step commands (copy-paste ready)** to:

✔ Clone your repo
✔ Setup backend
✔ Run server
✔ (Optional) Setup frontend
✔ Make it publicly accessible

---

# ☁️ 1. Connect to EC2

From your local terminal:

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

---

# 📦 2. Update System

```bash
sudo apt update && sudo apt upgrade -y
```

---

# 🟢 3. Install Node.js & npm

```bash
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
```

Check:

```bash
node -v
npm -v
```

---

# 📥 4. Clone Your GitHub Repo

```bash
git clone https://github.com/kaustubhgharat/Student_Record_Management.git
cd Student_Record_Management
```

---

# 📂 5. Install Dependencies

(Inside project folder)

```bash
npm install
```

---

# 🔐 6. Setup Environment Variables

Create `.env` file:

```bash
nano .env
```

Add (example):

```
PORT=5000
MONGO_URI=your_mongodb_atlas_connection_string
```

Save:

* `CTRL + X`
* `Y`
* `Enter`

---

# ▶️ 7. Run Backend Server

```bash
node server.js
```

OR (if using nodemon):

```bash
npx nodemon server.js
```

---

# 🌐 8. Allow Port in AWS (IMPORTANT)

Go to EC2 → Security Groups → Edit Inbound Rules

Add:

| Type       | Port | Source    |
| ---------- | ---- | --------- |
| Custom TCP | 5000 | 0.0.0.0/0 |

---

# 🌍 9. Test in Browser

Open:

```
http://your-ec2-public-ip:5000
```

---

# ⚡ 10. Run in Background (PM2 - Recommended)

Install PM2:

```bash
sudo npm install -g pm2
```

Start app:

```bash
pm2 start server.js
```

Save process:

```bash
pm2 save
pm2 startup
```

---

# 🖥️ 11. (Optional) Frontend Setup

If your repo has frontend folder:

```bash
cd frontend
npm install
npm run build
```

Install serve:

```bash
sudo npm install -g serve
serve -s build
```

---

# 🌐 12. Open Frontend Port

Allow port **3000 or 5000** in AWS security group.

---

# 🔥 Final Output

You’ll have:

* Backend running on:

  ```
  http://<EC2-IP>:5000
  ```
* Frontend (if deployed):

  ```
  http://<EC2-IP>:3000
  ```

---

# 💡 Bonus (Better Production Setup)

If you want full marks 💯, add:

### Use NGINX (optional but impressive)

```bash
sudo apt install nginx -y
```

---

# 🚨 Common Errors

| Issue                | Fix                  |
| -------------------- | -------------------- |
| App not opening      | Check security group |
| Mongo not connecting | Check MONGO_URI      |
| Port already used    | Change PORT          |

---

# ✅ If you want next

I can help you with:

✔ NGINX setup (domain + reverse proxy)
✔ Docker deployment (very important for CC)
✔ Fix errors from your repo specifically
✔ Complete report + architecture diagram

Just tell me 👍
