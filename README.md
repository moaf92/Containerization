# containerization
In this project we are going to containerized our application stack we will use rabbit MQ and memcashed images, and customize tomcat, mysql and nginx images . build and run these images from compose.yaml after that we will host these images on docker hub

# Steps to execute
- First we have to set up an Ubuntu "linux dist." vm and install docker on it and add your ubuntu user to docker group
- We will create three repos for our customized images on docker hub to host modified images
- In the tomcat image we will build our artifact using maven, delete the default app file and replace it with build artifact we are going to use multistage docker file.. onefor building the artifact the 
  other one for copying just the artifact to keep our image size small as possible
- In mysql image we have to set a dbpass and set the name of db this is a mandatory variable using 'ENV' all these are from documentation, after this copying sql file to our container
- In nginx image we will delete default configuration file and replace it with our one
- After this docker compose we will mention all our images we will build
- After building and testing these images by running containers, now time to push it to our dockerhub repo  "docker push <imagename>"
