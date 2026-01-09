# 🎓 Student Profile Static Site Generator

This project automatically generates **individual student portfolio webpages** using:

* ✅ HTML Template
* ✅ Student data from a CSV file
* ✅ Python script for automation

Each student gets their own folder named by **student_id**, containing an `index.html` profile page.

---

## 📁 Project Folder Structure

```
profile website/
│
├── template.html
├── generate_pages.py
├── students.csv
└── students_pages/
    ├── assets/
    │   ├── AIK073930.jpeg
    │   ├── AIK073361.jpeg
    │   └── ...
    │
    ├── AIK073930/
    │   └── index.html
    ├── AIK073361/
    │   └── index.html
    └── ...
```

---

## 📄 1. HTML Template (`template.html`)

The template uses placeholders which are replaced by Python:

| Placeholder      | Meaning                  |
| ---------------- | ------------------------ |
| `{{student_id}}` | Student unique ID        |
| `{{name}}`       | Student full name        |
| `{{email}}`      | Student email            |
| `{{github}}`     | GitHub profile URL       |
| `{{linkedin}}`   | LinkedIn profile URL     |
| `{{projects}}`   | Projects page / repo URL |

### 📸 Image Rule

Images are loaded using:

```html
<img src="../assets/{{student_id}}.jpeg">
```

So image files **must be named exactly as student_id** and stored in:

```
students_pages/assets/
```

Example:

```
AIK073930.jpeg
```

---

## 📊 2. CSV File (`students.csv`)

### ✅ Required Format

```csv
student_id,name,email,github,linkedin,projects
```

### ✅ Sample Data

```csv
AIK073930,Raju Jonnada,rajujonnada@12022001.xyz,https://github.com/JonnadaRaju,https://www.linkedin.com/in/jonnadaraju6014,https://github.com/JonnadaRaju?tab=repositories
AIK073361,Siva Kumar,siva@gmail.com,https://github.com/siva,https://www.linkedin.com/in/siva,https://github.com/siva?tab=repositories
```

⚠️ Do not use commas inside values unless wrapped in quotes.

---

## 🐍 3. Python Script (`generate_pages.py`)

### ✅ What It Does

* Reads `students.csv`
* Creates folder using `student_id`
* Replaces placeholders in `template.html`
* Writes `index.html` for each student

### ▶ Run Command

```bash
python generate_pages.py
```

After running, student pages will be created inside:

```
students_pages/
```

---

## 🌐 Opening Student Pages

Open any student page in browser:

```
students_pages/AIK073930/index.html
```

---

## 🔐 Version History

### ✅ Version 1

* HTML template with name, email, GitHub, LinkedIn
* Python generator

### ✅ Version 2

* Added `student_id`
* Folder name based on student_id

### ✅ Version 3 (Current)

* Image auto-linked using `student_id.jpeg`
* Added **Projects** social button

---

## 🚀 Future Improvements (Planned)

* [ ] Auto copy images into student folders
* [ ] Main index page listing all students
* [ ] QR code for each profile
* [ ] FastAPI upload CSV & auto-generate pages

---

## 👨‍💻 Author

Created as part of **AI Karyashala Backend Engineering Training**

Purpose: Practice real-world automation using Python, CSV, and HTML.

---

If you face any issue, check:

* CSV header names
* Image file names
* Folder structure

Happy Coding 🚀
