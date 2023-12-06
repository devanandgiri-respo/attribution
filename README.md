# Deploy Attribution-service in Docker Hub

## 1. Create a Docker Hub Account:

- If you don't have a Docker Hub account, go to [Docker Hub](https://hub.docker.com/) and sign up for a new account.
  
## 2. Login to Docker Hub:

```bash
docker login -u <username>   # Press Enter
Password: <password>
Login Succeeded  # This message will appear for successful login
```

## 3. Clone the attribution-service Repository from GitHub

```
git clone git@github.com:respo-financial/attribution-service.git
```
### checkout to root directory
```bash
git checkout develop_for_prod
```
### Add Environment Variables:
- Create a .env file in the root location and include environment keys used in the respective server.

## 4. Build and Push Docker Image:
Before build check the version on [Docker hub](https://hub.docker.com/) account
, currently, it's v1.0.1, next will be v1.0.2.

- Build docker image using command below:
```bash
docker build . --platform linux/amd64 -t respofin/attribution-service-prod:v1.0.2  # This creates an image with the specified name and version
```
- If you want to Test the image locally
```bash
docker run respofin/attribution-service-prod:v1.0.2
```
- Push the image to Docker Hub
```bash
docker push respofin/attribution-service-prod:v1.0.2 
```
* Note: The above command is only if you have already logged into docker hub using `docker login` command. Otherwise, you need to log in

## 5. Verify on Docker Hub:
- Go to [Docker hub](https://hub.docker.com/).
- Log in using your username and password.
- Check if the file is uploaded.

## 6. Share with DevOps Team:
- If the image is uploaded, share the image tag `(respofin/attribution-service-prod:v1.0.2)` with the DevOps team for deploying this image on the server.
