## 🛠️ **Day 1: Setting Up the DevOps Environment**

### 🔹 **Topics Covered:**
- 📚 **SDLC Lifecycle**: Introduction to **Software Development Life Cycle (SDLC)** and its phases.  
- 🔥 **Software Development Models:**  
    - 💧 Waterfall Model  
    - ⚡ Agile Model  
    - 🔁 Iterative Model, etc..  
    - ⚙️ DevOps Methodology  
- 🔧 **DevOps Fundamentals:**  
    - 💡 Understanding **CI/CD pipelines**  
    - 🚀 Introduction to **Jenkins** and its role in DevOps  

---

### 🐧 **Ubuntu Installation:**
- 🔹 Installed **Ubuntu ISO** on a Virtual Machine (VM).  
- 🔹 Configured **WSL (Windows Subsystem for Linux)** and installed **Ubuntu** using:
    ```bash
    wsl --install -d ubuntu
    ```
- 🔹 Verified the installation by launching the Ubuntu terminal and running basic commands.

---

### 🔥 **Jenkins Installation & Setup:**
- Installed **Jenkins** on WSL with the following steps:
    - Added the **Jenkins repository** and installed the service.  
    - Started the Jenkins server and accessed the **Jenkins dashboard** via:
    ``` 
    http://localhost:8080 
    ```
- 🎯 Created a **Freestyle Project** named `nginx`:
    - Added shell commands to install **Nginx**.  
    - Built the project and successfully installed **Nginx**.  
    - Verified the Nginx service by accessing the **default web page**.

---

### 📸 **Documentation & Version Control:**
- 🖼️ Took **screenshots** of the entire process, including:  
    - Ubuntu installation  
    - WSL setup  
    - Jenkins installation and project execution  
- 📝 Saved the screenshots as a **PDF**.  
- 🔥 Pushed the PDF to the `DevOps-Journey` repository using:
    ```bash
    git add .
    git commit -m "Task 1 initial commit"
    git push origin main
    ```
---

### ✅ **Key Takeaways:**
- 🎓 Learned the fundamentals of **DevOps** and **CI/CD** pipelines.  
- 🚀 Successfully installed and configured **Jenkins** on WSL.  
- 🛠️ Created and built a **Freestyle Project** with **Nginx installation**.  
- 📂 Documented the entire process with **screenshots and PDF** backup.  

---
