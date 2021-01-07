# dev_basic_stack

## Add Domain

sudo nano /etc/hosts

### insert domains

127.0.0.1 portainer.local
127.0.0.1 jenkins.local
127.0.0.1 nexus.local
127.0.0.1 sonar.local
127.0.0.1 registry.local
127.0.0.1 registry-ui.local
127.0.0.1 adminer.local
127.0.0.1 gitlab.local

## set max_map_count

sudo sysctl -w vm.max_map_count=262144

## run stack

docker swarm init
docker swarm join-token manager
docker stack deploy --compose-file portainer-agent-stack.yml devops
ou
docker stack deploy --compose-file devops-stack.yml devops

## remove stack

docker stack rm ${STACK_NAME}
docker swarm leave --force

## remove network stack

docker network rm ${NETWORK_NAME}
