Lets create a python app

- Dockerfile
- app.py
- requirements.txt

run: `docker build -t <app_name> <path>`
     `docker build -t friendlyhello .`

this should create an image with tag `friendlyhello`

check the image list
`docker image ls`

we can run the app by:
`docker run -p <port>:<mapping_port> <app_name>`
`docker run -p 4000:80 friendlyhello`

this should start the *friendlyhello* image, you can verify this
in *localhost:4000* you should be able to see the localhost


we can also run it in the background by using the detach option
`docker run -d -p 4000:80 friendlyhello`

browse: *localhost:4000*
you can see that it's alive and running

we can also confirm in by using `docker container ls`

a running image will create a *container*



we can also stop it by `docker stop <container_id>`

we can also share our image by saving it in the docker hub
(you need to have an account on hub.docker.com)
then hit `docker login`  and it will ask for your credential


lets tag an existing image to create new repo on docker
`docker tag <image> <username>/<repo_name>:<tag>`
`docker tag friendlyhello cdijairo/get-started:part2`

this will create a new image *cdijairo/get-started*
with tag *part2*


we can publish the image to the docker hub
`docker push cdijairo/get-started:part2`


you can verify if the repo is publish in you docker hub account


we can also pull and run it via
`docker run -p 4000:80 username/repository:tag`