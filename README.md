# docker-microservices

To start the application run docker-compose up -d command in a terminal.

Execute docker ps to confirm that all 3 containers are running.

Once all services (containers) are running, execute bash script to confirm that all checks passed:
bash <(curl -s https://raw.githubusercontent.com/kkenan/basic-microservices/master/health_check.sh)

You can run docker logs <CONTAINER ID> to check logs.

Run docker-compose down to stop the containers.
