# Node.js Kubernetes Application

This project is a Node.js application that is designed to run in a Kubernetes environment using Docker for containerization.

## Project Structure

```
nodejs-k8s-app
├── src
│   └── index.js          # Entry point of the Node.js application
├── Dockerfile             # Dockerfile for building the application image
├── .dockerignore          # Files and directories to ignore when building the Docker image
├── k8s
│   ├── deployment.yaml    # Kubernetes deployment configuration
│   └── service.yaml       # Kubernetes service configuration
├── package.json           # npm configuration file
└── package-lock.json      # npm lock file for consistent installs
```

## Getting Started

### Prerequisites

- Node.js (version 14 or higher)
- Docker
- Kubernetes (Minikube or any other cluster)

### Installation

1. Clone the repository:
   ```
   git clone <repository-url>
   cd nodejs-k8s-app
   ```

2. Install dependencies:
   ```
   npm install
   ```

### Running the Application Locally

To run the application locally, use the following command:
```
node src/index.js
```
The application will be available at `http://localhost:3000`.

### Docker

To build the Docker image, run:
```
docker build -t nodejs-k8s-app .
```

To run the Docker container, use:
```
docker run -p 3000:3000 nodejs-k8s-app
```

### Kubernetes Deployment

1. Apply the deployment configuration:
   ```
   kubectl apply -f k8s/deployment.yaml
   ```

2. Apply the service configuration:
   ```
   kubectl apply -f k8s/service.yaml
   ```

3. Access the application:
   Use `kubectl port-forward` to access the application:
   ```
   kubectl port-forward service/<service-name> 3000:3000
   ```

### License

This project is licensed under the MIT License.