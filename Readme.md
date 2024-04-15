
 - Reference for github runner || https://github.com/actions/runner/releases
- docker build --build-arg RUNNER_VERSION=2.315.0 --tag docker-github-runner .

- docker-compose up --scale runner=3 -d

for scalling run

- docker-compose up --scale runner=1 -d

To remove

- docker-compose stop
- docker rm $(docker ps -aq)



