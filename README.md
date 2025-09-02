# travis_lab
Teaching Travis CI

# Run locally to ensure it works:

# Install dependencies
npm install

# Start the app
npm start

# Push to GitHub
git init
git add .
git commit -m "Initial commit - Travis CI Docker demo"
git branch -M main
git remote add origin https://github.com/<your-username>/travis-docker-demo.git
git push -u origin main

# Connect to Travis CI

Go to https://travis-ci.com
 (for private repos) or https://travis-ci.org
 (for public).
Sign in with GitHub.
Enable the repository travis-docker-demo.

# Add Environment Variables in Travis CI

In Travis CI dashboard:
Go to your project → Settings.
Add:
DOCKER_USERNAME → Your Docker Hub username.
DOCKER_PASSWORD → Your Docker Hub password or access token.


# Create a Docker Hub Repository

Go to https://hub.docker.com/
Click Create Repository.
Name it travis-docker-demo.

# Trigger the Build

Push a commit to the main branch:
git commit --allow-empty -m "Trigger Travis build"
git push


Travis will:
Build the Docker image.
Push it to Docker Hub.

# Verify on Docker Hub

Go to your Docker Hub repo.
You should see:
latest tag
Commit SHA tag

# Test the Image

On any machine with Docker:
docker pull <your-docker-username>/travis-docker-demo:latest
docker run -p 3000:3000 <your-docker-username>/travis-docker-demo:latest

Visit http://localhost:3000