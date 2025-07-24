image_name = node
image_tag = 1.1.3
docker_user = sandeeptiwari0206
docker_password = St@02061994



#Instll Dependencies


install:
	npm install -i

#Test the code
#test:
#	npm test


#Linting

#lint:
#	npm lint

#Build Image
build:
	@echo "Creating Docker Image"
	docker build -t $(image_name):$(image_tag) .  
	@echo "Create a tag of image"
	docker tag $(image_name):$(image_tag) $(docker_user)/$(image_name):$(image_tag)

#Docker Login


login:
	@echo "Docker login"
	docker login -u $(docker_user) -p $(docker_password)
#Push Image

push:
	@echo "Push Docker Image to Artifactory"
	docker push $(docker_user)/$(image_name):$(image_tag)

#Run

run:
	docker run -d -p 3000:3000 --name NodeProject $(docker_user)/$(image_name):$(image_tag)

#All

all:	install build login push  run
