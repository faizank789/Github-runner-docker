![github](https://github.com/faizank789/Github-runner-docker/assets/22654388/1f8ef838-0c9a-44e9-b20a-7d467df88dcd)

1. Create .env file and mention below variables:
```
GH_OWNER='faizank789'
GH_REPOSITORY='github_runner_docker'
GH_TOKEN='ghp_kY9EpTuo9ddfdlHHYx8RBN6fD0YEIcL'
```

2. Reference link for versions || https://github.com/actions/runner/releases
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

----------------------------------------------------------------------------------------------------------------------
Example for reference:

Container Logs:
![logs](https://github.com/faizank789/Github-runner-docker/assets/22654388/346d359d-f7f7-455a-8a22-30ced9894453)


Console:
![dashboard](https://github.com/faizank789/Github-runner-docker/assets/22654388/71744b0c-a2b6-46b0-9eab-6df5d18bf09e)


Scaling: 
![terminal](https://github.com/faizank789/Github-runner-docker/assets/22654388/f6f402ce-dd32-4800-9256-3dfeacac96a3)

