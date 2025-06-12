Follow the instructions [here](https://github.com/databiosphere/terra-docker?tab=readme-ov-file#terra-base-images)

## For pushing to DockerHub
### 1. In the terminal login to Docker
### 2. Build the Dockerfile
- docker build --no-cache -t {create an img name} .
### 3. Add a tag
- docker tag {your img name} {username}/{reponame}:{tag}
### 4. Push to dockerHub
- docker push {username}/{reponame}:{tag}

### 5. Test it out
- Terra needs it to be public
- Use in terra
  - {username}/{reponame}:{tag}
