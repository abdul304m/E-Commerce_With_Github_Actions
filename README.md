# E-Commerce_With_Github_Actions

## Task 1: Project Setup
Step 1: Create GitHub Repository
1. Go to Github 
2. click New repository
3. Name it "ecommerce-platform" 
4. Choose Public (for easier testing) or Private.
5. Add a README (optional).

6. Click Create Repository.

![Create-g](./New-Pic-34/1.create-G.png)

![ecommerce](./New-Pic-34/2.ECOMMERCE.png)

## Clone repository locally:
"https://github.com/abdul304m/ecommerce-platform.git"

- cd ecommerce-platform
![cloning](./New-Pic-34/3.%20Cloning.png)

## Create project directories:
mkdir api webapp

![create-folder](./New-Pic-34/4.create-folder.png)

## Commit initial structure:
git add .
git commit -m "Initial project structure"
git push origin main

## Task 2: Initialize GitHub Actions
- Create directory: mkdir -p .github/workflows

- GitHub Actions workflows will go here (ci-backend.yml, ci-frontend.yml).

## Task 3: Backend API Setup
- Initialize Node.js project:
cd api
npm init -y
npm install express

![npm-instal](./New-Pic-34/5.npm-install.png)

npm install --save-dev jest supertest
![supertest](./New-Pic-34/10.supertest.png).

- Create a simple server (api/index.js):
![index-json](./New-Pic-34/6.index-js.png)

- Add a simple unit test (api/test/api.test.js):
![create-test-folder-fil](./New-Pic-34/12.create-test-folder-file.png)

![Api-test](./New-Pic-34/11.Api-test.png)

- Add test script in package.json:
![Add-Jest](./New-Pic-34/13.Add-Jest.png).

## Task 4: Frontend Setup
1. Initialize React app:
    cd ../webapp
    npx create-react-app .
![react-app](./New-Pic-34/14.react-app.png).

2. Implement basic features:
- Product listing: fetch from /api/products
- User login
- Order placement

3. Ensure frontend runs locally: "run npm start"

![Npm-run-locally](./New-Pic-34/16.Npm-run-locally.png)

![Reat-App](./New-Pic-34/15.Reat-App.png)

## Task 5: Continuous Integration (CI)
1. Backend workflow (.github/workflows/ci-backend.yml):
![backend-file](./New-Pic-34/17.backend-file.png)

2. Frontend workflow (.github/workflows/ci-frontend.yml):
![fronted-file](./New-Pic-34/18.fronted-file.png)


## Task 6: Docker Integration
1. Backend Dockerfile (api/Dockerfile):
![docker-file](./New-Pic-34/19.docker-fle.png)

2. Frontend Dockerfile (webapp/Dockerfile):
![fronted-dockerfile](./New-Pic-34/fronted-dockerfile.png)

3. Update workflows to build Docker images:
- Backend Workflow (.github/workflows/ci-backend.yml)

Go to your repo root:cd ~/ecommerce-platform
nano .github/workflows/ci-backend.yml
![update-backend-workflow](./New-Pic-34/20.update-backend.png)

- Frontend Workflow (.github/workflows/ci-frontend.yml)
nano .github/workflows/ci-frontend.yml
![update-frontend-workflow](./New-Pic-34/21.update-frontend-workflow.png).

## Task 7 & 8: Cloud Deployment
- The original requirement was to deploy the application to a cloud provider (AWS, Azure, GCP, or Render).
In this project, I used Docker Hub as the deployment target, which allows me to publish backend and frontend images to a public/private container registry.

Steps Implemented:
- Created a Personal Access Token in Docker Hub for secure authentication.

- Stored credentials in GitHub Secrets:

DOCKERHUB_USERNAME → my Docker Hub username

DOCKERHUB_TOKEN → personal access token

- Updated GitHub Actions workflows to:

Log in to Docker Hub using secrets

Build Docker images for backend and frontend

- Push the images to Docker Hub automatically on each push to main

## Task 9: Performance & Security
- Use GitHub caching for Node modules:

![Add-node-backend](./New-Pic-34/22.Add-node.png)

![Add-node-fronted](./New-Pic-34/23.Add-nde-fronted.png)

With this plan, you now have a full roadmap and workflow to implement your e-commerce CI/CD project from scratch.