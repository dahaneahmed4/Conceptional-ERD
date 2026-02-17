# 📊 Employee System Architecture Dashboard

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

> **A high-fidelity, single-file visualization of an Enterprise Entity-Relationship (ER) Model.**

## 📖 Overview

This repository contains a standalone web application designed to visualize the **Employee Participation Information System**. 

Instead of a static image or a basic PDF report, this project renders a **Power BI-style dashboard** entirely in the browser. It demonstrates advanced CSS3 techniques (Glassmorphism, Grid Layouts) and SVG manipulation to create a professional Database Architect interface.

**The Goal:** To model a complex organizational structure where Employees, Departments, and Projects interact with specific constraints (1:N) and roles (M:N).

---

## ✨ Key Features

* **🎨 Modern UI/UX:** Features a "Deep Space" dark mode theme (`#0f172a`) with translucent glass panels and neon data accents.
* **📐 SVG Crow's Foot Notation:** The ER diagram uses raw SVG paths to draw industry-standard database connectors (tridents/circles) for accurate cardinality representation.
* **⚡ Zero Dependencies:** The entire dashboard (Structure, Style, and Logic) is encapsulated in a **single HTML file**. No Node.js, React, or backend required.
* **📱 KPI Metrics:** Top-level cards displaying system stats (Entity Count, Normalization Level, Schema Type).
* **🧠 Logic Documentation:** Integrated side panels explain the architectural decisions, such as why an Associative Entity ("Participation") is required.

---

## 🚀 Quick Start

Since this is a client-side visualization, deployment is instant.

### Option 1: Run Locally
1.  Clone this repository:
    ```bash
    git clone [https://github.com/YOUR_USERNAME/employee-dashboard.git](https://github.com/YOUR_USERNAME/employee-dashboard.git)
    ```
2.  Navigate to the folder and locate `employee_system_dashboard.html`.
3.  **Double-click** to open in Chrome, Edge, Firefox, or Safari.

### Option 2: GitHub Pages
1.  Go to your repository **Settings**.
2.  Navigate to **Pages**.
3.  Select `main` branch and `/root` folder.
4.  Your dashboard will be live at `https://your-username.github.io/employee-dashboard/`.

---

## 🏗️ Architecture & Schema

The dashboard visualizes a normalized Relational Database model.

### 1. The Core Hierarchy (1:N)
The **Department** is the parent entity.
* **Constraint:** An employee belongs to *one* department.
* **Constraint:** A project belongs to *one* department.
* *Visual:* Represented by a single line from Department branching into Crow's Feet at Employee/Project.

### 2. The Many-to-Many Solution (M:N)
The challenge: *Employees work on multiple projects, and projects have multiple employees.*
* **Solution:** We cannot link Employee and Project directly.
* **Implementation:** An **Associative Table** (Participation) is created. It holds the Foreign Keys from both sides plus the specific **Role** attribute.

### 📋 Data Dictionary

| Entity | Type | PK | FK | Attributes |
| :--- | :--- | :--- | :--- | :--- |
| **Department** | Strong | `Num_S` | - | Label, Manager_Name |
| **Employee** | Weak | `Num_E` | `Num_S` | Name, Position, Salary |
| **Project** | Weak | `Num_P` | `Num_S` | Title, Start_Date, End_Date |
| **Participation** | Associative | *(Composite)* | `Num_E`, `Num_P` | **Role** |

---

## 📸 Screenshots

| **Dashboard View** | **ER Diagram Detail** |
| :---: | :---: |
| *[Add Screenshot 1]* | *[Add Screenshot 2]* |
| *Overview of KPIs and Layout* | *Close-up of SVG Connectors* |

---

## 🛠️ Tech Stack

* **HTML5:** Semantic structure.
* **CSS3:**
    * `backdrop-filter: blur()` for Glassmorphism.
    * CSS Grid & Flexbox for layout.
    * CSS Variables for theming.
* **SVG:** Inline vector graphics for diagram lines.
* **JavaScript (Vanilla):** Minimal DOM manipulation for hover effects.

---

## 🤝 Contributing

Contributions are welcome! If you want to improve the visualization or add more complex relationships:

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

*Generated with ❤️ by Gemini*
