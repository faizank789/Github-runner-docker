1. Create .env file and mention below variables:
```
GH_OWNER='faizank789'
GH_REPOSITORY='github_runner_docker'
GH_TOKEN='ghp_kY9EpTuo9ddfdlHHYx8RBN6fD0YEIcL'
```

3. Reference for github runner || https://github.com/actions/runner/releases
  - docker build --build-arg RUNNER_VERSION=2.315.0 --tag docker-github-runner .
  
3. Update "image" and  "RUNNER_VERSION" in docker-compose.yaml
   - example:
```     
version: '3.8'
services:
  runner:
    image: docker-github-runner:latest
    build:
      context: .
      args:
        RUNNER_VERSION: '2.292.0'
    environment:
      GH_TOKEN: ${GH_TOKEN}
      GH_OWNER: ${GH_OWNER}
      GH_REPOSITORY: ${GH_REPOSITORY}
```


4. for scalling run
- docker-compose up --scale runner=3 -d
- docker-compose up --scale runner=1 -d

5. To remove
   
- docker-compose stop
- docker rm $(docker ps -aq)



