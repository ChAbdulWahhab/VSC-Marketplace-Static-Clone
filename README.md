# 🌸 Tailwind CSS Setup (Plain HTML + CLI)

This guide shows how to set up **Tailwind CSS** from scratch — no frameworks, no React, just pure HTML.

---

## 🧩 1. Create Project Folder

```bash
mkdir tailwind-demo
cd tailwind-demo
````

---

## ⚙️ 2. Initialize npm

```bash
npm init -y
```

This creates a `package.json` file for managing dependencies.

---

## 💾 3. Install Tailwind and Required Tools

```bash
npm install -D tailwindcss@3.4.13 postcss autoprefixer vite
```

These are the required dev dependencies:

* **tailwindcss** → the main CSS framework
* **postcss** & **autoprefixer** → process and optimize CSS
* **vite** → optional local server for live reload

---

## ⚡ 4. Generate Tailwind & PostCSS Config Files

```bash
npx tailwindcss init -p
```

✅ This creates:

```
tailwind.config.js
postcss.config.js
```

---

## 📁 5. Project Folder Structure

After setup, your folder should look like this:

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
├── node_modules/
│
└── src/
    └── input.css
```

---

## 🎨 6. Create Input CSS File

Inside the `src/` folder, create a file named `input.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

## 🧱 7. Create `index.html`

In the project root, create `index.html`:

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

---

## 🧰 8. Update Tailwind Config File

Open `tailwind.config.js` and replace its content with:

```js
module.exports = {
  content: ["./index.html", "./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

This tells Tailwind which files to scan for classes.

---

## 🏗️ 9. Build Tailwind CSS

Run this command to generate the final `output.css` file:

```bash
npx tailwindcss -i ./src/input.css -o ./output.css --watch
```

Keep this running — it will rebuild CSS automatically whenever you make changes.

---

## 🌐 10. Open Your Project

Simply open `index.html` in your browser.

You should see:

> **Hello Tailwind!**
> (Styled beautifully with Tailwind)

---

## 🚀 Optional: Run Local Server with Vite

If you want live reloading:

```bash
npx vite
```

Then open the URL it shows (usually [http://localhost:5173](http://localhost:5173)).

---

## 🧹 11. .gitignore

Add a `.gitignore` file to keep your repo clean:

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

## ✅ Done!

You’ve successfully set up **Tailwind CSS** using the CLI method —
no frameworks, just HTML, CSS, and Tailwind power 💪

---

### 🧠 Quick Summary for Students

| Command                                                      | Purpose                       |
| ------------------------------------------------------------ | ----------------------------- |
| `npm init -y`                                                | Create project config         |
| `npm install -D tailwindcss postcss autoprefixer vite`       | Install dependencies          |
| `npx tailwindcss init -p`                                    | Generate config files         |
| `npx tailwindcss -i ./src/input.css -o ./output.css --watch` | Compile Tailwind              |
| `npx vite`                                                   | (Optional) Start local server |

```

---