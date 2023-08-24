# Note

try to set Ip for container

# Start Docker

`docker-compose up -d`

# List container

`docker container ls`

copy container-id of `postgres` IMAGE `74eae857a27e`

# inspect

`docker inspect 963ba6fb2bc0`

check `"IPAddress": "172.19.0.4",`

`docker network inspect --format='{{range .IPAM.Config}}{{.Subnet}}{{end}}'  963ba6fb2bc0`

`docker network inspect -f '{{json .Containers}}' 963ba6fb2bc0 | jq '.[] | .Name + ":" + .IPv4Address'`

`docker inspect --format='{{.NetworkSettings.Networks.pgadmin_frontend.IPAddress.IPv4Address}}'  postgres`

`docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' postgres`

docker inspect -f '{{.Id}}' postgres
docker inspect -f '{{.Created}}' postgres
docker inspect -f '{{.Args}}' postgres
docker inspect --format='{{json .Config}}' postgres
docker inspect --format='range .NetworkSettings.Networks.pgadmin_frontend.IPAMConfig.IPv4Address' postgres
docker inspect --format='range .State.Status' postgres

# Network

`docker network ls`
