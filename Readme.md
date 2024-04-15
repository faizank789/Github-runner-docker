
build docker image
- for reference ||  https://dev.to/pwd9000/create-a-docker-based-self-hosted-github-runner-linux-container-48dh
 - https://github.com/actions/runner/releases
- docker build --build-arg RUNNER_VERSION=2.315.0 --tag docker-github-runner-lin .

- docker-compose up --scale runner=3 -d

for scalling run

- docker-compose up --scale runner=1 -d

To remove

- docker-compose stop
- docker rm $(docker ps -aq)



