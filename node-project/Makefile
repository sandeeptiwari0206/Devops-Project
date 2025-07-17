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
	docker build -t node:1.1.2 .  
	@echo "Create a tag of image"
	docker tag node:1.1.2 sandeeptiwari0206/node:1.1.2

#Docker Login


login:
	@echo "Docker login"
	docker login -u sandeeptiwari0206 -p St@02061994
#Push Image

push:
	@echo "Push Docker Image to Artifactory"
	docker push sandeeptiwari0206/node:1.1.2

#Run

run:
	docker run -d -p 3000:3000 --name NodeProject sandeeptiwari0206/node:1.1.2

#All

all:	install build login push  run
