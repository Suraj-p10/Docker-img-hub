# Automating Workflow of CI/CD for Dockerized Flask App

This project demonstrates how to automate a CI/CD pipeline for a Flask web application using GitHub Actions and Docker. It ensures that every change pushed to the repository is tested, built, and deployed seamlessly.

---

## **Features**
- Flask web application containerized with Docker.
- Continuous Integration (CI): Runs tests on every push or pull request to the `main` branch.
- Continuous Deployment (CD): Builds and publishes the Docker image to DockerHub.
- Fully automated workflow using GitHub Actions.

---

## **File Structure**
```
.
├── app.py              # Flask application code
├── py_test.py          # Unit tests for the Flask app
├── requirements.txt    # Dependencies for the Flask app
├── DockerFile          # Docker configuration for the app
├── .github
│   └── workflows
│       └── ci-cd.yml   # GitHub Actions workflow file
```

---

## **Getting Started**

### **1. Prerequisites**
Ensure you have the following installed:
- Python 3.9+
- Docker
- Git
- GitHub account with DockerHub credentials stored as GitHub Secrets (`DOCKER_USERNAME` and `DOCKER_PASSWORD`).

---

### **2. Installation and Setup**

#### **Clone the Repository**
```bash
git clone https://github.com/<your-username>/dockerized-flask-app.git
cd dockerized-flask-app
```

#### **Set Up Virtual Environment**
```bash
python3 -m venv venev
source venev/bin/activate
pip install -r requirements.txt
```

#### **Run Locally**
```bash
python app.py
```
Access the app at [http://localhost:5000](http://localhost:5000).

#### **Run Tests**
```bash
pytest py_test.py
```

---

## **Dockerize the Application**

#### **Build the Docker Image**
```bash
docker build -t flasktest-app .
```

#### **Run the Docker Container**
```bash
docker run -p 5000:5000 flasktest-app
```
Access the app at [http://localhost:5000](http://localhost:5000).

---

## **GitHub Actions Workflow**

### **Workflow Overview**
The CI/CD pipeline is defined in `.github/workflows/ci-cd.yml` and includes the following steps:

#### **1. Build and Test**
- Checkout the repository.
- Set up Python 3.9.
- Install dependencies (`Flask` and `pytest`).
- Run unit tests using `pytest`.

#### **2. Build and Publish Docker Image**
- Set up Docker Buildx.
- Authenticate with DockerHub using GitHub Secrets.
- Build and push the Docker image to DockerHub with the tag `latest`.

### **Trigger Events**
- `push` to the `main` branch.
- `pull_request` targeting the `main` branch.

---

## **Secrets Configuration**
To enable DockerHub login, add the following secrets to your GitHub repository:
1. `DOCKER_USERNAME`: Your DockerHub username.
2. `DOCKER_PASSWORD`: Your DockerHub password.

---

## **Usage**
1. Clone the repository and make changes.
2. Push changes to the `main` branch.
3. The CI/CD pipeline will automatically:
   - Run tests to verify your changes.
   - Build and publish the Docker image to DockerHub.
4. Deploy the app using the updated Docker image.

---

## **Example**
### **Run the App Locally**
```bash
python app.py
```
### **Run the App via Docker**
```bash
docker run -p 5000:5000 flasktest-app
```

---

## **Contributing**
Contributions are welcome! Please fork the repository and create a pull request with your changes.

---

## **License**
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## **Contact**
For questions or support, reach out to:
- GitHub: [Suraj P10](https://github.com/Suraj-p10)
- DockerHub: [Suraj P10](https://hub.docker.com/u/surajp10)

