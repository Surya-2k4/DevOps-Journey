
# 🛒 E-commerce Application using CSV, Flask, Docker & Kubernetes

## 🚀 Overview
This project demonstrates building a simple E-commerce application using:
- **Backend:** Python with Flask for API services, reading product data from a CSV file.
- **Frontend:** HTML interface displaying the products.
- **Docker:** For containerizing the application.
- **Kubernetes:** For orchestrating and managing the services.

## 🛠️ Technologies Used
- Flask
- Docker
- Kubernetes
- Python (pandas for CSV handling)
- HTML, CSS, JS

---

## ⚙️ Steps Involved

### 1️⃣ **Project Setup**
- Create a directory: `mkdir shoppy && cd shoppy`
- Create two folders: `frontend` and `backend`.

### 2️⃣ **Backend Development**
- Navigate to the backend folder: `cd backend`
- Create `products.csv` with sample data:
```csv
ID,NAME,PRICE,QTY
101,Pen,20,2
102,Bag,1500,1
```
- Install Python and required libraries:
```bash
sudo apt update
sudo apt install python3-pip
pip3 install pandas
```
- Create `app.py` for reading CSV and returning JSON data.
- Add dependencies to `requirements.txt`:
```
flask
pandas
```

### 3️⃣ **Dockerization**
- Create `Dockerfile` for the backend.
- Build Docker image:
```bash
sudo docker build -t backend:latest .
```
- Verify Docker image:
```bash
docker images
```
- Run the Docker container:
```bash
docker run -p 7000:7000 backend
```
- Test the API:
```bash
curl http://localhost:7000/products
```

### 4️⃣ **Frontend Development**
- Navigate to the `frontend` folder.
- Create `index.html` with button functionality to display product data in a table.
- Create Dockerfile for the frontend.
- Build Docker image and run the container.

### 5️⃣ **Kubernetes Configuration**
- Create a `k8s` folder.
- Create:
    - `backend-deployment.yml` (port: 7000)
    - `frontend-deployment.yml` (port: 3000)
    - `service.yml` (combines frontend and backend services)
    - `configmap.yml` for configuration management.

---

## 🔥 **Next Steps (Tomorrow's Tasks)** 
- Continue with Kubernetes configurations.
- Implement scaling, load balancing, and service management.

---

✅ **Author:** Surya  

