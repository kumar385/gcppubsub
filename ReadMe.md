1. Create Jar
```
./gradlew build bootJar
```
2. Copy the Jar to docker folder from build/libs folder. We still need to avoid this step for building docker
3. CD docker folder, Build docker image
`
docker build -t TAG .
`
4. Start the docker container
`
docker run -p 8085:8085 -i IMAGE_ID
`


push docker to docker hub.
----
`docker push kumar385/experiment:1.0`


Push to gcr
----
1. Install required gcloud components
`
gcloud components install docker-credential-gcr
`
2. 
`
docker-credential-gcr configure-docker
`
3. Update tag for gcr
`
docker tag IMAGE_ID gcr.io/PROJECT_ID/NAME:TAG
`
3. 
`
docker push gcr.io/PROJECT_ID/NAME:TAG
`
-----
Delete all images
`docker system prune -a`
To see docker images
`docker images -a`
To delete dangling images
`docker images purge`