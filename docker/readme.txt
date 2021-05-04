docker logs -f [container_id]

docker exec -it [container_id] bash



docker tag node-app:0.2 gcr.io/[project-id]/node-app:0.2



docker images

docker push gcr.io/[project-id]/node-app:0.2

docker rmi node-app:0.2 gcr.io/[project-id]/node-app node-app:0.1
docker rmi node:6
docker rmi $(docker images -aq) # remove remaining images
docker images

docker pull gcr.io/[project-id]/node-app:0.2
docker run -p 4000:80 -d gcr.io/[project-id]/node-app:0.2
curl http://localhost:4000


