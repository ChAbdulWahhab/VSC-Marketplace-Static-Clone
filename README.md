# TailwindCSS Project Setup (Plain HTML + Vite)

This repository contains a simple **TailwindCSS + Vite** setup for plain HTML projects — no React or frameworks, just pure frontend.

---

## Part 1: How to Run This Project (After Downloading the Repo)

If you’ve cloned or downloaded this repository, follow these steps to run it locally.

### 1️⃣ Install Dependencies

Make sure Node.js is installed, then open your terminal inside the project folder and run:

```bash
npm install
```

This will install all dependencies listed in the `package.json` file:

```json
{
  "dependencies": {
    "autoprefixer": "^10.4.21",
    "postcss": "^8.5.6",
    "vite": "^7.1.12"
  },
  "devDependencies": {
    "tailwindcss": "^3.4.13"
  }
}
```

---

### 2️⃣ Start the Local Development Server

After the installation completes, start the project with:

```bash
npm start
```

This will automatically launch a **Vite** development server.
Then open the URL shown in your terminal (usually **[http://localhost:5173](http://localhost:5173)**) to preview the site.

---

### 3️⃣ Build Tailwind (Optional, for CSS Updates)

If you make any changes to Tailwind configuration or input CSS, you can rebuild the styles manually with:

```bash
npx tailwindcss -i ./src/input.css -o ./output.css --watch
```

Keep this command running while you edit the project.

---

## Part 2: Setting Up TailwindCSS from Scratch (Manual Setup Guide)

If you want to learn or manually create this setup yourself instead of using this repo, follow these steps.

### Step 1 — Create a Project Folder

```bash
mkdir tailwind-demo
cd tailwind-demo
```

### Step 2 — Initialize npm

```bash
npm init -y
```

### Step 3 — Install Required Packages

```bash
npm install -D tailwindcss postcss autoprefixer vite
```

### Step 4 — Generate Config Files

```bash
npx tailwindcss init -p
```

This creates two files:

```
tailwind.config.js
postcss.config.js
```

### Step 5 — Folder Structure

```
tailwind-demo/
│
├── index.html
├── output.css
│
├── package.json
├── postcss.config.js
├── tailwind.config.js
│
└── src/
    └── input.css
```

### Step 6 — Add Tailwind Directives

Inside `src/input.css`, add:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Step 7 — Configure Tailwind

Edit `tailwind.config.js`:

```js
module.exports = {
  content: ["./index.html", "./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

### Step 8 — Create an HTML File

In the root folder, make an `index.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tailwind Demo</title>
  <link rel="stylesheet" href="./output.css" />
</head>
<body class="bg-gray-100 text-center mt-10">
  <h1 class="text-3xl font-bold text-blue-600">Hello Tailwind!</h1>
</body>
</html>
```

### Step 9 — Build Tailwind

Run the build command:

```bash
npx tailwindcss -i ./src/input.css -o ./output.css --watch
```

### Step 10 — Run Local Server with Vite (Optional)

```bash
npx vite
```

Then open the provided URL (usually **[http://localhost:5173](http://localhost:5173)**).

---

## .gitignore (Recommended)

```
node_modules/
output.css
dist/
.vite/
.env*
.vscode/
.idea/
.DS_Store
Thumbs.db
```

---

## ✅ Done

You now have a fully functional **TailwindCSS + Vite** setup.
Students can either use this repository directly (`npm install` → `npm start`) or follow the manual guide above to build it from scratch.