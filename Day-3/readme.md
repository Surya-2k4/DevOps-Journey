
# 🚀 Jenkins + Docker CI/CD Pipeline Documentation

## ✅ Step 1: Create a GitHub Repository
- Go to: [GitHub](https://github.com)
- Click on **New Repository**
- Set the repository name as: `Jenkins-Docker-Demo`
- Select **Public**
- Click on **Create Repository**
- 📌 **Repo URL:**  
  `https://github.com/Surya-2k4/Jenkins-Docker-Demo.git`

---

## 🔐 Step 2: Generate a Personal Access Token (PAT)
- Go to: [GitHub Developer Settings](https://github.com/settings/tokens)
- Navigate to:  
  `Personal Access Tokens → Tokens (classic) → Generate New Token`
- Set a Note: `Jenkins Docker Pipeline`
- Select the following scopes:  
  - `repo`
  - `workflow`
  - `admin:repo_hook`
- Generate the token.

**⚠️ Important:** Do NOT expose your token in this README file.

---

## 🛠️ Step 3: Start and Enable Jenkins
- Open the terminal.
- Enable Jenkins to start at boot:
```bash
sudo systemctl enable jenkins
```
- Start the Jenkins service:
```bash
sudo systemctl start jenkins
```

---

## 🔑 Step 4: Access Jenkins
- Open your browser:  
  `http://localhost:8080`
- Log in with your Jenkins credentials:
  - **Username:** `Admin`
  - **Password:** (use the Jenkins-generated password)

---

## 🔨 Step 5: Create a New Project in Jenkins
- Go to **Jenkins Dashboard → New Item**
- Select **Pipeline**
- Name the project: `Docker-Pipeline`
- Click **OK**
- In the Pipeline Section:
  - Select **Pipeline script from SCM**
  - Choose **Git**
  - Enter the repo URL:  
    `https://github.com/Surya-2k4/Jenkins-Docker-Demo.git`
  - Select the branch: `main`
  - Click **Save**

---

## 🐙 Step 6: Clone the GitHub Repo Locally
- Open the terminal.
- Clone the GitHub repo:
```bash
git clone https://github.com/Surya-2k4/Jenkins-Docker-Demo.git
```
- Navigate into the cloned folder:
```bash
cd Jenkins-Docker-Demo
```
- List the files:
```bash
ls
```
✅ You should see:  
`app.py, Dockerfile, requirements.txt, compose-docker.yml`

---

## 📁 Step 7: Move All Files to the Repo
- Move the project files into the repo:
```bash
mv /path/to/your/files/* Jenkins-Docker-Demo/
```
- Verify the files:
```bash
ls
```

---

## 📤 Step 8: Commit and Push the Files
- Add all the files:
```bash
git add .
```
✅ (OR)
```bash
git add --all
```
- Commit the changes:
```bash
git commit -m "Initial Docker application commit"
```
- Push the files to the GitHub repo:
```bash
git push origin main
```
- Verify the files in the GitHub repository.

---

## 🐳 Step 9: Create a DockerHub Account
- Go to: [DockerHub](https://hub.docker.com)
- Sign up or log in.
- **Username:** `surya2k4`
- **Password:** (your DockerHub password)  

**⚠️ Important:** Do NOT expose your password in this README file.

---

## 🔑 Step 10: Add DockerHub Credentials to Jenkins
- Go to **Jenkins Dashboard → Manage Jenkins**
- Navigate to:  
  `Manage Credentials → System → Global Credentials → Add Credentials`
- Set the following values:
  - **Username:** `surya2k4`
  - **Password:** (DockerHub password)
  - **ID:** `docker`
- Click **Save**

---

## 📝 Step 11: Create the Jenkinsfile
- Create a `Jenkinsfile` with the following content:
```groovy
pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = 'docker'
    }

    stages {
        stage('Clone Repository') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t surya2k4/docker-app .'
                }
            }
        }

        stage('Push to DockerHub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_HUB_CREDENTIALS) {
                        sh 'docker push surya2k4/docker-app'
                    }
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 5001:5000 surya2k4/docker-app'
                }
            }
        }
    }
}
```

---

## 🚀 Step 12: Push Jenkinsfile to GitHub
- Add the `Jenkinsfile`:
```bash
git add Jenkinsfile
```
- Commit the changes:
```bash
git commit -m "Added Jenkinsfile"
```
- Push the changes to the GitHub repository:
```bash
git push origin main
```

---

## ✅ Step 13: Build the Project in Jenkins
- Go to **Jenkins → Your Project**
- Click **Build Now**
- Verify the console output for:
  - Successful build
  - Docker image pushed to DockerHub
  - Running the container on `localhost:5001`

---

## 🔥 Step 14: Test the Application
- Open your browser.
- Go to:  
  `http://localhost:5001`
- Verify that the app is running successfully.

---

## 🎯 Key Commands Summary
- **Enable Jenkins:**  
```bash
sudo systemctl enable jenkins
```
- **Start Jenkins:**  
```bash
sudo systemctl start jenkins
```
- **Clone Repo:**  
```bash
git clone <repo_url>
```
- **Add & Commit:**  
```bash
git add .
git commit -m "message"
```
- **Push to GitHub:**  
```bash
git push <repo_url>
```

---

## 🚀 Conclusion
You have successfully:  
✅ Created a GitHub repo.  
✅ Added GitHub PAT.  
✅ Configured DockerHub credentials in Jenkins.  
✅ Built a CI/CD pipeline using Jenkins and Docker.  
✅ Tested the Dockerized app locally on port `5001`.  

💡 Let me know if you need any modifications or further assistance! 🚀🔥
